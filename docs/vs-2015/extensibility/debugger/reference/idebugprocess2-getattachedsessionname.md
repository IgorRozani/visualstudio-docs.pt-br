---
title: IDebugProcess2::GetAttachedSessionName | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1ba2ad04d96f8970ca43c4f1a136d2676ed70fad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47475719"
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [IDebugProcess2::GetAttachedSessionName](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess2-getattachedsessionname).  
  
Obtém o nome da sessão que está sendo depurado neste processo. Um IDE pode exibir essas informações para um usuário que estiver depurando um processo específico em um computador específico.  
  
> [!NOTE]
>  Esse método é preterido e sua implementação deve retornar sempre `E_NOTIMPL`.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetAttachedSessionName(  
   BSTR* pbstrSessionName  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pbstrSessionName`  
  
## <a name="return-value"></a>Valor de retorno  
 Esse método deve retornar sempre `E_NOTIMPL`.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

