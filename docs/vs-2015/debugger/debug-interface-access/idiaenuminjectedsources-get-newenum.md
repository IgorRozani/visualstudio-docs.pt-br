---
title: IDiaEnumInjectedSources::get__NewEnum | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::get__NewEnum method
ms.assetid: f56cdcdb-dc71-43c7-82fe-e2500986f5bc
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a7077a6ec2e00ae8feafd3307b3998491f786b3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47462533"
---
# <a name="idiaenuminjectedsourcesgetnewenum"></a>IDiaEnumInjectedSources::get__NewEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [IDiaEnumInjectedSources::get__NewEnum](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenuminjectedsources-get-newenum).  
  
Recupera o <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> versão este enumerador.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 pRetVal  
 [out, retval] Retorna o `IUnknown` interface que representa o <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> versão este enumerador.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="see-also"></a>Consulte também  
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)



