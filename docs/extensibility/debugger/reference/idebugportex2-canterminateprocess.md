---
title: IDebugPortEx2::CanTerminateProcess | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortEx2::CanTerminateProcess
helpviewer_keywords:
- IDebugPortEx2::CanTerminateProcess
ms.assetid: 111f65d8-5a1a-42b3-9de3-dd9bb03a33fd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f44df279cd8ad4721a6b4559af1dc3defb94714a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugportex2canterminateprocess"></a>IDebugPortEx2::CanTerminateProcess
Determina se um processo pode ser encerrado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CanTerminateProcess(   
   IDebugProcess2* pPortProcess  
);  
```  
  
```csharp  
HRESULT CanTerminateProcess(   
   IDebugProcess2 pPortProcess  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pPortProcess`  
 [in] Um [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) objeto que representa o processo a ser finalizado.  
  
## <a name="return-value"></a>Valor de retorno  
 Retorna `S_OK` se o processo pode ser encerrado; caso contrário, retornará `S_FALSE`.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)