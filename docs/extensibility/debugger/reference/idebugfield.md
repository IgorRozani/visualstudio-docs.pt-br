---
title: IDebugField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugField
helpviewer_keywords: IDebugField interface
ms.assetid: adecdd1c-b1b9-4027-92da-74cbe910636f
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 00d3113f0151b9a2ad32259b24cc45dcca8bbccf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfield"></a>IDebugField
Essa interface representa um campo, ou seja, uma descrição de um tipo ou símbolo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
IDebugField : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Observações para implementadores  
 Um provedor de símbolo implementa essa interface como a classe base para todos os campos.  
  
## <a name="notes-for-callers"></a>Observações para chamadores  
 Esta interface é a classe base para todos os campos. Com base no valor de retorno de [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md), essa interface pode retornar mais especializadas interfaces usando [QueryInterface](/cpp/atl/queryinterface). Além disso, várias interfaces de retorno `IDebugField` objetos de vários métodos.  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem Vtable  
 A tabela a seguir mostra os métodos de `IDebugField`.  
  
|Método|Descrição|  
|------------|-----------------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)|Obtém informações de exibição sobre o símbolo ou tipo.|  
|[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)|Obtém o tipo de campo.|  
|[GetType](../../../extensibility/debugger/reference/idebugfield-gettype.md)|Obtém o tipo de campo.|  
|[GetContainer](../../../extensibility/debugger/reference/idebugfield-getcontainer.md)|Obtém o contêiner do campo.|  
|[GetAddress](../../../extensibility/debugger/reference/idebugfield-getaddress.md)|Obtém o endereço do campo.|  
|[GetSize](../../../extensibility/debugger/reference/idebugfield-getsize.md)|Obtém o tamanho de um campo, em bytes.|  
|[GetExtendedInfo](../../../extensibility/debugger/reference/idebugfield-getextendedinfo.md)|Obtém informações estendidas sobre um campo.|  
|[Igual a](../../../extensibility/debugger/reference/idebugfield-equal.md)|Compara dois campos.|  
|[GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)|Obtém informações de tipo independente sobre o símbolo ou o tipo.|  
  
## <a name="remarks"></a>Comentários  
 Um tipo é equivalente a uma linguagem C `typedef`.  
  
 No seguinte exemplo de linguagem do C++, `weather` é um tipo de classe e `sunny` e `stormy` são símbolos:  
  
```cpp  
class weather;  
weather sunny;  
weather stormy;  
```  
  
 Se um campo representa um símbolo ou tipo pode ser determinado chamando [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) e examinando o [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) resultados. Se o `FIELD_KIND_TYPE` bit é definido, o campo é um tipo e se o `FIELD_KIND_SYMBOL` bit é definido, ele é um símbolo.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Interfaces de Provedor de Símbolos](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)