---
title: Usar o Build ou o Release Management para testes automatizados no Visual Studio | Microsoft Docs
ms.date: 03/02/2018
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- automated testing, lab management, test lab
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 5596dbbe65dc57dcb1862b74ed6379d1e2c080cf
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2018
---
# <a name="use-build-and-release-management-instead-of-lab-management-for-automated-testing"></a>Usar o Build ou o Release Management em vez de o Lab Management para o teste automatizado

Se você usar o MTM (Microsoft Test Manager) e o Lab Management para o teste automatizado ou para a automação de compilar-implantar-testar, este tópico explicará como você pode atingir as mesmas metas usando os recursos [Build e Release](/vsts/build-release/) no TFS (Team Foundation Server) e no Visual Studio Team Services (VSTS).

## <a name="build-deploy-test-automation"></a>Automação de compilar-implantar-testar

O MTM e o Lab Management contam com uma definição de build XAML para automatizar o build, a implantação e o teste de seus aplicativos. A compilação XAML se baseia em vários constructos criados no MTM, como um ambiente de laboratório, conjuntos de teste e configurações do teste e em vários componentes de infraestrutura, como um Controlador de Build, Agentes de Build, Controlador de teste e Agentes de teste para atingir essa meta. Você pode fazer o mesmo com menos etapas usando o Build ou o Release Management no TFS e Team Services.

| Etapas | Com Build XAML | Com Build ou Release Management |
|-------|----------------------|-----------------|
| Identifique os computadores nos quais implantar o build e executar os testes. | Crie um ambiente de laboratório padrão no MTM com esses computadores. | N/D |
| Identifique os testes a serem executados. | Crie um conjunto de testes no MTM, crie casos de teste e associe a automação a cada caso de teste. Crie configurações de teste no MTM identificando a função dos computadores no ambiente de laboratório em que os testes devem ser executados. | Crie um conjunto de testes automatizados no MTM da mesma maneira se você planejar gerenciar seus testes por meio de planos de teste. Como alternativa, você poderá ignorar isso se desejar executar testes diretamente dos binários de teste produzidos por seus builds. Não é necessário criar as configurações de teste em nenhum dos casos. |
| Automatize a implantação e o teste. | Crie uma definição de build XAML usando LabDefaultTemplate.*.xaml. Especifique o build, os conjuntos de teste e o ambiente de laboratório na definição de build. | Crie uma [definição de build ou versão](/vsts/build-release/) com um único ambiente. Execute o mesmo script de implantação (da definição de build XAML) usando a tarefa de linha de comando e execute testes automatizados usando as tarefas de Implantação do Agente de Teste e Executar Testes Funcionais. Especifique a lista de computadores e suas credenciais como entradas para essas tarefas. |

Alguns dos benefícios de usar o Build ou o Release Management para esse cenário são:

* Não é necessário ter um Controlador de Build ou um Controlador de Teste.
* O Agente de Teste é instalado por meio de uma tarefa como parte do build ou da versão.
* É fácil personalizar as etapas de implantação. Você não está mais restrito a usar um único script. Você também pode aproveitar as várias tarefas que estão disponíveis no produto, bem como no Visual Studio Marketplace.
* Você não precisa manter conjuntos de testes. Você pode executar os testes diretamente dos binários.
* Você obtém uma experiência de relatório embutido avançada para os testes executados dentro de cada build ou versão.
* Você pode controlar quais ativos (versão, build, itens de trabalho, confirmações) atualmente estão implantadas e testadas em cada ambiente.
* Você pode personalizar e estender a automação para implantar facilmente em vários ambientes de teste e até mesmo na produção.
* Você pode agendar a automação para ocorrer sempre que houver um check-in ou confirmação ou em um momento específico todos os dias.

## <a name="self-service-management-of-scvmm-environments"></a>Gerenciamento de autoatendimento de ambientes SCVMM

O [Centro de Testes no Microsoft Test Manager](/vsts/manual-test/mtm/guidance-mtm-usage) dá suporte à capacidade de gerenciar uma biblioteca de modelos de ambiente, bem como provisionar ambientes sob demanda usando um [servidor SCVMM](/system-center/vmm/overview?view=sc-vmm-1801).

Os recursos de provisionamento de autoatendimento da Central de Laboratório têm duas metas distintas:

* Fornecer uma maneira mais simples de gerenciar a infraestrutura. Gerenciar a VM e os modelos de ambiente e criar automaticamente redes privadas para isolar os clones de ambientes uns dos outros eram exemplos de gerenciamento de infraestrutura.

