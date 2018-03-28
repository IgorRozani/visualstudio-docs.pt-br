---
title: Usar mapas de códigos para depurar aplicativos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Ultimate, visualizing code
- Visual Studio Ultimate, navigating code visually
- Visual Studio Ultimate, understanding code
- Visual Studio Ultimate, mapping code relationships
- Visual Studio Ultimate, code maps
- mapping code relationships
- code maps
- mapping relationships in code
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: ab5d32c6a25eb9db21970ade0034aa1afd219a61
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="use-code-maps-to-debug-your-applications"></a>Usar mapas de códigos para depurar aplicativos
Mapas de código podem ajudá-lo a evitar se perder em grandes bases de código, de código não familiar ou código herdado. Por exemplo, quando você estiver depurando, você talvez precise examine o código de vários arquivos e projetos. Usar mapas de códigos para navegar em torno de trechos de código e entender as relações entre eles. Dessa forma, você não precisa manter o controle desse código de cabeça ou desenhe um diagrama separado. Portanto, quando o trabalho for interrompido, o código mapeia atualização ajuda sua memória sobre o código que você está trabalhando.  

 ![Mapa de código &#45; mapear relações no código](../modeling/media/codemapstoryboardpaint.png "CodeMapStoryboardPaint")  

 **Mostra uma seta verde que onde o cursor aparece no editor**  

 Para obter detalhes sobre os comandos e as ações que você pode usar ao trabalhar com mapas de código, consulte [procurar e reorganizar mapas de código](../modeling/browse-and-rearrange-code-maps.md).  

## <a name="understand-the-problem"></a>Compreender o problema  
 Suponhamos que haja um bug em um programa de desenho no qual você está trabalhando. Para reproduzir o bug, abra a solução no Visual Studio e pressione **F5** para iniciar a depuração.  

 Quando você desenhar uma linha e escolha **desfazer o último traço**, nada acontecerá até você desenha a próxima linha.  

 ![Mapa de código &#45; bug de reprodução](../modeling/media/codemapstoryboardpaint0.png "CodeMapStoryboardPaint0")  

 Assim, você começa a investigação procurando o método `Undo`. Você o encontra na classe `PaintCanvas`.  

 ![Mapa de código &#45; encontrar código](../modeling/media/codemapstoryboardpaint1.png "CodeMapStoryboardPaint1")  

## <a name="start-mapping-the-code"></a>Começar a mapear o código  
 Iniciar agora mapeando o `undo` método e suas relações. No editor de códigos, você adiciona o método `undo` e os campos aos quais faz referência a um novo mapa de códigos. Quando você cria um novo mapa, ele pode demorar algum tempo para indexar o código. Isso ajuda a executar mais rapidamente as operações posteriores.  

 ![Mapa de código &#45; Mostrar campos relacionados e método](../modeling/media/codemapstoryboardpaint3.png "CodeMapStoryboardPaint3")  

> [!TIP]
>  O realce verde mostra os últimos itens que foram adicionados ao mapa. A seta verde mostra a posição do cursor no código. As setas entre os itens representam relações diferentes. Você pode obter mais informações sobre os itens no mapa de mover o mouse sobre eles e examinando seus dicas de ferramenta.  

 ![Mapa de código &#45; Mostrar dicas de ferramenta](../modeling/media/codemapstoryboardpaint4.png "CodeMapStoryboardPaint4")  

## <a name="navigate-and-examine-code-from-the-map"></a>Navegar e examinar o código no mapa  
 Para ver a definição de código para cada campo, clique duas vezes no campo no mapa ou selecione o campo e pressione **F12**. A seta verde alterna itens no mapa. O cursor no editor de códigos também se move automaticamente.  

 ![Mapa de código &#45; examinar a definição de campo](../modeling/media/codemapstoryboardpaint5.png "CodeMapStoryboardPaint5")  

 ![Mapa de código &#45; examinar a definição de campo](../modeling/media/codemapstoryboardpaint5a.png "CodeMapStoryboardPaint5A")  

> [!TIP]
>  Também é possível mover a seta verde no mapa movendo-se o cursor no editor de códigos.  

## <a name="understand-relationships-between-pieces-of-code"></a>Compreender as relações entre as partes do código  
 Agora você deseja saber qual o outro código interage com os campos `history` e `paintObjects`. É possível adicionar todos os métodos que referenciam esses campos no mapa. Você pode fazer isso de mapa ou de código no editor.  

 ![Mapa de código &#45; localizar todas as referências](../modeling/media/codemapstoryboardpaint6.png "CodeMapStoryboardPaint6")  

 ![Abra um mapa de código do editor de códigos](../modeling/media/codemapstoryboardpaint6a.PNG "CodeMapStoryboardPaint6A")  

> [!NOTE]
>  Se você adicionar itens de um projeto que é compartilhado entre vários aplicativos, como o Windows Phone ou da Windows Store, em seguida, esses itens apareçam sempre com o projeto de aplicativo atualmente ativas no mapa. Portanto, se você alterar o contexto para outro projeto de aplicativo, também altera o contexto no mapa para qualquer recém-adicionado itens de projeto compartilhado. Operações realizadas com um item no mapa se aplicam apenas aos itens que compartilham o mesmo contexto.  

 Altere o layout para reorganizar o fluxo de relações e para facilitar a leitura do mapa. Também é possível mover itens pelo mapa arrastando-os.  

 ![Mapa de código &#45; alterar layout](../modeling/media/codemapstoryboardpaint7a.png "CodeMapStoryboardPaint7A")  

> [!TIP]
>  Por padrão, **Layout Incremental** está ativado. Isso reorganiza o mapa o menos possível quando você adiciona novos itens. Para reorganizar mapa de inteiro sempre que você adicionar novos itens, desativar **Layout Incremental**.  

 ![Mapa de código &#45; alterar layout](../modeling/media/codemapstoryboardpaint7.png "CodeMapStoryboardPaint7")  

 Vamos examinar esses métodos. No mapa, clique duas vezes o **PaintCanvas** método, ou selecione este método e pressione **F12**. Você aprende que esse método cria `history` e `paintObjects` como listas vazias.  

 ![Mapa de código &#45; examinar a definição de método](../modeling/media/codemapstoryboardpaint8.png "CodeMapStoryboardPaint8")  

 Agora repita as mesmas etapas para examinar a definição do método `clear`. Você aprende que `clear` realiza algumas tarefas com `paintObjects` e `history`. Em seguida, ele chama o método `Repaint`.  

 ![Mapa de código &#45; examinar a definição de método](../modeling/media/codemapstoryboardpaint9.png "CodeMapStoryboardPaint9")  

 Agora examine a definição do método `addPaintObject`. Ele também realiza algumas tarefas com `history` e `paintObjects`. Ele também chama `Repaint`.  

 ![Mapa de código &#45; examinar a definição de método](../modeling/media/codemapstoryboardpaint10.png "CodeMapStoryboardPaint10")  

## <a name="find-the-problem-by-examining-the-map"></a>Encontre o problema examinando o mapa  
 Aparentemente, todos os métodos que modificam `history` e `paintObjects` chamam `Repaint`. Ainda assim, o método `undo` não chama `Repaint`, mesmo que `undo` modifique os mesmos campos. Então você acha que é possível corrigir esse problema chamando `Repaint` em `undo`.  

 ![Mapa de código &#45; localizar ausente chamada de método](../modeling/media/codemapstoryboardpaint11.png "CodeMapStoryboardPaint11")  

 Se você não tivesse um mapa para mostrar essa chamada perdida, poderia ser bem mais difícil encontrar esse problema, especialmente com um código mais complexo.  

## <a name="share-your-discovery-and-next-steps"></a>Compartilhar a descoberta e as próximas etapas  
 Antes de você ou alguma outra pessoa corrigir esse bug, é possível fazer anotações no mapa sobre o problema e como corrigi-lo.  

 ![Mapa de código &#45; itens de comentário e o sinalizador para acompanhamento](../modeling/media/codemapstoryboardpaint12.png "CodeMapStoryboardPaint12")  

 Por exemplo, é possível adicionar comentários ao mapa e sinalizar itens usando cores.  

 ![Mapa de código &#45; comentada e itens sinalizados](../modeling/media/codemapstoryboardpaint12a.png "CodeMapStoryboardPaint12A")  

 Se tiver o Microsoft Outlook instalado, você poderá enviar por email o mapa para outras pessoas. Também é possível exportar o mapa como uma imagem ou em outro formato.  

 ![Mapa de código &#45; compartilhamento, exportação, mail](../modeling/media/codemapstoryboardpaint13.png "CodeMapStoryboardPaint13")  

## <a name="fix-the-problem-and-show-what-you-did"></a>Corrigir o problema e mostrar o que você fez  
 Para corrigir esse bug, adicione a chamada de `Repaint` ao `undo`.  

 ![Mapa de código &#45; Adicionar chamada de método ausente](../modeling/media/codemapstoryboardpaint14.png "CodeMapStoryboardPaint14")  

 Para confirmar a correção, reinicie a sessão de depuração e tente reproduzir o erro. Escolhendo agora **desfazer o último traço** funciona conforme o esperado e confirma que você fez a correção correta.  

 ![Mapa de código &#45; confirmar código corrigir](../modeling/media/codemapstoryboardpaint15.png "CodeMapStoryboardPaint15")  

 É possível atualizar o mapa para mostrar a correção feita.  

 ![Mapa de código &#45; mapa de atualização com ausente chamada de método](../modeling/media/codemapstoryboardpaint16.png "CodeMapStoryboardPaint16")  

 Agora, seu mapa mostra um link entre **desfazer** e **redesenhar**.  

 ![Mapa de código &#45; mapa atualizadas com a chamada de método](../modeling/media/codemapstoryboardpaint17.png "CodeMapStoryboardPaint17")  

> [!NOTE]
>  Ao atualizar o mapa, você talvez veja uma mensagem afirmando que o índice de código usado para criar o mapa foi atualizado. Isso significa que alguém alterou o código, o que faz o mapa não corresponder ao código atual. Isso não impede você de atualizar o mapa, mas talvez precise recriar o mapa para confirmar se ele corresponde ao código.  

 Agora você concluiu sua investigação. Você encontrou e corrigiu o problema com êxito mapeando o código. Você também tem um mapa que ajuda a navegar no código, lembrar o que aprendeu e mostra as etapas que você seguiu para corrigir o problema.  

## <a name="see-also"></a>Consulte também  
 [Mapear métodos na pilha de chamadas durante a depuração](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)   
 [Visualizar código](../modeling/visualize-code.md)
