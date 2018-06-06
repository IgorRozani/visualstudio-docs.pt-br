---
title: Como definir uma linguagem específica do domínio
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.domainrelationship
- vs.dsltools.dsldesigner.domainclass
- vs.dsltools.dsldesigner.domaintype
helpviewer_keywords:
- Domain-Specific Language, domain class
- Domain-Specific Language, external types
- Domain-Specific Language, relationships
- Domain-Specific Language, domain properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: f870bce3abea444d6a04c0076d7110345c55ea7c
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750422"
---
# <a name="how-to-define-a-domain-specific-language"></a>Como definir uma linguagem específica do domínio
Para definir uma linguagem específica de domínio (DSL), você pode criar uma solução do Visual Studio de um modelo. A parte fundamental da solução é o diagrama de Definição de DSL, que é armazenado em DslDefinition.dsl. A Definição de DSL define as classes e formas da DSL. Depois de modificar e adicionar esses elementos, você pode adicionar o código do programa para personalizar a DSL com mais detalhes.

Se você for novo no DSLs, recomendamos que você leia o **laboratório de ferramentas de DSL**, que pode ser encontrado neste site: [Visualizaton e SDK de modelagem](http://go.microsoft.com/fwlink/?LinkID=186128)

##  <a name="templates"></a> Seleção de uma solução de modelo
 Para definir uma DSL, é necessário ter instalados os seguintes componentes:

|||
|-|-|
|Visual Studio|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|SDK de Visualização e Modelagem do Visual Studio||


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]


 Para criar uma nova linguagem específica de domínio, você deve criar uma nova solução do Visual Studio usando o modelo de projeto de linguagem específica de domínio.

#### <a name="to-create-a-dsl-solution"></a>Para criar uma solução DSL

1.  Criar uma solução com o **linguagem específica de domínio** modelo, que pode ser encontrado em **outros tipos/extensibilidade de projeto** no **novo projeto** caixa de diálogo.

     ![Criar caixa de diálogo DSL](../modeling/media/create_dsldialog.png)

     Quando você clica em **Okey**, o **Assistente de linguagem específica de domínio** abre e exibe uma lista de soluções do modelo DSL.

2.  Clique em cada modelo para ver uma descrição. Escolha a solução que mais se assemelha ao que você deseja criar.

     Cada modelo DSL define uma DSL de trabalho básica. Você editará essa DSL para atender aos seus próprios requisitos.

     Clique em cada exemplo para obter mais informações.

    -   Selecione **tarefa de fluxo** para criar uma DSL com raias. As raias são partições verticais ou horizontais do diagrama.

    -   Selecione **modelos de componente** para criar uma DSL com portas. As portas são pequenas formas na borda de uma forma maior.

    -   Selecione **diagramas de classe** para definir uma DSL com formas do compartimento. As formas do compartimento contêm listas de itens.

    -   Selecione **mínimo idioma** em outros casos, ou se você não tiver certeza.

    -   Selecione **mínimo Designer do WinForm** ou **mínimo WPF Designer** para criar uma DSL que é exibida em uma superfície de Windows Forms ou WPF. Você precisará gravar um código para definir o editor. Para mais informações, consulte os seguintes tópicos:

         [Criando uma linguagem específica de domínio baseada no Windows Forms](../modeling/creating-a-windows-forms-based-domain-specific-language.md)

         [Criando uma linguagem específica de domínio baseada no WPF](../modeling/creating-a-wpf-based-domain-specific-language.md)

3.  Insira uma extensão de nome de arquivo para sua DSL na página do assistente apropriada. Essa é a extensão que será usada pelos arquivos que contêm as instâncias de sua DSL.

    -   Escolha uma extensão de nome de arquivo que não esteja associada a nenhum aplicativo em seu computador ou em nenhum computador que você deseja instalar a DSL. Por exemplo, **docx** e **htm** seria inaceitável arquivo extensões de nome.

    -   O assistente o avisará se a extensão inserida está sendo usada como uma DSL. Considere usar uma extensão de nome de arquivo diferente. Também é possível redefinir a instância Experimental do SDK do Visual Studio para limpar os designers experimentais antigos. Clique em **iniciar**, clique em **todos os programas**, **SDK do Microsoft Visual Studio 2010**, **ferramentas**e, em seguida, **redefinição da Microsoft Instância do Visual Studio 2010 Experimental**.

4.  Você pode ajustar as configurações nas outras páginas ou manter os valores padrão.

5.  Clique em **Finalizar**.

     O assistente cria uma solução que contém dois ou três projetos e gera código a partir da definição da DSL.

 A interface do usuário agora se assemelha à imagem a seguir.

 ![designer de DSL](../modeling/media/dsl_designer.png)

 Essa solução define uma linguagem específica de domínio. Para obter mais informações, consulte [visão geral da Interface do usuário específica de domínio idioma ferramentas](../modeling/overview-of-the-domain-specific-language-tools-user-interface.md).

### <a name="test-the-solution"></a>Testar a solução
 A solução de modelo fornece uma DSL de trabalho, que pode ser modificada ou usada da forma como se encontra.

 Para testar a solução, pressione F5 ou CTRL+F5. Uma nova instância do Visual Studio é aberto no modo de avaliação.

 Na nova instância do Visual Studio, no Gerenciador de soluções, abra o arquivo de exemplo. Ele se abre como um diagrama, com uma caixa de ferramentas.

 Se você executar uma solução que você criou do **mínimo idioma** modelo, o Visual Studio experimental será parecida com o exemplo a seguir:

 ![](../modeling/media/dsl_min.png)

 Experimente com as ferramentas. Crie elementos e os conecte.

 Feche a instância experimental do Visual Studio.

> [!NOTE]
>  Após modificar a DSL, não será possível mais ver as formas no arquivo de teste Exemplo. Entretanto, poderá criar novos elementos.

### <a name="modifying-the-template-dsl"></a>Modificando a DSL do modelo
 Renomeie e mantenha algumas ou todas as classes de domínio e classes de formas na definição da DSL do modelo. Os novos nomes de classes devem ser nomes de CLR válidos, sem espaços ou pontuação.

 É especialmente útil manter estas classes:

