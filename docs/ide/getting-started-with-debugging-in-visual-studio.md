---
title: "Introdução à depuração no Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 12/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3a14d28-d811-4ff3-bd09-21dce14025ca
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e858d24a37fec49468981b44d450212ba2fa3654
ms.sourcegitcommit: 3285243d6c0521266053340fe06505885d12178b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2018
---
# <a name="get-started-with-debugging-in-visual-studio"></a>Introdução à depuração no Visual Studio
O Visual Studio fornece um poderoso conjunto integrado de ferramentas de depuração e build do projeto. Neste tópico, descubra como começar a usar o conjunto mais básico de recursos de interface do usuário de depuração.  

Se você ainda não tiver instalado o Visual Studio, acesse a página [Downloads do Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) para instalá-lo gratuitamente.

## <a name="my-code-doesnt-work-help-me-visual-studio"></a>Meu código não funciona. Ajude-me, Visual Studio!  
 Então, você descobriu o editor e criou alguns códigos. Agora, você deseja iniciar a depuração desse código. No Visual Studio, assim como acontece com a maioria dos IDEs, há duas fases para depuração: compilar o código para detectar e resolver erros de compilador e de projeto e executar código no ambiente para detectar e resolver erros de tempo de execução e dinâmicos.  

### <a name="build-your-code"></a>Compilar o código  
 Há dois tipos básicos de configuração de build: **Depuração** e **Versão**. A primeira configuração produz um executável maior e mais lento que permite uma experiência de depuração de tempo de execução interativa mais avançada, mas nunca deve ser enviado. A segunda compila um executável mais rápido e mais otimizado apropriado para enviar (pelo menos da perspectiva do compilador). A configuração de build padrão é **Depuração**.

A maneira mais fácil de compilar seu projeto é pressionar **F7**, mas você também pode iniciar o build selecionando **Compilar->Compilar Solução** no menu principal.  

 ![Seleção de menu do projeto de build do Visual Studio](../ide/media/vs_ide_gs_debug_build_menu_item.png "Vs_ide_gs_debug_build_menu_item")  

 Você pode observar o processo de build na janela de status **Saída** na parte inferior da interface do usuário do Visual Studio. Os erros, avisos e operações de build são exibidos aqui. Se você tiver erros (ou se tiver um aviso acima de um nível configurado), haverá falha no build. Você pode clicar nos erros e avisos para ir para a linha em que eles ocorreram. Recompile o projeto pressionando **F7** novamente (para recompilar apenas os arquivos com erros) ou **Ctrl+Alt+F7** (para uma recompilação completa e limpa).  

 Há duas janelas com abas de build na janela de resultados abaixo do editor: a janela **Saída**, que contém a saída bruta do compilador (incluindo mensagens de erro) e a janela **Lista de Erros**, que fornece uma lista filtrável e classificável de todos os erros e avisos.  

 Quando bem-sucedida, você verá resultados semelhantes a esse na janela **Saída**.  

 ![Saída de build bem-sucedido do Visual Studio](../ide/media/vs_ide_gs_debug_success_build.PNG "vs_ide_gs_debug_success_build")  

### <a name="review-the-error-list"></a>Examinar a Lista de Erros  
 A menos que não tenha feito nenhuma modificação no código compilado com êxito anteriormente, provavelmente haverá um erro. Se você não estiver familiarizado com a codificação, provavelmente haverá muitos deles. Às vezes os erros são óbvios, como um erro de sintaxe simples ou um nome de variável incorreto e às vezes eles são difíceis de entender, com apenas um código confuso para orientá-lo. Para uma exibição mais clara dos problemas, navegue até o final da janela **Saída** do build e clique na guia **Lista de Erros**. Isso leva a uma exibição mais organizada dos erros e avisos para o projeto e oferece algumas opções adicionais também.  

 ![Lista de Erros e Saída do Visual Studio](../ide/media/vs_ide_gs_debug_bad_build_error_list.PNG "Vs_ide_gs_debug_bad_build_error_list")  

 Clique na linha de erro na janela **Lista de Erros** e pule para a linha em que ocorre o erro. (Ou ative os números de linha clicando na barra **Início Rápido** na parte superior direita, digitando "números de linha" nela e pressionando Enter. Essa é a maneira mais rápida para chegar à entrada da janela **Opções** em que é possível ativar os números de linha. Saiba como usar a barra **Início Rápido** e poupe muitos cliques na interface do usuário!)  

 ![Editor com números de linha do Visual Studio](../ide/media/vs_ide_gs_debug_line_numbers.png "Vs_ide_gs_debug_line_numbers")  

 ![Opção de números de linha do Visual Studio](../ide/media/vs_ide_gs_debug_options_line_numbers.png "Vs_ide_gs_debug_options_line_numbers")  

 Use **Ctrl+G** para ir rapidamente para o número de linha em que ocorreu o erro.  

 O erro é identificado por um sublinhado vermelho de "rabisco". Passe o mouse sobre ele para obter detalhes adicionais. Faça a correção e ele desaparecerá, embora você possa inserir um novo erro com a correção. (Isso é chamado de "regressão".)  

 ![Focalizar o erro no Visual Studio](../ide/media/vs_ide_gs_debug_error_hover1.png "Vs_ide_gs_debug_error_hover1")  

 Percorra a lista de erros e resolva todos os erros em seu código.  

 ![Janela de erros de depuração do Visual Studio](../ide/media/vs_ide_gs_debug_error_list.PNG "Vs_ide_gs_debug_error_list")  

