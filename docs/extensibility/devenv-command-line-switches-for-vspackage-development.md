---
title: "Opções de linha de comando devenv para desenvolvimento de VSPackage | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /setup command line switch
- /resetskippkgs command line switch
- /noVSIP command line switch
- /rootsuffix command line switch
- command-line switches
- registry, Visual Studio SDK
- command line, switches
- Visual Studio SDK, command-line switches
ms.assetid: d65d2c04-dd84-42b0-b956-555b11f5a645
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 18c531bb849793de184f3797067dceff4bd10199
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="devenv-command-line-switches-for-vspackage-development"></a>Opções de linha de comando devenv para desenvolvimento de VSPackage
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]permite aos desenvolvedores automatizar tarefas de linha de comando ao executar devenv.exe, o arquivo que inicia o ambiente de desenvolvimento integrado (IDE) do Visual Studio.  
  
 As tarefas incluem:  
  
-   Implantando aplicativos em configurações predefinidas de fora do IDE.  
  
-   Automaticamente Construindo projetos usando a predefinição de configurações de compilação ou configurações de depuração.  
  
-   Carregando o IDE em configurações específicas, tudo a partir de fora do IDE. Além disso, você pode personalizar o IDE após a inicialização.  
  
## <a name="guidelines-for-switches"></a>Diretrizes para Switches  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]documentação descreve as opções de linha de comando do devenv de nível de usuário. Para obter mais informações, consulte [opções de linha de comando Devenv](../ide/reference/devenv-command-line-switches.md). Devenv também oferece suporte a opções de linha de comando adicionais que são úteis com VSPackage desenvolvimento, implantação e depuração.  
  
|Opção de linha de comando|Descrição|  
|--------------------------|-----------------|  
|/SafeMode|Inicia [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] no modo de segurança carregando apenas o padrão IDE e serviços. A opção /safemode impede que todos os VSPackages de terceiros carregamento quando [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] inicia, garantindo, assim, a execução estável.<br /><br /> Esta opção não aceita nenhum argumento.|  
|/resetskippkgs|Limpa todos os ignorar opções de carregamento que foram adicionadas por usuários que desejam evitar o carregamento de VSPackages problemáticos, em seguida, inicia [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. A presença de uma marca SkipLoading desabilita o carregamento de um VSPackage. Limpando a marca habilita novamente o carregamento do VSPackage.<br /><br /> Esta opção não aceita nenhum argumento.|  
|/rootsuffix|Inicia [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] usando um local alternativo. O comando a seguir é executado pelo atalho criado pelo [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] instalador:<br /><br /> devenv /RootSuffix exp<br /><br /> Nesse caso, exp identifica um local com um sufixo específico, por exemplo 10.0Exp em vez de 10.0. A instância experimental permite que você depure um VSPackage separadamente da instância do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] que você está usando para escrever código.<br /><br /> Essa opção pode ser qualquer cadeia de caracteres que identifica um local que você criou usando VSRegEx.exe. Para obter mais informações, consulte [a instância Experimental](../extensibility/the-experimental-instance.md).|  
|/Splash|Mostra o [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tela inicial como de costume e depois mostra uma caixa de mensagem antes de mostrar o IDE principal. A caixa de mensagem permite que você estude a tela inicial, para verificar se há um ícone de produto VSPackage, por exemplo.<br /><br /> Esta opção não aceita nenhum argumento.|  
  
## <a name="see-also"></a>Consulte também  
 [Adicionar opções de linha de comando](../extensibility/adding-command-line-switches.md)   
 [Opções de linha de comando devenv](../ide/reference/devenv-command-line-switches.md)