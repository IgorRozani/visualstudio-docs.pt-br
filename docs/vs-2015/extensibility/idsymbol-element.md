---
title: Elemento IDSymbol | Microsoft Docs
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
- IDSymbol element (VSCT XML schema)
- VSCT XML schema elements, IDSymbol
ms.assetid: 760cfd20-3c06-422c-9103-98bfa1f387f8
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3b4876144093d5e937a194095af1b128dc3efabd
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49253039"
---
# <a name="idsymbol-element"></a>Elemento IDSymbol
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

O `IDSymbol` elemento contém a ID do par GUID:ID que representa um menu, um grupo ou um comando. O GUID é proveniente do pai `GuidSymbol` elemento. O `IDSymbol` elemento tem um `name` que fornece um nome amigável para a ID, que está contida no atributo de `value` atributo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
<IDSymbol name=ElementName value="0x0010" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|name|Necessário. Nome do símbolo de ID.|  
|Valor |Necessário. Valor numérico da ID do símbolo de ID.|  
  
### <a name="child-elements"></a>Elementos filho  
 nenhuma.  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[Elemento GuidSymbol](../extensibility/guidsymbol-element.md)|Contém o GUID do par GUID:ID que representa um menu, um grupo ou um comando. Agrupa elementos `IDSymbol`.|  
  
## <a name="remarks"></a>Comentários  
 Cada `IDSymbol` elemento em um determinado `GuidSymbol` elemento deve ter um único `value`. No entanto, `IDSymbol` elementos que têm valores idênticos podem existir em um pacote, desde que eles tenham pais diferentes.  
  
## <a name="see-also"></a>Consulte também  
 [Arquivos da tabela de comandos do Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