-   A classe raiz é exibido no canto superior esquerdo do diagrama de definição de DSL, em **Classes e relacionamentos**. Renomeie-a com um nome diferente da DSL. Por exemplo, uma DSL denominada **MusicLibrary** pode ter uma classe raiz denominada **música**.

-   A classe do diagrama aparece na parte inferior direita do diagrama de definição de DSL, no **elementos de diagrama** coluna. Talvez seja necessário rolar para a direita para vê-la. Ele geralmente é denominado * YourDsl ***diagrama**.

-   Se você usou o **tarefa de fluxo** modelo e você deseja criar diagramas com raias, manter e renomeie a classe de domínio de ator e ActorSwimlane forma.

 Exclua ou renomeie outras classes para atender aos seus requisitos.

##  <a name="patterns"></a> Padrões para definir uma DSL
 Recomendamos que você desenvolva uma DSL adicionando ou ajustando um ou dois recursos por vez. Adicione um recurso, execute a DSL e teste-a, em seguida, adicione um ou dois recursos adicionais. Um recurso típico de sua DSL pode ser:

-   Uma classe de domínio, a relação de incorporação que conecta o elemento ao modelo, a forma necessária para exibir elementos dessa classe no diagrama e a ferramenta do elemento que permite aos usuários criar elementos.

-   As propriedades de domínio de uma classe de domínio e os decoradores que as exibem em uma forma.

-   Uma relação de referência e o conector que a exibe no diagrama, bem como a ferramenta de conector que permite aos usuários criar vínculos.

-   Uma personalização que exige código do programa, tal como uma restrição de validação ou um comando de menu.

 As seções a seguir descrevem como construir os tipos mais úteis de recursos DSL. Há vários outros padrões com os quais uma DSL pode ser construída, mas esses são os usados com mais frequência.

> [!NOTE]
>  Depois de adicionar um recurso, não se esqueça de clicar em **transformar todos os modelos** na barra de ferramentas do Gerenciador de soluções antes de compilar e executar seu DSL.

 A figura a seguir mostra as classes e relações que fazem parte da DSL usada de exemplo neste tópico.

 ![Relações de referência e inserindo](../modeling/media/music_classes.png)

 A próxima figura é um modelo de exemplo desta DSL:

 ![Modelo de instância de DSL gerado](../modeling/media/music_instance.png)

> [!NOTE]
>  "Modelo" refere-se a uma instância de sua DSL que os usuários criam e geralmente é exibida como um diagrama. Este tópico discute o diagrama da Definição de DSL e os diagramas de modelo que aparecem quando sua DSL é usada.

##  <a name="classes"></a> Definindo Classes de domínio
 As classes de domínio representam os conceitos de sua DSL. As instâncias são *elementos do modelo*. Por exemplo, em um **MusicLibrary** DSL você pode ter Classes de domínio chamado **álbum** e **música**.

 Para criar uma classe de domínio, você pode arrastar do **classe de domínio nomeado** ferramenta ao diagrama e, em seguida, renomeie a classe.

 Para obter mais informações, consulte [propriedades de Classes de domínio](../modeling/properties-of-domain-classes.md).

### <a name="create-an-embedding-relationship-for-each-domain-class"></a>Criar uma relação de incorporação para cada classe de domínio
 Cada classe de domínio, exceto a classe raiz, deve ser o destino de pelo menos uma relação incorporada ou ela deve herdar de uma classe que seja o destino de uma relação de incorporação.

 Em um modelo, todo elemento de modelo é um nó em uma única árvore de relações de incorporação. A origem e o destino de uma relação de incorporação são geralmente chamados de pai e filho.

 A seleção de um pai para uma classe de domínio depende de como você deseja que os tempos de vida de seus elementos dependam de outros elementos. Se um nó de uma árvore for excluído, sua subárvore geralmente também será excluída. Classes de elementos que tenham uma existência independente são, portanto, inseridas diretamente na classe raiz.

 Geralmente, ao exibir um elemento dentro de outro elemento, você deseja indicar uma relação de propriedade. Nesse caso, a classe pai mais apropriada é a classe do contêiner. A exceção é quando o item que você vê dentro de um contêiner é, na verdade, apenas um vínculo de referência a um elemento independente. Nesse caso, a exclusão do contêiner exclui a referência, mas não seu destino.

 Nos padrões de definição de DSL descritos neste tópico, assumiremos que os elementos exibidos dentro de um contêiner serão excluídos quando o contêiner for excluído. Esquemas mais complexos são possíveis e podem ser obtidos pela definição de regras.

|Como o elemento é exibido|Classe pai (incorporação)|Exemplo no modelo de solução DSL|
|------------------------------|--------------------------------|--------------------------------------|
|Forma no diagrama.<br /><br /> Raia.|Classe raiz da DSL.|Linguagem Mínima.<br /><br /> Fluxo de Tarefa: classe Ator.|
|Forma na raia.|Classe de domínio de elementos que são exibidos como raias.|Fluxo de Tarefa: classe Tarefa.|
|Item na lista em forma, em que o item será excluído se o contêiner for excluído.<br /><br /> Porta na borda da forma.|Classe de domínio mapeada conforme a forma do contêiner.|Diagrama de classe: classe Atributo.<br /><br /> Diagrama de componente: classe Porta.|
|Item na lista, não excluído se o contêiner for excluído.|Classe raiz da DSL.<br /><br /> A lista exibe vínculos de referência.||
|Não exibido diretamente.|A classe da qual ela forma parte.||

 No exemplo de Biblioteca de Músicas, Álbuns são exibidos como retângulos nos quais os títulos das Canções são listados. Portanto, o pai de Álbum é a classe raiz Música e o pai de Canção é Álbum.

 Para criar uma classe de domínio e seu inserindo ao mesmo tempo, clique o **inserindo relação** ferramenta, em seguida, clique na classe pai e, em seguida, clique em uma parte em branco do diagrama.

 Geralmente não é necessário ajustar o nome da relação de incorporação e de suas funções, pois acompanharão os nomes de classes automaticamente.

 Para obter mais informações, consulte [propriedades de domínio relações](../modeling/properties-of-domain-relationships.md) e [propriedades de funções de domínio](../modeling/properties-of-domain-roles.md).

