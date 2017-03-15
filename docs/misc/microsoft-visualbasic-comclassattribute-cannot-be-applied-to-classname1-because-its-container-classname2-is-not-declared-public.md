---
title: "&#39;Microsoft.VisualBasic.ComClassAttribute&#39; n&#227;o pode ser aplicado a &#39;&lt; classname1 &gt;&#39; porque seu cont&#234;iner &#39;&lt; classname2 &gt;&#39; n&#227;o est&#225; declarado como &#39;Public&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32504"
  - "bc32504"
helpviewer_keywords: 
  - "BC32504"
ms.assetid: 4138b639-88d6-4b51-afcd-c92a1be36f1c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Microsoft.VisualBasic.ComClassAttribute&#39; n&#227;o pode ser aplicado a &#39;&lt; classname1 &gt;&#39; porque seu cont&#234;iner &#39;&lt; classname2 &gt;&#39; n&#227;o est&#225; declarado como &#39;Public&#39;
Uma classe usando um `COMClassAttribute` Bloco de atributo é declarado dentro de uma classe que não é `Public`. Se uma classe deve ser exposta como um objeto COM, sua hierarquia de confinamento inteiro deve ser declarada com `Public` acesso.  
  
 **ID do erro:** BC32504  
  
### Para corrigir este erro  
  
-   Declarar todas as classes continentes `Public`, ou remover o `COMClassAttribute` Bloco de atributo.  
  
## Consulte também  
 [NÃO está em compilação: Atributos usados no Visual Basic](http://msdn.microsoft.com/pt-br/22231318-8a40-49af-9245-e0aab723563b)   
 [NÃO está em compilação: Aplicação de atributos](http://msdn.microsoft.com/pt-br/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [Classe ComClassAttribute](http://msdn.microsoft.com/pt-br/5c2f0835-9210-47dc-bc59-5c1769953574)   
 [Público](/dotnet/visual-basic/language-reference/modifiers/public)