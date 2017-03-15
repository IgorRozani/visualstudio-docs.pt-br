---
title: "CS0503 de erro do compilador | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0503"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0503"
ms.assetid: 12a337c9-8c5d-473d-8ce6-057b2c7e7935
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# CS0503 de erro do compilador
O método abstrato 'method' não pode ser marcado como virtual  
  
 É redundante para marcar um método membro como [abstrato](/dotnet/csharp/language-reference/keywords/abstract) e [virtual](/dotnet/csharp/language-reference/keywords/virtual) porque **abstrato** implica **virtual**.  
  
 O exemplo a seguir gera CS0503:  
  
```  
// CS0503.cs namespace x { abstract public class clx { abstract virtual public void f();   // CS0503 } }  
```