---
title: "O ConnectionTimeout deve ser maior que 0 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrNetwork_BadConnectionTimeout"
ms.assetid: 15ac09a7-47f0-44f3-9e84-5bd10bd07450
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# O ConnectionTimeout deve ser maior que 0
Quando o upload e download de arquivos com o [Objeto My.Computer.Network](/dotnet/visual-basic/language-reference/objects/my-computer-network-object), você deve especificar um `connectionTimeout` maior que `0`.  
  
### Para corrigir este erro  
  
-   Forneça um `connectionTimeout` maior do que `0`.  
  
## Consulte também  
 [Método UploadFile](http://msdn.microsoft.com/pt-br/5505ea3e-3dbd-460b-9f8f-62c84c0a4de6)   
 [Método DownloadFile](http://msdn.microsoft.com/pt-br/aeb7ed8f-1ac9-4242-ae57-9f35914eb329)   
 [Como carregar um arquivo](../Topic/How%20to:%20Upload%20a%20File%20in%20Visual%20Basic.md)   
 [Como baixar um arquivo](../Topic/How%20to:%20Download%20a%20File%20in%20Visual%20Basic.md)   
 [Operações de rede no .NET Framework com Visual Basic](http://msdn.microsoft.com/pt-br/c5379021-44ef-4d6a-acf5-e951fdcab6b2)