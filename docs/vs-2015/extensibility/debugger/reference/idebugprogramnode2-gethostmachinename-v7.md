---
title: IDebugProgramNode2::GetHostMachineName_V7 | Microsoft Docs
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
- IDebugProgramNode2::GetHostMachineName
helpviewer_keywords:
- IDebugProgramNode2::GetHostMachineName_V7
- IDebugProgramNode2::GetHostMachineNameIDebugProgramNode2::GetHostMachineName
ms.assetid: a992f2c9-f68b-4146-8cc2-027753bf7ce6
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3a84963032e23bec740f639b5aef27277a24095d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49194632"
---
# <a name="idebugprogramnode2gethostmachinenamev7"></a>IDebugProgramNode2::GetHostMachineName_V7
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

PRETERIDO. NÃO USE.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT GetHostMachineName_V7 (   
   BSTR* pbstrHostMachineName  
);  
```  
  
```csharp  
int GetHostMachineName_V7 (   
   out string pbstrHostMachineName  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pbstrHostMachineName`  
 [out] Retorna o nome do computador no qual o programa está em execução.  
  
## <a name="return-value"></a>Valor de retorno  
 Uma implementação deve retornar sempre `E_NOTIMPL`.  
  
## <a name="remarks"></a>Comentários  
  
> [!WARNING]
>  Desde [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], esse método não é mais usado e deve retornar sempre `E_NOTIMPL`.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)

