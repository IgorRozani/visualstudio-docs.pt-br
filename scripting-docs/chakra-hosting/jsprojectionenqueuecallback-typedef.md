---
title: Typedef JsProjectionEnqueueCallback | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bda4a3a80edac38ab2c3885c2256cdf9d03eb8c1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568306"
---
# <a name="jsprojectionenqueuecallback-typedef"></a>Typedef JsProjectionEnqueueCallback
O retorno de chamada de aplicativo que é chamado por JsRT quando uma API de projeção é concluída em um thread diferente do original.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `jsCallback`  
 O retorno de chamada a ser invocado no thread original.  
  
 `jsContext`  
 O contexto do aplicativo.  
  
 `callbackState`  
 O contexto de JsRT que deve ser passado para `jsCallback`.  
  
## <a name="remarks"></a>Comentários  
 Requer uma chamada para JsSetProjectionEnqueueCallback para receber retornos de chamada.  
  
 Essa API tem suporte apenas no modo de Borda.  
  
## <a name="requirements"></a>Requisitos  
 jsrt.h  
  
## <a name="see-also"></a>Consulte também  
 [Referência (Tempo de Execução do JavaScript)](../chakra-hosting/reference-javascript-runtime.md)