### <a name="review-errors-in-detail"></a>Examinar os erros detalhadamente  
 Muitos erros podem não fazem sentido para você, formulados como eles estão nos termos do compilador. Nesses casos, você precisará de informações adicionais. Na janela **Lista de Erros**, você pode realizar uma pesquisa automática do Bing para obter mais informações sobre o erro (ou aviso) clicando com o botão direito do mouse na linha de entrada correspondente e selecionando **Mostrar Ajuda para Erros** no menu de contexto.  

 ![Pesquisa do Bing da lista de erros do Visual Studio](../ide/media/vs_ide_gs_debug_error_list_error_help.png "Vs_ide_gs_debug_error_list_error_help")  

 Isso inicia uma guia dentro do Visual Studio que hospeda os resultados de uma pesquisa do Bing do código e texto do erro. Os resultados são de muitas origens diferentes na Internet e nem todos podem ser úteis.  

 Como alternativa, você pode clicar no valor do código de erro com hiperlinks na coluna **Código** da **Lista de Erros**. Isso inicializará uma pesquisa do Bing apenas do código de erro.  

### <a name="use-light-bulbs-to-fix-or-refactor-code"></a>Usar as lâmpadas para corrigir ou refatorar o código  
 As lâmpadas são um novo recurso do Visual Studio que permitem que você refatore o código embutido. Elas são uma maneira fácil de corrigir avisos comuns com rapidez e eficiência. Para acessá-las, clique com botão direito do mouse em um rabisco de aviso (ou pressione **Ctrl+**. ao passar o mouse sobre o rabisco) e, em seguida, selecione **Ações Rápidas**.  

 ![Opções rápidas da lâmpada do Visual Studio](../ide/media/vs_ide_gs_debug_light_bulb1.png "Vs_ide_gs_debug_light_bulb1")  

 Você verá uma lista de possíveis correções ou refatorações que podem ser aplicadas àquela linha de código.  

 ![Visualização da lâmpada do Visual Studio](../ide/media/vs_ide_gs_debug_light_bulb_preview_changes.PNG "Vs_ide_gs_debug_light_bulb_preview_changes")  

 As lâmpadas podem ser usadas sempre que os analisadores de código determinem que há uma oportunidade para corrigir, refatorar ou melhorar seu código. Clique em qualquer linha de código, clique com botão direito do mouse para abrir o menu de contexto e selecione **Ações Rápidas** (ou, novamente, se preferir eficiência, pressione **Ctrl+**). Se houver opções de refatoração ou melhoria disponíveis, elas serão exibidas, caso contrário, a mensagem `No quick options available here` será exibida no bisel do canto inferior esquerdo do IDE.  

 ![Texto “sem opções” da lâmpada do Visual Studio](../ide/media/vs_ide_gs_debug_light_bulb_no_options.PNG "Vs_ide_gs_debug_light_bulb_no_options")  

 Com experiência, você poderá usar rapidamente as teclas de direção e **Ctrl+**. para verificar se há oportunidades de refatoração da Opção Rápida e limpar seu código.  

 Para obter mais informações sobre as lâmpadas, leia [Realizar ações rápidas com lâmpadas](../ide/perform-quick-actions-with-light-bulbs.md).  

