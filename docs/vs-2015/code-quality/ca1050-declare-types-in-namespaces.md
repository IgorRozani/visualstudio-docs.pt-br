---
title: 'CA1050: Declarar tipos em namespaces | Microsoft Docs'
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
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5b6f8acdae5e3b95218cd5e22446b8bacfe5a92f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49277258"
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050: declarar tipos em namespaces
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|NomeDoTipo|DeclareTypesInNamespaces|
|CheckId|CA1050|
|Categoria|Microsoft.Design|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um tipo público ou protegido é definido fora do escopo de um namespace nomeado.

## <a name="rule-description"></a>Descrição da Regra
 Tipos são declarados em namespaces para evitar colisões de nome e como uma forma de organizar tipos relacionados em uma hierarquia de objetos. Tipos que estão fora de qualquer namespace nomeado estão em um namespace global que não pode ser referenciado no código.

## <a name="how-to-fix-violations"></a>Como Corrigir Violações
 Para corrigir uma violação dessa regra, coloque o tipo em um namespace.

## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos
 Embora você nunca precisará suprimir um aviso nessa regra, é seguro fazer isso quando o assembly nunca será usado em conjunto com outros assemblies.

## <a name="example"></a>Exemplo
 O exemplo a seguir mostra uma biblioteca que tenha um tipo declarado incorretamente fora de um namespace e um tipo que tem o mesmo nome declarado em um namespace.

 [!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TypesLiveInNamespaces/cs/FxCop.Design.TypesLiveInNamespaces.cs#1)]
 [!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.TypesLiveInNamespaces/vb/FxCop.Design.TypesLiveInNamespaces.vb#1)]

## <a name="example"></a>Exemplo
 O aplicativo a seguir usa a biblioteca que foi definida anteriormente. Observe que o tipo que é declarado fora de um namespace é criado quando o nome `Test` não são qualificados por um namespace. Observe também que, para acessar o `Test` digitar `Goodspace`, o nome do namespace é necessário.

 [!code-csharp[FxCop.Design.TestTypesLive#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestTypesLive/cs/FxCop.Design.TestTypesLive.cs#1)]
 [!code-vb[FxCop.Design.TestTypesLive#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.TestTypesLive/vb/FxCop.Design.TestTypesLive.vb#1)]



