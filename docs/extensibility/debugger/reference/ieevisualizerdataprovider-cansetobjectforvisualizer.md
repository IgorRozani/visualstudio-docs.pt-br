---
title: IEEVisualizerDataProvider::CanSetObjectForVisualizer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IEEVisualizerDataProvider::CanSetObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::CanSetObjectForVisualizer method
ms.assetid: 70fd3c6f-2f82-43a3-993b-c1dc8aa080bf
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 424cdb45f91c59a3a72474fc6c7a0e41a4dc9e17
ms.contentlocale: pt-br
ms.lasthandoff: 09/06/2017

---
# <a name="ieevisualizerdataprovidercansetobjectforvisualizer"></a>IEEVisualizerDataProvider::CanSetObjectForVisualizer
Este método determina se o visualizador pode ter o objeto de dados representa atualizado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CanSetObjectForVisualizer(  
   BOOL* b  
);  
```  
  
```csharp  
int CanSetObjectForVisualizer(  
   out int b  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `b`  
 [out] Diferente de zero (`TRUE`) se o objeto sobre o visualizador pode ser atualizado, zero (`FALSE`) se ele não é possível.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retorna `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="remarks"></a>Comentários  
 Um objeto pode não ser mutável se ele é associado à memória somente leitura, por exemplo.  
  
## <a name="see-also"></a>Consulte também  
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)
