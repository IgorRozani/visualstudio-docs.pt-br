---
title: IDebugFunctionPosition2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugFunctionPosition2
helpviewer_keywords: IDebugFunctionPosition2 interface
ms.assetid: a835f65b-91b0-48ad-8485-04534c814b1b
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3ae7a0dd442d8a48d6c69ecfd51b2fc17a2eb2fe
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugfunctionposition2"></a>IDebugFunctionPosition2
Essa interface representa uma posição abstrata de uma função em um documento de origem.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
IDebugFunctionPosition2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Observações para implementadores  
 O mecanismo de depuração (DE) implementa essa interface para representar a posição de uma função dentro de um documento de origem.  
  
## <a name="notes-for-callers"></a>Observações para chamadores  
 Essa interface é fornecida como parte de um [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) union (especificamente, uma [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) estrutura) que por sua vez é parte do [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) estrutura, usada na criação de um ponto de interrupção pendente.  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem Vtable  
 A tabela a seguir mostra os métodos de `IDebugFunctionPosition2`.  
  
|Método|Descrição|  
|------------|-----------------|  
|[GetFunctionName](../../../extensibility/debugger/reference/idebugfunctionposition2-getfunctionname.md)|Obtém o nome da função que essa posição é relativo.|  
|[GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)|Obtém o deslocamento do início da função.|  
  
## <a name="remarks"></a>Comentários  
 A posição representada por esta interface é baseado em texto, especificamente, uma [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) estrutura.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Interfaces de núcleo](../../../extensibility/debugger/reference/core-interfaces.md)   
 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)