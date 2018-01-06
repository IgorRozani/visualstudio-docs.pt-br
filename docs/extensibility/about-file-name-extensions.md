---
title: "Sobre extensões de nome de arquivo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- file extensions
- file name extensions
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8f504a70950ea9e808d50bd8b9bc7ef5dd92d699
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="about-file-name-extensions"></a>Sobre extensões de nome de arquivo
Ao registrar uma extensão de arquivo de um VSPackage, associá-lo com uma versão do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Isso é importante se mais de uma versão do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] é instalado em um computador.  
  
 Extensões de arquivo para VSPackages estão registradas com a chave HKEY_CLASSES_ROOT com um valor padrão que aponta para o associado identificador programático (ProgID).  
  
 Este é um exemplo das informações de registro para a extensão de arquivo. vcproj:  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)=" VisualStudio.vcproj.8.0"   
```  
  
 Arquivos associados [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] devem ter um ProgID com controle de versão, como `VisualStudio.vcproj.8.0`, para permitir instalações lado a lado do produto para manter as associações de extensão de arquivo entre as versões do produto. Um ProgID específico da versão também permite que você use verbos padrão, como abrir, editar e assim por diante, sem a preocupação de substituição ou que está sendo substituído por outros aplicativos ou as versões do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 Em alguns casos, o ProgID associado com uma extensão de arquivo não deve ser alterado. Por exemplo, o ProgID para a extensão de arquivo. htm (progid = htmlfile) é codificado em um número de lugares no sistema operacional e é amplamente conhecida e usada em associação com arquivos htm e.  
  
## <a name="see-also"></a>Consulte também  
 [Registrando extensões de nome de arquivo para implantações lado a lado](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [Especificar identificadores de arquivo para extensões de nome de arquivo](../extensibility/specifying-file-handlers-for-file-name-extensions.md)