* Fornecer uma maneira mais simples para as equipes consumirem as máquinas virtuais em suas atividades de teste e implantação. Disponibilizar os ambientes de laboratório por meio do mesmo modelo de segurança de projeto de equipe e o uso integrado dessas máquinas virtuais nos cenários de teste eram exemplos de consumo fácil.

No entanto, devido à evolução dos sistemas de gerenciamento de nuvem privada e pública mais avançados como o [Microsoft Azure](https://azure.microsoft.com/) e o [Microsoft Azure Stack](https://azure.microsoft.com/overview/azure-stack/), não há evolução dos recursos de gerenciamento de infraestrutura no TFS 2017 e posteriores. Em vez disso, o foco no fácil consumo de recursos gerenciado por meio de tais infraestruturas de nuvem continua.

A tabela a seguir resume as atividades típicas que você realizava na Central de Laboratório e como pode realizá-las por meio do SCVMM ou do Azure (se forem atividades de gerenciamento de infraestrutura) ou pelo TFS e pelo Team Services (se forem atividades de teste ou implantação):

| Etapas | Com a Central de Laboratório | Com Build ou Release Management |
|-------|----------------------|-----------------|
| Gerencie uma biblioteca de modelos de ambiente. | Crie um ambiente de laboratório. Instale o software necessário nas máquinas virtuais. Sysprep e armazene o ambiente como um modelo na biblioteca. | Use o console de administração do SCVMM diretamente para criar e gerenciar modelos de máquinas virtuais ou modelos de serviço. Ao usar o Azure, selecione um dos [modelos de início rápido do Azure](/resources/templates/). |
| Crie um ambiente de laboratório. | Selecione um modelo de ambiente na biblioteca e implante-o. Forneça os parâmetros necessários para personalizar as configurações da máquina virtual. | Use o console de administração do SCVMM diretamente para criar VMs ou instâncias de serviço de modelos. Use o Portal do Azure diretamente para criar recursos. Ou crie uma definição de versão com um ambiente. Use as tarefas do Azure ou as tarefas da [extensão de Integração do SCVMM](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) para criar novas máquinas virtuais. Criar uma nova versão dessa definição é equivalente a criar um novo ambiente na Central de Laboratório. |
| Conecte-se aos computadores. | Abra o ambiente de laboratório no Visualizador de ambiente. | Use o console de administração do SCVMM diretamente para se conectar às máquinas virtuais. Como alternativa, use o endereço IP ou os nomes DNS das máquinas virtuais para abrir as sessões de área de trabalho remota. |
| Crie um ponto de verificação de um ambiente ou restaure um ambiente para limpar o ponto de verificação. | Abra o ambiente de laboratório no Visualizador de ambiente. Selecione a opção de criar um ponto de verificação ou restaurar para um ponto de verificação anterior. | Use o console de administração do SCVMM diretamente para executar essas operações nas máquinas virtuais. Ou, para executar estas etapas como parte de uma automação e inclua as tarefas de ponto de verificação da [extensão de Integração do SCVMM](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) como parte do ambiente em uma definição de versão. |

## <a name="creation-of-network-isolated-environments"></a>Criação de ambientes isolados da rede

Um ambiente de laboratório isolado da rede é um grupo de máquinas virtuais SCVMM que podem ser clonadas com segurança sem causar conflitos de rede. Isso foi feito no MTM usando uma série de instruções que usavam um conjunto de placas de adaptador de rede para configurar as máquinas virtuais em uma rede privada e outro conjunto para configurar as máquinas virtuais em uma rede pública.

No entanto, o VSTS e o TFS, em conjunto com a tarefa de build e implantação do SCVMM, podem ser usados para gerenciar ambientes do SCVMM, provisionar redes virtuais isoladas e implementar cenários de build, implantação e teste. Por exemplo, você pode usar a tarefa para:

* Criar, restaurar e excluir pontos de verificação
* Criar novas máquinas virtuais usando um modelo
* Iniciar e parar máquinas virtuais
* Executar scripts do PowerShell personalizados para o SCVMM

Para obter mais informações, consulte [Create a virtual network isolated environment for build-deploy-test scenarios](/vsts/build-release/actions/virtual-networks/create-virtual-network) (Criar um ambiente isolado da rede virtual para cenários de build, implantação e teste).
