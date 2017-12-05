---
title: "Coletando estatísticas do aplicativo para serviços usando o método de amostragem do criador de perfil | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07840ab2-3a92-4744-ac87-48b19e0ceecd
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6bb7095a4e8b953fc9af68a1fb617ca4c1d2b94f
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2017
---
# <a name="collecting-application-statistics-for-services-by-using-the-profiler-sampling-method"></a>Coletando estatísticas do aplicativo para serviços usando o método de amostragem do criador de perfil
Esta seção descreve os procedimentos e as opções para coletar estatísticas de desempenho de serviços Windows usando o método de amostragem da linha de comando.  
  
> [!NOTE]
>  Os recursos de segurança aprimorados no Windows 8 e no Windows Server 2012 exigiram alterações significativas na maneira como o criador de perfil do Visual Studio coleta dados nessas plataformas. Os aplicativos UWP também requerem novas técnicas de coleta. Consulte [Ferramentas de desempenho em aplicativos do Windows 8 e do Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Tarefas comuns  
  
|Tarefa|Conteúdo relacionado|  
|----------|---------------------|  
|**Anexar o criador de perfil a um serviço .NET**|-   [How to: Attach the Profiler to a .NET Service to Collect Application Statistics (Como anexar o criador de perfil a um serviço do .NET para coletar estatísticas do aplicativo)](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)|  
|**Add tier-interaction data (Adicionar dados de interação de camada)**|-   [Coletando dados de interação entre camadas](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Attach the profiler to a C/C++ service (Anexar o criador de perfil a um serviço C/C++)**|-   [How to: Attach the Profiler to a Native Service to Collect Application Statistics (Como anexar o criador de perfil a um serviço nativo para coletar estatísticas do aplicativo)](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>Tarefas relacionadas  
  
### <a name="profiling-windows-services"></a>Criando o perfil de Serviços Microsoft Windows  
  
|Tarefa|Conteúdo relacionado|  
|----------|---------------------|  
|**Criar perfil usando o método de instrumentação**|-   [Coletando dados de tempo detalhados usando a instrumentação](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**Profile .NET memory allocation and garbage collection (Criar o perfil de alocação de memória e coleta de lixo do .NET)**|-   [Coletando dados de memória do .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
|**Criar perfil de contenção de recursos e atividade de thread**|-   [Coletando dados de simultaneidade](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
  
### <a name="profiling-by-using-the-sampling-method"></a>Criação de perfil usando o método de amostragem  
  
|Tarefa|Conteúdo relacionado|  
|----------|---------------------|  
|**Criar o perfil de aplicativos autônomos (clientes)**|-   [Coletando estatísticas do aplicativo usando amostragem](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Criar o perfil de aplicativos Web ASP.NET**|-   [Coletando estatísticas do aplicativo usando amostragem](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
  
### <a name="analyzing-sampling-data-views-and-reports"></a>Analisando exibições e relatórios dos dados de amostragem  
 [Exibições de dados do método de amostragem](../profiling/profiler-sampling-method-data-views.md)