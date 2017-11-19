---
title: Propriedade (Int32Array) byteOffset | Microsoft Docs
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
ms.assetid: 0182f916-b500-432c-96b3-c038ec7f85bd
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e01bda547ab3ad1a2751092e663844f8171dd3d9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
# <a name="byteoffset-property-int32array"></a>Propriedade byteOffset (Int32Array)
Somente leitura. O deslocamento dessa matriz desde o início de seu ArrayBuffer, em bytes, fixado na ocasião da construção.  
  
## <a name="syntax"></a>Sintaxe  
  
```JavaScript  
var arrayOffset = int32Array.byteOffset;  
```  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como obter o deslocamento da matriz.  
  
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
            alert(intArr.byteOffset);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Requisitos  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]