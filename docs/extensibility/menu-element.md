---
title: Elemento menu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, Menus
- Menus element (VSCT XML schema)
ms.assetid: ce0560f3-b4c9-4ab2-a99c-d4e10f37b9e0
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4a0aa02b3375a7b5d66d26e11dcedbd7b67d958
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="menu-element"></a>Elemento de menu
Define um item de menu. Esses são os seis tipos de menus: contexto, Menu, MenuController, MenuControllerLatched, barra de ferramentas e ToolWindowToolbar.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
<Menu guid="guidMyCommandSet" id="MyCommand" priority="0x100" type="button">  
  <Parent>... </Parent>  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</Menu>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|GUID|Necessário. GUID do identificador de comando GUID ID.|  
|id|Necessário. ID do identificador de comando GUID ID.|  
|priority|Opcional. Um valor numérico que especifica a posição relativa de um menu em um grupo de menus.|  
|ToolbarPriorityInBand|Opcional. Um valor numérico que especifica a posição relativa de uma barra de ferramentas em uma faixa quando a janela está inacessível.|  
|tipo|Opcional. Um valor enumerado que especifica o tipo de elemento.<br /><br /> Se não estiver presente, o tipo padrão é de Menu.<br /><br /> Contexto<br /> Um menu de atalho que é exibido quando um usuário clica uma janela. Um menu de atalho tem as seguintes características:<br /><br /> -Não usa os campos pai e prioridade quando o menu é exibido como um menu de atalho.<br />-Pode ser usado como um submenu e também como um menu de atalho. Nesse caso, os campos ID do grupo e prioridade são respeitados.<br />-É sempre não está disponível.<br /><br /> Um menu de atalho é exibido apenas quando as seguintes condições forem verdadeiras:<br /><br /> -A janela que o hospeda é exibida.<br />-Um manipulador de mouse no VSPackage detecta um atalho na janela e, em seguida, chama um método que trata o comando.<br />-O menu de atalho é exibido ao chamar o <xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager.ShowContextMenu%2A> método (a abordagem recomendada) ou o <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A> método.<br /><br /> Menu<br /> Fornece um menu suspenso. Um menu suspenso tem as seguintes características:<br /><br /> -Respeita o pai em sua definição.<br />-Deve ter um grupo pai, ou um CommandPlacement a um grupo.<br />-Pode ser um submenu em qualquer outro tipo de menu.<br />-É exibida automaticamente sempre que o menu pai é exibido.<br />-Não requer a implementação de qualquer código VSPackage para torná-lo exibido.<br /><br /> MenuController<br /> Fornece um menu suspenso do botão de divisão, que normalmente é usado em barras de ferramentas. Um menu MenuController tem as seguintes características:<br /><br /> -Deve estar contido em outro menu por meio de CommandPlacement ou pai.<br />-Respeita o pai em sua definição.<br />-Pode ter qualquer tipo de menu como seu pai.<br />-É automaticamente disponibilizado sempre que o menu pai é exibido.<br />-Não requer suporte para tornar o menu exibido.<br /><br /> Um comando de menu do botão de divisão é exibido no botão de menu. O comando exibido tem uma das seguintes características:<br /><br /> -É o último comando foi usado se o comando ainda é exibido e habilitado.<br />-É o primeiro comando exibido.<br /><br /> MenuControllerLatched<br /> Fornece um menu suspenso de botão de divisão para o qual um comando pode ser especificado como a seleção padrão marcando o comando como travada.<br /><br /> Um comando travado é um comando que é marcado no menu como selecionado, normalmente exibindo uma marca de seleção. Um comando pode ser marcado como travada se ele tiver o OLECMDF_LATCHED o sinalizador será definido nela em uma implementação do `QueryStatus` método o <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interface. Um menu MenuControllerLatched tem as seguintes características:<br /><br /> -Deve estar contido em outro menu por meio de um grupo pai ou CommandPlacement.<br />-Respeita o pai em sua definição.<br />-Pode ter qualquer tipo de menu como seu pai.<br />-Ficam disponíveis sempre que o menu pai é exibido.<br />-Não requer suporte para tornar o menu exibido.<br /><br /> Um comando de menu do botão de divisão é exibido no botão de menu. O comando exibido tem uma das seguintes características:<br /><br /> -É o primeiro comando exibido é travado.<br />-É o primeiro comando exibido.<br /><br /> Barra de ferramentas<br /> Fornece uma barra de ferramentas. Uma barra de ferramentas tem as seguintes características:<br /><br /> -Ignora o pai em sua definição.<br />-Não é possível fazer um submenu de qualquer grupo, nem mesmo usando CommandPlacement.<br />-Sempre podem ser exibidos clicando **barras de ferramentas** no **exibição** menu.<br />-Pode ser exibido usando um [VisibilityItem](../extensibility/visibilityitem-element.md).<br />-Não requer nenhum código para criá-lo. Para obter um exemplo sobre como criar uma barra de ferramentas, consulte [adicionando uma barra de ferramentas](../extensibility/adding-a-toolbar.md).<br /><br /> ToolWindowToolbar<br /> Fornece uma barra de ferramentas que está anexada a uma janela de ferramenta específica, assim como uma barra de ferramentas é anexada ao ambiente de desenvolvimento.<br /><br /> -Ignora o pai em sua definição.<br />-Não é possível fazer um submenu de qualquer grupo, nem mesmo usando CommandPlacement.<br />-É exibida somente quando a janela de ferramenta que hospeda a barra de ferramentas é exibida e o VSPackage explicitamente adiciona a barra de ferramentas para a janela da ferramenta. Isso geralmente é feito quando a janela de ferramentas é criada por obter a propriedade de host de barra de ferramentas (conforme representado pelo <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolWindowToolbarHost> interface) do quadro de janela de ferramenta e, em seguida, chamar o <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolWindowToolbarHost.AddToolbar%2A> método.|  
|Condição|Opcional. Consulte [atributos condicionais](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|Pai|Opcional. O elemento pai do item de menu.|  
|CommandFlag|Necessário. Consulte [comando sinalizador elemento](../extensibility/command-flag-element.md). Os valores válidos de CommandFlag para um Menu são da seguinte maneira:<br /><br /> -   **AlwaysCreate**<br />-   **DefaultDocked**<br />-   **DefaultInvisible** -esse sinalizador não afeta a exibição das barras de ferramentas.<br />-   **DontCache**<br />-   **DynamicVisibility** -esse sinalizador não afeta a exibição das barras de ferramentas.<br />-   **IconAndText**<br />-   **NoCustomize**<br />-   **NotInTBList**<br />-   **NoToolbarClose**<br />-   **TextoAltera**<br />-   **TextIsAnchorCommand**|  
|Cadeias de caracteres|Necessário. Consulte [cadeias de caracteres de elemento](../extensibility/strings-element.md). O filho `ButtonText` elemento deve ser definido.|  
|Anotação|Comentário opcional.|  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[Elemento Menus](../extensibility/menus-element.md)|Define todos os menus que implementa um VSPackage.|  
  
## <a name="example"></a>Exemplo  
  
```  
<Menu guid="cmdGuidWidgetCommands" id="menuIDEditWidget"  
  priority="0x0002" type="Menu">  
  <Parent guid="cmdSetGuidWidgetCommands" id="groupIDFileEdit">  
    <CommandFlag>AlwaysCreate</CommandFlag>  
    <Strings>  
      <ButtonText>Edit Widget</ButtonText>  
    </Strings>  
    </Parent>  
</Menu>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Arquivos da tabela de comandos do Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)