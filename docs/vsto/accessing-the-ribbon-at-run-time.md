---
title: Acesso a faixa de opções em tempo de execução
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Globals class, Ribbon
- Ribbon [Office development in Visual Studio], accessing
- RibbonManager class
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: abeffdbc61861aae3c0c9c53cb07d597abaa31c9
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34263207"
---
# <a name="access-the-ribbon-at-runtime"></a>Acesso a faixa de opções em tempo de execução
  Você pode escrever código para mostrar, ocultar e modificar a faixa de opções e permitir que os usuários executar o código de controles em um painel tarefa personalizada, o painel de ações ou a região de formulário do Outlook.  

 Você pode acessar a faixa de opções usando a `Globals` classe. Para projetos do Outlook, você pode acessar as faixas de opções que aparecem em uma janela do Inspetor do Outlook ou o Outlook Explorer específica.  

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  

## <a name="access-the-ribbon-by-using-the-globals-class"></a>Acesso a faixa de opções usando a classe Globals  
 Você pode usar o `Globals` classe para acessar a faixa de opções em um projeto no nível do documento ou um projeto de suplemento do VSTO em qualquer lugar no projeto.  

 Para obter mais informações sobre o `Globals` de classe, consulte [Global de acesso a objetos em projetos do Office](../vsto/global-access-to-objects-in-office-projects.md).  

 O exemplo a seguir usa o `Globals` classe para acessar uma faixa de opções personalizada denominada `Ribbon1` e defina o texto que aparece em uma caixa de combinação na faixa de opções para `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#4](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#4)]
 [!code-csharp[Trin_Outlook_FR_Access#4](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#4)]  

## <a name="access-a-collection-of-ribbons-that-appear-in-a-specific-outlook-inspector-window"></a>Acessar uma coleção de faixas de opções que aparecem em uma janela específica do Inspetor do Outlook  
 Você pode acessar uma coleção de faixas de opções que aparecem no Outlook *inspetores*. Um inspetor é uma janela que é aberta no Outlook, quando os usuários executam determinadas tarefas, como a criação de mensagens de email. Para acessar a faixa de opções de uma janela de Inspetor, chame o `Ribbons` propriedade do `Globals` classe e passar uma <xref:Microsoft.Office.Interop.Outlook.Inspector> objeto que representa o Inspetor.  

 O exemplo a seguir obtém a coleção de faixa de opções do Inspetor que tem o foco no momento. Neste exemplo, em seguida, acessa uma faixa de opções chamada `Ribbon1` e define o texto que aparece em uma caixa de combinação na faixa de opções para `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#5](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#5)]
 [!code-csharp[Trin_Outlook_FR_Access#5](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#5)]  

## <a name="access-a-collection-of-ribbons-that-appear-for-a-specific-outlook-explorer"></a>Acessar uma coleção de faixas de opções que aparecem para um navegador específico do Outlook  
 Você pode acessar uma coleção de faixas de opções que aparecem no Outlook *Explorer*. Um Explorer é a interface do usuário principal do aplicativo (IU) para uma instância do Outlook. Para acessar a faixa de opções de uma janela do Explorer, chame o `Ribbons` propriedade do `Globals` classe e passar uma <xref:Microsoft.Office.Interop.Outlook.Explorer> objeto que representa o Gerenciador.  

 O exemplo a seguir obtém a coleção de faixa de opções do Explorer que tem o foco no momento. Neste exemplo, em seguida, acessa uma faixa de opções chamada `Ribbon1` e define o texto que aparece em uma caixa de combinação na faixa de opções para `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#6](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#6)]
 [!code-csharp[Trin_Outlook_FR_Access#6](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#6)]  

## <a name="see-also"></a>Consulte também  
 [Visão geral da faixa de opções](../vsto/ribbon-overview.md)   
 [Designer de faixa de opções](../vsto/ribbon-designer.md)   
 [XML da faixa de opções](../vsto/ribbon-xml.md)   
 [Visão geral do modelo de objeto de faixa de opções](../vsto/ribbon-object-model-overview.md)   
 [Passo a passo: Criar uma guia personalizada usando o Designer de faixa de opções](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Passo a passo: Atualizar os controles em uma faixa de opções em tempo de execução](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Personalizar uma faixa de opções para Outlook](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Acesso a uma região de formulário em tempo de execução](../vsto/accessing-a-form-region-at-run-time.md)  
