---
title: Função JsSetPrototype | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 88e1e421-4ae5-4e3b-b377-19256cc80e9f
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f46a84921cc2e74cbfcf7bbd734e1d01282090c0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568736"
---
# <a name="jssetprototype-function"></a>Função JsSetPrototype
Define o protótipo de um objeto.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
STDAPI_(JsErrorCode) JsSetPrototype(  
   _In_ JsValueRef object,  
   _In_ JsValueRef prototypeObject  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `object`  
 O objeto cujo protótipo deve ser alterado.  
  
 `prototypeObject`  
 O novo protótipo do objeto.  
  
## <a name="return-value"></a>Valor de retorno  
 O código `JsNoError` se a operação foi bem-sucedida, caso contrário, um código de falha.  
  
## <a name="remarks"></a>Comentários  
 Exige um contexto de script ativo.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** jsrt.h  
  
## <a name="see-also"></a>Consulte também  
 [Referência (Tempo de Execução do JavaScript)](../chakra-hosting/reference-javascript-runtime.md)