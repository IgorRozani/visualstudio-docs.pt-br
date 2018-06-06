---
title: Depurando por meio do Visualizador de Repositório
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, store viewer
- Domain-Specific Language, store
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5424fc8e3bdf80f5a6f19086f4e73360af95dad7
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748404"
---
# <a name="debugging-by-using-the-store-viewer"></a>Depurando por meio do Visualizador de Repositório
Com o Visualizador de armazenar, você pode examinar o estado de um *armazenar* usado pelo [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]. O Visualizador de armazenar exibe todos os elementos de modelo de domínio que estão em uma loja específica, juntamente com as propriedades de elemento e links entre os elementos.

## <a name="opening-store-viewer"></a>Visualizador do armazenamento de abertura
 Quando você está no [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] experimental de compilação, interromper seu código em um ponto de interrupção em que uma instância do repositório contém informações de modelo. Em seguida, abra o Visualizador de repositório, digitando o seguinte comando no **imediato** janela:

```
Microsoft.VisualStudio.Modeling.Diagnostics.StoreViewer.Show(mystore);
```

> [!NOTE]
>  Você deve substituir `mystore` com o nome da sua instância do repositório. Além disso, se você adicionar o namespace ao seu código, você pode digitar o comando para exibir o Visualizador de armazenamento sem o namespace totalmente qualificado:
>
>  `using Microsoft.VisualStudio.Modeling.Diagnostics;`
>
>  `...`
>
>  `StoreViewer.Show(mystore);`

 O `Show` método tem várias sobrecargas. Você pode especificar uma instância de uma loja ou uma partição como o parâmetro.

 Como alternativa, você pode colocar a linha de código que exibe o Visualizador de repositório em qualquer lugar no seu código em que o parâmetro que você passa para o `Show` método está no escopo. Essa ação exibe o Visualizador de armazenar quando a linha de código é executado como um instantâneo do conteúdo do repositório.

### <a name="using-store-viewer"></a>Usando o Visualizador de armazenamento
 Quando abre o Visualizador de armazenamento, uma janela de Windows Forms sem janela restrita aparece, como mostra a ilustração a seguir.

 ![](../modeling/media/storeviewer2.png) Visualizador de armazenamento

 O Visualizador de armazenamento possui três painéis: o painel esquerdo, o painel superior direito e o painel inferior direito. O painel esquerdo é uma exibição de árvore dos tipos de `DomainDataDirectory` membro de um repositório. Se você expandir o nó da partição e clique em um elemento, as propriedades aparecem no painel superior direito. Se o elemento estiver vinculado a outros elementos, os elementos adicionais aparecem no painel inferior direito. Se você clicar duas vezes um elemento no painel inferior direito, o elemento é realçado no painel esquerdo.

## <a name="see-also"></a>Consulte também

- [Navegando por um modelo no código do programa e atualizando-o](../modeling/navigating-and-updating-a-model-in-program-code.md)