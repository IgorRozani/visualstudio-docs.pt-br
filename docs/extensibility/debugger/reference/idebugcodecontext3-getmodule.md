---
title: IDebugCodeContext3::GetModule | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugCodeContext3::GetModule
ms.assetid: 8e4317b8-8255-486c-a896-a68ed94f8aa1
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fe847347c942db71b1a341d39739ecbbfa7102b9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcodecontext3getmodule"></a>IDebugCodeContext3::GetModule
Recupera uma referência para a interface do módulo de depuração.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetModule(   
   IDebugModule2 **ppModule  
);  
```  
  
```csharp  
public int GetModule(   
   out IDebugModule2 ppModule  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `ppModule`  
 [out] Referência para a interface de depuração do módulo.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retorna `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como implementar esse método para um **CDebugCodeContext** objeto que expõe o [IDebugBeforeSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2.md) interface.  
  
```cpp  
HRESULT CDebugCodeContext::GetModule(IDebugModule2** ppModule)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pModule;  
  
    IfFalseGo( ppModule, E_INVALIDARG );  
    *ppModule = NULL;  
  
    IfFailGo( this->GetModule(&pModule) );  
    IfFailGo( pModule->QueryInterface(IID_IDebugModule2, (void**) ppModule) );  
  
Error:  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Consulte também  
 [IDebugCodeContext3](../../../extensibility/debugger/reference/idebugcodecontext3.md)