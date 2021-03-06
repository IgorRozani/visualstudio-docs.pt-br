---
title: Como instalar um adaptador de dados de diagnóstico no Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, installing
ms.assetid: 907e65d8-0408-44b3-9e5e-e631892c1726
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 9d2d6c30696636bc8fd2ca571940ac0165eabbcf
ms.sourcegitcommit: 28909340cd0a0d7cb5e1fd29cbd37e726d832631
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44321041"
---
# <a name="how-to-install-a-custom-diagnostic-data-adapter"></a>Como instalar um adaptador de dados de diagnóstico personalizado

Se você criou um adaptador de dados de diagnóstico personalizado ou se obteve um adaptador de dados de diagnóstico personalizado para uso, poderá instalar seu assembly de adaptador de dados de diagnóstico ao copiar o arquivo de assembly para ele no diretório correto em seu computador local.

 Se desejar usar o adaptador de dados de diagnóstico personalizado para uma função em um ambiente, instale o adaptador de dados de diagnóstico em todos os computadores que executem agentes de teste que possam ser usados para essa função.

 Use o seguinte procedimento para instalar o adaptador personalizado de diagnóstico nos locais apropriados. Você precisará de permissões administrativas em qualquer computador onde você instala o adaptador de dados de diagnóstico.

## <a name="install-a-custom-diagnostic-data-adapter"></a>Instalar um adaptador de dados de diagnóstico personalizado

### <a name="to-install-a-custom-diagnostic-data-adapter"></a>Para instalar um adaptador de dados de diagnóstico padrão

1.  Para usar o adaptador de dados de diagnóstico quando você executar testes no computador do cliente ou em um computador de agente, copie todos os arquivos do diretório de compilação para o seguinte diretório no computador de destino com base no caminho de instalação:

     *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors*

     Os arquivos a serem copiados são:

    -   O assembly do adaptador de dados de diagnóstico (*.dll*) (obrigatório).

    -   O arquivo de dados de depuração (*.pdb*) do adaptador (opcional).

    -   O arquivo de configuração do adaptador (`<diagnostic data adapter name>.dll.config`), se você tem configurações padrão (opcional).

    -   O assembly do editor de configuração, se você criou um para editar as configurações do adaptador (opcional). Isso é somente para computadores clientes. Os computadores do agente não usam o editor.

    > [!NOTE]
    > Embora o adaptador de dados de diagnóstico e seu editor de configuração possam ser criados no mesmo projeto e ser compilados no mesmo assembly, você pode usar projetos separados e criar assemblies separados para eles, se preferir.

     Para obter mais informações sobre como definir suas configurações de teste para usar um ambiente ao executar testes, confira [Coletar dados de diagnóstico em testes manuais (Azure Test Plans)](/azure/devops/test/mtm/collect-more-diagnostic-data-in-manual-tests?view=vsts).

2.  Para selecionar o adaptador de dados de diagnóstico para um teste, primeiro você precisa selecionar as configurações de um teste existente ou criar um novo no Microsoft Test Manager ou no Visual Studio e, então, selecionar o adaptador de dados de diagnóstico na guia **Dados e Diagnósticos** das configurações de teste selecionadas.

3.  Se você criou e instalou um editor de configurações do adaptador de dados de diagnóstico, para configurar o adaptador de dados de diagnóstico para suas configurações de teste, escolha **Configurar** ao lado do seu adaptador e faça as alterações. Em seguida, escolha **Salvar**. Para obter mais informações sobre como criar um editor de configuração para o coletor de dados de diagnóstico, confira [Como criar um editor personalizado de dados para o adaptador de dados de diagnóstico](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md).

4.  Se estiver executando seus testes no Microsoft Test Manager, você poderá atribuir essas configurações de teste ao seu plano de teste antes de executar os testes ou usar o comando **Executar com opções** para atribuir e substituir configurações de teste. Para obter mais informações sobre as configurações de teste, confira [Coletar informações de diagnóstico usando configurações de teste](../test/collect-diagnostic-information-using-test-settings.md).

     Se você estiver executando seus testes do Visual Studio, deverá definir essas configurações de teste como ativas. Para obter mais informações sobre as configurações de teste, confira [Coletar informações de diagnóstico usando configurações de teste](../test/collect-diagnostic-information-using-test-settings.md).

5.  Execute seus testes usando as configurações de teste com o adaptador de dados de diagnóstico selecionado.

## <a name="see-also"></a>Consulte também

- [Como criar um adaptador de dados de diagnóstico](../test/how-to-create-a-diagnostic-data-adapter.md)
- [Como criar um editor personalizado de dados para o adaptador de dados de diagnóstico](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [Projeto de amostra para criar um adaptador de dados de diagnóstico](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
- [Criar um adaptador de dados de diagnóstico para coletar dados personalizados ou afetar um computador de teste](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [Coletar informações de diagnóstico usando configurações de teste](../test/collect-diagnostic-information-using-test-settings.md)