### <a name="debug-your-running-code"></a>Depurar seu código em execução  
 Agora que você compilou seu código com êxito e fez uma limpeza rápida, execute-o pressionando **F5** ou selecionando **Depurar->Iniciar Depuração**. Isso iniciará o aplicativo em um ambiente de depuração para que você pode observar seu comportamento em detalhes. O IDE do Visual Studio muda enquanto o aplicativo é executado: a janela **Saída** é substituída por duas novas (na configuração de janela padrão), a janela com guias **Autos/Locais/Inspeção** e a janela com guias **Pilha de Chamadas/Pontos de Interrupção/Configuração de Exceção/Saída**. Essas janelas têm várias guias que permitem inspecionar e avaliar as variáveis, os threads, as pilhas de chamadas e vários outros comportamentos do aplicativo enquanto ele é executado.  

 ![Janelas Autos e Pilha de Chamadas do Visual Studio](../ide/media/vs_ide_gs_debug_autos_and_call_stack.PNG "Vs_ide_gs_debug_autos_and_call_stack")  

 Você pode parar o aplicativo pressionando **Shift+F5** ou clicando no botão **Parar**. Ou, pode simplesmente fechar a janela principal do aplicativo (ou a caixa de diálogo da linha de comando).  

 Se seu código for executado perfeitamente e exatamente como esperado, parabéns! No entanto, se ele tiver parado, falhado ou fornecido alguns resultados estranhos, você precisará localizar a origem desses problemas e corrigir os bugs.  

### <a name="set-simple-breakpoints"></a>Definir pontos de interrupção simples  
 Pontos de interrupção são o recurso mais básico e essencial da depuração confiável. Um ponto de interrupção indica quando o Visual Studio deve suspender o código em execução para que você possa examinar os valores das variáveis ou o comportamento de memória ou se uma ramificação de código está sendo executada ou não. Você NÃO precisa recompilar um projeto após configurar e remover pontos de interrupção.  

 Defina um ponto de interrupção clicando na margem distante da linha em que você deseja que a interrupção ocorra ou pressione **F9** para definir um ponto de interrupção na linha de código atual. Quando você executar o código, ele será pausado (ou *interrompido*) antes das instruções para esta linha de código serem executadas.  

 ![Ponto de interrupção do Visual Studio](../ide/media/vs_ide_gs_debug_breakpoint1.png "Vs_ide_gs_debug_breakpoint1")   

 Os usos comuns para os pontos de interrupção incluem:  

1.  Para restringir a origem de uma falha ou travamento, dispersá-la ao longo e ao redor do código da chamada de método que você acredita que está causando a falha. Conforme você executa o código no depurador, remova e redefina os pontos de interrupção mais próximos até encontrar a linha de código incorreta.  Consulte a próxima seção para aprender a executar o código no depurador.

2.  Ao introduzir um novo código, defina um ponto de interrupção no início dele e execute o código para verificar se ele está se comportando conforme o esperado.

3.  Se tiver implementado um comportamento complicado, defina pontos de interrupção para o código de algoritmo para que você possa inspecionar os valores das variáveis e dados quando o programa for interrompido.  

4.  Se estiver escrevendo código C ou C++, use de pontos de interrupção para parar o código para que você possa inspecionar os valores de endereço (procure por NULL) e contagens de referência ao depurar para falhas relacionadas à memória.  

 Para obter mais informações sobre como usar pontos de interrupção, leia [Usando pontos de interrupção](../debugger/using-breakpoints.md).  

