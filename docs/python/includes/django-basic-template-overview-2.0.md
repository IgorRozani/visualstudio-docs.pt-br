---
ms.topic: include
ms.openlocfilehash: ff6523d33e29f4fcc6fd02c08e0a35ac00892829
ms.sourcegitcommit: aea5cdb76fbc7eb31d1e5cc3c8d6adb0c743220f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "39638385"
---
### <a name="create-a-project-using-django-20"></a>Criar um projeto usando o Django 2.0

No momento, o **modelo do Projeto Web em Branco do Django** usa a versão mais recente do Django 1.x. Para usar o Django 2.x, o meio mais rápido é importar arquivos do Django 2.x para um projeto do Django 1.x. Ao seguir esse processo, você aproveita outros detalhes tratados pelo modelo de projeto do Visual Studio.

1. Crie um projeto do Django 1.x usando o modelo **Projeto Web em Branco do Django**, conforme descrito na seção anterior. No entanto, no prompt de **Este projeto requer dependências externas**, escolha **Eu vou instalá-las sozinho**. Marque essa opção para evitar a instalação de dependências que serão desinstaladas em uma etapa posterior.

1. Abra um prompt de comando e navegue até uma pasta temporária.

1. Execute `pip install django` para instalar o pacote mais recente do Django em seu ambiente global do Python.

1. Execute `django-admin startproject <project_name>` substituindo `<project_name>` pelo mesmo nome de projeto usado na Etapa 1, como "HelloDjango". O comando `startproject` cria um arquivo *manage.py* juntamente com uma pasta correspondente `<project_name>` que contém os arquivos *\_\_init\_\_.py*, *settings.py*, *urls.py* e *wsgi.py*.

1. No Visual Studio, substitua os arquivos do Django 1.x no projeto pelos arquivos do Django 2.x da seguinte maneira:

    1. No **Gerenciador de Soluções**, exclua **manage.py** e a pasta de aplicativos do Django.
    1. Clique com o botão direito do mouse no projeto, selecione o comando **Adicionar** > **Item Existente**, navegue até lá e escolha o arquivo **manage.py** criado na Etapa 4 e clique em **OK**. Em seguida, o Visual Studio copia o arquivo para o projeto.
    1. Clique com o botão direito do mouse no projeto novamente, marque o comando **Adicionar** > **Pasta Existente**, navegue até lá e escolha a pasta de aplicativo criada na Etapa 4 e clique em **OK**. Em seguida, o Visual Studio copia a pasta inteira e os quatro arquivo para o projeto.
    1. Clique com o botão direito do mouse em **manage.py** e escolha **Definir como Arquivo de Inicialização**.

    > [!Important]
    > O nome do aplicativo mostrado no projeto do Visual Studio deve corresponder a `<project_name>` usado com o utilitário `django-admin` uma vez que o utilitário usa esse nome em forma de um namespace nos arquivos de código do Python.

1. Abra *requirements.txt*, altere o conteúdo para `django >=2.0, <3` e salve o arquivo.

1. No **Gerenciador de Soluções**, clique com o botão direito do mouse no nó **Ambientes do Python** e escolha **Adicionar Ambiente Virtual**. Aceite os valores padrão na caixa de diálogo que é exibida e escolha **Criar**. Aceite as solicitações de privilégios de administrador.