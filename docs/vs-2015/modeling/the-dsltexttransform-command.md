---
title: O comando DslTextTransform | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, commands
ms.assetid: 7d025d0b-6543-4a49-9f6b-8b8cfcad77ee
caps.latest.revision: 32
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 1dbbf44a4adfe20f1940da32540eaad81c97251b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269367"
---
# <a name="the-dsltexttransform-command"></a>O comando DslTextTransform
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

DslTextTransform.cmd é um script que chama TextTransform.exe e executa-o com opções comuns. Você pode usar DslTextTransformation.cmd para automatizar uma compilação noturna de seu [!INCLUDE[dsl](../includes/dsl-md.md)] projetos. Para obter mais informações, consulte [gerando arquivos com o utilitário TextTransform](../modeling/generating-files-with-the-texttransform-utility.md).  
  
 DslTextTransform.cmd está localizado no seguinte diretório:  
  
 **\<Caminho de instalação do SDK do Visual Studio > \VisualStudioIntegration\Tools\Bin**  
  
 Você pode especificar os argumentos a seguir como entrada para DslTextTransform.cmd:  
  
-   O diretório de saída do projeto de modelo de domínio.  
  
-   O diretório de saída do projeto de definição de designer.  
  
-   O local do arquivo de modelo de texto.  
  
 DslTextTransform.cmd processa o arquivo de modelo de texto especificado usando os processadores de diretriz padrão e assemblies. Se você criar processadores de diretriz personalizados, você pode criar seu próprio arquivo de lote que chama TextTransform.exe. Nesse arquivo em lotes, você pode especificar seus assemblies e os processadores de diretriz personalizados associados.



