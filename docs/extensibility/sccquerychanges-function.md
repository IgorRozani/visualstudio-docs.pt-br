---
title: "Função SccQueryChanges | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccQueryChanges
helpviewer_keywords: SccQueryChanges function
ms.assetid: 4cd58eb3-6952-49b1-9620-8682e3eaa604
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 589013b996f9ed018e28292a27c6a760eef1dae7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="sccquerychanges-function"></a>Função SccQueryChanges
Essa função enumera uma lista de arquivos, fornecendo informações sobre as alterações de nome para cada arquivo por meio de uma função de retorno de chamada especificada.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
SCCRTN SccQueryChanges(  
   LPVOID           pContext,  
   LONG             nFiles,  
   LPCSTR*          lpFileNames,  
   QUERYCHANGESFUNC pfnCallback,  
   LPVOID           pvCallerData  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 pContext  
 [in] O ponteiro de contexto de plug-in de controle de origem.  
  
 nFiles  
 [in] Número de arquivos em `lpFileNames` matriz.  
  
 lpFileNames  
 [in] Matriz de nomes de arquivo para obter informações sobre.  
  
 pfnCallback  
 [in] Função de retorno de chamada a ser chamada para cada nome de arquivo na lista (consulte [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md) para obter detalhes).  
  
 pvCallerData  
 [in] Valor que será passado inalterados para a função de retorno de chamada.  
  
## <a name="return-value"></a>Valor de retorno  
 A implementação de plug-in de controle de origem dessa função deve retornar um dos seguintes valores:  
  
|Valor|Descrição|  
|-----------|-----------------|  
|SCC_OK|O processo de consulta foi concluído com êxito.|  
|SCC_E_PROJNOTOPEN|O projeto não foi aberto no controle de origem.|  
|SCC_E_ACCESSFAILURE|Houve um problema ao acessar o sistema de controle de origem, provavelmente devido a problemas de rede ou de contenção.|  
|SCC_E_NONSPECIFICERROR|Ocorreu um erro geral ou não especificado.|  
  
## <a name="remarks"></a>Comentários  
 As alterações que está sendo consultadas para são para o namespace: especificamente, renomear, adicionando e removendo um arquivo.  
  
## <a name="see-also"></a>Consulte também  
 [Funções de API de plug-in de controle de origem](../extensibility/source-control-plug-in-api-functions.md)   
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)   
 [Códigos de erro](../extensibility/error-codes.md)