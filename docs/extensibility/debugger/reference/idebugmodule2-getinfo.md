---
title: IDebugModule2::GetInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugModule2::GetInfo
helpviewer_keywords:
- GetInfo method
- IDebugModule2::GetInfo method
ms.assetid: de337e66-294f-4ac9-b21e-71fac7418e36
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e9d88f78d9f3942eb4744168c874a37db26dd144
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmodule2getinfo"></a>IDebugModule2::GetInfo
Obtém informações sobre este módulo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetInfo(   
   MODULE_INFO_FIELDS dwFields,  
   MODULE_INFO*       pInfo  
);  
```  
  
```cpp  
int GetInfo(   
   enum_MODULE_INFO_FIELDS dwFields,  
   MODULE_INFO[]           pInfo  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `dwFields`  
 [in] Uma combinação de sinalizadores do [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) enumeração que especificam quais campos de `pInfo` devem ser preenchidos.  
  
 `pInfo`  
 [out no] Um [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) estrutura que é preenchida com uma descrição do módulo.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retorna `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="remarks"></a>Comentários  
 O [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) estrutura contém o nome do módulo que é exibido no **módulos** janela.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)