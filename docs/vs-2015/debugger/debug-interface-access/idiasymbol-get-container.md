---
title: 'Idiasymbol:: Get_container | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
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
- IDiaSymbol::get_container method
ms.assetid: 24e832eb-80b3-484c-a41b-11477ec9de99
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b41a17d1eff1067aef278e3071c4464a2ffed3f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49237413"
---
# <a name="idiasymbolgetcontainer"></a>IDiaSymbol::get_container
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Essa função recupera um ponteiro para um símbolo que representa o recipiente/pai desse símbolo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT get_container(  
   IDiaSymbol **pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pRetVal`  
 [out] Retorna um ponteiro para um `IDiaSymbol` que contém informações sobre o contêiner desse símbolo.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará S_OK; Caso contrário, retornará S_FALSE ou um código de erro.  
  
> [!NOTE]
>  Um valor de retorno de S_FALSE significa que a propriedade não está disponível para o símbolo.  
  
## <a name="requirements"></a>Requisitos  
  
|Requisito|Descrição|  
|-----------------|-----------------|  
|Cabeçalho:|dia2.h|  
|Versão:|V DIA SDK 8.0|  
  
## <a name="see-also"></a>Consulte também  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



