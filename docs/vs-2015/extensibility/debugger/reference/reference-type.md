---
title: REFERENCE_TYPE | Microsoft Docs
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
- REFERENCE_TYPE
helpviewer_keywords:
- REFERENCE_TYPE enumeration
ms.assetid: b1ffba10-eb9d-48ba-bf48-6d8b71d6f270
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1b6ed3d68284efd5dbc297bbc72a964f4f7292ab
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49177340"
---
# <a name="referencetype"></a>REFERENCE_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Especifica o tipo de referência.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
enum enum_REFERENCE_TYPE {   
   REF_TYPE_WEAK   = 0x0001,  
   REF_TYPE_STRONG = 0x0002  
};  
typedef DWORD REFERENCE_TYPE;  
```  
  
```csharp  
public enum enum_REFERENCE_TYPE {   
   REF_TYPE_WEAK   = 0x0001,  
   REF_TYPE_STRONG = 0x0002  
};  
```  
  
## <a name="members"></a>Membros  
 REF_TYPE_WEAK  
 Especifica uma referência fraca. Não pode ser combinado com `REF_TYPE_STRONG`.  
  
 REF_TYPE_STRONG  
 Especifica uma referência forte. Não pode ser combinado com `REF_TYPE_WEAK`.  
  
## <a name="remarks"></a>Comentários  
 Usado como o `dwRefType` membro a [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) estrutura.  
  
 Passado como um parâmetro para o [SetReferenceType](../../../extensibility/debugger/reference/idebugreference2-setreferencetype.md) método.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Enumerações](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [SetReferenceType](../../../extensibility/debugger/reference/idebugreference2-setreferencetype.md)

