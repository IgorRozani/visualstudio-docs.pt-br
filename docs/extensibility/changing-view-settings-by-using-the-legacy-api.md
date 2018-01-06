---
title: "Alterar configurações de exibição usando a API herdado | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - changing view settings
ms.assetid: 12c9b300-0894-4124-96a1-764326176d77
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dc68bf5f8a0e61b80200cd5454b78bcdda78cdfe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="changing-view-settings-by-using-the-legacy-api"></a>Alterar configurações de exibição usando a API herdado
As configurações para os principais recursos do editor, como quebra automática de linha, a margem de seleção e o espaço virtual, podem ser alteradas pelo usuário por meio do **opções** caixa de diálogo. No entanto, também é possível alterar essas configurações por meio de programação.  
  
## <a name="changing-settings-by-using-the-legacy-api"></a>Alterar as configurações usando a API herdado  
 O <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> interface expõe um conjunto de propriedades do editor de texto. A exibição de texto contém uma categoria de propriedades (GUID_EditPropCategory_View_MasterSettings) que representa o grupo de configurações alteradas por meio de programação para a exibição de texto. Depois que as configurações de exibição foram alteradas dessa maneira, eles não podem ser alterados a **opções** caixa de diálogo até que elas são redefinidas.  
  
 A seguir está o processo normal para alterar as configurações de exibição para uma instância do editor de núcleo.  
  
1.  Chamar `QueryInterface` sobre o (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>) para o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> interface.  
  
2.  Chamar o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> método, especificando um valor de GUID_EditPropCategory_View_MasterSettings para o `rguidCategory` parâmetro.  
  
     Isso retorna um ponteiro para o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> interface, que contém o conjunto de propriedades forçados para o modo de exibição. As configurações neste grupo são forçadas permanentemente. Se uma configuração não estiver nesse grupo, ela continuará com as opções especificadas no **opções** caixa de diálogo ou comandos do usuário.  
  
3.  Chamar o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> método, especificando o valor de configurações apropriadas no `idprop` parâmetro.  
  
     Por exemplo, para forçar a quebra automática de linha, chamar <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> e especifique um valor de VSEDITPROPID_ViewLangOpt_WordWrap, `vt` para o `idprop` parâmetro. Nessa chamada `vt` é uma VARIANTE do tipo VT_BOOL e `vt.boolVal` é VARIANT_TRUE.  
  
## <a name="resetting-changed-view-settings"></a>Redefinir as configurações de exibição alterada  
 Para redefinir a qualquer exibição alterada configuração para uma instância do editor de núcleo, chame o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> método e especifique o valor de configuração apropriada no `idprop` parâmetro.  
  
 Por exemplo, para permitir quebra automática de flutuar livremente, você deve removê-lo da categoria de propriedade chamando <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> e especificando um valor de VSEDITPROPID_ViewLangOpt_WordWrap para o `idprop` parâmetro.  
  
 Para remover alteradas todas as configurações para o editor de núcleo de uma vez, especifique um valor de VSEDITPROPID_ViewComposite_AllCodeWindowDefaults, vt para o `idprop` parâmetro. Nessa chamada, vt é uma VARIANTE do tipo VT_BOOL e vt.boolVal é VARIANT_TRUE.  
  
## <a name="see-also"></a>Consulte também  
 [Dentro do Editor de núcleo](../extensibility/inside-the-core-editor.md)   
 [Acessando theText exibição usando a API herdado](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)   
 [Caixa de diálogo Opções](../ide/reference/options-dialog-box-visual-studio.md)