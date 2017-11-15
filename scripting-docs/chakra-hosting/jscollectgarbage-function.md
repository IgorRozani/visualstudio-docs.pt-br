---
title: "Função JsCollectGarbage | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsCollectGarbage
helpviewer_keywords: JsCollectGarbage function
ms.assetid: 995c79a5-6e18-45be-81ff-2a5d3348edb8
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b783e9716d9de1a618d8bb640ce0b507801612d2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
# <a name="jscollectgarbage-function"></a>Função JsCollectGarbage
Executa uma coleta de lixo completa.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
STDAPI_(JsErrorCode) JsCollectGarbage(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `runtime`  
 O tempo de execução em que a coleta de lixo será executada.  
  
## <a name="return-value"></a>Valor de retorno  
 O código `JsNoError` se a operação foi bem-sucedida, caso contrário, um código de falha.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** jsrt.h  
  
## <a name="see-also"></a>Consulte também  
 [Referência (Tempo de Execução do JavaScript)](../chakra-hosting/reference-javascript-runtime.md)