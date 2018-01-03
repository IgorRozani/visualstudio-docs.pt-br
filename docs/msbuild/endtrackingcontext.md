---
title: EndTrackingContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
apiname: EndTrackingContext
apilocation: filetracker.dll
apitype: COM
helpviewer_keywords: EndTrackingContext
ms.assetid: c2c5d794-8dc8-4594-8717-70dc79a0e75d
caps.latest.revision: "3"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 976b6af01b26d6fb8738d1d418b09fb04a61c5c6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="endtrackingcontext"></a>EndTrackingContext
Finaliza o contexto atual de acompanhamento.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT WINAPI EndTrackingContext();  
```  
  
## <a name="return-value"></a>Valor retornado  
 Um **HRESULT** com o conjunto de bits **SUCCEEDED** se o contexto de acompanhamento tiver sido finalizado.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** FileTracker.h  
  
## <a name="see-also"></a>Consulte também  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)