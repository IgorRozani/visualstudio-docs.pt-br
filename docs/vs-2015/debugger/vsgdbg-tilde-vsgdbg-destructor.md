---
title: 'VsgDbg:: ~ VsgDbg (destruidor) | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a3b97fb-d344-4df7-b195-9347d1edfcf7
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c43fb5c46ce3c1f33cfbb79fd68f793381f84e3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49212050"
---
# <a name="vsgdbgvsgdbg-destructor"></a>VsgDbg::~VsgDbg (Destruidor)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Destrói uma instância da `VsgDbg` classe. Se informações de gráficos ativamente está sendo registradas, o arquivo de log de gráficos é finalizado e fechado, e os recursos que foram usados durante a captura ativamente informações gráficas são liberados.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
~VsgDbg();  
```  
  
## <a name="see-also"></a>Consulte também  
 [VsgDbg::VsgDbg (Construtor)](../debugger/vsgdbg-vsgdbg-constructor.md)



