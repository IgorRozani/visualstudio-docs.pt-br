---
title: Coletando Dados de Memória por meio de um Aplicativo Web ASP .NET Usando a Linha de Comando do Criador de Perfil | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- profiling tools,.NET memory method
ms.assetid: 57acf2b0-327a-4c0e-8078-ac2f6d99457d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 161f96c38a12de1f29a0f4ebd5d3779f31cf8f23
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2018
---
# <a name="collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line"></a>Coletando dados de memória a partir de um aplicativo Web do ASP.NET usando a linha de comando do criador de perfil
Esta seção descreve os procedimentos e as opções para coletar alocação de memória e dados de tempo de vida do objeto para um aplicativo Web ASP .NET usando a ferramenta de linha de comando **VSPerfCmd**.  
  
> [!NOTE]
>  A ferramenta **VSPerfCmd** dá acesso completo à funcionalidade de Ferramentas de Criação de Perfil, inclusive pausar e retomar a criação de perfil e coletar dados adicionais do processador e de contadores de desempenho do Windows. Também é possível usar a ferramenta de linha de comando **VSPerfASPNETCmd** quando essa funcionalidade não for necessária. Em comparação com a ferramenta de linha de comando [VSPerfCmd](../profiling/vsperfcmd.md), nenhuma variável de ambiente precisa ser definida nem é necessário reiniciar o computador. Para obter mais informações, consulte [Criação de perfil do site rápida com VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Tarefas comuns  
  
|Tarefa|Conteúdo relacionado|  
|----------|---------------------|  
|**Anexar o criador de perfil a um aplicativo ASP.NET em execução**|-   [Como Anexar o Criador de Perfil a um Aplicativo Web ASP .NET para Coletar Dados de Memória](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)|  
|**Instrumentar binários compilados estatisticamente**|-   [Como Instrumentar um Aplicativo do ASP.NET Compilado Estaticamente e Coletar Dados de Memória](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
|**Instrumentar binários compilados dinamicamente**|-   [Como Instrumentar um Aplicativo do ASP.NET Compilado Dinamicamente e Coletar Dados de Memória](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)|  
  
## <a name="related-tasks"></a>Tarefas relacionadas  
  
### <a name="profiling-aspnet-web-applications"></a>Criando perfil de aplicativos Web do ASP.NET  
  
|Tarefa|Conteúdo relacionado|  
|----------|---------------------|  
|**Criar perfil usando o método de amostragem**|-   [Coletando estatísticas do aplicativo usando amostragem](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|  
|**Criar perfil usando o método de instrumentação**|-   [Coletando dados de tempo detalhados usando a instrumentação](../profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method.md)|  
|**Criar perfil de contenção de recursos e atividade de thread**|-   [Coletando dados de simultaneidade](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="profiling-net-framework-memory-data"></a>Criando perfis de dados de memória do .NET Framework  
  
|Tarefa|Conteúdo relacionado|  
|----------|---------------------|  
|**Criar o perfil de aplicativos autônomos (clientes)**|-   [Coletando dados de memória do .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications.md)|  
|**Profile services (Serviços de perfil)**|-   [Coletando dados de memória do .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="analyzing-net-memory-data-views-and-reports"></a>Analisando modos de exibição e relatórios de dados de memória do .NET  
 [Exibições de dados da memória do .NET](../profiling/dotnet-memory-data-views.md)  
  
## <a name="reference"></a>Referência  
 [Referência de ferramentas de criação de perfil de linha de comando](../profiling/command-line-profiling-tools-reference.md)