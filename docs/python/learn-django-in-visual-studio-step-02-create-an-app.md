---
title: Tutorial – Saiba mais sobre Django no Visual Studio, etapa 2
description: Um passo a passo dos conceitos básicos do Django no contexto dos projetos do Visual Studio, mostrando especificamente as etapas para criar um aplicativo e usar modos de exibição e modelos.
ms.date: 04/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 4050694685302eb527b33d8810bc7f92974bc305
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
---
# <a name="tutorial-step-2-create-a-django-app-with-views-and-page-templates"></a>Etapa 2 do tutorial: Criar um aplicativo do Django com modos de exibição e modelos de página

**Etapa anterior: [Criar uma solução e um projeto do Visual Studio](learn-django-in-visual-studio-step-01-project-and-solution.md)**

O que você tem até o momento no projeto do Visual Studio são apenas os componentes do nível do site de um *projeto* do Django, que pode executar um ou mais *aplicativos* de Django. A próxima etapa é criar seu primeiro aplicativo com uma única página.

Nesta etapa, você aprenderá a:

> [!div class="checklist"]
> - Criar um aplicativo do Django com uma única página (etapa 2-1)
> - Executar o aplicativo do projeto do Django (etapa 2-2)
> - Renderizar um modo de exibição usando HTML (etapa 2-3)
> - Renderizar um modo de exibição usando um modelo de página do Django (etapa 2-4)

## <a name="step-2-1-create-an-app-with-a-default-structure"></a>Etapa 2-1: Criar um aplicativo com uma estrutura padrão

Um aplicativo do Django é um pacote separado em Python que contém um conjunto de arquivos relacionados para uma finalidade específica. Um projeto do Django pode conter qualquer número de aplicativos, o que reflete o fato de que um host da Web pode servir qualquer número de pontos de entrada separados de um único nome de domínio. Por exemplo, um projeto do Django para um domínio como contoso.com pode conter um aplicativo para www.contoso.com, um segundo aplicativo para support.contoso.com e um aplicativo de terceiro para docs.contoso.com. Nesse caso, o projeto do Django manipula o roteamento de URL e as configurações no nível do site (nos seus arquivos `urls.py` e `settings.py`), enquanto cada aplicativo tem seu próprio estilo e comportamento por meio dos seus roteamentos, modos de exibição, modelos, arquivos estáticos e interfaces administrativas internos.

Um aplicativo do Django normalmente começa com um conjunto padrão de arquivos. O Visual Studio fornece modelos de item para inicializar um aplicativo do Django dentro de um projeto do Django, junto com um comando de menu integrado que tem a mesma finalidade:

- Modelos: no **Gerenciador de Soluções**, clique com botão direito do mouse no projeto e selecione **Adicionar** > **Novo item**. Na caixa de diálogo **Adicionar Novo Item**, selecione o modelo "Django 1.9 App", especifique o nome do aplicativo no campo **Nome** e selecione **OK**.

- Integrado comando: no **Gerenciador de Soluções**, clique com o botão direito no projeto e selecione **Adicionar** > **Aplicativo do Django**. Esse comando solicita um nome e cria um aplicativo do Django 1.9.

    ![Comando de menu para adicionar um aplicativo do Django](media/django/step02-add-django-app-command.png)

Usando qualquer método, crie um aplicativo com o nome "HelloDjangoApp". O resultado é uma pasta no seu projeto com o nome que contém itens conforme descrito na tabela a seguir.

![Arquivos de aplicativo do Django no Gerenciador de Soluções](media/django/step02-django-app-in-solution-explorer.png)

