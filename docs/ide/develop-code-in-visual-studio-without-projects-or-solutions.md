---
title: "Desenvolver código no Visual Studio sem projetos nem soluções | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.texteditor
dev_langs:
- JScript
- VB
- CSharp
helpviewer_keywords:
- code, editing
- code editor, syntax coloring
- code editor [Visual Studio]
- brace matching
- code editor, line numbers
- code editor, brace matching
- line numbers
- syntax coloring
- code editor
- code files
- code
ms.assetid: cb53bb9b-5b76-4759-b9b8-7bf32298bcbb
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 78b59ff3d8d6c54465ce29334c1dbe041b7a71be
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2018
---
# <a name="develop-code-in-visual-studio-without-projects-or-solutions"></a>Desenvolver código no Visual Studio sem projetos nem soluções  
No Visual Studio 2017, é possível abrir códigos de quase todos os tipos de projeto baseado em diretório no Visual Studio sem a necessidade de um arquivo de solução ou de projeto. Isso significa que você pode, por exemplo, encontrar um projeto de código no Git, cloná-lo, abri-lo diretamente no Visual Studio e começar o desenvolvimento sem precisar criar uma solução ou um projeto.  

Não apenas é possível editar o código e compilá-lo no Visual Studio, mas também navegar pelo código (por exemplo, usando o comando Navegar Para). O código será exibido com a colorização de sintaxe e, em muitos casos, incluirá o preenchimento de declaração básico e depuração, completo com pontos de interrupção. Algumas linguagens incluirão ainda mais funcionalidades. Consulte [Criar configurações do editor portáteis e personalizadas](create-portable-custom-editor-options.md) para obter mais informações.  

## <a name="open-code-anywhere"></a>Abrir o código em qualquer lugar  
Você pode abrir o código no Visual Studio das seguintes maneiras:  

- Na barra de menus do Visual Studio, escolha **Arquivo**, **Abrir**, **Pasta** e, em seguida, navegue para a localização do código.  

- No menu de contexto (acesso por clique com o botão direito do mouse) de uma pasta que contém o código, escolha o comando **Abrir no Visual Studio**.  

- Escolha o link **Abrir Pasta** na Página Inicial do Visual Studio.  

- Código aberto clonado de um repositório GitHub.  

