---
title: "CS0127 de erro do compilador | Microsoft Docs"
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
  - "CS0127"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0127"
ms.assetid: b20333bf-badf-4f96-a3ee-bd35f4f7e807
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# CS0127 de erro do compilador
Como 'function' retorna void, uma palavra\-chave return não deve ser seguida por uma expressão de objeto  
  
 Um método com um [void](/dotnet/csharp/language-reference/keywords/void) tipo não pode retornar um valor de retorno. Para obter mais informações, consulte [Métodos](/dotnet/csharp/programming-guide/classes-and-structs/methods).  
  
 O exemplo a seguir gera CS0127:  
  
```  
// CS0127.cs namespace MyNamespace { public class MyClass { public int hiddenMember2 { get { return 0; } set   // CS0127, set has an implicit void return type { return 0;   // remove return statement to resolve this CS0127 } } public static void Main() { } } }  
```