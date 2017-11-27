---
title: ': Get_registerid | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_registerId method
ms.assetid: f881e793-eb9e-48dc-a847-dd61d77174fc
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5fe8b131e715f5fa55d2d2f99cb8c4714996290
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetregisterid"></a>IDiaSymbol::get_registerId
Recupera o designador de registro do local quando o [enumeração LocationType](../../debugger/debug-interface-access/locationtype.md) é definido como `LocIsEnregistered`.  
  
## <a name="syntax"></a>Sintaxe  
  
```C++  
HRESULT get_registerId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pRetVal`  
 [out] Retorna o designador de registro do local.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retorna `S_OK`; caso contrário, retorna `S_FALSE` ou um código de erro.  
  
> [!NOTE]
>  Um valor de retorno `S_FALSE` significa que a propriedade não está disponível para o símbolo.  
  
## <a name="remarks"></a>Comentários  
 Se o símbolo é em relação a um registro, ou seja, se o símbolo [enumeração LocationType](../../debugger/debug-interface-access/locationtype.md) é definido como `LocIsRegRel`, use o `get_registerId` método seguido por uma chamada para o [: Get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md) método para obter o deslocamento do registro onde se encontra o símbolo.  
  
## <a name="see-also"></a>Consulte também  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Enumeração LocationType](../../debugger/debug-interface-access/locationtype.md)