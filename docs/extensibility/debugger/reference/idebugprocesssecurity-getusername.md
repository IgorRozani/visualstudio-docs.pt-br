---
title: IDebugProcessSecurity::GetUserName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: aa8da8828dbbc314ce976572d1f6bd9d5abf5721
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
Obtém o nome de usuário do fornecedor de porta.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetUserName(  
    BSTR *pbstrUserName  
);  
```  
  
```csharp  
int GetUserName (  
    string pbstrUserName  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pbstrUserName`  
 [out] Uma cadeia de caracteres que contém o nome de usuário.  
  
## <a name="return-value"></a>Valor de retorno  
 Se o método for bem-sucedido, ele retornará `S_OK`. Caso contrário, ele retorna um código de erro.  
  
## <a name="remarks"></a>Comentários  
 `GetUserName`Retorna o nome de usuário que é exibido no **nome de usuário** coluna o **anexar ao processo** caixa de diálogo. Para exibir o **anexar ao processo** caixa de diálogo, clique em **anexar ao processo** no **ferramentas** menu no [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ambiente de desenvolvimento integrado (IDE).  
  
## <a name="see-also"></a>Consulte também  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)