| Item | Descrição |
| --- | --- |
| `__init.py__` | O arquivo que identifica o aplicativo como um pacote. |
| `migrations` | Uma pasta na qual o Django armazena scripts que atualizam o banco de dados para se alinhar com as alterações nos modelos. Em seguida, as ferramentas de migração do Django aplicam as alterações necessárias a qualquer versão anterior do banco de dados para que corresponda aos modelos atuais. Com as migrações, você mantém o foco nos seus modelos e permite que o Django lide com o esquema de banco de dados subjacente. As migrações são discutidas na etapa 6; no momento, a pasta contém simplesmente um arquivo `__init.py__` (o que indica que a pasta define seu próprio pacote de Python). |
| `templates` | Uma pasta para os modelos de página do Django que contém um único arquivo `index.html`. Modelos são blocos de HTML aos quais os modos de exibição podem adicionar informações para renderizar dinamicamente uma página. Modelos de página "variáveis", como `{{ content }}` em `index.html`, são espaços reservados para valores dinâmicos, conforme explicado mais adiante neste artigo (etapa 2). Normalmente, os aplicativos do Django criam um namespace para seus modelos, colocando-os em uma subpasta que corresponda ao nome do aplicativo. |
| `admin.py` | O arquivo Python no qual você estende a interface administrativa do aplicativo (veja a etapa 6), que é usada para ver e editar dados em um banco de dados. Inicialmente, esse arquivo contém apenas a instrução `from django.contrib import admin`. O Django inclui uma interface administrativa padrão por meio de entradas no arquivo `settings.py` do projeto do Django, que você pode ativar removendo a marca de comentário das entradas existentes em `urls.py`. |
| `apps.py` | Um arquivo Python que define uma classe de configuração para o aplicativo (veja abaixo, depois desta tabela). |
| `models.py` | Modelos são objetos de dados, identificados por funções, por meio dos quais os modos de exibição interagem com o banco de dados subjacente do aplicativo (veja a etapa 6). O Django fornece a camada de conexão de banco de dados para que os aplicativos não precisem se preocupar com esses detalhes. O arquivo `models.py` é um local padrão no qual criar os modelos e, inicialmente, contém apenas a instrução `from django.db import models`. |
| `tests.py` | Um arquivo Python que contém a estrutura básica de testes de unidade. |
| `views.py` | Os modos de exibição são o que você normalmente considera páginas da Web, que recebem uma solicitação HTTP e retornam uma resposta HTTP. Os modos de exibição costumam ser renderizados como HTML que os navegadores da Web conseguem exibir, mas um modo de exibição não precisa necessariamente ser visível (como um formulário intermediário). Um modo de exibição é definido por uma função Python que tem a responsabilidade de renderizar o HTML para enviar ao navegador. O arquivo `views.py` é um local padrão no qual criar modos de exibição e, inicialmente, contém apenas a instrução `from django.shortcuts import render`. |

O conteúdo de `app.py` aparece da seguinte maneira ao usar o nome "HelloDjangoApp":

```python
from django.apps import AppConfig

class HelloDjangoAppConfig(AppConfig):
    name = 'HelloDjango'
```

### <a name="question-is-creating-a-django-app-in-visual-studio-any-different-from-creating-an-app-on-the-command-line"></a>Pergunta: Há alguma diferença entre criar um aplicativo do Django no Visual Studio e criar um aplicativo na linha de comando?

Resposta: A execução do comando **Adicionar** > **Aplicativo do Django** ou o uso de **Adicionar** > **Novo Item** com um modelo de aplicativo do Django produz os mesmos arquivos que o comando do Django `manage.py startapp <app_name>`. A vantagem de criar o aplicativo no Visual Studio é que a pasta do aplicativo e todos os seus arquivos são automaticamente integrados ao projeto. Você pode usar o mesmo comando do Visual Studio para criar qualquer número de aplicativos em seu projeto.

## <a name="step-2-2-run-the-app-from-the-django-project"></a>Etapa 2-2: Executar o aplicativo a partir do projeto do Django

Neste ponto, se você executar novamente o projeto no Visual Studio (usando o botão de barra de ferramentas ou **Depurar** > **Iniciar depuração**), você ainda verá a página padrão. Nenhum conteúdo do aplicativo é exibido porque você precisa definir uma página específica do aplicativo e adicionar o aplicativo ao projeto do Django:

1. Na pasta `HelloDjangoApp`, modifique `views.py` para corresponder ao código a seguir, que define um modo de exibição chamado "index":

    ```python
    from django.shortcuts import render
    from django.http import HttpResponse

    def index(request):
        return HttpResponse("Hello, Django!")
    ```

1. Na pasta `BasicProject` (criada na etapa 1), modifique `urls.py` para corresponder pelo menos ao código a seguir (você pode manter os comentários instrutivos, se quiser):

    ```python
    from django.conf.urls import include, url
    import HelloDjangoApp.views

    # Django processes URL patterns in the order they appear in the array
    urlpatterns = [
        url(r'^$', HelloDjangoApp.views.index, name='index'),
        url(r'^home$', HelloDjangoApp.views.index, name='home'),
    ]
    ```

    Cada padrão de URL descreve os modos de exibição para os quais o Django direciona URLs específicos relacionados ao site (ou seja, a parte que segue "https://www.domain.com/"). A primeira entrada em `urlPatterns` que começa com a expressão regular `^$` é o roteamento para a raiz do site, "/". A segunda entrada, `^home$` direcionado especificamente para "/home". É possível ter qualquer número de roteamentos para o mesmo modo de exibição.

