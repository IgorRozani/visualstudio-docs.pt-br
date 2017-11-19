---
title: "Função SccQueryInfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccQueryInfo
helpviewer_keywords: SccQueryInfo function
ms.assetid: 3973d336-a9b7-41a2-a4e6-bb8184a96aaf
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e5c2e974fe2cd0f6d95b97bba0ba2ffa22c1095e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="sccqueryinfo-function"></a>Função SccQueryInfo
Esta função obtém as informações de status para um conjunto de arquivos selecionados no controle de origem.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
SCCRTN SccQueryInfo(  
   LPVOID  pvContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 pvContext  
 [in] A estrutura de contexto de plug-in de controle de origem.  
  
 nFiles  
 [in] Número de arquivos especificados no `lpFileNames` matriz e o comprimento do `lpStatus` matriz.  
  
 lpFileNames  
 [in] Uma matriz de nomes de arquivos a ser consultado.  
  
 lpStatus  
 [out no] Uma matriz na qual o plug-in de controle de origem retorna os sinalizadores de status para cada arquivo. Para obter mais informações, consulte [código de Status do arquivo](../extensibility/file-status-code-enumerator.md).  
  
## <a name="return-value"></a>Valor de retorno  
 A implementação de plug-in de controle de origem dessa função deve retornar um dos seguintes valores:  
  
|Valor|Descrição|  
|-----------|-----------------|  
|SCC_OK|Consulta foi bem-sucedida.|  
|SCC_E_ACCESSFAILURE|Houve um problema ao acessar o sistema de controle de origem, provavelmente causado por problemas de rede ou de contenção. Recomenda-se uma nova tentativa.|  
|SCC_E_PROJNOTOPEN|O projeto não está aberto no controle de origem.|  
|SCC_E_NONSPECIFICERROR|Falha não específica.|  
  
## <a name="remarks"></a>Comentários  
 Se `lpFileName` é uma cadeia de caracteres vazia, atualmente, não há nenhuma informação de status para atualizar. Caso contrário, é o nome de caminho completo do arquivo para o qual as informações de status podem ter sido alterado.  
  
 A matriz de retorno pode ser um bitmask de `SCC_STATUS_xxxx` bits. Para obter mais informações, consulte [código de Status do arquivo](../extensibility/file-status-code-enumerator.md). Um sistema de controle do código-fonte não pode oferecer suporte a todos os tipos de bit. Por exemplo, se `SCC_STATUS_OUTOFDATE` não é oferecido, o bit não está definido.  
  
 Ao usar essa função para check-out de arquivos, observe o seguinte `MSSCCI` requisitos de status:  
  
-   `SCC_STATUS_OUTBYUSER`é definido quando o usuário atual fez check-out do arquivo.  
  
-   `SCC_STATUS_CHECKEDOUT`não é possível definir a menos que `SCC_STATUS_OUTBYUSER` está definido.  
  
-   `SCC_STATUS_CHECKEDOUT`só é definido quando o arquivo é extraído no diretório de trabalho designado.  
  
-   Se o arquivo está com check-out pelo usuário atual em um diretório que não seja o diretório de trabalho, `SCC_STATUS_OUTBYUSER` está definida, mas `SCC_STATUS_CHECKEDOUT` não é.  
  
## <a name="see-also"></a>Consulte também  
 [Funções de API de plug-in de controle de origem](../extensibility/source-control-plug-in-api-functions.md)   
 [Código de Status do arquivo](../extensibility/file-status-code-enumerator.md)