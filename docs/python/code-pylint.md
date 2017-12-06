---
title: Usando o PyLint no Visual Studio | Microsoft Docs
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
ms.openlocfilehash: dbb4c3d0a2d9077572a80c43d9d49d9c7e898dce
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2017
---
# <a name="using-pylint-to-check-python-code"></a>Usando o PyLint para verificar o código do Python

O [PyLint](https://www.pylint.org/), uma ferramenta amplamente usada que verifica se há erros no código do Python e incentiva bons padrões de codificação do Python, é integrado ao Visual Studio para projetos do Python.

Basta clicar com o botão direito do mouse em um projeto do Python no Gerenciador de Soluções e selecionar **Python > Executar PyLint...**:

![Comando PyLint no menu de contexto em projetos do Python](media/code-pylint-command.png)

Usando esses prompts de comando você instala o PyLint no ambiente ativo se ele ainda não estiver presente.

Os avisos e erros do PyLint são exibidos na janela Lista de Erros:

![Lista de erros do PyLint](media/code-pylint-error-list.png)

Clicar duas vezes em um erro leva você diretamente para o código-fonte que gerou o problema.

> [!Tip]
> Consulte a [referência de recursos do PyLint](https://pylint.readthedocs.io/en/latest/technical_reference/features.html) para obter uma lista detalhada de todas as mensagens de saída do PyLint.

## <a name="setting-pylint-command-line-options"></a>Configurando opções de linha de comando do PyLint

A seção [opções de linha de comando](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) da documentação do PyLint descreve como controlar o comportamento do PyLint por meio de um arquivo de configuração `.pylintrc`. Um arquivo desse tipo pode ser colocado na raiz de um projeto do Python no Visual Studio ou em outro lugar, dependendo da abrangência desejada da aplicação das configurações.

Por exemplo, para suprimir os avisos “docstring ausente” mostrados na imagem anterior com um arquivo `.pylintrc` em um projeto, execute as etapas:

1. Na linha de comando, navegue até a raiz do projeto (que contém o arquivo `.pyproj`) e execute o seguinte comando para gerar um arquivo de configuração comentado:

   ```bash
   pylint --generate-rcfile > .pylintrc
   ```

1. No Gerenciador de Soluções do Visual Studio, clique com o botão direito do mouse no projeto, selecione **Adicionar > Saindo do Item...**, navegue até o novo arquivo `.pylintrc` e o selecione e, em seguida, selecione **Adicionar**.

1. Abra o arquivo para edição, que contém uma variedade de configurações com as quais você pode trabalhar. Para desabilitar um aviso, localize a seção `[MESSAGES CONTROL]` e, em seguida, localize a configuração `disable` nessa seção. Há uma longa cadeia de mensagens específicas, à qual é possível acrescentar os avisos desejados. Neste exemplo, acrescente `,missing-docstring` (incluindo a vírgula delimitadora).

1. Salve o arquivo `.pylintrc` e execute o PyLint novamente para ver se agora os avisos estão suprimidos.
