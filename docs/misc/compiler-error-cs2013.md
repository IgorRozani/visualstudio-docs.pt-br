---
title: "CS2013 de erro do compilador | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS2013"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2013"
ms.assetid: 8a57b4c8-02fc-4f73-b489-121ff468c17d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# CS2013 de erro do compilador
Número base de imagem inválido 'value'  
  
 Um valor inválido \(não um número\) foi passado para o [\/baseaddress](/dotnet/csharp/language-reference/compiler-options/baseaddress-compiler-option) opção de compilador.  
  
 O exemplo a seguir gera CS2013:  
  
```  
// CS2013.cs // compile with: /target:library /baseaddress:x // CS2013 expected class MyClass { }  
```