---
title: Como serializar informações de símbolo | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Performance.General
helpviewer_keywords:
- profiling tools, serializing symbol information
- performance tools, serializing symbol information
ms.assetid: 9e0da706-6325-4073-83d1-aeab3b7c137a
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a6c0e567131d36cbc7e805533f7d5acb9c5f3277
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49256549"
---
# <a name="how-to-serialize-symbol-information"></a>Como serializar informações de símbolo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode serializar os símbolos que são necessários para analisar seu aplicativo. A serialização de símbolos adiciona símbolos no arquivo .vsp. Ao adicionar informações de símbolo no arquivo .vsp, outras pessoas podem analisar um relatório de desempenho sem ter acesso aos símbolos originais. Se os símbolos não forem serializados, você deverá ter os arquivos originais instrumentados .exe e .pdb para analisar o arquivo .vsp.  
  
### <a name="to-automatically-serialize-symbol-information"></a>Para serializar informações de símbolo automaticamente  
  
1.  No menu **Ferramentas**, clique em **Opções**.  
  
     A caixa de diálogo **Opções** é exibida.  
  
2.  Clique em **Ferramentas de Desempenho**.  
  
3.  Em **Configuração Geral**, selecione **Serializar informações de símbolo automaticamente**.  
  
## <a name="see-also"></a>Consulte também  
 [Configurando sessões de desempenho](../profiling/configuring-performance-sessions.md)   
 [Como fazer referência a informações de símbolo do Windows](../profiling/how-to-reference-windows-symbol-information.md)   
 [Como salvar arquivos de relatório analisados](http://msdn.microsoft.com/en-us/0340ddde-caf4-48ac-8af3-d15dcdade556)



