---
title: 'Idialinenumber:: Get_columnnumberend | Microsoft Docs'
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
- IDiaLineNumber::get_columnNumberEnd method
ms.assetid: 02fa56c1-87b6-405a-adee-3bb6bc62de2d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 48de7129ffb1f9966873db8bbf3c306c3a85d80a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49191699"
---
# <a name="idialinenumbergetcolumnnumberend"></a>IDiaLineNumber::get_columnNumberEnd
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Recupera o número da coluna baseado em um código-fonte em que a expressão ou instrução termina.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT get_columnNumberEnd (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pRetVal`  
 [out] Retorna o número da coluna em que a expressão ou instrução termina. Se o valor for zero, as informações de coluna final não estão presentes.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`. Retorna `S_FALSE` se não há suporte para essa propriedade. Caso contrário, retornará um código de erro.  
  
## <a name="remarks"></a>Comentários  
 O valor da coluna retornado por esse método é um byte de deslocamento para a linha para a posição após o último caractere da instrução na linha.  
  
## <a name="see-also"></a>Consulte também  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)



