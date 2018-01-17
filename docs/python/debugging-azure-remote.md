---
title: "Depuração remota do Azure com Python no Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: e0cac283dacb0f63005f67dc279087726de26772
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2018
---
# <a name="remotely-debugging-python-code-on-azure"></a>Depurar o código do Python remotamente no Azure

O [suporte do Python no Visual Studio](installation.md) inclui a capacidade de depurar o código do Python remotamente em execução no Serviço de Aplicativo do Azure. Ao contrário da depuração remota simples, o computador de destino neste cenário não é diretamente acessível por TCP e, portanto, o Visual Studio fornece um proxy que expõe o protocolo do depurador por HTTP. Os projetos criados com o modelo da Web configuram esse proxy automaticamente no arquivo `web.debug.config` gerado. A depuração remota também é habilitada quando você publica uma configuração Depuração do projeto, conforme descrito em [Publicando no Serviço de Aplicativo do Azure](template-web.md#publishing-to-azure-app-service).

Como a depuração remota do Azure usa soquetes da Web, os soquetes devem estar habilitados para o Serviço de Aplicativo por meio do [portal do Azure](https://portal.azure.com), acessando **Configurações > Configurações de aplicativo**, definindo **Configurações gerais > Soquetes da Web** como **Ativado** e selecionando **Salvar** para aplicar a alteração. (Observe que as configurações **Depuração** não se aplicam à depuração do Python.)

![Habilitando soquetes da Web no portal do Azure](media/azure-remote-debugging-enable-web-sockets.png)

Depois que o projeto for implantado corretamente e os soquetes da Web forem habilitados, é possível se anexar ao Serviço de Aplicativo em **Gerenciador de Servidores** no Visual Studio (**Exibir > Gerenciador de Servidores**). Localize seu site em **Azure > Serviço de Aplicativo** e o grupo de recursos aplicável, clique com o botão direito do mouse e selecione **Anexar Depurador (Python)**. (O comando **Anexar Depurador** destina-se a aplicativos .NET em execução no IIS e será útil apenas se você co-hospedar o código do .NET junto com o aplicativo do Python.)

O Visual Studio levará você diretamente a um conjunto de instruções para a anexação direta, conforme descrito abaixo em [Anexando sem o Gerenciador de Servidores](#attaching-without-server-explorer). Se você não vir o comando **Anexar Depurador (Python)** ou o Visual Studio não conseguir se anexar ao seu site, consulte [Solução de problemas da depuração remota do Azure](debugging-azure-remote-troubleshooting.md).

Se a anexação for bem-sucedida, o Visual Studio alternará para uma exibição de depurador. A barra de ferramentas indica o processo que está sendo depurado como um URI `wss://`:

![Depurando um site do Serviço de Aplicativo do Azure](media/azure-remote-debugging-attached.png)

Depois de anexada, a experiência de depuração ocorre, basicamente, da mesma maneira que a depuração remota normal, sujeita a algumas restrições. Em particular, o servidor Web do IIS que manipula as solicitações de entrada e as delega ao código do Python por meio do FastCGI tem um tempo limite para a manipulação de solicitação, que usa como padrão 90 segundos. Se a manipulação de solicitação levar mais tempo do que o tempo limite (por exemplo, devido a um processo em pausa em um ponto de interrupção), o IIS encerrará o processo, encerrando a sessão de depuração. 

## <a name="attaching-without-server-explorer"></a>Anexando sem o Gerenciador de Servidores

Para anexar o depurador diretamente ao Serviço de Aplicativo, siga as instruções fornecidas na página de informações do proxy WebSocket que é implantado pelo Visual Studio em seu site em `<site_url>/ptvsd` como `ptvsdemo.azurewebsites.net/ptvsd`. Ao visitar essa página, também é verificado se o proxy está configurado corretamente:

![Página de informações do proxy de depuração remota do Azure](media/azure-remote-debugging-proxy-info-page.png)

Conforme indicado, construa uma URL usando o segredo de `web.debug.config`, que é gerado novamente sempre que o projeto é publicado. Esse arquivo está oculto por padrão no Gerenciador de Soluções e não está incluído no projeto, portanto, mostre todos os arquivos ou abri-lo em um editor separado. Depois de abrir o arquivo, observe o valor da appSetting chamada `WSGI_PTVSD_SECRET`:

![Determinando o ponto de extremidade do depurador em um Serviço de Aplicativo do Azure](media/azure-remote-debugging-secret.png)

A URL de que você precisa agora está no formato `wss://<secret>@<site_name>.azurewebsites.net/ptvsd`, em que você substitui &lt;secret&gt; e &lt;site_name&gt; na cadeia de caracteres pelos valores específicos.

Para anexar o depurador, selecione **Depurar > Anexar ao Processo**, selecione **Depuração remota do Python** no menu suspenso **Transporte**, insira a URL na **Caixa de texto qualificadora** e pressione Enter. Se o Visual Studio puder se conectar com êxito ao Serviço de Aplicativo, ele mostrará um único processo do Python na lista. Selecione-o e, em seguida, **Anexar** para iniciar a depuração:

![Usando a caixa de diálogo Anexar ao Processo para se anexar a um site do Azure](media/azure-remote-debugging-manual-attach.png)
