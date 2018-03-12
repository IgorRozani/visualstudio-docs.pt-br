---
title: -Updateconfiguration (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /updateconfiguration Devenv switch
- Devenv, /updateconfiguration switch
- updateconfiguration Devenv switch
ms.assetid: 9a1084cc-8b68-4ccc-aaea-f95939164338
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0ec3bfc47829bce2fe5ad836c970cb28f8a1294e
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2018
---
# <a name="updateconfiguration-devenvexe"></a>/Updateconfiguration (devenv.exe)
Notifica o [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] para mesclar os pacotes [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] no sistema e verificar o cache MEF para as alterações.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
devenv /updateconfiguration  
```  
  
## <a name="remarks"></a>Comentários  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] executa este comando automaticamente quando você instala um pacote VSIX. Você deve executar `devenv.exe /updateconfiguration` após a aplicação de patch em seus arquivos de modo que [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] atualize o cache MEF. Isso permite que você avalie se a correção é adequada.  
  
## <a name="example"></a>Exemplo  
 A linha de comando a seguir faz com que [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] mescle os pacotes [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] no sistema e verifique o cache MEF para quaisquer eventuais alterações.  
  
```  
Devenv.exe /updateconfiguration  
```  
  
## <a name="see-also"></a>Consulte também  
 [Personalizar o IDE do Visual Studio](../../ide/personalizing-the-visual-studio-ide.md)   
 [Opções de linha de comando devenv](../../ide/reference/devenv-command-line-switches.md)