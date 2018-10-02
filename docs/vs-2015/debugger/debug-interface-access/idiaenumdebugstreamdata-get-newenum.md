---
title: IDiaEnumDebugStreamData::get__NewEnum | Microsoft Docs
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
- IDiaEnumDebugStreamData::get__NewEnum method
ms.assetid: 023b3e31-0fc9-478d-88e8-af2ce762f322
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c2fc1bd97960b12edcab21421a74fd995aa6e1da
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47465568"
---
# <a name="idiaenumdebugstreamdatagetnewenum"></a>IDiaEnumDebugStreamData::get__NewEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [IDiaEnumDebugStreamData::get__NewEnum](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumdebugstreamdata-get-newenum).  
  
Recupera o <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> versão este enumerador.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 pRetVal  
 [out] Retorna o `IUnknown` interface que representa o <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> versão este enumerador.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="see-also"></a>Consulte também  
 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)



