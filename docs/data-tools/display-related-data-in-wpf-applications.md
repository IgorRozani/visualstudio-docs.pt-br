---
title: Exibir dados relacionados em aplicativos WPF
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: 3aa80194-0191-474d-9d28-5ec05654b426
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 38c25cc1631529895a11af566298ce22930a2e6a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746540"
---
# <a name="display-related-data-in-wpf-applications"></a>Exibir dados relacionados em aplicativos WPF
Em alguns aplicativos, você talvez queira trabalhar com dados que vêm de várias tabelas ou entidades que estão relacionadas entre si em uma relação pai-filho. Por exemplo, você talvez queira exibir uma grade que exibe os clientes de um `Customers` tabela. Quando o usuário seleciona um cliente específico, outro grade exibe os pedidos do cliente de um relacionados `Orders` tabela.

Você pode criar controles associados a dados que exibem dados relacionados arrastando itens a partir de **fontes de dados** janela para o Designer do WPF.

## <a name="to-create-controls-that-display-related-records"></a>Para criar controles que exibem registros relacionados

1. Sobre o **dados** menu, clique em **Mostrar fontes de dados** para abrir o **fontes de dados** janela.

2. Clique em **adicionar nova fonte de dados**e conclua o **configuração da fonte de dados** assistente.

3. Abra o designer do WPF e certifique-se de que o designer contém um contêiner que é um destino válido para os itens a **fontes de dados** janela.

     Para obter mais informações sobre os destinos de soltar válidas, consulte [WPF associar controles a dados no Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

4. No **fontes de dados** janela, expanda o nó que representa a tabela pai ou do objeto da relação. A tabela pai ou o objeto está no lado "um" de uma relação um-para-muitos.

5. Arraste o nó pai (ou todos os itens individuais no nó pai) da **fontes de dados** window para um destino válido no designer.

     O Visual Studio gera o XAML que cria novos controles de associação de dados para cada item que você arrasta. O XAML também adiciona um novo <xref:System.Windows.Data.CollectionViewSource> para a tabela pai ou o objeto para os recursos de destino de soltar. Para algumas fontes de dados, o Visual Studio também gera código para carregar os dados na tabela pai ou do objeto. Para obter mais informações, consulte [WPF associar controles a dados no Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

6. No **fontes de dados** janela, localize a tabela filho relacionada ou o objeto. Objetos e tabelas filho relacionadas aparecem como nós expansíveis na parte inferior da lista do nó pai de dados.

7. Arraste o nó filho (ou todos os itens individuais no nó filho) da **fontes de dados** window para um destino válido no designer.

     O Visual Studio gera o XAML que cria novos controles de associação de dados para cada um dos itens que você arrasta. O XAML também adiciona um novo <xref:System.Windows.Data.CollectionViewSource> para a tabela filho ou objeto para os recursos de destino de soltar. Essa nova <xref:System.Windows.Data.CollectionViewSource> está associado à propriedade da tabela pai ou do objeto que você acabou de arrastar para o designer. Para algumas fontes de dados, o Visual Studio também gera código para carregar os dados na tabela filho ou objeto.

     A figura a seguir demonstra o relacionados **pedidos** tabela do **clientes** tabela em um conjunto de dados a **fontes de dados** janela.

     ![Relação de exibição de janela fontes de dados](../data-tools/media/datasources2.gif)

## <a name="see-also"></a>Consulte também

- [Associar controles WPF a dados no Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [Criar tabelas de pesquisa em aplicativos do WPF](../data-tools/create-lookup-tables-in-wpf-applications.md)