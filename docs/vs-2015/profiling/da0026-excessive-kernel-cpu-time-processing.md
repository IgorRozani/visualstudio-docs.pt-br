---
title: 'DA0026: excesso de processamento de tempo de CPU do kernel | Microsoft Docs'
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
- vs.performance.rules.DA0026
- vs.performance.DA0026
- vs.performance.26
ms.assetid: 4cfc8a29-b29b-4a72-b386-03d8856fdf8a
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 95aac29eb4610712cc113ea9efee413ca20d2390
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49186232"
---
# <a name="da0026-excessive-kernel-cpu-time-processing"></a>DA0026: processamento de tempo de CPU do kernel excessivo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Id da regra | TODO |  
| Categoria | Uso das ferramentas de criação de perfil |  
| Método de criação de perfil | Amostragem |  
| Mensagem | Foi medida uma quantidade relativamente alta de tempo de CPU em modo kernel. Considere a possibilidade de investigar a origem com a amostragem SysCall habilitada. |  
| Tipo de regra | Informações |  
  
 Ao criar o perfil usando a amostragem, a memória do .NET ou métodos de contenção de recursos, é necessário coletar pelo menos 10 amostras para disparar essa regra.  
  
## <a name="cause"></a>Causa  
 A proporção de tempo da CPU que foi executada em modo kernel excedeu o tempo gasto no modo de usuário. Considere uma nova criação de perfil e a amostragem do número de chamadas do sistema (syscalls) para determinar a causa dos altos tempos de execução de modo do kernel.  
  
## <a name="rule-description"></a>Descrição da Regra  
 A proporção relativamente alta de tempo gasto pelo aplicativo na execução em modo kernel pode garantir uma investigação adicional. Um aplicativo de modo de usuário faz a transição para o modo de kernel para executar operações de E/S, aguardar os primitivos de sincronização de thread ou de processo ou fazer chamadas do sistema. É possível investigar os tipos de chamadas do sistema feitas pelo aplicativo e quais funções são responsáveis por elas ao selecionar a opção para coletar as pilhas de chamadas de amostra com base em chamadas do Sistema.  
  
## <a name="how-to-fix-violations"></a>Como Corrigir Violações  
 Para investigar os tipos de chamadas do sistema feitas pelo aplicativo, execute o perfil novamente e selecione a opção para coletar amostras com base em chamadas do sistema. Consulte [Como escolher eventos de amostragem](../profiling/how-to-choose-sampling-events.md) se estiver executando as ferramentas de criação de perfil na IDE para obter mais informações. Se você estiver executando as ferramentas de criação de perfil por meio da linha de comando, consulte a seção **Opções de intervalo de amostragem** do tópico [VSPerfCmd](../profiling/vsperfcmd.md) na referência das ferramentas de linha de comando das Ferramentas de Criação de Perfil.



