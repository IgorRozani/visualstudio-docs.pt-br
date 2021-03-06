---
title: Propriedades de elementos em diagramas de atividade UML | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.teamarch.activitydiagram.shapes.properties
helpviewer_keywords:
- UML, element properties
- activity diagrams, properties
ms.assetid: 9849d45e-65d5-46bd-a319-757e90b7c748
caps.latest.revision: 19
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: c9f2830f66ad7f79a49b096bb489b542124efe6e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269966"
---
# <a name="properties-of-elements-on-uml-activity-diagrams"></a>Propriedades de elementos em diagramas de atividade UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Em um diagrama de atividade UML, cada elemento no diagrama tem propriedades. Para ver as propriedades de um elemento, clique com botão direito do elemento no diagrama ou no **Gerenciador de modelos UML** e, em seguida, clique em **propriedades**. As propriedades aparecem na **propriedades** janela.  
  
> [!NOTE]
>  Este tópico é sobre as propriedades de elementos em diagramas de atividade UML. Para obter informações sobre como ler diagramas de atividade UML, consulte [diagramas de atividade UML: referência](../modeling/uml-activity-diagrams-reference.md). Para obter mais informações sobre como desenhar diagramas de atividade UML, consulte [diagramas de atividade UML: diretrizes](../modeling/uml-activity-diagrams-guidelines.md).  
  
## <a name="properties-of-elements"></a>Propriedades de elementos  
  
|Propriedade|Padrão|Elemento|Descrição|  
|--------------|-------------|-------------|-----------------|  
|**Nome**|Um nome padrão|Todos|Identifica o elemento.|  
|**Nome qualificado**|Pacote:: nome|Todos|Identifica exclusivamente o elemento. O nome qualificado do pacote que contém o prefixo.|  
|**Itens de trabalho**|0 associados|Todos|O número de itens de trabalho associado a este elemento. Para associar itens de trabalho, consulte [vincular elementos de modelo e itens de trabalho](../modeling/link-model-elements-and-work-items.md).|  
|**Descrição**|(nenhum)|Todos|Você pode fazer observações gerais sobre o elemento aqui.|  
|**Cor**|(padrão para o tipo)|Todos|A cor da forma.|  
|**Corpo**|(nenhum)|Ação|Especifica a ação em detalhes.|  
|**Linguagem**|(nenhum)|Ação|A linguagem da expressão no corpo.|  
|**Pós-condições locais**|(nenhum)|Ação de envio, aceitar, comportamento de chamada, chamada de operação|Restrições que devem ser atendidas quando a execução termina. A meta obtida pela ação.|  
|**Pré-condições locais**|(nenhum)|Ação de envio, aceitar, comportamento de chamada, chamada de operação|Restrições que devem ser atendidas antes do início da execução.|  
|**É síncrono**|verdadeiro|Chame o comportamento, chame a operação|-Se for true, a ação aguarda até que a atividade será finalizada.|  
|**Comportamento**|(nenhum)|Comportamento da chamada|-A atividade foi invocada.|  
|**operação**|(nenhum)|Operação de chamada|-A operação invocada.|  
|**É desempacotar**|False|Aceitar eventos|-Se for true, pode haver vários pinos de saída com tipo e dados são desempacotados neles. Se for false, todos os dados são exibidos em um pin.|  
|**Limite superior**|**\***|Nó de objeto, o parâmetro de atividade|**0** indica que os dados devem passar diretamente ao longo do fluxo.<br /><br /> **\*** indica que os dados podem ser armazenados no fluxo.|  
|**Seleção**|(nenhum)|Objeto nó, o parâmetro de atividade, o pino de entrada, o pino de saída, o fluxo do objeto|Invoca um processo que filtra os dados. Esse processo pode ser definido em outro diagrama.|  
|**Ordenação**|(nenhum)|Pino de entrada de nó, o parâmetro de atividade do objeto, pinos de saída|-Como vários tokens são armazenados.|  
|**É o controle**|False|Pino de entrada, pinos de saída|-Se for true, o fluxo nesse pin é um fluxo de controle. Se for false, ele é um fluxo de objeto.|  
|**Tipo**|(nenhum)|Nó de objeto do pino de entrada, pinos de saída, o parâmetro de atividade|– O tipo de objetos transmitidos.<br />-O tipo pode ser um tipo primitivo como inteiro ou um classificador definido em outro lugar no modelo. Se você inserir o nome de um tipo que não está definido, ele aparecerá na **tipos não especificados** seção do Gerenciador de modelos UML.|  
|**Multiplicidade**|1|Pino de entrada, pinos de saída|-Pode ser um único valor, ou um intervalo `[n..m]`.<br />-O limite inferior `n` – a ação não é possível iniciar (para um pino de entrada) ou parar (para um pino de saída) até que não haja `n` objetos aguardando o pin.<br />-Limite `m` – a ação não pode consumir ou produzir mais de `m` objetos em uma execução. * significa que não há nenhum limite.|  
|**Transformação**|(nenhum)|Fluxo de objeto|-Invoca um processo que transforma os dados. Esse processo pode ser definido em outro diagrama.|  
|**É Multicast**|False|Fluxo de objeto|-Indica que pode haver vários objetos de destinatário ou componentes.|  
|**É MultiReceive**|False|Fluxo de objeto|-Indica que pode haver vários objetos de destinatário ou componentes.|  
|**É a única execução**|False|Diagrama de atividade|-Se definido, o que há no máximo uma execução de neste diagrama, cada vez.|  
  
## <a name="see-also"></a>Consulte também  
 [Diagramas de atividade UML: referência](../modeling/uml-activity-diagrams-reference.md)   
 [Diagramas de atividade UML: diretrizes](../modeling/uml-activity-diagrams-guidelines.md)



