---
title: 'CA1724: Os nomes de tipo não devem corresponder a Namespaces | Microsoft Docs'
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
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 64999653e326cc99ca9b1880966406dde41ce52e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49246747"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: os nomes de tipo não devem corresponder a namespaces
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|NomeDoTipo|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|Categoria|Microsoft.Naming|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um nome de tipo corresponde a um [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] nomes de namespace em uma comparação que diferencia maiusculas de minúsculas.

## <a name="rule-description"></a>Descrição da Regra
 Os nomes de tipo não devem corresponder aos nomes de namespaces definidos na biblioteca de classes do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]. A violação dessa regra pode reduzir a usabilidade da biblioteca.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Selecione um nome de tipo que não coincide com o nome de um [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] namespace da biblioteca de classe.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Para novos desenvolvimentos, nenhum conhecidos ocorrem de cenários em que você deve suprimir um aviso nessa regra. Antes de você suprime o aviso, considere cuidadosamente como os usuários da sua biblioteca talvez estejam confusos pelas nome correspondente. Para o envio de bibliotecas, talvez você precise suprimir um aviso nessa regra.



