---
title: Tarefa GetFrameworkSdkPath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkSdkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkSdkPath task [MSBuild]
- MSBuild, GetFrameworkSdkPath task
ms.assetid: 2ef82b98-02b6-40cf-a9b5-f0e882fb5064
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8a24d7e459e0320cd33ad5fe1b3c2fe60f6e0d91
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="getframeworksdkpath-task"></a>Tarefa GetFrameworkSdkPath
Recupera o caminho para o [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  
  
## <a name="task-parameters"></a>Parâmetros da tarefa  
 A tabela a seguir descreve os parâmetros da tarefa `GetFrameworkSdkPath`.  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`FrameworkSdkVersion20Path`|Parâmetro de saída opcional somente leitura `String`.<br /><br /> Retorna o caminho para o SDK do .NET versão 2.0, se presente. Caso contrário, retornará `String.Empty`.|  
|`FrameworkSdkVersion35Path`|Parâmetro de saída opcional somente leitura `String`.<br /><br /> Retorna o caminho para o SDK do .NET versão 3.5, se presente. Caso contrário, retornará `String.Empty`.|  
|`FrameworkSdkVersion40Path`|Parâmetro de saída opcional somente leitura `String`.<br /><br /> Retorna o caminho para o SDK do .NET versão 4.0, se presente. Caso contrário, retornará `String.Empty`.|  
|`Path`|Parâmetro de saída `String` opcional.<br /><br /> Contém o caminho para o SDK mais recente do .NET, se houver qualquer versão. Caso contrário, retornará `String.Empty`.|  
  
## <a name="remarks"></a>Comentários  
 Além dos parâmetros listados acima, essa tarefa herda parâmetros da classe <xref:Microsoft.Build.Tasks.TaskExtension>, que herda da classe <xref:Microsoft.Build.Utilities.Task>. Para obter uma lista desses parâmetros adicionais e suas descrições, consulte [Classe base TaskExtension](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa a tarefa `GetFrameworkSdkPath` para armazenar o caminho para o [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] na propriedade `SdkPath`.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkSdkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="SdkPath" />  
        </GetFrameworkSdkPath>  
        <Message Text="$(SdkPath)"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Tarefas](../msbuild/msbuild-tasks.md)   
 [Referência de tarefas](../msbuild/msbuild-task-reference.md)