---
title: IDebugThread2::GetName | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugThread2::GetName
helpviewer_keywords:
- IDebugThread2::GetName
ms.assetid: eec54b8f-4a0e-4919-b0f9-81d4bd1e0b6f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 98ef4ff5a2e1896bccaab82b32c1244da9f1ca2a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31120043"
---
# <a name="idebugthread2getname"></a>IDebugThread2::GetName
Obtém o nome de um thread.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetName (   
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetName (   
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pbstrName`  
 [out] Retorna o nome do thread.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retorna `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="remarks"></a>Comentários  
 O nome recuperado é sempre um nome que pode ser exibido, e esse nome descreve o thread. O nome do thread pode ser derivado de uma arquitetura de tempo de execução que oferece suporte a nomeadas threads, ou pode ser um nome derivado do mecanismo de depuração. Como alternativa, o nome do thread pode ser definido por uma chamada para o [SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md) método.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)