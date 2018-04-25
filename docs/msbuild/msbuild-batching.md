---
title: Separação em lotes no MSBuild | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, batching
ms.assetid: d35c085b-27b8-49d7-b6f8-8f2f3a0eec38
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e7b769cc89095aca5b22aed46375f56c2ab4c987
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2018
---
# <a name="msbuild-batching"></a>Separação em lotes no MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] tem a capacidade de dividir as listas de itens em categorias diferentes ou lotes com base nos metadados do item, além de executar um destino ou uma tarefa uma vez com cada lote.  
  
## <a name="task-batching"></a>Lote de tarefas  
 O lote de tarefas permite que você simplifique os arquivos de projeto ao fornecer uma maneira de dividir as listas de itens em lotes diferentes e passar cada um desses lotes para uma tarefa separadamente. Isso significa que um arquivo de projeto só precisa ter a tarefa e seus atributos declarados uma vez, mesmo que seja executado várias vezes.  
  
 Especifique que você deseja que [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] execute o processamento em lote com uma tarefa usando a notação %(*ItemMetaDataName*) em um dos atributos da tarefa. O exemplo a seguir divide a lista de itens `Example` em lotes com base no valor do item de metadados `Color` e passa cada um dos lotes para a tarefa `MyTask` separadamente.  
  
> [!NOTE]
>  Se não houver referência à lista de itens em outro lugar nos atributos de tarefa ou se o nome dos metadados for ambíguo, você pode usar a notação %(*ItemCollection.ItemMetaDataName*) para qualificar totalmente o valor de metadados do item a ser usado para processamento em lotes.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 Para obter exemplos mais específicos de envio em lote, consulte [Metadados de item em lote de tarefas](../msbuild/item-metadata-in-task-batching.md).  
  
## <a name="target-batching"></a>Lote de destino  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] verifica se as entradas e saídas de um destino estão atualizadas antes de executar o destino. Se as entradas e saídas estiverem atualizadas, o destino será ignorado. Se uma tarefa dentro de um destino usar processamento em lote, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] precisa determinar se as entradas e saídas para cada lote de itens estão atualizadas. Caso contrário, o destino será executado sempre que for atingido.  
  
 O exemplo a seguir mostra um elemento `Target` que contém um atributo `Outputs` com a notação %(*ItemMetaDataName*). [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vai dividir a lista de itens `Example` em lotes com base nos metadados do item `Color` e analisar os carimbos de data/hora dos arquivos de saída para cada lote. Se as saídas de um lote não estiverem atualizadas, o destino é executado. Caso contrário, o destino será ignorado.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask"  
        Inputs="@(Example)"  
        Outputs="%(Color)\MyFile.txt">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 Para obter outro exemplo de lote de destino, consulte [Metadados do item no lote de destino](../msbuild/item-metadata-in-target-batching.md).  
  
## <a name="property-functions-using-metadata"></a>Funções de propriedade usando metadados  
 O envio em lote pode ser controlado por funções de propriedade que incluem metadados. Por exemplo,  
  
 `$([System.IO.Path]::Combine($(RootPath),%(Compile.Identity)))`  
  
 usa <xref:System.IO.Path.Combine%2A> para combinar um caminho de pasta raiz com um caminho do item de compilação.  
  
 Funções de propriedade podem não aparecer em valores de metadados.  Por exemplo,  
  
 `%(Compile.FullPath.Substring(0,3))`  
  
 não é permitido.  
  
 Para obter mais informações sobre funções de propriedade, consulte [Funções de propriedade](../msbuild/property-functions.md).  
  
## <a name="see-also"></a>Consulte também  
 [Elemento ItemMetadata (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)   
 [Conceitos do MSBuild](../msbuild/msbuild-concepts.md)   
 [Referência do MSBuild](../msbuild/msbuild-reference.md)   
 [Conceitos avançados](../msbuild/msbuild-advanced-concepts.md)