> [!NOTE]
>  Incorporação não é o mesmo que herança. Os filhos em uma relação de incorporação não herdam recursos de seus pais.

### <a name="add-domain-properties-to-each-domain-class"></a>Adicionar propriedades de domínio em cada classe de domínio
 As propriedades de domínio armazenam valores. Os exemplos são: Nome, Título, Data de Publicação.

 Clique em **propriedades do domínio** na classe, pressione a tecla ENTER e, em seguida, digite o nome de uma propriedade. O tipo padrão de uma propriedade de domínio é a Cadeia de Caracteres. Se você quiser alterar o tipo, selecione a propriedade de domínio e defina o **tipo** no **propriedades** janela. Se o tipo que você deseja não estiver na lista suspensa, consulte [adicionar tipos de propriedade](#addTypes).

 **Defina uma propriedade de nome do elemento.** Selecione uma propriedade de domínio que possa ser usada para identificar elementos no gerenciador de linguagens. Por exemplo, na classe de domínio Canção que você poderia escolher a propriedade de domínio Título. No **propriedades** janela, defina **é o nome do elemento** para `true`.

### <a name="create-derived-domain-classes"></a>Criar classes de domínio derivadas
 Se você deseja que uma classe de domínio tenha variantes que herdam suas propriedades e relações, crie classes que derivam dela. Por exemplo, Álbum pode ter as classes derivadas WMA e MP3.

 Criar a classe derivada usando o **classe de domínio** ferramenta.

 Clique o **herança** ferramenta, clique na classe derivada e, em seguida, clique na classe base.

 É recomendável configurar o **modificador de herança** da classe base para **abstrata**. Se você acha que talvez precise de instâncias da classe base, considere, em vez disso, criar uma classe derivada separada para elas.

 As classes derivadas herdam as propriedades e funções de suas classes base.

### <a name="tidy-the-dsl-definition-diagram"></a>Organizar o diagrama de Definição de DSL
 Ao adicionar relações, algumas de suas classes aparecerão em mais de um lugar. Para reduzir o número de aparências e tornar esse diagrama mais amplo, clique com botão direito a classe de destino de uma relação e, em seguida, clique em **colocar árvore aqui**. O efeito oposto, com o botão direito a classe de destino de uma relação e clique em **divisão árvore**. Se você não vir esses comandos de menu, certifique-se de que apenas a classe de domínio esteja escolhida.

 Use CTRL+Seta para Cima e CTRL+Seta para Baixo para mover as classes de domínio e as classes de forma.

### <a name="test-the-domain-classes"></a>Testar as classes de domínio

##### <a name="to-test-the-new-domain-classes"></a>Para testar as novas classes de domínio

1.  **Clique em transformar todos os modelos** na barra de ferramentas do Gerenciador de soluções, para gerar o código de designer DSL. Você pode automatizar esta etapa. Para obter mais informações, consulte [como automatizar a transformação de todos os modelos](http://msdn.microsoft.com/b63cfe20-fe5e-47cc-9506-59b29bca768a).

2.  **Compilar e executar o DSL.** Pressione F5 ou CTRL + F5 para executar uma nova instância do Visual Studio no modo de avaliação. Na instância experimental do Visual Studio, abra ou crie um arquivo que tem a extensão de nome de arquivo de seu DSL.

3.  **Abra o Gerenciador.** No lado do diagrama está janela do Gerenciador de idioma, que geralmente é chamada *YourLanguage* Explorer. Se você não vir essa janela, ela pode estar em uma guia no Gerenciador de Soluções. Se você não é possível encontrá-lo, no **exibição** , aponte para **outras janelas**e, em seguida, clique em *YourLanguage* **Explorer**.

     Seu gerenciador apresentará uma exibição em árvore do modelo.

4.  **Crie novos elementos.** Clique com botão direito no nó raiz na parte superior e, em seguida, clique em **adicionar novo * YourClass*.

     Uma nova instância de sua classe aparecerá no Gerenciador de linguagens.

5.  Verifique se cada instância possui um nome diferente ao criar novas instâncias. Isso ocorrerá somente se você tiver definido o **é o nome do elemento** sinalizador em uma propriedade de domínio.

6.  **Examine as propriedades do domínio. Com uma instância da classe selecionada,** Inspecione a janela Propriedades. Ela deve mostrar as propriedades de domínio definidas nesta classe de domínio.

7.  **Salve o arquivo, feche-o e reabra-**. Após a expansão dos nós, todas as instâncias criadas devem estar visíveis no gerenciador.

##  <a name="shapes"></a> Definindo as formas no diagrama
 Você pode definir as classes de elementos que aparecem em um diagrama como retângulos, elipses ou ícones.

#### <a name="to-define-a-class-of-elements-that-appear-as-shapes-on-a-diagram"></a>Para definir uma classe de elementos que aparece como formas em um diagrama

1.  **Definir e testar uma classe de domínio, conforme descrito em**[Definindo Classes de domínio](#classes) **.**

    -   O pai da classe deve ser a classe raiz. Ou seja, deve haver uma relação de incorporação entre a classe raiz e a nova classe de domínio.

    -   Se o seu diagrama tiver raias, o pai pode ser a classe de domínio que é mapeada para uma raia. Antes de continuar com esse procedimento, consulte [definindo uma DSL com raias](#swimlanes).

2.  **Adicionar uma classe de forma** representar os elementos do diagrama de modelo. Arraste de uma das seguintes ferramentas para o diagrama de Definição de DSL:

    -   **Forma de geometria** fornece um retângulo ou uma elipse.

    -   **Forma da imagem** exibe uma imagem que você fornecer.

    -   **Forma do compartimento** é um retângulo que contém uma ou mais listas de itens.

     Renomeie a classe de formas, a qual aparecerá no lado direito do diagrama de Definição de DSL, em Formas e Conectores.

3.  **Definir uma imagem, se você tiver criado uma forma de imagem**.

    1.  Crie um arquivo de imagem de qualquer tamanho. Os formatos BMP, JPEG, GIF e EMF são compatíveis.

    2.  No Gerenciador de Soluções, adicione o arquivo à solução em Dsl\Resources.

    3.  Retorne ao diagrama de Definição de DSL e selecione a nova classe de forma de imagem.

    4.  Na janela Propriedades, clique o **imagem** propriedade.

    5.  No **Selecionar imagem** caixa de diálogo, clique no menu suspenso em **nome de arquivo**e selecione a imagem.

4.  **Adicione decoradores de texto para a forma, para exibir as propriedades do domínio.**

     Para exibir o nome ou o título do elemento de modelo, você provavelmente precisará de pelo menos um decorador de texto.

     Clique com botão direito do cabeçalho da classe shape, aponte para **adicionar**e, em seguida, clique em **texto decorador**. Defina o nome do decorador e no conjunto de janela de propriedades seu **posição**.

5.  **Conecte cada forma com um mapa de elemento de diagrama para a classe de domínio deve exibir**.

     Clique o **mapa de elemento de diagrama** ferramenta, em seguida, a classe de domínio, clique a classe de forma.

6.  **Mapear as propriedades para decoradores o texto.**

    1.  Selecione a linha cinza entre a classe de domínio e a classe de forma que representa o mapa de elemento do diagrama.

    2.  No **DSL detalhes** janela, clique no **decorador mapas** guia. Se você não vir o **DSL detalhes** janela, no **exibição** , aponte para **outras janelas** e, em seguida, clique em **DSL detalhes**. Normalmente é necessário aumentar a parte superior desta janela para ver todo o seu conteúdo.

    3.  Escolha o nome de um decorador. Em **Exibir propriedade**, selecione o nome de uma propriedade da classe de domínio. Repita isso para cada decorador.

         Se você quiser exibir uma propriedade de um elemento relacionado, clique em navegador de árvore da lista suspensa em **caminho para exibir a propriedade**.

    4.  Certifique-se de que haja uma marca de seleção ao lado de cada nome de decorador.

     ![Janela de detalhes de DSL e mapeamentos de forma](../modeling/media/dsldetailswindow.png)

7.  **Tornar um item de caixa de ferramentas para criar elementos da classe de domínio.**

    1.  Em **DSL Explorer**, expanda o **Editor** nó e todos os seus nós sub.

    2.  Clique com botão direito no nó em **guias da caixa de ferramentas** que tem o mesmo nome de seu DSL, por exemplo MusicLibrary. Clique em **adicionar elemento ferramenta**.

        > [!NOTE]
        >  Se você com o botão direito do **ferramentas** nó, você não verá **adicionar elemento ferramenta**. Em vez disso, clique no nó acima dele.

    3.  Na janela Propriedades, com a nova ferramenta de elemento selecionada, defina **classe** para a classe de domínio que você tiver adicionado recentemente.

    4.  Definir **legenda** e **dica de ferramenta**.

    5.  Definir **ícone caixa de ferramentas** a um ícone que será exibido na caixa de ferramentas. Você pode configurá-lo como um novo ícone ou um ícone já usado por outra ferramenta.

         Para criar um novo ícone, abra Dsl\Resources em **Gerenciador de soluções**. Copie e cole um dos arquivos BMP da ferramenta de elemento existente. Renomeie a cópia colada e clique duas vezes para editá-la.

         Retornar ao diagrama de definição de DSL, selecione a ferramenta e na janela Propriedades, clique em **[...]**  na **ícone caixa de ferramentas**. No **Selecione Bitmap** caixa de diálogo, selecione seu. Arquivo BMP no menu suspenso.

 Para obter mais informações, consulte [propriedades de formas de geometria](../modeling/properties-of-geometry-shapes.md) e [formas de propriedades de imagem](../modeling/properties-of-image-shapes.md).

#### <a name="to-test-shapes"></a>Para testar as formas

1.  **Clique em transformar todos os modelos** na barra de ferramentas do Gerenciador de soluções, para gerar o código de designer DSL.

2.  **Compilar e executar o DSL.** Pressione F5 ou CTRL + F5 para executar uma nova instância do Visual Studio no modo de avaliação. Na instância experimental do Visual Studio, abra ou crie um arquivo que tem a extensão de nome de arquivo de seu DSL.

3.  **Verifique se as ferramentas de elemento aparecem na caixa de ferramentas.**

4.  **Criar formas** arrastando-se de uma ferramenta para o diagrama de modelo.

5.  **Verifique se cada decorador de texto aparece,** e que:

    1.  Você pode editá-lo, a menos que você definiu o **é somente leitura do UI** sinalizador na propriedade de domínio.

    2.  Quando você edita a propriedade na janela Propriedades ou no decorador, a outra exibição é atualizada.

 Depois de testar inicialmente uma forma, talvez você queira ajustar algumas de suas propriedades e adicionar outros recursos mais avançados. Para obter mais informações, consulte [personalizar e estender uma linguagem específica do domínio](../modeling/customizing-and-extending-a-domain-specific-language.md).

##  <a name="references"></a> Definindo relações de referência
 Você pode definir uma relação de referência entre qualquer classe de domínio de origem e qualquer classe de domínio de destino. As relações de referência são geralmente exibidas em um diagrama como conectores, que são linhas entre formas.

 Por exemplo, se Álbuns de música e Artistas forem exibidos como formas no diagrama, será possível definir um relação chamada ArtistsAppearedOnAlbums, a qual vincula os Artistas aos Álbuns nos quais eles trabalharam. Veja o exemplo na figura.

 ![Modelo de instância de DSL gerado](../modeling/media/music_instance.png)

 As relações de referência também podem vincular elementos do mesmo tipo. Por exemplo, em uma DSL que representa uma árvore genealógica, a relação entre pais e seus filhos é uma relação de referência de Pessoa a Pessoa.

### <a name="define-a-reference-relationship"></a>Definir uma relação de referência
 Clique na ferramenta Relação de Referência, na classe de domínio de origem da relação e na classe de domínio de destino. A classe de destino pode ser a mesma que a classe de origem.

 Cada relação possui duas funções, representadas pela linha de cada lado da caixa de relação. Você pode selecionar cada função e configurar suas propriedades na janela Propriedades.

 **Considere a possibilidade de renomear as funções**. Por exemplo, em uma relação entre Pessoa e Pessoa, talvez você queira alterar os nomes padrão para Pais e Filhos, Gerente e Subordinados, Professor e Aluno, etc.

 **Ajustar multiplicidades de cada função**, se necessário. Se você deseja que cada Pessoa tenha no máximo um Gerente, configure a multiplicidade que aparece abaixo do rótulo Gerente no diagrama como 0..1.

 **Adicione propriedades de domínio para a relação.** Na figura, a relação Artista-Álbum tem uma propriedade de função.

 **Defina a propriedade permite duplicatas da relação,** se mais de um link da mesma classe pode existir entre o mesmo par de elementos de modelo. Por exemplo, você poderia permitir que um Professor ensinasse mais de uma Matéria para o mesmo Aluno.

 ![Mapas de formas para conectores](../modeling/media/music_connector.png)

 Para obter mais informações, consulte [propriedades de domínio relações](../modeling/properties-of-domain-relationships.md) e [propriedades de funções de domínio](../modeling/properties-of-domain-roles.md).

### <a name="define-a-connector-to-display-the-relationship"></a>Definir um conector para exibir a relação
 Um conector exibe uma linha entre duas formas no diagrama do modelo.

 Arraste o **conector** ferramenta para o diagrama de definição de DSL.

 Adicione decoradores de texto se desejar exibir rótulos no conector. Configure suas posições. Para permitir que o usuário move um decorador de texto, defina seu **é Moveable** propriedade.

 Use o **mapa de elemento de diagrama** ferramenta para vincular o conector para a relação de referência.

 Com o mapa de elemento de diagrama selecionado, abra o **DSL detalhes** janela e abra o **decorador mapas** guia.

 Selecione cada **decorador** e defina **Exibir propriedade** para a propriedade de domínio correto.

 Certifique-se de que uma marca de seleção aparece ao lado de cada item de **decoradores** lista.

### <a name="define-a-connection-builder-tool"></a>Definir uma ferramenta do construtor de conexões
 No **DSL Explorer** janela, expanda o **Editor** nó e todos os seus subnós.

 Clique com botão direito no nó que tem o mesmo nome de seu DSL e, em seguida, clique em **adicionar nova ferramenta de Conexão**.

 Enquanto a nova ferramenta estiver selecionada, na janela Propriedades:

-   Definir o **legenda** e **dica de ferramenta**.

-   Clique em **Conexão construtor** e selecione o construtor apropriado para a nova relação.

-   Definir **ícone caixa de ferramentas** para o ícone que você deseja exibir na caixa de ferramentas. Você pode configurá-lo como um novo ícone ou um ícone já usado por outra ferramenta.

     Para criar um novo ícone, abra Dsl\Resources em **Gerenciador de soluções**. Copie e cole um dos arquivos BMP da ferramenta de elemento existente. Renomeie a cópia colada e clique duas vezes para editá-la.

     Retornar ao diagrama de definição de DSL, selecione a ferramenta e na janela Propriedades, clique em **[...]**  na **ícone caixa de ferramentas**. No **Selecione Bitmap** caixa de diálogo, selecione seu. Arquivo BMP no menu suspenso.

##### <a name="to-test-a-reference-relationship-and-connector"></a>Para Testar um relação de Referência e um Conector

1.  **Clique em transformar todos os modelos** na barra de ferramentas do Gerenciador de soluções, para gerar o código de designer DSL.

2.  **Compilar e executar o DSL.** Pressione F5 ou CTRL + F5 para executar uma nova instância do Visual Studio no modo de avaliação. Na instância experimental do Visual Studio, abra ou crie um arquivo que tem a extensão de nome de arquivo de seu DSL.

3.  **Verifique se a ferramenta de conexão aparece na caixa de ferramentas.**

4.  **Criar formas** arrastando-se de uma ferramenta para o diagrama de modelo.

5.  **Criar conexões** entre as formas. Clique na ferramenta do conector, em uma forma e em outra forma.

6.  **Verifique se que você não pode criar conexões entre classes inadequados.** Por exemplo, se a sua relação for entre Álbuns e Artistas, verifique se não é possível vincular Artistas a Artistas.

7.  **Verifique se o multiplicidades estão corretas. Por exemplo, verifique se que você não pode conectar uma pessoa para mais de um gerente.**

8.  **Verifique se cada decorador de texto aparece,** e que:

    1.  Você pode editá-lo, a menos que você definiu o **é somente leitura do UI** sinalizador na propriedade de domínio.

    2.  Quando você edita a propriedade na janela Propriedades ou no decorador, a outra exibição é atualizada.

 Depois de testar inicialmente um conector, talvez você queira ajustar algumas de suas propriedades e adicionar outros recursos mais avançados. Para obter mais informações, consulte [personalizar e estender uma linguagem específica do domínio](../modeling/customizing-and-extending-a-domain-specific-language.md).

##  <a name="compartments"></a> Definição de formas que contêm listas: formas do compartimento
 Uma forma do compartimento contém uma ou mais listas de itens. Por exemplo, em uma DSL de Biblioteca de Músicas, você poderia usar formas do compartimento para representar os Álbuns de música. Em cada Álbum, há uma lista de Canções.

 ![Forma do compartimento](../modeling/media/compartmentshape.png)

 No método mais simples de obter esse efeito em uma definição de DSL, você define uma classe de domínio para o contêiner e uma classe de domínio para cada lista. A classe de contêiner é mapeada para a forma do compartimento.

 ![Mapa de formas](../modeling/media/music_mapcomp.png)

 Para obter mais informações, consulte [propriedades de compartimento formas](../modeling/properties-of-compartment-shapes.md).

#### <a name="to-define-a-compartment-shape"></a>Para definir uma forma do compartimento

1.  **Criar a classe de contêiner de domínio**. Clique o **inserindo relação** ferramenta, clique na classe raiz do modelo e, em seguida, clique em uma parte em branco do diagrama DSL definição. Com isso, você cria a classe de domínio chamada Álbum na figura de exemplo.

     Como alternativa, em vez de incorporar na classe raiz, você pode incorporar o contêiner em uma classe de domínio que seja mapeada para uma raia.

     Adicionar uma propriedade de domínio como o nome para a classe e defina seu **é o nome do elemento** sinalizador na janela Propriedades.

2.  **Criar a classe de domínio do item de lista**. Clique o **inserindo relação** ferramenta, clique na classe de contêiner (álbum) e, em seguida, clique em uma parte em branco do diagrama. Com isso, você cria a classe de domínio chamada Canção na figura de exemplo.

     Adicionar uma propriedade de domínio, como o título para a classe e defina seu **é o nome do elemento** sinalizador.

     Adicione outras propriedades de domínio.

     Adicione outra classe de domínio do item de lista que você deseja exibir.

3.  **Para combinar vários tipos de item na lista**, criar classes que herdam da classe de lista. Tornar a classe lista abstrata definindo seu **modificador de herança**.

     Por exemplo, se você desejar que música clássica seja classificada por compositor em vez de por artista, é possível criar duas subclasses de Canção, ClassicalSong e NonClassicalSong.

4.  **Criar a forma de compartimento**. Arraste do **forma do compartimento** ferramenta para o diagrama de definição de DSL.

     Adicione um decorador de texto e defina seu nome.

     Adicione um compartimento e defina seu nome.

5.  Para permitir que o usuário ocultar os compartimentos de lista, a classe de forma de compartimento de atalho, aponte para **adicionar**e, em seguida, clique em **decorador de expandir/recolher**. Na janela Propriedades, configure a posição do decorador.

6.  Clique o **mapa de elemento de diagrama** ferramenta, clique a classe de contêiner de domínio e, em seguida, clique na forma de compartimento.

7.  Selecione o vínculo de mapa do elemento do diagrama entre a classe de domínio e a forma. No **DSL detalhes** janela:

    1.  Clique o **decoradores** guia. Clique no nome do decorador e, em seguida, selecione o item apropriado em **exibição propriedade**. Certifique-se de que exista uma marca de seleção ao lado do nome do decorador.

    2.  Clique o **mapas de compartimento** guia.

         Clique no nome do compartimento.

         Em **caminho de coleção de elementos exibidos**, vá para a classe de elemento de lista (música). Clique na seta suspensa para usar a ferramenta de navegador.

         Em **propriedade Display**, selecione a propriedade que deve ser exibida na lista. No exemplo, será Título.

> [!NOTE]
>  Usando os campos Caminho nos campos de Mapa do Decorador e Mapa de Compartimento, é possível tornar as relações entre as classes de domínio e a forma do compartimento mais complexas.

#### <a name="to-define-a-tool-for-creating-the-shape"></a>Para definir uma ferramenta para criar a forma

1.  **Tornar um item de caixa de ferramentas para criar elementos da classe de domínio.**

2.  Em **DSL Explorer**, expanda o **Editor** nó e todos os seus nós sub.

3.  Clique com botão direito no nó em **guias da caixa de ferramentas** que tem o mesmo nome de seu DSL, por exemplo MusicLibrary. Clique em **adicionar elemento ferramenta**.

    > [!NOTE]
    >  Se você com o botão direito do **ferramentas** nó, você não verá **adicionar elemento ferramenta**. Em vez disso, clique no nó acima dele.

4.  Na janela Propriedades, com a nova ferramenta de elemento selecionada, defina **classe** para a classe de domínio que você tiver adicionado recentemente.

5.  Definir **legenda** e **dica de ferramenta**.

6.  Definir **ícone caixa de ferramentas** a um ícone que será exibido na caixa de ferramentas. Você pode configurá-lo como um novo ícone ou um ícone já usado por outra ferramenta.

     Para criar um novo ícone, abra Dsl\Resources em **Gerenciador de soluções**. Copie e cole um dos arquivos .BMP da ferramenta de elemento existente. Renomeie a cópia colada e clique duas vezes para editá-la.

     Retornar ao diagrama de definição de DSL, selecione a ferramenta e na janela Propriedades, clique em **[...]**  na **ícone caixa de ferramentas**. No **Selecione Bitmap** caixa de diálogo, selecione o arquivo BMP no menu suspenso.

#### <a name="to-test-a-compartment-shape"></a>Para testar uma forma do compartimento

1.  **Clique em transformar todos os modelos** na barra de ferramentas do Gerenciador de soluções, para gerar o código de designer DSL.

2.  **Compilar e executar o DSL.** Pressione F5 ou CTRL + F5 para executar uma nova instância do Visual Studio no modo de avaliação. Na instância experimental do Visual Studio, abra ou crie um arquivo que tem a extensão de nome de arquivo de seu DSL.

3.  **Verifique se a ferramenta aparece na caixa de ferramentas.**

4.  Arraste a ferramenta para o diagrama de modelo. Com isso, uma forma é criada.

     Verifique se o nome do elemento aparece e é configurado automaticamente como um valor padrão.

5.  Com o botão direito do cabeçalho da nova forma e, em seguida, clique em Adicionar *seu Item de lista.* No exemplo, o comando é Adicionar Canção.

     Verifique se aparece um item na lista e se ele tem um novo nome.

6.  Clique em um dos itens da lista e examine a janela Propriedades. Você deve ver as propriedades dos itens da lista.

7.  Abra o Gerenciador de linguagens. Verifique se você pode ver os nós do contêiner com os nós do item de lista dentro.

 ![Pesquisador de objetos gerado de DSL](../modeling/media/music_explorer.png)

 Depois de testar inicialmente uma forma do compartimento, talvez você queira ajustar algumas de suas propriedades e adicionar outros recursos mais avançados. Para obter mais informações, consulte [personalizar e estender uma linguagem específica do domínio](../modeling/customizing-and-extending-a-domain-specific-language.md).

### <a name="displaying-a-reference-link-in-a-compartment"></a>Exibindo um vínculo de referência em um compartimento
 Geralmente, um elemento que você exibe em um compartimento é um filho do elemento que é representado pela forma do compartimento. No entanto, algumas vezes, você pode desejar exibir um elemento que esteja vinculado a ele com uma relação de referência.

 Por exemplo, podemos adicionar um segundo compartimento a AlbumShape que exibe uma lista dos Artistas que estão vinculados ao Álbum.

 Nesse caso, o compartimento deve exibir o vínculo, e não o elemento referenciado. Isso ocorre porque quando o usuário seleciona o item no compartimento e pressiona DELETE, ele deseja que o link seja excluído, e não o elemento referenciado.

 Entretanto, é possível fazer com que o nome do elemento referenciado apareça no compartimento.

 O procedimento a seguir pressupõe que você já tenha criado a classe de domínio, a relação de referência, a forma do compartimento e o mapa de elemento de diagrama, conforme descrito anteriormente nesta seção.

##### <a name="to-display-a-reference-link-in-a-compartment"></a>Para exibir um vínculo de referência em um compartimento

1.  **Adicionar um compartimento na forma de compartimento**. No diagrama de definição de DSL, clique com botão direito a classe de forma de compartimento, aponte para **adicionar**e, em seguida, clique em **compartimento**.

2.  Definir **caminho de coleção de elementos exibidos** para navegar até o link, em vez de seu elemento de destino. Clique no menu suspenso e use a exibição em árvore para selecionar a relação de referência em vez de seu destino. No exemplo, a relação é **ArtistAppearedOnAlbums**.

3.  Definir **caminho para a propriedade de exibição** para navegar no link para o elemento de destino. No exemplo, isso é **artista**.

4.  Definir **propriedade Display** para a propriedade apropriada do elemento de destino, por exemplo **nome**.

5.  **Transformar todos os modelos**, compilar e executar o DSL e abrir um modelo de teste.

6.  No diagrama de modelo, crie as classes de forma apropriadas, defina seus nomes e crie um vínculo entre eles. Na forma do compartimento, devem aparecer os nomes dos elementos vinculados.

7.  Selecione o vínculo ou o item na forma do compartimento. O vínculo e o item devem desaparecer.

##  <a name="ports"></a> Definindo as portas no limite de outra forma
 Uma porta é uma forma que está localizada no limite de outra forma.

 As portas também podem ser usadas para fornecer um ponto de conexão fixo em outra forma, no qual o usuário pode desenhar conectores. Nesse caso, você pode tornar a forma da porta transparente.

 Para ver um exemplo que usa portas, selecione o **diagrama de componente** modelo quando você cria uma nova solução DSL. Este exemplo mostra os pontos principais que você pode considerar ao definir as portas:

-   Há uma classe de domínio que representa o contêiner das portas, `Component`.

-   Há uma classe de domínio que representa portas. No exemplo, ela é `ComponentPort`.

-   Há uma relação de incorporação da classe de domínio de contêiner à classe de domínio de porta. Para obter mais informações, consulte [Definindo Classes de domínio](#classes).

-   Se você deseja combinar tipos diferentes de portas no mesmo contêiner, é possível criar subclasses da classe de domínio da porta. No exemplo, `InPort` e `OutPort` são herdados de `ComponentPort`.

-   A classe de domínio de contêiner pode ser mapeada para qualquer tipo de forma. No exemplo, ela é `ComponentShape`. Para obter mais informações, consulte [definindo formas](#shapes).

-   As classes de domínio de porta são mapeadas para formas de porta. Você pode mapear as classes derivadas para classes de forma de porta separadas ou mapear a classe base para uma classe de forma de porta.

 Em outros aspectos, as formas de porta se comportar conforme descrito em [definindo formas](#shapes).

 Para obter mais informações, consulte [formas de propriedades de porta](../modeling/properties-of-port-shapes.md).

##  <a name="swimlanes"></a> Definindo uma DSL com raias
 As raias são uma partição horizontal ou vertical de um diagrama. Cada raia corresponde a um elemento de modelo. Sua definição de DSL requer uma classe de domínio para os elementos de raia.

 A melhor maneira de criar uma DSL com raias é criar uma nova solução DSL e escolher o modelo de solução Fluxo de Tarefa. Na Definição de DSL, a classe Ator é a classe de domínio mapeada para a raia. Renomeie essa e as outras classes da forma adequada ao seu projeto.

 Para adicionar uma classe que será exibida como uma forma dentro de uma raia, crie uma Relação de Incorporação entre a classe de raia e sua nova classe. Os usuários poderão arrastar elementos de uma raia para outra, mas cada elemento estará sempre dentro de uma raia específica. No modelo de solução Fluxo de Tarefa, FlowElement é um filho da classe de raia.

 Para adicionar uma classe que será exibida como uma forma independentemente de raias, crie uma Relação de Incorporação entre a classe raiz e sua nova classe. Os usuários poderão colocar essas formas em qualquer lugar no diagrama, inclusive nos limites de raias e fora das raias. No modelo de solução Fluxo de Tarefa, Comment é um filho da classe raiz.

 Para obter mais informações, consulte [propriedades de raias](../modeling/properties-of-swimlanes.md).

##  <a name="addTypes"></a> Adicionando tipos de propriedade

### <a name="domain-enumerations-and-literals"></a>Enumerações e literais de domínio
 Uma enumeração de domínio é um tipo com vários valores de literais.

 Para adicionar uma enumeração de domínio, clique com botão direito a raiz do modelo no **DSL Explorer** e, em seguida, clique em **adicionar novo domínio enumeração**. O elemento aparecerá no **DSL Explorer** sob o **tipos de domínio** nó. Esse elemento não aparece no diagrama.

 Para adicionar os literais de enumeração para a enumeração de domínio, clique com botão direito a enumeração de domínio no **DSL Explorer** e, em seguida, clique em **adicionar nova enumeração Literal**.

 Por padrão, uma propriedade que possui um tipo de enumeração pode ser configurada para somente um valor de enumeração por vez. Se quiser que os usuários e programadores para poder definir qualquer combinação de valores - "campo de bits" - defina a **IsFlags** propriedade de enumeração.

### <a name="external-types"></a>Tipos externos
 Quando você define o tipo de uma propriedade de domínio, se você não encontrar o tipo desejado no **tipo** lista suspensa, você pode adicionar um tipo externo. Por exemplo, você pode adicionar o **Drawing** tipo à lista.

 Para adicionar um tipo, com o botão direito a raiz do modelo no Pesquisador de objetos de DSL e, em seguida, clique em **adicionar novo tipo externo**. Na janela Propriedades, defina o nome como **cor** e o namespace a ser **System. Drawing**. Este tipo agora aparece no Gerenciador de DSL em **tipos de domínio**. Você pode escolhê-lo sempre que definir o tipo de uma propriedade de domínio.

##  <a name="custom"></a> Personalizando o DSL
 Usando as técnicas descritas neste tópico, é possível criar com rapidez uma DSL com uma notação diagramática, uma forma XML legível e as ferramentas básicas necessárias para gerar código e outros artefatos.

 Há dois métodos de extensão da definição de DSL:

1.  Ajuste a DSL usando mais recursos da Definição de DSL. Por exemplo, você pode criar uma única ferramenta de conector capaz de criar vários tipos de conectores e você pode controlar as regras com as quais a exclusão de um elemento também exclui elementos relacionados. Essas técnicas são obtidas, em sua maioria, ao configurar valores na Definição de DSL, e alguns deles necessitam de algumas linhas do código do programa.

     Para obter mais informações, consulte [personalizar e estender uma linguagem específica do domínio](../modeling/customizing-and-extending-a-domain-specific-language.md).

2.  Estenda suas ferramentas de modelagem usando o código do programa para obter efeitos mais avançados. Por exemplo, você pode criar comandos de menu que alteram o modelo e você pode criar ferramentas que integram duas ou mais DSLs. O VMSDK foi projetado especificamente para facilitar a integração de suas extensões com o código gerado a partir da Definição de DSL.  Para obter mais informações, consulte [escrevendo código para personalizar uma linguagem específica do domínio](../modeling/writing-code-to-customise-a-domain-specific-language.md).

### <a name="changing-the-dsl-definition"></a>Alterando a definição de DSL
 Ao criar qualquer item em uma definição de DSL, diversos valores padrão são configurados automaticamente. Depois de configurados, você poderá alterá-los. Isso simplifica o desenvolvimento de uma DSL e ainda permite personalizações avançadas.

 Por exemplo, quando você mapeia uma forma para um elemento, o Caminho do Elemento Pai do mapeamento é configurado automaticamente, de acordo com a relação de incorporação da classe de domínio. Entretanto, se posteriormente você alterar a relação de incorporação, o caminho do elemento pai não é alterado automaticamente.

 Você deve, portanto, estar ciente de que ao alterar algumas relações em sua Definição de DSL, não é incomum que erros sejam relatados ao salvar a definição ou ao Transformar Todos os Modelos. A maioria dos erros é fácil de corrigir. Clique duas vezes no relatório de erros para ver o local do erro.

 Consulte também [como: alterar o Namespace de uma linguagem específica do domínio](../modeling/how-to-change-the-namespace-of-a-domain-specific-language.md).

##  <a name="trouble"></a> Solução de problemas
 A tabela a seguir lista alguns dos problemas mais comuns encontrados ao projetar uma DSL, junto com as sugestões para sua solução. Conselhos estão disponível na [Extensibililty Fórum das ferramentas de visualização](http://go.microsoft.com/fwlink/?LinkId=186074).

|Problema|Sugestão|
|-------------|----------------|
|As alterações feitas no arquivo de Definição de DSL não surtiram efeito.|Clique em **transformar todos os modelos** na barra de ferramentas acima do Gerenciador de soluções e reconstrua a solução.|
|As formas mostram o nome de um decorador em vez do valor de propriedade.|Configure o mapeamento do decorador. No diagrama de Definição de DSL, clique no mapa do elemento do diagrama, que é a linha cinza entre a classe de domínio e a classe de forma.<br /><br /> Abra o **DSL detalhes** janela. Se você não pode vê-lo, no menu Exibir, aponte para **outras janelas**e, em seguida, clique em **DSL detalhes**.<br /><br /> Clique o **decorador mapas** guia. Escolha o nome do decorador. Certifique-se de que a caixa ao lado esteja marcada. Em **Exibir propriedade**, selecione o nome de uma propriedade de domínio.<br /><br /> Para obter mais informações, consulte [formas no diagrama](#shapes).|
|Não consigo adicionar uma coleção no Gerenciador de DSL. Por exemplo, quando clico com o botão direito do mouse em Ferramentas, não encontro o comando "Adicionar Ferramenta" no menu.<br /><br /> No gerenciador de minha DSL, não consigo adicionar um elemento à lista.|Clique com o botão direito do mouse no item acima do nó ao qual você está tentando adicionar elementos. Quando desejar adicionar elementos a uma lista, o comando Adicionar não estará no nó da lista, mas em seu proprietário.|
|Criei uma classe de domínio, mas não consigo criar instâncias no gerenciador de linguagens.|Cada classe de domínio, exceto a raiz, deve ser o destino de uma relação de incorporação.|
|No gerenciador de minha DSL, os elementos são mostrados somente com seus nomes de tipos.|Na definição de DSL, selecione uma propriedade da classe de domínio e nas propriedades da janela, defina **é o nome do elemento** como true.|
|Minha DSL sempre é aberta no editor XML.|Isso pode ocorrer em função de um erro durante a leitura do arquivo. No entanto, mesmo após a correção desse erro, você deve redefinir explicitamente o editor para que seja o designer de DSL.<br /><br /> O item de projeto, clique **abrir com** e selecione * YourLanguage ***Designer (padrão)**.|
|A caixa de ferramentas de minha DSL não aparece após a mudança de nomes do assembly.|Verifique e atualize **DslPackage\GeneratedCode\Package.tt** para obter mais informações, consulte [como: alterar o Namespace de uma linguagem específica do domínio](../modeling/how-to-change-the-namespace-of-a-domain-specific-language.md).|
|A caixa de ferramentas de minha DSL não aparece, mas não alterei o nome do assembly.<br /><br /> Ou, uma caixa de mensagens aparece relatando a falha ao carregar uma extensão.|Redefina a instância experimental e recompile sua solução.<br /><br /> 1.  No Windows menu Iniciar, em **todos os programas**, expanda [!INCLUDE[vssdk_current_long](../misc/includes/vssdk_current_long_md.md)], em seguida, **ferramentas**e, em seguida, clique em **redefinir a instância de Experimental Microsoft Visual Studio**.<br />2.  No Visual Studio**criar** menu, clique em **recompilar solução**.|

## <a name="see-also"></a>Consulte também

- [Introdução às linguagens específicas de domínio](../modeling/getting-started-with-domain-specific-languages.md)
- [Criando uma linguagem específica de domínio baseada no Windows Forms](../modeling/creating-a-windows-forms-based-domain-specific-language.md)
- [Criando uma linguagem específica de domínio baseada no WPF](../modeling/creating-a-wpf-based-domain-specific-language.md)