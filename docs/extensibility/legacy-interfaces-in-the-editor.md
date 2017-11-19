---
title: Interfaces herdadas no Editor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy
ms.assetid: 741d45f5-0ea3-4614-972a-8728fe054e07
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4b437dad35850a20696702b84d8ea98ead8a1e9e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="legacy-interfaces-in-the-editor"></a>Interfaces herdadas no Editor
Você pode acessar o editor do Visual Studio de interfaces herdadas. O SDK do Visual Studio inclui adaptadores conhecidos como *shims*, que permitem que essas interfaces interagir com o novo editor. No entanto, é recomendável que você atualize seu código herdado para usar o novo editor de API. Seu código terão um desempenho melhor e você pode usar as novas tecnologias, como o Windows Presentation Foundation (WPF) e o Managed Extensibility Framework (MEF).  
  
## <a name="related-topics"></a>Tópicos relacionados  
  
|Título|Descrição|  
|-----------|-----------------|  
|[Adaptando um código herdado para o Editor](../extensibility/adapting-legacy-code-to-the-editor.md)|Explica como adaptar o seu código para o novo editor.|  
|[Comportamento de novo ou alterado com adaptadores de Editor](../extensibility/new-or-changed-behavior-with-editor-adapters.md)|Explica como o comportamento dos adaptadores de editor é diferente das versões anteriores do editor.|  
|[Dentro do Editor de núcleo](../extensibility/inside-the-core-editor.md)|Descreve os diferentes componentes de versões anteriores do editor.|  
|[Criando o Editor de núcleo usando a API herdado](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)|Explica como usar a API herdada para instanciar o editor de núcleo.|  
|[Fábricas de editor](../extensibility/editor-factories.md)|Explica como usar as fábricas de editor com a API herdada.|  
|[Como: registrar tipos de arquivo do Editor](../extensibility/how-to-register-editor-file-types.md)|Explica como vincular a uma extensão de nome de arquivo para o seu editor.|  
|[Passo a passo: Criando um Editor de núcleo e registrando um tipo de arquivo do Editor](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)|Explica como criar um núcleo de editor e vinculá-lo uma extensão de nome de arquivo.|  
|[Como: fornecer contexto para editores](../extensibility/how-to-provide-context-for-editors.md)|Explica como fornecer contexto para o editor.|  
|[Serviços de idioma e o Editor de núcleo](../extensibility/language-services-and-the-core-editor.md)|Explica as interações entre um serviço de linguagem e um editor.|  
|[Acessando o Buffer de texto usando a API herdado](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)|Explica como acessar o buffer de texto usando a API herdada.|  
|[Acessando theText exibição usando a API herdado](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)|Explica como acessar a exibição de texto usando a API herdada.|  
|[Personalização do Windows de código usando a API herdado](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)|Explica como personalizar janelas de código usando a API herdada.|  
|[Acessando as camadas de texto usando a API herdado](../extensibility/accessing-text-layers-by-using-the-legacy-api.md)|Explica como acessar diferentes camadas de texto usando a API herdada.|  
|[Usar marcadores de texto com a API herdado](../extensibility/using-text-markers-with-the-legacy-api.md)|Explica como adicionar marcadores de texto usando a API herdada.|  
|[Personalizando Menus e controles do Editor usando a API herdado](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)|Explica como personalizar controles do editor usando a API herdada.|  
|[Gerenciamento de desfazer e refazer usando a API herdado](../extensibility/managing-undo-and-redo-by-using-the-legacy-api.md)|Explica como gerenciar desfazer e refazer usando a API herdada.|  
|[Como: implementar o localizar e substituir o mecanismo](../extensibility/how-to-implement-the-find-and-replace-mechanism.md)|Explica como gerenciar localizar e substituir, usando a API herdada.|  
|[Como: suprimir notificações de alteração de arquivo](../extensibility/how-to-suppress-file-change-notifications.md)|Explica como suprimir notificações de alteração de arquivo usando a API herdada.|  
|[Criar designers e editores personalizados](../extensibility/creating-custom-editors-and-designers.md)|Explica como criar designers e editores personalizados.|  
|[Desenvolver um serviço de linguagem herdado](../extensibility/internals/developing-a-legacy-language-service.md)|Fornece links para documentos sobre os recursos que fornecem recursos de personalização para a [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] editor de núcleo, adicionando suporte para um serviço de linguagem.|  
|[Usando fontes e cores](../extensibility/using-fonts-and-colors.md)|Explica como usar fontes e cores com interfaces herdadas.|