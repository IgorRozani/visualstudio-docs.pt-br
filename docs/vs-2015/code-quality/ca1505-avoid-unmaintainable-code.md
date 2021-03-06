---
title: 'CA1505: Evitar código que | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d5c333299f323e03a01b121fb18799e9249bcc11
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49223282"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: evitar código que não possa ser mantido
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|NomeDoTipo|AvoidUnmantainableCode|
|CheckId|CA1505|
|Categoria|Microsoft.Maintainability|
|Alteração Significativa|Não são significativas|

## <a name="cause"></a>Causa
 Um tipo ou um método tem um baixo valor de índice de facilidade de manutenção.

## <a name="rule-description"></a>Descrição da Regra
 O índice de facilidade de manutenção é calculado usando as seguintes métricas: linhas de código, o volume de programa e a complexidade ciclomática. Volume do programa é uma medida da dificuldade de compreensão de um tipo ou método que se baseia no número de operadores e operandos no código. A complexidade ciclomática é uma medida da complexidade estrutural do tipo ou método. Você pode aprender mais sobre as métricas de código em [medindo complexidade e facilidade de manutenção do código gerenciado](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md).

 Um índice de facilidade de manutenção baixa indica que um tipo ou método é provavelmente difícil de manter e seria um bom candidato para refazer o design.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir essa violação, recriar o tipo ou método e tente dividi-lo em menores e mais concentrados tipos ou métodos.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Exclua esse aviso quando um tipo ou método ainda é considerado sustentável, apesar de seu tamanho grande ou quando o tipo ou método não pode ser dividido.

## <a name="see-also"></a>Consulte também
 [Avisos de facilidade de manutenção](../code-quality/maintainability-warnings.md) [medindo complexidade e facilidade de manutenção do código gerenciado](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)



