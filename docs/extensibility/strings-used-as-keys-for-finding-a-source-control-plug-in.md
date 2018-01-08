---
title: Cadeias de caracteres usadas como chaves para localizar um controle de origem plug-in | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control plug-ins, strings used for finding
ms.assetid: c1e31f76-42a1-4c3d-afb2-664044ef12fd
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1acc753d2a02c3be88687a4e42d71d23e988af48
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="strings-used-as-keys-for-finding-a-source-control-plug-in"></a>Cadeias de caracteres usadas como chaves para localizar um controle de origem plug-in
As cadeias de caracteres a seguir são as chaves para acessar o registro para localizar informações sobre o controle de origem plug-in.  
  
 `STR_SCC_PROVIDER_REG_LOCATION`, `STR_PROVIDERREGKEY`, `STR_SCCPROVIDERPATH`, e `STR_SCCPROVIDERNAME` são as chaves do registro ou valores usados para registrar uma DLL como um plug-in de controle de origem para o Visual Studio.  
  
 `SCC_PROJECTNAME_KEY`, `SCC_PROJECTAUX_KEY`, `SCC_KEY, SCC_FILE_SIGNATURE`, e `SCC_STATUS_FILE` são usados para descrever o formato da MSSCCPRJ. Arquivos SCC.  
  
## <a name="string-keys-and-values"></a>Chaves de cadeia de caracteres e valores  
  
|Chave|Valor|  
|---------|-----------|  
|`STR_SCC_PROVIDER_REG_LOCATION`|Software\SourceCodeControlProvider|  
|`STR_PROVIDERREGKEY`|ProviderRegKey|  
|`STR_SCCPROVIDERPATH`|SCCServerPath|  
|`STR_SCCPROVIDERNAME`|SCCServerName|  
|`STR_SCC_INI_SECTION`|Controle do código fonte|  
|`STR_SCC_INI_KEY`|SourceCodeControlProvider|  
|`SCC_PROJECTNAME_KEY`|SCC_Project_Name|  
|`SCC_PROJECTAUX_KEY`|SCC_Aux_Path|  
|`SCC_STATUS_FILE`|MSSCCPRJ. SCC|  
|`SCC_KEY`|SCC|  
|`SCC_FILE_SIGNATURE`|Um arquivo de controle do código fonte|  
|`SCC_NSE`|Extensão de Namespace|  
|`SCC_NSE_PREFIX`|Prefixo Protocal|  
|`SCC_NSE_DisableOpenSCC`|DisableOpenFromSourceControl|  
|`STR_SCCHELPCOLLECTION`|HelpCollection|  
|`STR_UI_LANGUAGE`|UILanguage|  
|`STR_SRCSAFE_ROOT_KEY`|Software\Microsoft\SourceSafe|  
  
## <a name="see-also"></a>Consulte também  
 [Plug-ins de controle de origem](../extensibility/source-control-plug-ins.md)   
 [Como: instalar um plug-in de controle de origem](../extensibility/internals/how-to-install-a-source-control-plug-in.md)   
 [Arquivo MSSCCPRJ.SCC](../extensibility/mssccprj-scc-file.md)