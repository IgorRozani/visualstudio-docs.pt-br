---
title: "DA0012: volume significativo de reflexão | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DAReflection
- vs.performance.12
- vs.performance.rules.DA0012
- vs.performance.DA0011
ms.assetid: c92a1d76-21fa-426e-8b1b-a3c08e9bcbca
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 203de647342affb9d81f0a57d0bcd44ac983f307
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="da0012-significant-amount-of-reflection"></a>DA0012: volume significativo de reflexão
|||  
|-|-|  
|ID de regra|DA0012|  
|Categoria|Uso do .NET Framework|  
|Métodos de criação de perfil|Amostragem|  
|Mensagem|Talvez você esteja usando a Reflexão de forma excessiva. Essa é uma operação cara.|  
|Tipo de regra|Aviso|  
  
## <a name="cause"></a>Causa  
 Chamadas aos métodos System.Reflection como InvokeMember e GetMember ou a métodos Type como MemberInvoke são uma proporção significativa dos dados de criação de perfil. Quando possível, considere a substituição desses métodos pela associação antecipada aos métodos de assemblies dependentes.  
  
## <a name="rule-description"></a>Descrição da Regra  
 A reflexão é um recurso flexível do .NET Framework que pode ser usado para realizar a associação tardia do aplicativo a um Assembly dependente em tempo de execução ou para criar e executar dinamicamente novos tipos durante o tempo de execução. No entanto, essas técnicas podem diminuir o desempenho se forem usadas com frequência ou chamadas em loops estreitos.  
  
 Para obter mais informações, consulte a seção [Reflection and Late Binding](http://go.microsoft.com/fwlink/?LinkId=177826) (Reflexão e associação tardia) de Chapter 5 — Improving Managed Code Performance (Capítulo 5 – Melhorando o desempenho de código gerenciado) no volume Improving .NET Application Performance and Scalability (Melhorando o desempenho e a escalabilidade de aplicativos .NET) na biblioteca Microsoft Patterns and Practices (Padrões e Práticas da Microsoft) no MSDN.  
  
## <a name="how-to-investigate-a-warning"></a>Como investigar um aviso  
 Clique duas vezes na mensagem da janela Lista de Erros para navegar para a [Exibição de Detalhes da Função](../profiling/function-details-view.md) dos dados de criação de perfil. Examine as funções de chamada do método System.Type ou System.Reflection para encontrar as seções do programa que fazem o uso mais frequente de APIs de Reflexão do .NET. Evite usar métodos que retornam metadados. Quando o desempenho do aplicativo for crítico, talvez seja necessário evitar o uso da associação tardia e a criação de tipos dinamicamente em tempo de execução.