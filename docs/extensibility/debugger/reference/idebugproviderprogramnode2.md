---
title: IDebugProviderProgramNode2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProviderProgramNode2
helpviewer_keywords:
- IDebugProviderProgramNode2
ms.assetid: f0bca1cc-afbe-44cf-b5aa-d078aa685d24
caps.latest.revision: 8
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8c083d9b054ecde18d1e1fff8ca5bb8cbb6be659
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugproviderprogramnode2"></a>IDebugProviderProgramNode2
Essa interface realiza marshaling das interfaces de programa nos limites do processo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
IDebugProviderProgramNode2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Observações para implementadores  
 O mecanismo de depuração (DE) implementa essa interface no mesmo objeto que implementa [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) para dar suporte a interfaces marshaling nos limites do processo.  
  
## <a name="notes-for-callers"></a>Observações para chamadores  
 Chamar [QueryInterface](/cpp/atl/queryinterface) em um `IDebugProgramNode2` interface para obter essa interface. Se essa interface não pode ser obtida, o DE não oferece suporte para marshaling de interfaces.  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem Vtable  
 Essa interface implementa o método a seguir:  
  
|Método|Descrição|  
|------------|-----------------|  
|[UnmarshalDebuggeeInterface](../../../extensibility/debugger/reference/idebugproviderprogramnode2-unmarshaldebuggeeinterface.md)|Obtém uma interface especificada nos limites do processo.|  
  
## <a name="remarks"></a>Comentários  
 Essa interface é implementada quando o DE é executado em um espaço de processo separado do programa que está sendo depurado: por exemplo, quando o DE está em execução no espaço de processo do Visual Studio, em vez de espaço de processo do programa que está sendo depurado.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Interfaces de núcleo](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)