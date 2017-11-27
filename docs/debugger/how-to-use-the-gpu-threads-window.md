---
title: "Exibição de Threads de GPU no depurador | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.gputthreads
- vs.debug.gputhreads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, GPU threads window
ms.assetid: c647c502-a9f0-48e0-a430-976744a5fa51
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 23bb4ee4550f70681152fc14cc66a642597125ad
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-the-gpu-threads-window"></a>Como usar a janela Threads de GPU
Na janela Threads da GPU, você pode examinar e trabalhar com threads que estão sendo executadas no GPU no aplicativo que você está depurando. Para obter mais informações sobre aplicativos que são executados na GPU, consulte [visão geral do C++ AMP](/cpp/parallel/amp/cpp-amp-overview).  
  
 A janela de Threads da GPU contém uma tabela na qual cada linha representa um conjunto de threads de GPU que têm os mesmos valores em todas as colunas. Você pode classificar, reorganizar, remover e agrupar os itens que estão nas colunas. Você pode sinalizar, remover sinalização, congelar (suspender) e descongelar (retomar) threads da janela de Threads da GPU. As colunas a seguir são exibidas na janela Threads da GPU:  
  
-   A coluna do sinalizador, na qual você pode marcar um thread ao qual deseja prestar atenção especial.  
  
-   A coluna de segmento atual, no qual uma seta amarela indica que o thread atual.  
  
-   O **a contagem de threads** coluna, que exibe o número de threads no mesmo local.  
  
-   O **linha** coluna, que exibe a linha de código em que cada grupo de threads está localizado.  
  
-   O **endereço** coluna, que exibe o endereço de instrução em que cada grupo de threads está localizado. Por padrão, essa coluna está ocultada.  
  
-   O **local** coluna, que é o local no código-fonte.  
  
-   O **Status** coluna, que mostra se o thread está ativo, bloqueado, não iniciada ou concluída.  
  
-   O **bloco** coluna, que mostra o índice de bloco para os threads na linha.  
  
 O cabeçalho da tabela mostra que o quadro e o thread estão sendo exibidos.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-display-the-gpu-threads-window"></a>Para exibir a janela Threads da GPU  
  
1.  No **Gerenciador de Soluções**, abra o menu de atalho para o projeto e escolha **Propriedades**.  
  
2.  No **páginas de propriedade** janela para o projeto em **propriedades de configuração**, escolha **depuração**.  
  
3.  No **depurador a iniciar** lista, selecione **depurador Local do Windows**. No **tipo de depurador** lista, selecione **somente GPU**. Você deve escolher este depurador para parar em pontos de interrupção no código executado no GPU.  
  
4.  Selecione o botão **OK**.  
  
5.  Defina um ponto de interrupção no código do GPU.  
  
6.  Na barra de menus, escolha **Depurar**, **Iniciar Depuração**. Aguarde até que o aplicativo atinja o ponto de interrupção.  
  
7.  Uma barra de menus, escolha **depurar**, **Windows**, **Threads de GPU**.  
  
### <a name="to-switch-to-a-different-thread"></a>Para alternar para um thread diferente  
  
-   Clique duas vezes na coluna. (Teclado: selecione a linha e escolha Enter.)  
  
### <a name="to-display-a-particular-tile-and-thread"></a>Para exibir um determinado bloco e o thread  
  
1.  Escolha o **expanda alternador de Thread** botão na janela de Threads de GPU.  
  
2.  Insira os valores do quadro e de thread nas caixas de texto.  
  
3.  Escolha o botão que tem a seta.  
  
### <a name="to-display-or-hide-a-column"></a>Para exibir ou ocultar uma coluna  
  
-   Abra o menu de atalho para a janela Threads de GPU, escolha **colunas**e, em seguida, escolha a coluna que você deseja exibir ou ocultar.  
  
### <a name="to-sort-by-a-column"></a>Para classificar por coluna  
  
-   Selecione o título da coluna.  
  
### <a name="to-group-threads"></a>Para agrupar threads  
  
-   Abra o menu de atalho para a janela Threads de GPU, escolha **Group By**e, em seguida, escolha um dos nomes de coluna exibidos. Escolha **nenhum** para desagrupe os threads.  
  
### <a name="to-freeze-or-thaw-a-row-of-threads"></a>Para congelar ou descongelar uma linha de threads  
  
-   Abra o menu de atalho para a linha e escolha **congelar** ou **descongelar**.  
  
### <a name="to-flag-or-unflag-a-row-of-threads"></a>Para sinalizar ou remover sinalização de uma linha de threads  
  
-   Selecione a coluna do sinalizador para o segmento, ou abra o menu de atalho para o thread e escolha **sinalizador** ou **Unflag**.  
  
### <a name="to-display-only-flagged-threads"></a>Para exibir somente threads sinalizados  
  
-   Escolha o botão de sinalizador na janela Threads da GPU.  
  
## <a name="see-also"></a>Consulte também  
 [Depurar aplicativos multithread](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Como: usar a janela Inspeção paralela](../debugger/how-to-use-the-parallel-watch-window.md)   
 [Passo a passo: depurando um aplicativo C++ AMP](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)