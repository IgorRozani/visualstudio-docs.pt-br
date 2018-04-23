---
title: BPREQI_FIELDS90 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- BPREQI_FIELDS90 enumeration
ms.assetid: bf6f7efc-39f2-46a2-906d-c3647bf89995
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ef4363b210fff059a88f80bd7377d91971ef2bce
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="bpreqifields90"></a>BPREQI_FIELDS90
Enumera os valores válidos que especificam as informações a serem recuperados sobre uma solicitação de ponto de interrupção. Esta enumeração estende o [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) enumeração.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
enum enum_BPREQI_FIELDS90  
{  
   // VS 8.0 values  
   BPREQI90_BPLOCATION                = 0x0001,  
   BPREQI90_LANGUAGE                  = 0x0002,  
   BPREQI90_PROGRAM                   = 0x0004,  
   BPREQI90_PROGRAMNAME               = 0x0008,  
   BPREQI90_THREAD                    = 0x0010,  
   BPREQI90_THREADNAME                = 0x0020,  
   BPREQI90_PASSCOUNT                 = 0x0040,  
   BPREQI90_CONDITION                 = 0x0080,  
   BPREQI90_FLAGS                     = 0x0100,  
   BPREQI90_ALLOLDFIELDS              = 0x01ff,  
   BPREQI90_VENDOR                    = 0x0200,  
   BPREQI90_CONSTRAINT                = 0x0400,  
   BPREQI90_TRACEPOINT                = 0x0800,  
  
   // Values added in VS 9.0  
   BPREQI90_MACROTRACEPOINT           = 0x1000,  
  
   BPREQI90_ALLFIELDS                 = 0xffff  
};  
typedef DWORD BPREQI_FIELDS90;  
```  
  
```csharp  
public enum enum_BPREQI_FIELDS90  
{  
    // VS 8.0 values  
    BPREQI90_BPLOCATION                = 0x0001,  
    BPREQI90_LANGUAGE                  = 0x0002,  
    BPREQI90_PROGRAM                   = 0x0004,  
    BPREQI90_PROGRAMNAME               = 0x0008,  
    BPREQI90_THREAD                    = 0x0010,  
    BPREQI90_THREADNAME                = 0x0020,  
    BPREQI90_PASSCOUNT                 = 0x0040,  
    BPREQI90_CONDITION                 = 0x0080,  
    BPREQI90_FLAGS                     = 0x0100,  
    BPREQI90_ALLOLDFIELDS              = 0x01ff,  
    BPREQI90_VENDOR                    = 0x0200,  
    BPREQI90_CONSTRAINT                = 0x0400,  
    BPREQI90_TRACEPOINT                = 0x0800,  
  
    // Values added in VS 9.0  
    BPREQI90_MACROTRACEPOINT           = 0x1000,  
  
    BPREQI90_ALLFIELDS                 = 0xffff  
};  
```  
  
#### <a name="parameters"></a>Parâmetros  
 BPREQI90_BPLOCATION  
 Inicializar ou use o `bpLocation` campo (localização do ponto de interrupção) do [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) ou [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) estrutura.  
  
 BPREQI90_LANGUAGE  
 Inicializar ou use o `guidLanguage` campo o `BP_REQUEST_INFO` ou `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_PROGRAM  
 Inicializar ou use o `pProgram` campo o `BP_REQUEST_INFO` ou `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_PROGRAMNAME  
 Inicializar ou use o `bstrProgramName` campo o `BP_REQUEST_INFO` ou `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_THREAD  
 Inicializar ou use o `pThread` campo o `BP_REQUEST_INFO` ou `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_THREADNAME  
 Inicializar ou use o `bstrThreadName` campo o `BP_REQUEST_INFO` ou `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_PASSCOUNT  
 Inicializar ou use o `bpPassCount` campo o `BP_REQUEST_INFO` ou `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_CONDITION  
 Inicializar ou use o `bpCondition` campo (condição de ponto de interrupção) da `BP_REQUEST_INFO` ou `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_FLAGS  
 Inicializar ou use o `dwFlags` campo o `BP_REQUEST_INFO` ou `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_ALLOLDFIELDS  
 Inicializar ou use todos os campos para o do `BP_REQUEST_INFO` estrutura.  
  
 BPREQI90_VENDOR  
 Inicializar ou use o `guidVendor` campo `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_CONSTRAINT  
 Inicializar ou use o `bstrConstraint` campo `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_TRACEPOINT  
 Inicializar ou use o `bstrTracepoint` campo `BP_REQUEST_INFO2` estrutura.  
  
 BPREQI90_MACROTRACEPOINT  
 Inicializar ou use o `bstrMacroTracepoint` campo `BP_REQUEST_INFO2` estrutura. BPREQI_ALLFIELDS não inclui esse campo.  
  
 BPREQI90_ALLFIELDS  
 Especifica todos os campos para o `BP_REQUEST_INFO2` estrutura.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Enumerações](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)