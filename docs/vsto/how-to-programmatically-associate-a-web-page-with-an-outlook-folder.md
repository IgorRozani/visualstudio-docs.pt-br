---
title: 'How to: Programmatically Associate a Web Page with an Outlook Folder | Microsoft Docs'
ms.custom: 
ms.date: 02/02/2017
ms.prod: visual-studio-dev14
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- folders [Office development in Visual Studio], Web pages and
- Outlook [Office development in Visual Studio], Web pages attached to folders
- Web pages [Office development in Visual Studio], Outlook folders
ms.assetid: b211b1b2-11e4-4316-87b7-98a3d10f95d1
caps.latest.revision: 16
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: c3f4eeb5aa8de09da03c1d2d3a1b97967c70b4af
ms.contentlocale: pt-br
ms.lasthandoff: 08/30/2017

---
# <a name="how-to-programmatically-associate-a-web-page-with-an-outlook-folder"></a>How to: Programmatically Associate a Web Page with an Outlook Folder
  This example checks for a folder named `HtmlView` in Microsoft Office Outlook. If the folder does not exist, the code creates the folder and assigns a Web page to it. If the folder exists, the code displays the folder contents.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Example  
 [!code-csharp[Trin_OL_HTMLFolder#1](../vsto/codesnippet/CSharp/Trin_OL_HTMLFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>See Also  
 [Working with Folders](../vsto/working-with-folders.md)   
 [How to: Programmatically Retrieve a Folder by Name](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [How to: Programmatically Create Custom Folder Items](../vsto/how-to-programmatically-create-custom-folder-items.md)  
  
  