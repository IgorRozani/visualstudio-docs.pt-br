---
title: "Cores de sintaxe em um serviço de linguagem herdado | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- syntax coloring
- language services, syntax coloring
ms.assetid: f65ff67e-8c20-497a-bebf-5e2a5b5b012f
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 88af397feba9b06eabd73ec23dcf1204ebe755e6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="syntax-coloring-in-a-legacy-language-service"></a>Cores de sintaxe em um serviço de linguagem herdado
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]usa um serviço de cores para identificar elementos da linguagem e exibi-los com as cores especificadas em um editor.  
  
## <a name="colorizer-model"></a>Modelo de colorizador  
 A idioma serviço implementa o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> interface, que é usado por editores. Essa implementação é um objeto separado do serviço de idioma, conforme mostrado na ilustração a seguir.  
  
 ![Gráfico do colorizador SVC](../../extensibility/internals/media/figlgsvccolorizer.gif "FigLgSvcColorizer")  
Modelo de colorizador simples  
  
> [!NOTE]
>  O serviço de cores de sintaxe é separada da geral [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] mecanismo para colorir o texto. Para obter mais informações sobre o geral [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] mecanismo suporte coloração, consulte [usando fontes e cores](../../extensibility/using-fonts-and-colors.md).  
  
 Além de colorizador, o serviço de linguagem pode fornecer itens pode ser coloridos personalizados que são usados pelo editor de anúncios que fornece itens personalizados de pode ser coloridos. Você pode fazer isso com a implementação de <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> interface no mesmo objeto que implementa o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> interface. Retorna o número de itens pode ser coloridos personalizados quando o editor chama o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> método e retorna um item pode ser colorido personalizado individual quando chama o editor de <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> método.  
  
 O <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> método retorna um objeto que implementa o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> interface. Se o serviço de linguagem dá suporte a valores de cor de 24 bits ou alto, ele deve implementar o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> interface no mesmo objeto, como o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> interface.  
  
## <a name="how-a-vspackage-uses-a-language-service-colorizer"></a>Como um VSPackage usa um colorizador de serviço de linguagem  
  
1.  O VSPackage deve obter o serviço de idioma apropriado, o que requer que o serviço de linguagem VSPackage para fazer o seguinte:  
  
    1.  Usar um objeto que implementa o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> interface para obter o texto a ser coloridos.  
  
         Texto geralmente é exibido usando um objeto que implementa o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> interface.  
  
    2.  Obter o serviço de linguagem ao consultar o provedor de serviços de VSPackage para o GUID do serviço de linguagem. Serviços de idioma são identificados no registro pela extensão de arquivo.  
  
    3.  Associar o serviço de linguagem com o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> chamando seu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> método.  
  
2.  O VSPackage pode obter e usar o objeto colorizador da seguinte maneira:  
  
    > [!NOTE]
    >  Não é necessário obter uma linguagem de objetos de colorizador do serviço explicitamente VSPackages que use o editor de núcleo. Assim que uma instância do editor de núcleo obtém um serviço de idioma apropriado, ele executa todas as tarefas de colorização mostradas aqui.  
  
    1.  Obter o objeto de colorizador do serviço de linguagem, que implementa o `T:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer`, e <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2> interfaces, chamando o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> método do serviço de linguagem <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> objeto.  
  
    2.  Chamar o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> método para obter as informações de colorizador para um determinado intervalo de texto.  
  
         <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>Retorna uma matriz de valores, um para cada caractere na extensão de texto que está sendo colorido. Os valores são índices em uma lista de item pode ser colorido é a lista de item pode ser colorido padrão mantidas pelo editor de núcleo ou uma lista de item personalizado que pode ser colorido mantido pelo serviço de idioma em si.  
  
    3.  Use as informações de colorização retornadas pelo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> método para exibir o texto selecionado.  
  
> [!NOTE]
>  Além de usar um colorizador de serviço de linguagem, um VSPackage também pode usar o uso geral [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] cores mecanismo de texto. Para obter mais informações sobre esse mecanismo, consulte [usando fontes e cores](../../extensibility/using-fonts-and-colors.md).  
  
## <a name="in-this-section"></a>Nesta seção  
 [Implementar a coloração de sintaxe](../../extensibility/internals/implementing-syntax-coloring.md)  
 Discute como um editor acessa um serviço de linguagem coloração de sintaxe e que o serviço de linguagem deve implementar para dar suporte a sintaxe de cores.  
  
 [Como usar itens de coloração internos](../../extensibility/internals/how-to-use-built-in-colorable-items.md)  
 Demonstra como usar itens pode ser coloridos internos do serviço de linguagem.  
  
 [Itens de coloração personalizados](../../extensibility/internals/custom-colorable-items.md)  
 Descreve como implementar itens personalizados de pode ser coloridos.  
  
## <a name="see-also"></a>Consulte também  
 [Usando fontes e cores](../../extensibility/using-fonts-and-colors.md)