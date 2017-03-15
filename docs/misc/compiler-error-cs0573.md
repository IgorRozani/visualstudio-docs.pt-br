---
title: "CS0573 de erro do compilador | Microsoft Docs"
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
  - "CS0573"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0573"
ms.assetid: 10ef9625-44f1-4936-ada3-56938357aa01
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# CS0573 de erro do compilador
declaração de campo: não é possível ter inicializadores de campo de instância em structs  
  
 Você não pode inicializar um campo de instância de um [struct](/dotnet/csharp/language-reference/keywords/struct). Campos de tipos de valor serão inicializados com seus valores padrão e campos de tipo de referência serão inicializados com `null`.  
  
## Exemplo  
 O exemplo a seguir gera CS0573:  
  
```  
// CS0573.cs namespace x { public class clx { public static void Main() { } } public struct cly { clx a = new clx();   // CS0573 // clx a;            // OK int i = 7;           // CS0573 // int i;            // OK } }  
```