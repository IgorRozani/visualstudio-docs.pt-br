---
title: Propriedade (Int32Array) byteLength | Microsoft Docs
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
ms.assetid: 9d09754d-d08b-434a-a9c4-46700fa49377
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9e8df3807fc1fd5cf5397094c6638cbc24b03df
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
# <a name="bytelength-property-int32array"></a>Propriedade byteLength (Int32Array)
Somente leitura. O comprimento dessa matriz desde o início de seu ArrayBuffer, em bytes, fixado na ocasião da construção.  
  
## <a name="syntax"></a>Sintaxe  
  
```JavaScript  
var arrayByteLength = int32Array.byteLength;  
```  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como obter o tamanho da matriz.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Int32Array(buffer.byteLength / 4);  
            alert(intArr.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Requisitos  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]