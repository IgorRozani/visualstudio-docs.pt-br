---
title: ALM (Gerenciamento do Ciclo de Vida do Aplicativo) com aplicativos Xamarin | Microsoft Docs
ms.date: 08/21/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: ff978cc2-5a25-46d6-921b-e51adaa65992
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: e4dea73bc3d3c1e7db77544b24be1525fca0a202
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44282348"
---
# <a name="devops-with-xamarin-apps"></a>DevOps com aplicativos Xamarin

O Xamarin permite criar aplicativos móveis de plataforma cruzada direcionados para Android, iOS e Windows usando C#, .NET e Visual Studio. O Xamarin permite que uma grande parte do código seja compartilhada entre plataformas, com apenas um pequeno percentual precisando ser específico da plataforma. Para obter mais informações sobre o Xamarin em si, consulte [Visual Studio e Xamarin](../cross-platform/visual-studio-and-xamarin.md).

Desenvolver aplicativos para plataformas modernas envolve muito mais atividades do que apenas escrever código. Essas atividades, conhecidas como DevOps (desenvolvimento + operações), abrangem o ciclo de vida completo do aplicativo e incluem trabalhos de planejamento e acompanhando, elaboração e implementação de código, gerenciamento de um repositório de código-fonte, execução de builds, gerenciamento de integrações e implantações contínuas, testes (incluindo testes de unidade e testes de IU), execução de várias formas de diagnóstico em ambientes de desenvolvimento e produção e monitoramento de desempenho do aplicativo e dos comportamentos do usuário em tempo real por meio de telemetria e análise.

O Visual Studio, com o Azure DevOps Services e o Team Foundation Server, oferece uma variedade de funcionalidades de DevOps. Muitos deles são totalmente aplicáveis a projetos de plataforma cruzada. Isso vale principalmente para os aplicativos Xamarin, porque eles são criados com C# e .NET, que são usados para a criação de algumas ferramentas de DevOps. Outras ferramentas exigem uma integração forte com os ambientes de build e de tempo de execução. Uma vez que os aplicativos Xamarin são executados em plataformas não Windows e usam a implementação Mono do .NET, o Xamarin fornece ferramentas especializadas para determinadas necessidades.

As tabelas a seguir identificam quais recursos de DevOps no Visual Studio devem funcionar bem com um projeto do Xamarin e quais têm limitações. Consulte a documentação vinculada para obter detalhes sobre os recursos em si.

## <a name="agile-tools"></a>Ferramentas agile

Link de referência: **[About Agile tools and Agile project management](/azure/devops/boards/backlogs/overview?view=vsts)** (Sobre as ferramentas Agile e o gerenciamento de projetos Agile)

Comentário Geral: todos os recursos de planejamento e acompanhamento são independentes do tipo de projeto e de linguagens de codificação.

|Recurso|Tem suporte com o Xamarin|Comentários Adicionais|
|-------------|----------------------------|-------------------------|
|Gerenciar listas de pendências e sprints|Sim||
|Acompanhamento de trabalho|Sim||
|Colaboração da sala da equipe|Sim||
|Quadros kanban|Sim||
|Relatar e visualizar o progresso|Sim||

## <a name="modeling"></a>Modelagem

Link de referência: **[Analisar e modelar a arquitetura](../modeling/analyze-and-model-your-architecture.md)**

Recursos de design são independentes da linguagem de codificação ou funcionam com linguagens .NET como C#. Consulte [Funções de arquitetura e diagramas de modelagem no desenvolvimento de software](../modeling/scenario-change-your-design-using-visualization-and-modeling.md#ModelingDiagramsTools) para aspectos relacionados a código.

|Recurso|Tem suporte com o Xamarin|Comentários Adicionais|
|-------------|----------------------------|-------------------------|
|Diagramas de sequência|Sim||
|Grafos de dependência|Sim||
|Hierarquia de chamadas|Sim||
|Designer de Classe|Sim||
|Gerenciador de arquitetura|Sim||
|Diagramas UML (caso de uso, atividade, classe, componente, sequência e DSL)|Sim||
|Diagramas de camada|Sim||
|Validação da camada|Sim||

## <a name="code"></a>Código

|Recurso|Tem suporte com o Xamarin|Comentários Adicionais|
|-------------|----------------------------|-------------------------|
|[Usar o TFVC (Controle de Versão do Team Foundation)](/azure/devops/repos/tfvc/overview?view=vsts) ou o Azure Repos|Sim||
|[Introdução ao GIT no Azure Repos](/azure/devops/repos/git/gitquickstart?view=vsts&tabs=visual-studio)|Sim||
|[Melhorar a qualidade do código](../test/improve-code-quality.md)|Sim||
|[Localizar alterações de código e outros históricos](../ide/find-code-changes-and-other-history-with-codelens.md)|Sim|Exceto entre os limites específicos da plataforma em que a implementação não é resolvida até o tempo de execução.|
|[Usar mapas de códigos para depurar aplicativos](../modeling/use-code-maps-to-debug-your-applications.md)|Sim||

