---
title: "CS0562 de erro do compilador | Microsoft Docs"
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
  - "CS0562"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0562"
ms.assetid: dceecce5-90ce-4554-820c-f4c06b2b8258
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# CS0562 de erro do compilador
O parâmetro de um operador unário deve ser do tipo recipiente  
  
 A declaração de método para uma sobrecarga de operador deve seguir determinadas diretrizes. Para obter mais informações, consulte [operadores sobrecarregáveis](/dotnet/csharp/programming-guide/statements-expressions-operators/overloadable-operators) e [Operator Overloading Sample](http://msdn.microsoft.com/pt-br/1c6b4610-0a49-4532-8fa7-f694cfc65743).  
  
## Exemplo  
 O exemplo a seguir gera CS0562:  
  
```  
// CS0562.cs public class iii { public static implicit operator int(iii x) { return 0; } public static implicit operator iii(int x) { return null; } public static iii operator +(int aa)   // CS0562 // try the following line instead // public static iii operator +(iii aa) { return (iii)0; } public static void Main() { } }  
```