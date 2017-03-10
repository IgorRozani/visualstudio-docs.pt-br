---
title: "CS0554 de erro do compilador | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0554"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0554"
ms.assetid: 884db4b2-3a69-4434-9a25-526f596e03c8
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# CS0554 de erro do compilador
'rotina de conversão': usuário definido a conversão em\/de classe derivada  
  
 Conversões definidas pelo usuário para valores de uma classe derivada não são permitidas; não é necessário um operador.  
  
 Consulte o capítulo 6 na especificação de linguagem c\# para obter mais informações sobre conversões definidas pelo usuário.  
  
 O exemplo a seguir gera CS0554:  
  
```  
// CS0554.cs namespace x { public class ii { // delete the conversion routine to resolve CS0554 public static implicit operator ii(a aa) // CS0554 { return new ii(); } } public class a : ii { public static void Main() { } } }  
```