## <a name="build"></a>Build

Link de referência: **[Azure Pipelines](/azure/devops/pipelines/index?view=vsts)**

|Recurso|Tem suporte com o Xamarin|Comentários Adicionais|
|-------------|----------------------------|-------------------------|
|Servidor TFS local|Sim|Computadores de build devem ter Xamarin instalado e podem ser vinculados a um computador OSX para compilar para iOS. Confira [Usar TFVC](/azure/devops/repos/tfvc/overview?view=vsts)|
|Servidor de build local vinculado ao Azure Pipelines|Sim|Consulte [Build and release agents](/azure/devops/pipelines/agents/agents?view=vsts) (Agentes de build e de versão) para obter instruções.|
|Serviço de controlador hospedado do Azure Pipelines|Sim|Consulte [Compilar seu aplicativo Xamarin](/azure/devops/pipelines/languages/xamarin?view=vsts&tabs=vsts).|
|Compilar definições com pré e pós-scripts|Sim||
|Integração contínua incluindo check-ins restritos|Sim|Check-ins restritos somente para TFVC, uma vez que Git funciona em um modelo de solicitação pull, em vez de check-ins.|

## <a name="test"></a>Teste

|Recurso|Tem suporte com o Xamarin|Comentários Adicionais|
|-------------|----------------------------|-------------------------|
|Planejando testes, criando casos de teste e organizando conjuntos de testes|Sim||
|Teste manual|Sim||
|Gerenciador de Teste (testes de gravação e reprodução)|Sim|Somente dispositivos Windows e emuladores Android do Visual Studio. Gravação para todos os dispositivos é possível com o [Xamarin Test Recorder](/appcenter/test-cloud/uitest/).|
|Cobertura de código|N/D||
|[Efetuar teste de unidade em seu código](../test/unit-test-your-code.md)|Sim|Para os destinos Android e Windows, as ferramentas internas do MSTest podem ser usadas. Para executar testes de unidade em Windows, Android e iOS, o Xamarin recomenda NUnit. Confira [Usar o TFVC](/azure/devops/repos/tfvc/overview?view=vsts).|
|[Usar a automação de interface do usuário para testar seu código](../test/use-ui-automation-to-test-your-code.md)|Somente Windows|O gravador de teste da interface do usuário do Visual Studio é somente Windows. Para todas as plataformas, confira [Xamarin.UITest](/appcenter/test-cloud/uitest/).|

## <a name="improve-code-quality"></a>Melhorar a qualidade do código

Link de referência: **[Melhorar a qualidade do código](../test/improve-code-quality.md)**

|Recurso|Tem suporte com o Xamarin|Comentários Adicionais|
|-------------|----------------------------|-------------------------|
|[Analisar a qualidade do código gerenciado](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)|Sim||
|[Localizar código duplicado usando detecção de clone de código](https://msdn.microsoft.com/library/hh205279.aspx)|Sim||
|[Medir complexidade e facilidade de manutenção do código gerenciado](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|Sim||
|[Gerenciador de Desempenho](../profiling/performance-explorer.md)|Não|Use o [Xamarin Profiler](/xamarin/cross-platform/deploy-test/) por meio do Xamarin Studio em vez disso. Observe que o Xamarin Profiler está atualmente em visualização e ainda não funciona para destinos do Windows.|
|[Analisar problemas de memória do .NET Framework](https://msdn.microsoft.com/library/dn342825.aspx)|Não|Ferramentas do Visual Studio não têm ganchos na estrutura Mono para a criação de perfil.|

## <a name="release-management"></a>Gerenciamento de liberações

Link de referência: **[Build e versão no Azure Pipelines e no TFS](/azure/devops/pipelines/overview?view=vsts)**

|Recurso|Tem suporte com o Xamarin|Comentários Adicionais|
|-------------|----------------------------|-------------------------|
|Gerenciar processos de versão|Sim||
|Implantação para servidores para carregamento lateral por meio de scripts|Sim||
|Carregar para a loja de aplicativos|Parcial|Estão disponíveis extensões que podem automatizar esse processo para algumas lojas de aplicativos.  Consulte [Extensões para o Azure DevOps Services](https://marketplace.visualstudio.com/VSTS); por exemplo, a [extensão para Google Play](https://marketplace.visualstudio.com/items?itemName=ms-vsclient.google-play).|

## <a name="monitor-with-hockeyapp"></a>Monitorar com HockeyApp

Link de referência: **[Monitorar com HockeyApp](https://www.hockeyapp.net/features/)**

|Recurso|Tem suporte com o Xamarin|Comentários Adicionais|
|-------------|----------------------------|-------------------------|
|Análise de falhas, telemetria e distribuição beta|Sim||
