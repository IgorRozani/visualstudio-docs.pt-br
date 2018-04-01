---
title: IDebugObject::GetManagedDebugObject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
caps.latest.revision: 9
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c3b0720aa8757564d06a29de2c51e53b6bb12a1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
Cria uma cópia do objeto gerenciado no espaço de endereço do mecanismo de depuração.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetManagedDebugObject(   
   IDebugManagedObject** ppObject  
);  
```  
  
```csharp  
int GetManagedDebugObject(  
   out IDebugManagedObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `ppObject`  
 [out] Retorna um [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) objeto que representa o objeto gerenciado recém-criado.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará S_OK; Caso contrário, retorna um código de erro. Retornará E_FAIL se este [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) não representa uma instância da classe de valor gerenciado.  
  
## <a name="remarks"></a>Comentários  
 Isso [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objeto deve representar uma instância da classe de valor gerenciado, como um `System.Decimal` instância. Fazendo uma cópia local, a sobrecarga de chamada [avaliar](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) é eliminado.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)