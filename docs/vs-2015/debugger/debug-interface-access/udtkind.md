---
title: UdtKind | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- UdtKind enumeration
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7576d0c04008da11a1795e041e03269d4d93f3c4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47464984"
---
# <a name="udtkind"></a>UdtKind
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [UdtKind](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/udtkind).  
  
Descreve a variedade de tipo definido pelo usuário (UDT).  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
enum UdtKind {   
   UdtStruct,  
   UdtClass,  
   UdtUnion,  
   UdtInterface  
};  
```  
  
## <a name="elements"></a>Elementos  
 UdtStruct  
 UDT é uma estrutura.  
  
 UdtClass  
 UDT é uma classe.  
  
 UdtUnion  
 UDT é uma união.  
  
 UdtInterface  
 UDT é uma interface.  
  
## <a name="remarks"></a>Comentários  
 Os valores nesta enumeração são retornados pelo [idiasymbol:: Get_udtkind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md) método.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: cvconst.h  
  
## <a name="see-also"></a>Consulte também  
 [Enumerações e estruturas](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)



