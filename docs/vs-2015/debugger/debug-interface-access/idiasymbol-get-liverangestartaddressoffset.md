---
title: IDiaSymbol::get_liveRangeStartAddressOffset | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
- IDiaSymbol::get_liveRangeStartAddressOffset
ms.assetid: f5b28914-0a14-4b22-8259-59d7f97ee610
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d0da08e8e9d79ee5d94b81225bd241f8a1071f27
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49249282"
---
# <a name="idiasymbolgetliverangestartaddressoffset"></a>IDiaSymbol::get_liveRangeStartAddressOffset
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Retorna a parte do deslocamento do endereço inicial do intervalo no qual o símbolo local é válido.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT get_liveRangeStartAddressOffset (   
   DWORD* offset  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `offset`  
 [out] Retorna a parte do deslocamento do intervalo de endereços inicial.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.  
  
> [!NOTE]
>  Um código de erro retornado significa que o símbolo não tem informações de intervalo em tempo real.  
  
## <a name="remarks"></a>Comentários  
 O endereço formado pela seção e deslocamento é o início do intervalo no qual o símbolo é válido.  
  
 Para obter a parte da seção do endereço, use [IDiaSymbol::get_liveRangeStartAddressSection](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddresssection.md).  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: Dia2.h  
  
 Biblioteca: diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>Consulte também  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