### <a name="inspect-your-code-at-run-time"></a>Inspecionar seu código no tempo de execução  
 Quando seu código em execução atinge um ponto de interrupção e pausa, a linha de código marcada em amarelo (a instrução atual) não foi executada ainda. Neste ponto, pode ser útil executar a instrução atual e, em seguida, inspecionar os valores alterados. Você pode usar vários comandos *step* para executar o código no depurador. Se o código marcado for uma chamada de método, você poderá intervir nele pressionando **F11**. Você também pode *ultrapassar* a linha de código pressionando **F10**. Para obter detalhes sobre como percorrer o código e comandos adicionais, leia [Navegar pelo código com o depurador](../debugger/navigating-through-code-with-the-debugger.md).

 ![Inspeção do valor de tempo de execução do Visual Studio](../ide/media/vs_ide_gs_debug_hit_breakpoint.PNG "vs_ide_gs_debug_inspect_value")

 Na ilustração anterior, você pode avançar uma instrução do depurador pressionando **F10** ou **F11** (como não há nenhuma chamada de método, os dois comandos têm o mesmo resultado).

 Quando o depurador entra em pausa, você pode inspecionar suas variáveis e pilhas de chamadas para determinar o que está acontecendo. Os valores estão nos intervalos que você espera ver? As chamadas estão sendo feitas na ordem correta?  

 ![Inspeção do valor de tempo de execução do Visual Studio](../ide/media/vs_ide_gs_debug_inspect_value.PNG "vs_ide_gs_debug_inspect_value")  

 Passe o mouse sobre uma variável para ver os valores e referências que ela contém no momento. Se você vir um valor que não esperava, provavelmente haverá um bug nas linhas de código anteriores ou de chamada.  Para obter informações mais detalhadas, [saiba mais](../debugger/getting-started-with-the-debugger.md) sobre como usar o depurador.

 Além disso, o Visual Studio exibe a janela Ferramentas de Diagnóstico, na qual você pode observar o uso de memória e CPU do aplicativo ao longo do tempo. Mais tarde no desenvolvimento do seu aplicativo, você pode usar essas ferramentas para procurar uso intenso da CPU ou alocação de memória inesperada. Use-o em conjunto com a janela **Inspeção** e com os pontos de interrupção para determinar o que está ocasionando o uso intenso inesperado ou os recursos não liberados.  Para obter mais informações, consulte [Tour do recurso de criação de perfil](../profiling/profiling-feature-tour.md).

### <a name="run-unit-tests"></a>Executar testes de unidade  
 Testes de unidade são a primeira linha de defesa contra erros no código porque, quando realizados corretamente, eles testam uma única “unidade” de código, normalmente uma única função e são geralmente muito mais fáceis de depurar do que a depuração do programa completo. O Visual Studio instala as estruturas de teste de unidade da Microsoft para código gerenciado e nativo. Use uma estrutura de teste de unidade para criar testes de unidade, executá-los e relatar os resultados desses testes. Execute os testes de unidade novamente quando realizar alterações para testar se o código ainda está funcionando corretamente. Quando você usa o Visual Studio Enterprise Edition, pode executar testes automaticamente após cada build.  

 Para começar, leia [Gerar testes de unidade para seu código com IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md).  

 Para saber mais sobre testes de unidade no Visual Studio e como eles podem ajudá-lo a criar código de melhor qualidade, leia [Noções básicas de teste de unidade](../test/unit-test-basics.md).  

### <a name="perform-static-code-analysis"></a>Realizar análise de código estático  
 "Análise de código estático" é uma forma elegante de dizer "verificar automaticamente meu código quanto a problemas comuns que podem levar a erros em tempo de execução ou a problemas no gerenciamento do código". Crie o hábito de executá-lo depois de limpar os erros óbvios que impediam o build e reserve um tempo para resolver os avisos que ele pode produzir. Você evitará algumas dores de cabeça no futuro, bem como aprenderá algumas técnicas de estilo de código.  

 Pressione **Alt+F11** (ou selecione **Analisar > Executar Análise de Código na Solução** no menu superior) para iniciar a análise de código estático. Isso poderá levar algum tempo se você tiver muito código.  

 ![Item de menu Análise de Código no Visual Studio](../ide/media/vs_ide_gs_debug_run_code_analysis.png "Vs_ide_gs_debug_run_code_analysis")  

 Os avisos novos ou atualizados aparecerão na guia **Lista de Erros** na parte inferior do IDE. Clique nos avisos para acessá-los.  

 ![Lista de Erros com Avisos do Visual Studio](../ide/media/vs_ide_gs_debug_code_analysis_warning_error_list.PNG "vs_ide_gs_debug_code_analysis_warning_error_list")  

 Os avisos serão identificados com um rabisco verde-amarelo brilhante em vez de um vermelho. Passe o mouse sobre eles para obter mais detalhes e clique com o botão direito do mouse neles para obter um menu de contexto para auxiliar nas opções de correção ou refatoração.  

 ![Foco do Aviso da Análise de Código do Visual Studio](../ide/media/vs_ide_gs_debug_code_analysis_warning_hover.png "vs_ide_gs_debug_code_analysis_warning_hover")  

## <a name="see-also"></a>Consulte também  
 [Tour dos recursos do depurador](../debugger/debugger-feature-tour.md)  
 [Saiba mais sobre como usar o depurador](../debugger/getting-started-with-the-debugger.md)
