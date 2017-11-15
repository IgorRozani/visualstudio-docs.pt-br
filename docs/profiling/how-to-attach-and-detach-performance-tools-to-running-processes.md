---
title: "Como anexar e desanexar ferramentas de desempenho de processos em execução | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.attach
helpviewer_keywords:
- performance tools, attach process
- profiling tools, detach process
- profiling tools, attach process
- performance tools, detach process
- profiler
ms.assetid: 56a99c39-e7f6-4f48-ae56-04ab8e022bf7
caps.latest.revision: "30"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 630a51cc9933b1e7b71f2926c6a057bff13bc81b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-attach-and-detach-performance-tools-to-running-processes"></a>Como anexar e desanexar ferramentas de desempenho de processos em execução
O criador de perfil pode ser usado para anexar ou desanexar de um processo em execução para facilitar a amostragem e a coleta de dados de desempenho. É possível usar esse método para criar o perfil de um processo quando você deseja evitar a coleta de dados sobre o tempo de carregamento do aplicativo ou para monitorar o desempenho de um processo após ele atingir um estado específico.  
  
> [!NOTE]
>  As etapas a seguir se aplicam aos processos de anexar e desanexar de dentro do IDE (ambiente de desenvolvimento integrado) do [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. Para obter informações sobre como usar ferramentas de linha de comando, consulte [Criação de perfil da linha de comando](../profiling/using-the-profiling-tools-from-the-command-line.md). Para obter informações sobre como criar o perfil de serviços, consulte [Criando o perfil de serviços](../profiling/command-line-profiling-of-services.md).  
  
 Os processos que estão disponíveis para criação de perfil dependem das Permissões de acesso do usuário definidas por um administrador do computador. Uma conta de usuário pode, por exemplo, ter permissão para qualquer um dos seguintes:  
  
-   Recursos avançados de criação de perfil, quando o administrador tiver configurado o início do driver e do serviço.  
  
-   Criação de perfil de amostra apenas (usuários de domínio).  
  
-   Acesso negado à criação de perfil para todos.  
  
 Para obter mais informações, consulte [Criação de perfil e segurança do Windows Vista](../profiling/profiling-and-windows-vista-security.md) e as opções de administração em [VSPerfCmd](../profiling/vsperfcmd.md).  
  
### <a name="to-attach-to-a-running-process"></a>Para anexar a um processo em execução  
  
1.  No menu **Depurar**, aponte para **Criador de Perfil**, em seguida, para **Gerenciador de Desempenho** e clique em **Anexar**.    
  
     É exibida a caixa de diálogo **Anexar Criador de Perfil a Processo**.  
  
2.  Clique no nome do processo ao qual deseja anexar.  
  
3.  Clique em **Anexar**.  
  
### <a name="to-detach-from-a-running-process"></a>Para desanexar de um processo em execução  
  
1.  No menu **Depurar**, aponte para **Criador de Perfil**, em seguida, para **Gerenciador de Desempenho** e clique em **Desanexar**. 
  
     É exibida a caixa de diálogo **Anexar Criador de Perfil a Processo**.  
  
2.  Clique no nome da imagem da qual deseja desanexar.  
  
3.  Clique em **Desanexar**.  
  
## <a name="see-also"></a>Consulte também  
 [Controlando a coleta de dados](../profiling/controlling-data-collection.md)   
 [Visão geral da sessão de desempenho](../profiling/performance-session-overview.md)   
 [Como iniciar e encerrar a coleta de dados de desempenho](../profiling/how-to-start-and-end-performance-data-collection.md)   
 [Criação de perfil e segurança do Windows Vista](../profiling/profiling-and-windows-vista-security.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)