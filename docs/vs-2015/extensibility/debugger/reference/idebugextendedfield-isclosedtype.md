---
title: IDebugExtendedField::IsClosedType | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IsClosedType
- IDebugExtendedField::IsClosedType
ms.assetid: 9136fc57-74ff-4fe4-a6e2-b137cb9d5b08
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a22872c54694dadf22003cda62ed1c97dd9a3c69
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49174456"
---
# <a name="idebugextendedfieldisclosedtype"></a>IDebugExtendedField::IsClosedType
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Determina se o campo representa um tipo fechado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT IsClosedType(  
   void  
);  
```  
  
```csharp  
int IsClosedType();  
```  
  
## <a name="return-value"></a>Valor de retorno  
 Se o campo for um tipo fechado, retornará `S_OK`; caso contrário, retorna `S_FALSE`.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)

