---
title: "Quais opções de publicação são adequadas para mim? | Microsoft Docs"
ms.custom: 
ms.date: 03/09/2017
ms.reviewer: riande
ms.suite: 
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ASP.NET, web applications, deployment, publishing
ms.assetid: 3A13F685-531C-457D-A98E-631888011E4B
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 22c9aa56ab63d0c7c3b342e2c50cf81045580b54
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# Quais opções de publicação são adequadas para mim?

De dentro do Visual Studio, os aplicativos Web podem ser publicados diretamente nos seguintes destinos:

- [Serviço de Aplicativo do Azure](#azure-app-service)
- [Máquinas Virtuais do Azure](#azure-virtual-machines)
- [Sistema de arquivos](#file-system)
- [Destinos personalizados (IIS, FTP, etc.) ](#custom-targets), que inclui todos os servidores Web arbitrários.

Na guia **Publicar** é possível selecionar um perfil de publicação existente, importar um perfil existente ou criar um novo perfil usando as opções descritas aqui.

## Aplicativos Web do Serviço de Aplicativo do Azure

Os [Aplicativos Web do Serviço de Aplicativo do Azure](/azure/app-service/app-service-web-overview) (ou apenas Aplicativos Web) ajudam os desenvolvedores a criar rapidamente uma variedade de serviços e aplicativos Web escalonáveis sem infraestrutura de manutenção.

Você determina a capacidade de computação que um aplicativo Web tem escolhendo um [plano ou tipo de preço](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview) para o Serviço de Aplicativo recipiente. Você pode ter vários aplicativos Web (e outros tipos de aplicativos) compartilhando o mesmo Serviço de Aplicativo sem alterar o tipo de preço. Por exemplo, você pode hospedar o desenvolvimento, o preparo e a produção de aplicativos Web juntos no mesmo Serviço de Aplicativo.

Um Serviço de Aplicativo é executado em máquinas virtuais hospedadas na nuvem no Azure, mas essas máquinas virtuais são gerenciadas para você. Cada Aplicativo Web em um Serviço de Aplicativo receberá uma URL \*.azurewebsites.net exclusiva; todos os tipos de preço diferentes de Gratuito também permitem a atribuição de nomes de domínio personalizados ao site.

### Quando escolher os Aplicativos Web do Serviço de Aplicativo do Azure

- Você deseja implantar um aplicativo Web que é acessível pela Internet.
- Você deseja escalonar automaticamente seu aplicativo Web de acordo com a demanda sem a necessidade de reimplantar.
- Você não deseja manter uma infraestrutura de servidor (incluindo atualizações de software).
- Você não precisa de nenhuma personalização de nível de computador nos servidores que hospedam seu aplicativo Web.

> Se quiser usar o Serviço de Aplicativo do Azure em seu próprio datacenter ou em outros computadores locais, você poderá fazer isso usando o [Azure Stack](https://azure.microsoft.com/overview/azure-stack/).

Para obter mais informações sobre a publicação de aplicativos do ASP.NET Core, consulte [Publicar um aplicativo Web ASP.NET Core no Serviço de Aplicativo do Azure usando o Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs).

## Máquinas Virtuais do Azure

As [Máquinas Virtuais (VMs) do Azure](https://azure.microsoft.com/documentation/services/virtual-machines/) permitem criar e gerenciar qualquer número de recursos de computação na nuvem. Ao assumir a responsabilidade por todos os softwares e atualizações nas VMs, você pode personalizá-los tanto quanto desejar conforme exigido pelo seu aplicativo Web. Você pode acessar as máquinas virtuais diretamente por meio da Área de Trabalho Remota e cada uma delas manterá seu endereço IP atribuído por quanto tempo for desejado.

O escalonamento de um aplicativo Web hospedado em máquinas virtuais envolve a criação VMs adicionais de acordo com a demanda e, em seguida, implantar o software necessário. Esse nível adicional de controle permite você escalonar de maneira diferente em diferentes regiões globais. Por exemplo, se seu aplicativo estiver atendendo a funcionários em uma diversos escritórios regionais, será possível escalonar suas VMs de acordo com o número de funcionários nessas regiões, potencialmente reduzindo os custos.

Para obter informações adicionais, consulte a [comparação detalhada](https://azure.microsoft.com/documentation/articles/choose-web-site-cloud-service-vm/) entre o Serviço de Aplicativo do Azure, as Máquinas Virtuais do Azure e outros serviços do Azure que podem ser usados como destinos de implantação, usando a opção Personalizar no Visual Studio.

### Quando escolher Máquinas Virtuais de Aplicativo do Azure

- Você deseja implantar um aplicativo Web que é acessível pela Internet, com controle total sobre o tempo de vida dos endereços IP atribuídos.
- Você precisa de personalizações em nível de computador em seus servidores que incluem: software adicional, como um sistema de banco de dados especializado, configurações de rede específicas, partições de disco e assim por diante.
- Você deseja um nível de controle refinado sobre o escalonamento de seu aplicativo Web.
- Você precisa ter acesso direto aos servidores que hospedam seu aplicativo por qualquer outro motivo.

> Se quiser usar as Máquinas Virtuais do Azure em seu próprio datacenter ou em outros computadores locais, você poderá fazer isso usando o [Azure Stack](https://azure.microsoft.com/overview/azure-stack/).


## Sistema de arquivos

A implantação no sistema de arquivos significa simplesmente copiar os arquivos do seu aplicativo Web para uma pasta específica em seu próprio computador. Isso geralmente é usado para fins de teste ou para implantar o aplicativo para uso por um número limitado de pessoas, caso o computador também esteja executando um servidor Web. Se a pasta de destino for compartilhada em uma rede, a implantação no sistema de arquivos poderá disponibilizar os arquivos do aplicativo Web para outras pessoas que poderão, por sua vez, implantá-la em servidores específicos.

Todas os computadores locais que estão executando um servidor Web podem disponibilizar seu aplicativo através da Internet ou de uma Intranet, dependendo de como estiver configurado e das redes às quais estiver conectado. (Se você conectar um computador diretamente à Internet, seja muito cuidado protegendo-o contra ameaças externas.) Como você gerencia esses computadores, você está no controle total das configurações de hardware e software.

Observe que se, por algum motivo (como acesso ao computador), não for possível usar os serviços de nuvem como o Serviço de Aplicativo do Azure ou as Máquinas Virtuais do Azure, você poderá usar o [Azure Stack](https://azure.microsoft.com/overview/azure-stack/) em seu próprio datacenter. O Azure Stack permite gerenciar e usar recursos de computação por meio do Serviço de Aplicativo do Azure e das Máquinas Virtuais do Azure e ainda manter tudo localmente.

### Quando escolher a implantação de sistema de arquivos

- Você só precisa implantar o aplicativo em um compartilhamento de arquivos do qual outras pessoas vão implantá-lo em servidores diferentes.
- Você precisa apenas de uma implantação de teste local.
- Você deseja examinar e potencialmente modificar os arquivos do aplicativo independentemente, antes de enviá-los a outro destino de implantação.

Para obter mais informações sobre a implantação de aplicativos .NET Core, consulte [Implantando aplicativos .NET Core com o Visual Studio](/dotnet/core/deploying/deploy-with-vs).

## Destinos personalizados

Um destino personalizado permite que você implante seu aplicativo Web em um destino diferente do Serviço de Aplicativo do Azure, das Máquinas Virtuais do Azure ou do sistema de arquivos local. Ele pode ser implantado em um sistema de arquivos ou qualquer outro servidor (Internet ou Intranet) ao qual você tem acesso, inclusive aqueles em outros serviços de nuvem. Ele pode funcionar com a Implantação da Web (arquivos ou .ZIP) e FTP.

Ao escolher um destino personalizado, o Visual Studio solicitará um nome de perfil e, em seguida, coletará informações de **Conexão** adicionais, incluindo o servidor de destino ou o local, um nome de site e as credenciais. É possível controlar os seguintes comportamentos na guia **Configurações**:

- A configuração que você deseja implantar.
- Se os arquivos existentes serão removidos do destino.
- Se a pré-compilação será feita durante a publicação.
- Se os arquivos serão excluídos da pasta App_Data da implantação.

É possível criar vários perfis de implantação Personalizados no Visual Studio, possibilitando o gerenciamento dos perfis com configurações diferentes.

### Quando escolher a implantação personalizada

- Você está usando serviços de nuvem em um provedor diferente do Azure que pode ser acessado por meio de URLs.
- Você deseja implantar usando credenciais diferentes das que você usa no Visual Studio ou daquelas diretamente ligadas às suas contas do Azure.
- Você deseja excluir os arquivos do destino a cada vez que implantar.

Para obter mais informações sobre a publicação para IIS, consulte [IIS 8.0 Using ASP.NET 3.5 and ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) (IIS 8.0 usando ASP.NET 3.5 e ASP.NET 4.5) e [Depuração remota ASP.NET em um computador remoto do IIS](../../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md).