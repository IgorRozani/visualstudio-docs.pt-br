---
title: "Método 1 (Boolean) toString | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c46b43c0-6946-407a-b0e0-49cba90e226a
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 17dd9503e4e09aafca3d153662bf7487538cda3d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
# <a name="tostring-method-boolean-1"></a>Método 1 (Boolean) toString
Retorna uma representação em cadeia de caracteres de um objeto.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
boolean.toString()  
```  
  
## <a name="parameters"></a>Parâmetros  
 `boolean`  
 Necessário. Um objeto para o qual obter uma representação de cadeia de caracteres.  
  
## <a name="return-value"></a>Valor de retorno  
 Se o valor booliano é `true`, retorna "true". Caso contrário, retorna "false".  
  
## <a name="remarks"></a>Comentários  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir ilustra o uso do **toString** método.  
  
```JavaScript  
var s = new Boolean(0);  
document.write(s.toString());  
  
// Output: false;  
  
```  
  
## <a name="requirements"></a>Requisitos  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]