---
title: Configuração de solução | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- solution configurations
ms.assetid: f22cfc75-3e31-4e0d-88a9-3ca99539203b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f7b2a453d4ea4e8b92b40ee126f9441e6f353606
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="solution-configuration"></a>Configuração de solução
Configurações da solução armazenam propriedades de nível de solução. Eles direcionam o comportamento do **iniciar** chave (F5) e **criar** comandos. Por padrão, esses comandos criar e iniciar a configuração de depuração. Os dois comandos são executados no contexto de uma configuração de solução. Isso significa que o usuário pode esperar F5 para iniciar e qualquer solução ativa é configurada por meio das configurações de compilação. O ambiente é projetado para otimizar para soluções em vez de projetos quando se trata de criação e execução.  
  
 A barra de ferramentas padrão do Visual Studio contém um botão de início e uma configuração de solução suspensa à direita do botão Iniciar. Essa lista permite aos usuários escolher a configuração a ser iniciado quando F5 é pressionado, criar suas próprias configurações de solução ou editar uma configuração existente.  
  
> [!NOTE]
>  Não há nenhuma interface de extensibilidade para criar ou editar as configurações de solução. Você deve usar `DTE.SolutionBuilder`. No entanto, há APIs de extensibilidade para gerenciar a compilação da solução. Para obter mais informações, consulte <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2>.  
  
 Aqui está como você pode implementar as configurações de solução com suporte pelo seu tipo de projeto:  
  
-   Projeto  
  
     Exibe os nomes dos projetos encontrados na solução atual.  
  
-   Configuração  
  
     Para fornecer a lista de configurações com suporte pelo seu tipo de projeto e exibidos nas páginas de propriedade, implementar <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>.  
  
     A coluna de configuração exibe o nome da configuração de projeto para compilar nesta configuração de solução e lista todas as configurações do projeto quando você clica no botão de seta. O ambiente chama o <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgNames%2A> método para preencher essa lista. Se o <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgProviderProperty%2A> método indica que o projeto dá suporte à edição de configuração, novo ou editar seleções também são exibidas sob o título de configuração. Cada uma dessas seleções iniciar caixas de diálogo que chamam métodos do `IVsCfgProvider2` interface para editar as configurações do projeto.  
  
     Se um projeto não dá suporte a configurações, a coluna de configuração exibe nenhum e está desabilitada.  
  
-   Plataforma  
  
     Exibe a plataforma cria para a configuração do projeto selecionado e lista todas as plataformas disponíveis para o projeto quando você clica no botão de seta. O ambiente chama o <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetPlatformNames%2A> método para preencher essa lista. Se o <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgProviderProperty%2A> método indica que o projeto dá suporte à edição de plataforma, novo ou editar seleções também são exibidas sob o título de plataforma. Cada uma dessas seleções iniciar caixas de diálogo que chamam `IVsCfgProvider2` métodos para editar as plataformas disponíveis do projeto.  
  
     Se um projeto não dá suporte a plataformas, a coluna de plataforma para o projeto exibe nenhum e está desabilitada.  
  
-   Build  
  
     Especifica se o projeto é compilado, a configuração da solução atual. Projetos não selecionados não são criados quando os comandos de compilação de nível de solução são invocados apesar de todas as dependências de projeto que eles contêm. Projetos selecionados não possam ser criadas ainda estão incluídos na depuração, execução, empacotamento e implantação da solução.  
  
-   Implantar  
  
     Especifica se o projeto será implantado quando os comandos Start ou implantar são usados com a configuração de compilação da solução selecionada. A caixa de seleção para esse campo estará disponível se o projeto oferece suporte à implantação implementando o <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> interface no seu <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> objeto.  
  
 Depois que uma nova configuração de solução é adicionada, o usuário pode selecioná-lo na caixa de lista suspensa de configuração da solução na barra de ferramentas para criar e/ou iniciar essa configuração.  
  
## <a name="see-also"></a>Consulte também  
 [Gerenciar opções de configuração](../../extensibility/internals/managing-configuration-options.md)   
 [Configuração de projeto para criação](../../extensibility/internals/project-configuration-for-building.md)   
 [Objeto de configuração do projeto](../../extensibility/internals/project-configuration-object.md)