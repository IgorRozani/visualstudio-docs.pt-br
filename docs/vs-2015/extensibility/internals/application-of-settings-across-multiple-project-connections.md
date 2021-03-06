---
title: Aplicação de configurações entre várias conexões de projeto | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, application of settings
ms.assetid: 2116d3d0-c46c-4d0a-b482-08a178584f46
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 81d6a1f540314863e4e24b3b91c7f4112e0af8f0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49197607"
---
# <a name="application-of-settings-across-multiple-project-connections"></a>Aplicação de configurações em várias conexões de projeto
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Um plug-in de controle do código-fonte criado usando o código-fonte controle plug-in API 1.2, pode usar uma operação em lote para executar a mesma operação de controle do código-fonte entre vários projetos ou vários contextos de conexão. Lotes podem ser usados para eliminar redundantes, caixas de diálogo a experiência do usuário por projeto.  
  
 Se um usuário seleciona vários itens que pertencem a mais de uma conexão em um plug-in de controle do código-fonte criado usando o código-fonte controle plug-in API 1.1, (por exemplo, dois projetos para Web em máquinas diferentes de compartilhamento de arquivos) e verifica-os, o usuário vê a mesma caixa de diálogo repetidamente. Isso acontece mesmo se o usuário clica o **aplicar a todos** caixa na caixa de diálogo de seleção porque o IDE redefine seu estado para cada contexto de conexão.  
  
## <a name="new-capability-flag"></a>Novo sinalizador de recurso  
 `SccBeginBatch` Função conjuntos a `SCC_CAP_BATCH` sinalizador para indicar que uma operação em lote está em andamento  
  
## <a name="new-functions"></a>Novas funções  
 Novas funções a seguir dão suporte a operação em lote:  
  
-   [SccBeginBatch](../../extensibility/sccbeginbatch-function.md)  
  
-   [SccEndBatch](../../extensibility/sccendbatch-function.md)  
  
 O `SCCBeginBatch` função inicia um grupo de operações de controle do código-fonte. `SccEndBatch` Fecha o grupo. Os grupos não podem ser aninhados.  
  
## <a name="see-also"></a>Consulte também  
 [Novidades na Versão 1.2 da API do plug-in de controle de código-fonte](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)

