---
title: Criando modelos de Item e projeto personalizados | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 586da5dc-f678-402b-afd0-0332959fd7a6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b3081537b1704fd461a458798d646bf7eeb65f0a
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2017
---
# <a name="creating-custom-project-and-item-templates"></a>Criando modelos de Item e projeto personalizados
O SDK do Visual Studio inclui modelos de projeto para criar um modelo de projeto personalizado e um modelo de item personalizado. Esses modelos incluem algumas substituições de parâmetro comum e criar como arquivos zip. Elas não serão implantadas automaticamente, e eles não estão disponíveis na instância experimental. Você deve copiar o zip arquivos para o local  
  
 Os modelos de criação de modelo permitem incluir modelos em extensões maior. Isso permite que você implementar o controle de versão nos arquivos de origem e criar um grupo de projetos de modelo em um pacote do VSIX.  
  
 Para cenários de criação do modelo básico, você deve usar o **exportar modelo** assistente, o que gera um arquivo compactado. Para obter mais informações sobre a criação do modelo básico, consulte [criando modelos de projeto e Item](../ide/creating-project-and-item-templates.md).  
  
 A partir do Visual Studio de 2017, verificação de modelos de item e projeto personalizados será não executada. Em vez disso, a extensão deve fornecer arquivos de manifesto do modelo que descrevem o local de instalação desses modelos. Você pode usar o Visual Studio de 2017 para atualizar as extensões VSIX. Se você implantar sua extensão usando um MSI, você deve gerar os arquivos de manifesto do modelo manualmente. Para obter mais informações, consulte [atualização personalizar modelos de projeto e Item para Visual Studio de 2017](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md). O esquema de manifesto do modelo está documentado em [Visual Studio Template manifesto Schema Reference](../extensibility/visual-studio-template-manifest-schema-reference.md).  
  
## <a name="creating-a-project-template"></a>Criando um modelo de projeto  
  
1.  Crie um projeto de modelo de projeto. Você pode encontrar o modelo de projeto no **novo projeto** caixa de diálogo, no Visual Basic ou Visual c# **extensibilidade** pasta.  
  
     O modelo gera um arquivo de classe, um ícone, um arquivo. vstemplate, um arquivo de projeto editável chamado ProjectTemplate.vbproj ou ProjectTemplate.csproj e alguns arquivos que normalmente são gerados por outros tipos de projeto, esse arquivo resx, um AssemblyInfo arquivo e um arquivo Settings. Cada arquivo de código contém substituições de parâmetro comum quando apropriado.  
  
2.  Adicionar e remover itens de projeto conforme necessário para seu projeto. Não remova o arquivo de projeto editável, o arquivo AssemblyInfo ou o arquivo. vstemplate.  
  
3.  Atualize o arquivo. vstemplate para refletir quaisquer adições e exclusões. O [projeto](../extensibility/project-element-visual-studio-templates.md) elemento deve conter um [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) elemento para cada arquivo a ser incluído no modelo.  
  
4.  Modifique seus arquivos de código e outro conteúdo voltado para o usuário e adicione substituições de parâmetro apropriado.  
  
5.  Modifica o conteúdo gerado conforme necessário.  
  
6.  Compile o projeto.  
  
     Visual Studio cria um arquivo. zip que contém o modelo. Ela não está implantada e ele não está disponível na instância experimental.  
  
## <a name="creating-an-item-template"></a>Criando um modelo de Item  
  
1.  Crie um projeto de modelo de Item.  
  
     O modelo gera um arquivo de classe, um ícone, um arquivo. vstemplate e um arquivo AssemblyInfo. O arquivo de classe contém algumas substituições de parâmetro comum.  
  
2.  Adicionar e remover itens de projeto conforme necessário para seu projeto.  
  
3.  Atualize o arquivo. vstemplate para refletir quaisquer adições e exclusões. O [projeto](../extensibility/project-element-visual-studio-templates.md) elemento deve conter um [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) elemento para cada arquivo a ser incluído no modelo.  
  
4.  Modifique seus arquivos de código e outro conteúdo voltado para o usuário e adicione substituições de parâmetro apropriado.  
  
5.  Modifica o conteúdo gerado conforme necessário.  
  
6.  Compile o projeto.  
  
     Visual Studio cria um arquivo compactado que contém o modelo. Ela não está implantada e ele não está disponível na instância experimental.  
  
## <a name="deployment"></a>Implantação  
  
#### <a name="to-deploy-the-project-or-item-template"></a>Para implantar o modelo de projeto ou item  
  
1.  Crie um projeto do VSIX. Para obter mais informações, consulte [modelo de projeto do VSIX](../extensibility/vsix-project-template.md).  
  
2.  Defina o projeto do VSIX como o projeto de inicialização. No **Solution Explorer**, selecione o nó do projeto VSIX, com o botão direito e selecione **definir como projeto de inicialização**.  
  
3.  Defina o projeto de modelo de projeto como um ativo do projeto VSIX. Abra o arquivo .vsixmanifest. Vá para o **ativos** guia e clique em **novo**.  
  
    1.  Definir o **tipo** campo **Microsoft.VisualStudio.ProjectTemplate** ou **Microsoft.VisualStudio.ItemTemplate**.  
  
    2.  Para a fonte, selecione o **um projeto na solução atual** opção e, em seguida, selecione o projeto que contém o modelo.  
  
4.  Compile a solução e, em seguida, pressione F5. A instância experimental aparece.  
  
5.  Para um projeto de modelo de projeto, você deve ver o modelo de projeto listado no **novo projeto** caixa de diálogo (**arquivo > Novo > projeto**), no Visual c# ou Visual Basic nó. Para um projeto de modelo de item, você deve ver o modelo de item listado na caixa de diálogo Adicionar Novo Item (no **Solution Explorer**, selecione o nó do projeto e clique em **Adicionar / Novo Item**).  
  
## <a name="see-also"></a>Consulte também  
 [Referência de modelo do Visual Studio](../ide/visual-studio-template-reference.md)