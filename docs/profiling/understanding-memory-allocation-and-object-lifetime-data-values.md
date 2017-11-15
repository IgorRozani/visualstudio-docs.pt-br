---
title: "Entendendo a alocação de memória e os valores de dados de tempo de vida do objeto| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET memory profiling method
- Profiling Tools, .NET memory method
ms.assetid: a22445b3-39a6-4919-8506-2b5b0ceaf77e
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d2df71ef2498e3e5cf1f1bfef1dd16867d3e8991
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="understanding-memory-allocation-and-object-lifetime-data-values"></a>Entendendo a alocação de memória e os valores de dados de vida útil de objetos
O método de criação de perfil para *alocação de memória .NET* das [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ferramentas de criação de perfil coleta informações sobre o tamanho e o número de objetos que foram criados em uma alocação ou destruídos em uma coleta de lixo e informações adicionais sobre a *pilha de chamadas* da função quando o evento ocorreu. Uma *pilha de chamadas* é uma estrutura dinâmica que armazena informações sobre as funções que estão em execução no processador.  
  
 **Requisitos**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 O criador de perfil de memória interrompe o processador do computador em cada alocação de um objeto do .NET Framework em um aplicativo de perfil. Quando os dados de tempo de vida do objeto também são coletados, o criador de perfil interrompe o processador após cada coleta de lixo do .NET Framework. Os dados são agregados para cada função de perfil e para cada tipo de objeto.  
  
## <a name="allocation-data"></a>Dados de alocação  
 Quando ocorre um evento .memory, as contagens totais e tamanhos dos objetos de memória alocados ou destruídos são incrementados.  
  
 Quando ocorre um evento de alocação de .memory, o criador de perfil incrementa as contagens de amostragem para cada função na pilha de chamadas. Quando os dados são coletados, apenas uma função na pilha de chamadas está atualmente executando o código em seu corpo de função. As outras funções na pilha são pais na hierarquia de chamadas de função que estão aguardando para que as funções que chamaram retornarem.  
  
-   Para o evento de alocação, o criador de perfil incrementa a contagem de exemplo *exclusiva* da função que está executando as instruções de exemplo. Como um exemplo exclusivo também é parte do total de exemplos (*inclusivo*) da função, a contagem inclusiva de amostras da função atualmente ativa também será incrementada.  
  
-   O criador de perfil incrementa a contagem inclusiva de exemplo de todas as outras funções na pilha de chamadas.  
  
## <a name="lifetime-data"></a>Dados de tempo de vida  
 O coletor de lixo do .NET Framework gerencia a alocação e a liberação de memória para seu aplicativo. Para otimizar o desempenho do coletor de lixo, o heap gerenciado é dividido em três gerações: 0, 1 e 2. O coletor de lixo do tempo de execução armazena novos objetos na geração 0. Os objetos que sobrevivem as coletas são promovidos e armazenados para as gerações 1 e 2.  
  
 O coletor de lixo recupera memória, desalocando uma geração inteira de objetos. Para objetos que o aplicativo com perfil criou, o tempo de vida do objeto exibe o número e o tamanho dos objetos e a geração quando eles são recuperados.