1. Execute o projeto novamente para ver a mensagem "Olá, Django!" conforme definida pelo modo de exibição. Pare o servidor ao terminar.

### <a name="commit-to-source-control"></a>Confirmar o controle do código-fonte

Como você já fez alterações no seu código e as testou com êxito, agora é o momento ideal para revisar e confirmar as alterações ao controle do código-fonte. Etapas posteriores neste tutorial lembram o momento apropriado para confirmar o controle do código-fonte novamente e encaminham você de volta para esta seção.

1. Selecione o botão de alterações na parte inferior do Visual Studio (círculos abaixo), que encaminha para o **Team Explorer**.

    ![Botão de alterações de controle do código-fonte na barra de status do Visual Studio](media/django/step02-source-control-changes-button.png)

1. No **Team Explorer**, digite uma mensagem de confirmação, como "Criar aplicativo inicial do Django" e selecione **Confirmar Tudo**. Quando a confirmação for concluída, será exibida a mensagem "Confirmação de <hash> criada localmente. Sincronize para compartilhar suas alterações com o servidor". Se você quiser enviar alterações por push para o repositório remoto, selecione **Sincronizar**, depois selecione **Push** em **Confirmações de Saída**. Também é possível acumular várias confirmações locais antes de enviar para o repositório remoto.

    ![Enviar confirmações por push para repositório remoto no Team Explorer](media/django/step02-source-control-push-to-remote.png)

### <a name="question-what-is-the-r-prefix-before-the-routing-strings-for"></a>Pergunta: Para que serve o prefixo "r" antes das cadeias de caracteres de roteamento?

Resposta: O prefixo "r" em uma cadeia de caracteres em Python significa "raw", que instrui o Python a não escapar de nenhum caractere dentro da cadeia. Como as expressões regulares usam muitos caracteres especiais, o uso do prefixo "r" torna muito mais fácil ler essas cadeias de caracteres do que se elas contivessem alguns caracteres de escape '\'.

### <a name="question-what-do-the--and--characters-mean-in-the-url-routing-entries"></a>Pergunta: O que significam os caracteres ^ e $ nas entradas de roteamento de URL?

Resposta: Nas expressões regulares que definem padrões de URL, ^ significa "início de linha" e $ significa "fim de linha", em que novamente as URLs são relativas à raiz do site (a parte que segue `https://www.domain.com/`). A expressão regular `^$` efetivamente significa "em branco" e, portanto, corresponde à URL completa `https://www.domain.com/` (nada é adicionado à raiz do site). O padrão `^home$` corresponde exatamente a `https://www.domain.com/home/`. (O Django não usa o / à direita na correspondência de padrões).

Se você não usar um $ à direita em uma expressão regular, assim como em `^home`, o padrão de URL corresponderá a *qualquer* URL que comece com "home", como "home", "homework", "homestead" e "home192837".

