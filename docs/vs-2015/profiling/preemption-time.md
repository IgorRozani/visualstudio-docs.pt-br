---
title: Tempo de preempção | Microsoft Docs
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
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 943111386539ddb9ac686b0551dfe176f9e2d320
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49194059"
---
# <a name="preemption-time"></a>Tempo de preempção
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Esses segmentos na linha do tempo estão associados os tempos de bloqueio categorizados como Preempção. Esta categoria implica que um thread é alternado devido a um destes motivos:  
  
-   O agendador substituiu usando um thread de prioridade mais alta.  
  
-   O quantum de execução do thread expirou e outros threads estavam prontos para execução.  
  
 Durante esse tempo, um thread foi bloqueado por uma espera de kernel, motivo pelo qual a visualização simultânea está contando como preempção. Segmentos de preempção iniciam quando um thread é empurrado para fora de um núcleo lógico e terminam quando esse thread continua a execução.  
  
 A dica de ferramenta para um segmento que admitiu preempção exibe o nome do processo ou thread que causou a preempção. No entanto, isso não significa que o processo ou thread que assumiu o controle foi realmente executado durante o período de admitiu preempção.  
  
## <a name="see-also"></a>Consulte também  
 [Exibição de Threads](../profiling/threads-view-parallel-performance.md)



