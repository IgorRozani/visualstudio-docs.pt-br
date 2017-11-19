---
title: "Função Symbol.for (JavaScript) | Microsoft Docs"
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
ms.assetid: 27db15f3-9108-4892-8f89-e84031729cb6
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b7e47c00fbaa321d71a3eeba79e523eee719fb2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
# <a name="symbolfor-function-javascript"></a>Função Symbol.for (JavaScript)
Retorna o símbolo para uma chave especificada ou, se a chave não estiver presente, cria um novo objeto de símbolo com a nova chave.  
  
## <a name="syntax"></a>Sintaxe  
  
```vb  
Symbol.for(key);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `key`  
 Necessário. A chave para o símbolo, que também é usado como a descrição.  
  
## <a name="remarks"></a>Comentários  
 Este método pesquisa o símbolo no Registro global de símbolos. Se você serializar símbolos como cadeias de caracteres, use o Registro global de símbolos para certificar-se de que uma determinada cadeia de caracteres seja mapeada para o símbolo correto para todas as pesquisas.  
  
## <a name="example"></a>Exemplo  
  
```JavaScript  
var sym = Symbol.for("desc");  
  
console.log(sym.toString());  
  
// Two different object references.  
console.log(Symbol("symbol") === Symbol.for("symbol");)  
// Single object reference.   
console.log(Symbol.for("symbol") === Symbol.for("symbol");)  
  
// Output:  
// Symbol(desc);  
// false  
// true  
```  
  
## <a name="requirements"></a>Requisitos  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]