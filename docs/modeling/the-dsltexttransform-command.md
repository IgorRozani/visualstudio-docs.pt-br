---
title: O comando DslTextTransform | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, commands
ms.assetid: 7d025d0b-6543-4a49-9f6b-8b8cfcad77ee
caps.latest.revision: "30"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 4b8c7040cabf05b30920654996891bc8d19f42db
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="the-dsltexttransform-command"></a>O comando DslTextTransform
DslTextTransform.cmd é um script que chama TextTransform.exe e executa-o com opções comuns. Você pode usar DslTextTransformation.cmd para automatizar uma noturna compilação do seu [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] projetos. Para obter mais informações, consulte [gerando arquivos com o utilitário TextTransform](../modeling/generating-files-with-the-texttransform-utility.md).  
  
 DslTextTransform.cmd está localizado no seguinte diretório:  
  
 **\<Caminho de instalação do Visual Studio SDK > \VisualStudioIntegration\Tools\Bin**  
  
 Você pode especificar os argumentos a seguir como entrada para DslTextTransform.cmd:  
  
-   O diretório de saída do projeto de modelo de domínio.  
  
-   O diretório de saída do projeto definição designer.  
  
-   O local do arquivo de modelo de texto.  
  
 DslTextTransform.cmd processa o arquivo de modelo de texto especificado usando os processadores de diretiva padrão e assemblies. Se você criar processadores de diretivas personalizadas, você pode criar seu próprio arquivo de lote que chama TextTransform.exe. Nesse arquivo de lote, você pode especificar seus assemblies e os processadores de diretiva personalizados associados.