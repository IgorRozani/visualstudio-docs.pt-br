---
title: IDebugProgramNodeAttach2::OnAttach | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords:
- IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
caps.latest.revision: 4
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 424bcc9299103139de292f405d4f162b35347425
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49171724"
---
# <a name="idebugprogramnodeattach2onattach"></a>IDebugProgramNodeAttach2::OnAttach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Anexa ao programa associado ou adia o processo de anexação para o [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) método.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT OnAttach(  
   [in] REFGUID guidProgramId  
);  
```  
  
```csharp  
int OnAttach(  
   ref Guid guidProgramId  
};  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `guidProgramId`  
 [in] `GUID` para atribuir ao programa associado.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`. Retorna `S_FALSE` se o [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) método não deve ser chamado. Caso contrário, retornará um código de erro.  
  
## <a name="remarks"></a>Comentários  
 Esse método é chamado durante o processo de anexação, antes de [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) método é chamado. O `OnAttach` método pode executar o processo de anexação (nesse caso, esse método retorna `S_FALSE`) ou adiar o processo de anexação para o `IDebugEngine2::Attach` método (o `OnAttach` retorno do método `S_OK`). Em ambos os casos, o `OnAttach` método pode definir o `GUID` do programa que está sendo depurado a determinado `GUID`.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [Anexar](../../../extensibility/debugger/reference/idebugengine2-attach.md)

