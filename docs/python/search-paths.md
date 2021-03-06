---
title: Como caminhos de pesquisa de Python são aplicados
description: Uma visão geral de como o Visual Studio usa caminhos de pesquisa do Python nos projetos e ambientes.
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 2a02bf78d731764b0725c03cefb4959451a40b9c
ms.sourcegitcommit: 4c60bcfa2281bcc1a28def6a8e02433d2c905be6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42627027"
---
# <a name="how-visual-studio-uses-python-search-paths"></a>Como o Visual Studio usa caminhos de pesquisa de Python

Com o uso típico do Python, a variável de ambiente `PYTHONPATH` (ou `IRONPYTHONPATH`, etc.) fornece o caminho de pesquisa padrão para arquivos de módulo. Ou seja, quando você usa uma instrução `from <name> import...` ou `import <name>`, o Python pesquisa os seguintes locais, nessa ordem, por um nome correspondente:

1. Módulos internos do Python.
1. A pasta que contém o código do Python que você está executando.
1. O "caminho de pesquisa do módulo", conforme definido pela variável de ambiente aplicável. (Consulte [O caminho de pesquisa do módulo](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) e [Variáveis de ambiente](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) na documentação básica do Python.)

No entanto, o Visual Studio ignora a variável de ambiente do caminho de pesquisa, mesmo quando ela tiver sido configurada para todo o sistema. Na verdade, ela é precisamente ignorada *porque* é definida para todo o sistema e, portanto, gera algumas perguntas que não podem ser respondidas automaticamente: os módulos referenciados são destinados ao Python 2.7 ou ao Python 3.6 e posteriores? Eles substituirão os módulos da biblioteca padrão? O desenvolvedor está ciente desse comportamento ou essa é uma tentativa de sequestro mal-intencionada?

Dessa forma, o Visual Studio fornece um meio para especificar caminhos de pesquisa diretamente nos projetos e ambientes. O código que você executa ou depura no Visual Studio recebe os caminhos de pesquisa no valor de `PYTHONPATH` (e outras variáveis equivalentes). Ao adicionar caminhos de pesquisa, o Visual Studio inspeciona as bibliotecas nessas localizações e compila bancos de dados do IntelliSense para elas quando necessário (Visual Studio 2017 versão 15.5 e anterior; a criação do banco de dados pode demorar algum tempo, dependendo do número de bibliotecas).

Para adicionar um caminho de pesquisa, clique com o botão direito do mouse no item **Caminhos de Pesquisa** no **Gerenciador de Soluções**, escolha **Adicionar Pasta ao Caminho de Pesquisa** e escolha a pasta a ser incluída. Esse caminho é usado para qualquer ambiente associado ao projeto. (Você poderá ver erros se o ambiente tiver base no Python 3, e você tentar adicionar um caminho de pesquisa aos módulos do Python 2.7.)

Os arquivos com uma extensão *.zip* ou *.egg* também podem ser adicionados como caminhos de pesquisa quando **Adicionar Arquivo Morto Zip para Caminho de Pesquisa** for escolhido. Assim como ocorre com pastas, o conteúdo desses arquivos é examinado e disponibilizado para o IntelliSense.

Se estiver usando regularmente os mesmos caminhos de pesquisa e o conteúdo não for alterado com frequência, poderá ser mais eficiente instalá-lo na pasta de pacotes do site. Em seguida, o caminho de pesquisa é analisado e armazenado no banco de dados do IntelliSense. Ele sempre é associado ao ambiente pretendido e não exige a adição de um caminho de pesquisa a cada projeto.

### <a name="see-also"></a>Consulte também

- [Gerenciar ambientes do Python no Visual Studio](managing-python-environments-in-visual-studio.md)
- [Selecionar um intérprete para um projeto](selecting-a-python-environment-for-a-project.md)
- [Usar requirements.txt para dependências](managing-required-packages-with-requirements-txt.md)
- [Referência à janela Ambientes do Python](python-environments-window-tab-reference.md)