Para fazer experiências com expressões regulares diferentes, use ferramentas online, como [regex101.com](https://regex101.com) em [pythex.org](http://www.pythex.org).

## <a name="step-2-3-render-a-view-using-html"></a>Etapa 2-3: Renderizar um modo de exibição usando HTML

A função `index` que você tem até agora em `views.py` gera nada mais que uma resposta HTTP de texto simples para a página. A maioria das páginas da Web reais responde com páginas HTML avançadas que geralmente incorporam dados dinâmicos. Na verdade, a principal razão para definir um modo de exibição usando uma função é poder gerar esse conteúdo dinamicamente.

Como o argumento para `HttpResponse` é apenas uma cadeia de caracteres, você pode criar qualquer HTML que quiser em uma cadeia de caracteres. Como um exemplo simples, substitua a função `index` pelo código a seguir (mantendo as instruções `from` existentes), que gera uma resposta HTML usando o conteúdo dinâmico que é atualizado toda vez que você atualiza a página:

```python
from datetime import datetime

def index(request):
    now = datetime.now()

    html_content = "<html><head><title>Hello, Django</title></head><body>"
    html_content += "<strong>Hello Django!</strong> on " + now.strftime("%A, %d %B, %Y at %X")
    html_content += "</body></html>"

    return HttpResponse(html_content)
```

Execute o projeto novamente para ver uma mensagem como "**Olá, Django!** na segunda-feira, 16 de abril de 2018, às 16:28:10". Atualize a página para atualizar a hora e confirme que o conteúdo está sendo gerado com cada solicitação. Pare o servidor ao terminar.

> [!Tip]
> Um atalho para parar e reiniciar o projeto é usar o comando de menu **Depurar**  >  **Reiniciar** (Ctrl+Shift+F5) ou o botão de reinicialização na barra de ferramentas de depuração:
>
> ![Botão de reinicialização na barra de ferramentas de depuração no Visual Studio](media/debugging-restart-toolbar-button.png)

## <a name="step-2-4-render-a-view-using-a-page-template"></a>Etapa 2-4: Renderizar um modo de exibição usando um modelo de página

Gerar HTML no código funciona bem para páginas muito pequenas, mas à medida que as páginas ficam mais sofisticadas, normalmente é ideal manter as partes HTML estáticas da sua página (junto com referências a arquivos CSS e JavaScript) como "modelos de página" nos quais você insere conteúdo dinâmico gerado por código. Na seção anterior, apenas a data e a hora da chamada `now.strftime` são dinâmicas, o que significa que todos os outros conteúdos podem ser colocados em um modelo de página.

Um modelo de página do Django é um bloco de HTML que pode conter qualquer número de tokens de substituição chamados "variáveis" que são delineados por `{{` e `}}`, como em `{{ content }}`. O módulo de modelagem do Django substitui as variáveis por conteúdo dinâmico que você fornece no código.

As etapas a seguir demonstram o uso de modelos de página:

1. Na pasta `BasicProject`, que contém o projeto do Django, abra o arquivo `settings.py` e adicione o nome do aplicativo, "HelloDjangoApp", à lista `INSTALLED_APPS`. A adição do aplicativo à lista informa ao projeto do Django que há uma pasta com esse nome contendo um aplicativo:

    ```python
    INSTALLED_APPS = [
        'HelloDjangoApp',
        # Other entries...
    ]
    ```

1. Também em `settings.py`, garanta que o objeto `TEMPLATES` contenha a seguinte linha (incluída por padrão), que instrui o Django a procurar por modelos na pasta `templates` de um aplicativo instalado:

    ```json
    'APP_DIRS': True,
    ```

1. Na pasta `HelloDjangoApp`, abra o `templates/index.html` arquivo de modelo de página para observar se ele contém uma variável `{{ content }}`:

    ```html
    <html>
    <head><title></title></head>

    <body>

    {{ content }}

    </body>
    </html>
    ```

1. Na pasta `HelloDjangoApp`, abra `views.py` e substitua a função `index` pelo código a seguir, que usa a função auxiliar `django.shortcuts.render`. O auxiliar `render` fornece uma interface simplificada para trabalhar com modelos de página. Mantenha todas as instruções `from` existentes.

    ```python
    from django.shortcuts import render   # Added for this step

    def index(request):
        now = datetime.now()

        return render(
            request,
            "index.html",  # Relative path from the 'templates' folder to the template file
            {
                'content': "<strong>Hello Django!</strong> on " + now.strftime("%A, %d %B, %Y at %X")
            }
        )
    ```

    O primeiro argumento para `render`, como você pode ver, é o objeto de solicitação, seguido pelo caminho relativo para o arquivo de modelo dentro da pasta `templates` do aplicativo. Um arquivo de modelo recebe o nome do modo de exibição ao qual ele oferece suporte, se apropriado. O terceiro argumento para `render` é um dicionário de variáveis ao qual o modelo se refere. Você pode incluir objetos no dicionário e, nesse caso, uma variável no modelo pode se referir a `{{ object.property }}`.

1. Execute o projeto e observe o resultado. Você deve ver uma mensagem semelhante àquela vista na etapa 2-2, indicando que o modelo funciona.

    Observe, no entanto, que o HTML usado na propriedade `content` é processado apenas como texto simples, porque a função `render` escapa automaticamente esse HTML. Embora você possa fazer escapes, o ideal é evitar o uso de HTML embutido. A formatação e o estilo são melhor mantidos no modelo de página, não no código, e é simples criar variáveis adicionais quando necessário.

    Por exemplo, altere `templates/index.html` para corresponder à seguinte marcação, que adiciona um título de página e mantém toda a formatação no modelo de página:

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
        </head>
        <body>
            <strong>{{ message }}</strong>{{ content }}
        </body>
    </html>
    ```

    Depois, escreva a função do modo de exibição `index` da seguinte maneira, para fornecer valores para todas as variáveis no modelo de página:

    ```python
    def index(request):
        now = datetime.now()

        return render(
            request,
            "index.html",  # Relative path from the 'templates' folder to the template file
            {
                'title' : "Hello Django",
                'message' : "Hello Django!",
                'content' : " on " + now.strftime("%A, %d %B, %Y at %X")
            }
        )
    ```

1. Pare o servidor e reinicie o projeto. Observe que a página agora é renderizada corretamente:

    ![Aplicativo em execução usando o modelo](media/django/step02-result.png)

1. <a name="template-namespacing"></a>Como etapa final, mova seus modelos para uma subpasta com o mesmo nome do seu aplicativo, o que cria um namespace e evita possíveis conflitos com outros aplicativos que você venha a adicionar ao projeto. Ou seja, crie uma subpasta em `templates` chamada `HelloDjangoApp`, mova `index.html` para essa subpasta e modifique a função do modo de exibição `index` para se referir ao novo caminho do modelo, `HelloDjangoApp/index.html`. Em seguida, execute o projeto, verifique se a página é renderizada corretamente e pare o servidor.

1. Confirme suas alterações no controle do código-fonte e atualize seu repositório remoto, se desejado, conforme descrito na [etapa 2-2](#commit-to-source-control).

### <a name="question-do-page-templates-have-to-be-in-a-separate-file"></a>Pergunta: Os modelos de páginas precisam ficar em um arquivo separado?

Resposta: Embora os modelos geralmente sejam mantidos em arquivos HTML separados, também é possível usar um modelo embutido. No entanto, é recomendável usar um arquivo separado para manter uma distinção clara entre marcação e código.

### <a name="question-must-templates-use-the-html-file-extension"></a>Pergunta: Os modelos devem usar a extensão de arquivo .html?

Resposta: A extensão `.html` para arquivos de modelo de página é totalmente opcional, porque você sempre identifica o caminho relativo exato para o arquivo no segundo argumento para a função `render`. No entanto, o Visual Studio (e outros editores) costuma fornecer recursos como preenchimento de código e coloração de sintaxe com arquivos `.html`, o que supera o fato de os modelos de página não serem estritamente HTML.

De fato, quando você está trabalhando com um projeto do Django, o Visual Studio detecta automaticamente quando o arquivo HTML que você está editando é, na verdade, um modelo do Django e fornece determinados recursos de preenchimento automático. Por exemplo, quando você começa a digitar um comentário de modelo de página do Django, `{#`, o Visual Studio fornece automaticamente os caracteres de fechamento `#}`. Os comandos **Comentar Seleção** e **Remover Marca de Comentário da Seleção** (no menu **Editar** > **Avançado** e na barra de ferramentas) também usam comentários de modelo em vez de comentários em HTML.

### <a name="question-when-i-run-the-project-i-see-an-error-that-the-template-cannot-be-found-whats-wrong"></a>Pergunta: Quando executo o projeto, é exibido um erro indicando que não é possível encontrar o modelo. Qual é o problema?

Resposta: Se forem exibidos erros indicando que o modelo não pode ser encontrado, certifique-se de ter adicionado o aplicativo a `settings.py` do projeto do Django na lista `INSTALLED_APPS`. Sem essa entrada, o Django não conseguirá procurar na pasta `templates` do aplicativo.

### <a name="question-why-is-template-namespacing-important"></a>Pergunta: Por que o namespace do modelo é importante?

Resposta: Quando o Django procura por um modelo referido na função `render`, ele usa qualquer arquivo encontrado primeiro que corresponda ao caminho relativo. Se você tiver vários aplicativos do Django no mesmo projeto que usem as mesmas estruturas de pasta para os modelos, é provável que um aplicativo use inadvertidamente um modelo de outro aplicativo. Para evitar esses erros, sempre crie uma subpasta na pasta `templates` do aplicativo que corresponda ao nome do aplicativo para evitar toda e qualquer duplicação.

## <a name="next-steps"></a>Próximas etapas

> [!div class="nextstepaction"]
> [Fornecer arquivos estáticos, adicionar páginas e usar a herança do modelo](learn-django-in-visual-studio-step-03-serve-static-files-and-add-pages.md)

## <a name="going-deeper"></a>Aprofundando-se

- [Como gravar seu primeiro aplicativo do Django, parte 1 – (modos de exibição)](https://docs.djangoproject.com/en/2.0/intro/tutorial01/#write-your-first-view) (docs.djangoproject.com)
- Para conhecer mais recursos de modelos do Django, como os elementos inclui e herança, confira [A linguagem de modelos do Django](https://docs.djangoproject.com/en/2.0/ref/templates/language/) (docs.djangoproject.com)
- [Treinamento em expressões regulares no inLearning](https://www.linkedin.com/learning/topics/regular-expressions) (LinkedIn)
- Código-fonte do tutorial no GitHub: [Microsoft/python-sample-vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django)