### <a name="to-open-code-from-a-cloned-github-repo"></a>Para abrir o código de um repositório GitHub clonado  
O exemplo a seguir mostra como clonar um repositório GitHub e, em seguida, abrir seu código no Visual Studio. Para seguir este procedimento, você deve ter uma conta do GitHub e o Git para Windows instalado no sistema. Consulte [Inscrevendo em uma nova conta do GitHub](https://help.github.com/articles/signing-up-for-a-new-github-account/) e o [Git para Windows](https://git-for-windows.github.io/) para obter mais informações.  

1. Acesse o repositório que deseja clonar no GitHub.  

1. Escolha o botão **Clonar ou Baixar** e, em seguida, selecione o botão **Copiar para Área de Transferência** no menu suspenso para copiar a URL segura do repositório do GitHub.  

  ![Botão de clone do GitHub](./media/VSIDE_Code_Clone.png)

    > [!NOTE]
    >  Embora você também tenha a opção de abrir o projeto na área de trabalho ou baixar um arquivo .zip do projeto, este exemplo demonstra como clonar o repositório usando o método de URL segura.

1. No Visual Studio, escolha a guia **Team Explorer** para abrir o Team Explorer.  

1. No Team Explorer, na seção **Repositórios Git Locais**, escolha o comando **Clonar** e, em seguida, cole a URL da página do GitHub na caixa de texto.  

  ![Clonar o projeto](./media/VSIDE_Code_Clone2.png)

1. Escolha o botão **Clonar** para clonar os arquivos do projeto para um repositório Git local. Dependendo do tamanho do repositório, esse processo poderá levar vários minutos.  

1. Depois que o repositório for clonado para o sistema, no Team Explorer, escolha o comando **Abrir** no menu de contexto (acesso com clique com o botão direito do mouse) do repositório recém-clonado.  

  ![Repositório clonado](./media/VSIDE_Code_Clone3.png)

1. Escolha o comando **Mostrar Exibição de Pasta** para exibir os arquivos no Gerenciador de Soluções  

  ![Mostrar exibição de pasta](./media/VSIDE_Code_Clone3_show.png)

  Agora é possível procurar pastas e arquivos no repositório clonado, além de exibir e pesquisar o código no editor de códigos do Visual Studio, completo com colorização de sintaxe e outros recursos.

    ![Pesquisando o código do projeto clonado](./media/VSIDE_Code_Clone4.png)  

|         |         |
|---------|---------|
|  ![ícone de câmera para vídeo](../install/media/video-icon.png "Assistir a um vídeo")  |    [Assista a um vídeo](https://mva.microsoft.com/en-us/training-courses/getting-started-with-visual-studio-2017-17798?l=lp3TOKD6D_6711787171) sobre como clonar e abrir o código de um repositório do GitHub no Visual Studio. |

## <a name="debug-your-code"></a>Depurar seu código  
É possível depurar o código no Visual Studio sem um projeto ou uma solução. Para depurar algumas linguagens, talvez seja necessário especificar um *arquivo de inicialização* válido no projeto de código, como um script, executável ou projeto. O Visual Studio executa esse código especificado primeiro ao depurar o código.  

A caixa de listagem suspensa ao lado do botão Iniciar na barra de ferramentas lista todos os itens de inicialização detectados pelo Visual Studio, bem como os itens escolhidos por você especificamente em uma pasta.  

![Botão Executar](./media/VSIDE_Code_Run_Button.png)  

O Visual Studio reconhece os projetos automaticamente, mas os scripts (como o Python e o JavaScript) precisam ser explicitamente selecionados como um item de inicialização antes que sejam exibidos na lista. Além disso, alguns itens de inicialização, como o MSBuild e CMake, podem ter várias configurações de build que são exibidas na lista suspensa do Botão Executar.  

Atualmente, o Visual Studio dá suporte à depuração para as seguintes linguagens:  

- Node.js  

- Python  

- Projetos baseados em MSBuild (C#, VB, C++)  

- Qualquer executável com arquivos PDB (Depurador do Python).  

### <a name="to-debug-nodejs-and-python"></a>Para depurar o Node.js e o Python:  
1. Instale o Node.js, as Ferramentas Python ou o Visual Studio 2017 e o tempo de execução do Node.js.  

1. No menu de contexto de um arquivo JavaScript no Gerenciador de Soluções, escolha o comando **Definir como Item de Inicialização**.  

1. Escolha a tecla **F5** para iniciar a depuração.  

### <a name="to-debug-msbuild-projects"></a>Para depurar projetos do MSBuild  
1. No menu do Visual Studio, escolha **Depurar**. No menu suspenso, escolha o projeto ou selecione o projeto ou o arquivo que você deseja exibir como o item de inicialização no Gerenciador de Soluções.  

1. Escolha a tecla **F5** para iniciar a depuração.  

### <a name="to-debug-executable-files"></a>Para depurar arquivos executáveis  
1. No menu do Visual Studio, escolha **Depurar**. No menu suspenso, escolha o projeto ou selecione o projeto ou o arquivo que você deseja exibir como o item de inicialização no Gerenciador de Soluções.  

1. Escolha a tecla **F5** para iniciar a depuração.  

## <a name="enable-custom-build-tools"></a>Habilitar ferramentas de build personalizadas
O Visual Studio sabe como executar várias linguagens diferentes, mas não como executar tudo. Se o Visual Studio souber como executar a linguagem, será possível executar o código imediatamente. Caso você tente executar o código, mas o Visual Studio não saiba como executá-lo, uma barra de informações solicita a designação de um arquivo na base de código para atuar como o item de inicialização.  

No entanto, se a base de código usar ferramentas de build personalizadas não reconhecidas pelo Visual Studio, provavelmente, você não poderá executar e depurar o código no Visual Studio antes de concluir algumas etapas adicionais. Você deve especificar um tipo de arquivo executável válido, como um compilador, juntamente com quaisquer parâmetros e argumentos personalizados necessários para a linguagem. Para habilitar isso, o Visual Studio fornece *tarefas de build*. É possível criar uma tarefa de build para especificar todos os itens que uma linguagem precisa para compilar e executar seu código.  

Você também pode criar tarefas de build arbitrárias que podem fazer quase tudo o que você deseja. Por exemplo, é possível criar uma tarefa para listar o conteúdo de uma pasta ou renomear um arquivo. Se preferir, é possível criar tarefas de build personalizadas mais direcionadas que executam ações como compilação do projeto usando argumentos específicos. As etapas a seguir mostram como criar ambos os tipos de tarefas de build.  

#### <a name="to-create-an-arbitrary-build-task"></a>Para criar uma tarefa de build arbitrária  
1. Escolha o arquivo ou a pasta do projeto no Gerenciador de Soluções na qual você deseja a tarefa e, no arquivo ou no menu de contexto (acesso por clique com o botão direito do mouse) da pasta, escolha **Configurar Tarefas**.  

  ![Configurar tarefas](./media/VSIDE_Code_Config_Task.png)

  Se você escolher **Configurar Tarefas**, um arquivo chamado tasks.vs.json será aberto. Se esse arquivo não existir, ele será criado. Esse arquivo contém as tarefas de build para a pasta ou o arquivo selecionado.  

  ![Arquivo tasks.vs.json](./media/VSIDE_Code_Tasks_JSON.png)

1. Adicione a tarefa de build a seguir a tasks.vs.json. Para este exemplo, adicionaremos uma tarefa simples chamada “Listar saídas”, que lista os arquivos e as subpastas da pasta selecionada na janela de Saída. (A nova tarefa deve ser adicionada dentro da matriz de “tarefas” existente.)  

  ```xml
      {
        "taskName": "List outputs",
        "appliesTo": "*",
        "type": "command",
        "command": "${env.COMSPEC}",
        "args": [
          "dir ${outDir}"
        ]
      },
  ```
  A tarefa de build completa deve ser parecida com a mostrada abaixo.  

  ![Tarefa de build arbitrária](./media/VSIDE_Code_Tasks_ArbTask.png)

1. Salvar o projeto.  

1. Abra o menu de contexto da pasta selecionada. Você deverá ver a nova tarefa de build arbitrária exibida na parte inferior do menu de contexto.  

  ![Comando arbitrário de tarefa de build](./media/VSIDE_Code_Tasks_ArbTask2.png)

1. Escolha o novo comando **Listar saídas** para executar a tarefa.  

### <a name="to-create-a-custom-build-task"></a>Para criar uma tarefa de build personalizada
Neste procedimento, adicionaremos duas tarefas de build personalizadas que usam nMake para compilar e limpar o código.  

1. Escolha um arquivo do projeto no Gerenciador de Soluções que você desejará designar mais tarde como o item de inicialização. No menu de contexto (acesso por clique com o botão direito do mouse) do arquivo, escolha **Configurar Tarefas**.  

  ![Comando personalizado de tarefa de build](./media/VSIDE_Code_Tasks_CustTask1.png)

1. Adicione as tarefas de build a seguir a tasks.vs.json. Para este exemplo, adicionaremos duas tarefas: uma chamada “makefile-build”, que usa o comando nMake para compilar o projeto e a outra chamada “makefile-clean”, que chama o comando nMake com o argumento “limpo”. Essas tarefas devem ser adicionadas dentro da matriz de “tarefas” existente. (Observe que essas são apenas tarefas de build de exemplo. Para que elas realmente funcionem, você precisa ter a carga de trabalho que contém [nNake](/cpp/build/nmake-reference) instalada no sistema.)

  ```xml
  {
  "taskName": "makefile-build",
  "appliesTo": "makefile",
  "type": "command",
  "contextType": "build",
  "command": "nmake"
  },
  {
  "taskName": "makefile-clean",
  "appliesTo": "makefile",
  "type": "command",
  "contextType": "clean",
  "command": "nmake",
  "args": [
    "clean"
    ]
  },
  ```
  A tarefa de build personalizada completa deve ser parecida com a mostrada abaixo.  

  ![Tarefa de build personalizada](./media/VSIDE_Code_Tasks_CustTask2.png)

1. Salvar o projeto.  

1. Abra o menu de contexto do arquivo selecionado. As novas tarefas de build personalizadas devem ser exibidas na parte central do menu de contexto.  

  ![Comando personalizado de tarefa de build](./media/VSIDE_Code_Tasks_CustTask3.png)

  > [!NOTE]
  > Os comandos são exibidos sob o comando **Configurar Tarefas** devido a suas configurações `contextType`; “build” e “clean” são comandos de build e, portanto, são exibidos na seção de build na parte central do menu de contexto.  

  Agora que você associou os comandos de build personalizados ao arquivo, é possível designar o arquivo como o item de inicialização.  

1. No menu de contexto do arquivo, escolha **Definir como Item de Inicialização**.  

  ![Comando personalizado de tarefa de build](./media/VSIDE_Code_Tasks_CustTask4.png)

1. Na barra de ferramentas, escolha a seta suspensa ao lado do botão Iniciar. O item de inicialização agora aparece como uma opção.  

  ![Comando personalizado de tarefa de build](./media/VSIDE_Code_Tasks_CustTask5.png)

Agora é possível escolher o botão **Iniciar** ou a tecla **F5** para executar a base de código. É possível editar e depurar a base de código no Visual Studio, mesmo que o Visual Studio não reconheça as ferramentas de build da base de código. A saída da tarefa de build é exibida na janela **Saída** e os erros de build são exibidos na **Lista de Erros**. O arquivo de tarefa de build tasks.vs.json associa o loop de desenvolvimento interno do Visual Studio às ferramentas de build personalizadas usadas pela base de código.  

As tarefas de build personalizadas podem ser adicionadas a arquivos individuais ou a todos os arquivos de um tipo específico. Por exemplo, os arquivos do pacote NuGet podem ser configurados para terem uma tarefa “Restaurar Pacotes” ou todos os arquivos de origem podem ser configurados para terem uma tarefa de análise estática, como um linter para todos os arquivos .js.  

O Visual Studio dá suporte à substituição `$variable` do VSCode na raiz de tasks.vs.json, além de variáveis de ambiente (como `$env.var`) ou chaves.  

## <a name="specify-build-output"></a>Especificar a saída de build  
Se o projeto precisar ser compilado, será possível adicionar uma marca adicional chamada `output` ao arquivo tasks.vs.json. Vejamos um exemplo.  

`"output": "${workspaceRoot}\\bin\\hellomake.exe"`

A especificação da localização de saída notifica o Visual Studio em que localização ele deverá encontrar a saída de build do projeto.  

## <a name="tasksvsjson-file-location"></a>Localização do arquivo tasks.vs.json  
Por padrão, o arquivo tasks.vs.json está localizado em uma pasta oculta chamada `.vs`. Para exibir arquivos ocultos no Visual Studio, escolha o botão **Mostrar Todos os Arquivos** na barra de ferramentas do Gerenciador de Soluções.  

![Comando arbitrário de tarefa de build](./media/VSIDE_Code_Tasks_FileLocation.png)

O arquivo tasks.vs.json é oculto porque a maioria dos usuários geralmente não deseja verificá-lo no controle do código-fonte. No entanto, se desejar verificá-lo no controle do código-fonte, arraste o arquivo para a raiz do projeto na qual ele estará visível.  

Outros arquivos .json podem estar presentes na pasta .vs, mas os únicos que você deverá mover são os arquivos tasks.vs.json e launch.vs.json (se houver). O arquivo launch.vs.json configura o depurador do Visual Studio, enquanto o arquivo tasks.vs.json configura o build no Visual Studio.  

## <a name="see-also"></a>Consulte também
[Escrevendo código no editor de código e texto](../ide/writing-code-in-the-code-and-text-editor.md)
