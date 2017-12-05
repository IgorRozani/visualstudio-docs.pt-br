---
title: Como personalizar menus e barras de ferramentas no Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.renametoolbar
- vs.customize.toolbars
- vs.buttoneditor
- vs.customize.commands
- vs.newtoolbar
helpviewer_keywords:
- captions, customizing toolbar
- custom toolbars [Visual Studio]
- command buttons, customizing toolbar
- labels, customizing toolbar
- images [Visual Studio], toolbar buttons
- buttons [Visual Studio], custom toolbars
- toolbars [Visual Studio], creating in the IDE
- icons [Visual Studio], customizing toolbar
- commands [Visual Studio], customizing environment
- customizing toolbars
- toolbars [Visual Studio], customizing
- toolbars [Visual Studio], customizing in the IDE
ms.assetid: b570ae2f-5302-45dc-9cc9-8d4d1ad50603
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 124448e5c989597361f678b290fe345968f0cf08
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-customize-menus-and-toolbars-in-visual-studio"></a>Como personalizar menus e barras de ferramentas no Visual Studio
Para personalizar o Visual Studio, além de adicionar e remover barras de ferramentas e menus na barra de menus, você também pode adicionar e remover comandos em qualquer barra de ferramentas ou menu.  
  
> [!WARNING]
>  Depois de personalizar uma barra de ferramentas ou um menu, verifique se a respectiva caixa de seleção permanece marcada na caixa de diálogo **Personalizar**. Caso contrário, as alterações não persistirão depois que você fechar e reabrir o Visual Studio.
  
## <a name="adding-removing-or-moving-a-menu-on-the-menu-bar"></a>Adicionando, removendo ou movendo um menu na barra de menus  
  
1.  Na barra de menus, escolha **Ferramentas**, **Personalizar**.  
  
     A caixa de diálogo **Personalizar** é aberta.  
  
2.  Na guia **Comandos**, deixe o botão de opção **Barra de menus** selecionado, deixe **Barra de Menus** selecionado na lista ao lado dessa opção e realize um dos seguintes conjuntos de etapas:  
  
    -   Para adicionar um menu, escolha o botão **Adicionar Novo Menu**, escolha o botão **Modificar Seleção** e nomeie o menu que você deseja adicionar.  
  
        ![Personalizar a caixa de diálogo mostrando como adicionar um menu](../ide/media/addmenu.png "AddMenu")  
  
    -   Para remover um menu, selecione-o na lista **Controles** e escolha o botão **Excluir**.  
  
    -   Para mover um menu na barra de menus, escolha o menu na lista **Controles** e escolha o botão **Mover para Cima** ou **Mover para Baixo**.  
  
## <a name="adding-removing-or-moving-a-toolbar"></a>Adicionando, removendo ou movendo uma barra de ferramentas  
  
1.  Na barra de menus, escolha **Ferramentas**, **Personalizar**.  
  
     A caixa de diálogo **Personalizar** é aberta.  
  
2.  Na guia **Barra de Ferramentas**, realize um dos seguintes conjuntos de etapas:  
  
    -   Para adicionar uma barra de ferramentas, escolha o botão **Novo**, especifique um nome para a barra de ferramentas que você deseja adicionar e escolha o botão **OK**.  
  
        ![Personalizar a caixa de diálogo mostrando como adicionar uma barra de ferramentas](../ide/media/addtoolbar.png "AddToolbar")  
  
    -   Para remover uma barra de ferramentas personalizada, selecione-a na lista **Barras de Ferramentas** e escolha o botão **Excluir**.  
  
        > [!IMPORTANT]
        >  Você pode excluir as barras de ferramentas que cria, mas não as barras de ferramentas padrão.  
  
    -   Para mover uma barra de ferramentas para outro local de encaixe, selecione-a na lista **Barras de Ferramentas**, escolha o botão **Modificar Seleção** e escolha um local na lista exibida.  
  
        Você também pode arrastar uma barra de ferramentas pela sua borda esquerda para movê-la para qualquer lugar na área de encaixe principal.  
  
        > [!NOTE]
        >  Para obter mais informações sobre como melhorar a usabilidade e a acessibilidade das barras de ferramentas, consulte [Como definir opções de acessibilidade do IDE](../ide/reference/how-to-set-ide-accessibility-options.md).  
  
## <a name="customizing_menu">Personalizando um menu ou uma barra de ferramentas</a>
  
1.  Na barra de menus, escolha **Ferramentas**, **Personalizar**.  
  
    A caixa de diálogo **Personalizar** é aberta.  
  
2.  Na guia **Comandos**, escolha o botão de opção do tipo de elemento que você deseja personalizar.  
  
3.  Na lista desse tipo de elemento, escolha o menu ou a barra de ferramentas que deseja personalizar e executa um dos seguintes conjuntos de etapas:  
  
    -   Para adicionar um comando, escolha o botão **Adicionar Comando**.  
  
        Na caixa de diálogo **Adicionar Comando**, escolha um item na lista **Categorias**, escolha um item na lista **Comandos** e escolha o botão **OK**.  
  
        ![Adicionar caixa de diálogo Comando no Visual Studio](../ide/media/addcommand.png "AddCommand")  
  
    -   Para excluir um comando, escolha-o na lista **Controles** e escolha o botão **Excluir**.  
  
    -   Para reorganizar comandos, escolha um comando na lista **Controles** e escolha o botão **Mover para Cima** ou **Mover para Baixo**.  
  
    -   Para agrupar comandos em uma linha horizontal, primeiro escolha um comando na lista **Controles**, escolha o botão **Modificar Seleção** e, em seguida, escolha **Começar um Grupo** no menu exibido.  
  
## <a name="resetting-a-menu-or-a-toolbar"></a>Redefinindo um menu ou uma barra de ferramentas  
  
1.  Na barra de menus, escolha **Ferramentas**, **Personalizar**.  
  
    A caixa de diálogo **Personalizar** é aberta.  
  
2.  Na guia **Comandos**, escolha o botão de opção do tipo de elemento que você deseja redefinir.  
  
3.  Na lista desse tipo de elemento, escolha o menu ou a barra de ferramentas que deseja redefinir.  
  
4.  Escolha o botão **Modificar Seleção** e escolha **Redefinir** no menu exibido.  
  
    Também é possível redefinir todos os menus e barras de ferramentas escolhendo o botão **Redefinir Tudo**.

## <a name="see-also"></a>Consulte também
[Personalizando o IDE](../ide/personalizing-the-visual-studio-ide.md)  
[Personalizando o editor](../ide/customizing-the-editor.md)