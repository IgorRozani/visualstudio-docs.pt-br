---
title: "Criar um sistema de projeto básico, parte 2 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- writing a project system
- project system
- tutorial
ms.assetid: aee48fc6-a15f-4fd5-8420-7f18824de220
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 699f9176fd39cacaf2bb4f433cd9d2ceb8e326b5
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2018
---
# <a name="creating-a-basic-project-system-part-2"></a>Criando um sistema de projeto básico, parte 2
A primeiro passo a passo da série, [criando um sistema básico de projeto, parte 1](../extensibility/creating-a-basic-project-system-part-1.md), mostra como criar um sistema de projeto básico. Este passo a passo se baseia no sistema de projeto básico, adicionando um modelo do Visual Studio, uma página de propriedades e outros recursos. Você deve concluir a primeiro passo a passo antes de iniciar este.  
  
 Este passo a passo ensina como criar um tipo de projeto que tem o .myproj de extensão de nome de arquivo de projeto. Para concluir o passo a passo, você não precisa criar seu próprio idioma porque pega emprestado o passo a passo do sistema de projeto Visual c# existente.  
  
 Este passo a passo ensina como realizar estas tarefas:  
  
-   Crie um modelo do Visual Studio.  
  
-   Implante um modelo do Visual Studio.  
  
-   Criar um nó do filho do tipo de projeto no **novo projeto** caixa de diálogo.  
  
-   Habilite substituição de parâmetro no modelo do Visual Studio.  
  
-   Crie uma página de propriedades do projeto.  
  
> [!NOTE]
>  As etapas neste passo a passo são baseadas em um projeto c#. No entanto, com exceção de informações específicas, como as extensões de nome de arquivo e código, você pode usar as mesmas etapas para um projeto do Visual Basic.  
  
## <a name="creating-a-visual-studio-template"></a>Criando um modelo do Visual Studio  
 [Criando um sistema básico de projeto, parte 1](../extensibility/creating-a-basic-project-system-part-1.md) mostra como criar um modelo de projeto básico e adicioná-lo para o sistema do projeto. Ele também mostra como registrar esse modelo com o Visual Studio usando o <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> atributo, que grava o caminho completo da pasta \Templates\Projects\SimpleProject\ no registro do sistema.  
  
 Usando um modelo do Visual Studio (arquivo. vstemplate) em vez de um modelo de projeto básico, você pode controlar como o modelo aparecerá no **novo projeto** caixa de diálogo e como os parâmetros de modelo são substituídos.  Um arquivo. vstemplate é um arquivo XML que descreve como arquivos de origem devem ser incluídas quando um projeto é criado usando o modelo de sistema do projeto. O sistema de projeto é criado com a coleta de arquivo. vstemplate e os arquivos de origem em um arquivo. zip e implantado, copiando o arquivo. zip para um local conhecido para o Visual Studio. Esse processo é explicado em mais detalhes posteriormente neste passo a passo.  
  
1.  Em [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], abra a solução de SimpleProject que você criou seguindo [criando um sistema básico de projeto, parte 1](../extensibility/creating-a-basic-project-system-part-1.md).  
  
2.  No arquivo SimpleProjectPackage.cs, localizar o atributo ProvideProjectFactory. Substitua o segundo parâmetro (o nome do projeto) com null e o quarto parâmetro (o caminho para a pasta de modelo de projeto) ". \\\NullPath ", da seguinte maneira.  
  
    ```  
    [ProvideProjectFactory(typeof(SimpleProjectFactory), null,  
        "Simple Project Files (*.myproj);*.myproj", "myproj", "myproj",  
        ".\\NullPath",  
    LanguageVsTemplate = "SimpleProject")]  
    ```  
  
3.  Adicione um arquivo XML denominado SimpleProject.vstemplate para a pasta \Templates\Projects\SimpleProject\.  
  
4.  Substitua o conteúdo de SimpleProject.vstemplate com o código a seguir.  
  
    ```xml  
    <VSTemplate Version="2.0.0" Type="Project"  
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
      <TemplateData>  
        <Name>SimpleProject Application</Name>  
        <Description>  
            A project for creating a SimpleProject application  
         </Description>  
         <Icon>SimpleProject.ico</Icon>  
         <ProjectType>SimpleProject</ProjectType>  
      </TemplateData>  
      <TemplateContent>  
        <Project File="SimpleProject.myproj" ReplaceParameters="true">  
          <ProjectItem ReplaceParameters="true" OpenInEditor="true">  
              Program.cs  
          </ProjectItem>  
          <ProjectItem ReplaceParameters="true" OpenInEditor="false">  
             AssemblyInfo.cs  
          </ProjectItem>  
        </Project>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
5.  No **propriedades** janela, selecione todos os cinco arquivos na pasta \Templates\Projects\SimpleProject\ e definir o **ação de compilação** para **ZipProject**.  
  
 ![](../extensibility/media/simpproj2.png "SimpProj2")  
  
 O \<TemplateData > seção determina o local e a aparência do tipo de projeto SimpleProject no **novo projeto** caixa de diálogo, da seguinte maneira:  
  
-   O \<nome > elemento nomeia o modelo de projeto aplicativo SimpleProject.  
  
-   O \<descrição > elemento contém a descrição que aparece no **novo projeto** caixa de diálogo quando o modelo de projeto está selecionado.  
  
-   O \<ícone > elemento Especifica o ícone que aparece junto com o tipo de projeto SimpleProject.  
  
-   O \<ProjectType > o tipo de projeto em nomes de elementos de **novo projeto** caixa de diálogo. Esse nome substitui o parâmetro de nome de projeto do atributo ProvideProjectFactory.  
  
    > [!NOTE]
    >  O \<ProjectType > elemento deve corresponder a `LanguageVsTemplate` argumento o `ProvideProjectFactory` atributo no arquivo SimpleProjectPackage.cs.  
  
 O \<TemplateContent > seção descreve esses arquivos que são gerados quando um novo projeto é criado:  
  
-   SimpleProject.myproj  
  
-   Module.vb  
  
-   AssemblyInfo.cs  
  
 Todos os três arquivos tem `ReplaceParameters` definido como true, o que permite a substituição de parâmetro.  O arquivo Program.cs tem `OpenInEditor` definido como true, o que faz com que o arquivo a ser aberto no editor de código quando um projeto é criado.  
  
 Para obter mais informações sobre os elementos no esquema de modelo do Visual Studio, consulte o [referência de esquema de modelo do Visual Studio](../extensibility/visual-studio-template-schema-reference.md).  
  
> [!NOTE]
>  Se um projeto tiver mais de um modelo do Visual Studio, cada modelo é em uma pasta separada. Todos os arquivos nessa pasta devem ter o **ação de compilação** definida como **ZipProject**.  
  
## <a name="adding-a-minimal-vsct-file"></a>Adicionar um arquivo. VSCT mínimo  
 Visual Studio deve ser executado no modo de instalação para reconhecer um modelo novo ou modificado do Visual Studio. Modo de instalação requer um arquivo. VSCT esteja presente. Portanto, você deve adicionar um arquivo. VSCT mínimo para o projeto.  
  
1.  Adicione um arquivo XML denominado SimpleProject.vsct ao projeto SimpleProject.  
  
2.  Substitua o conteúdo do arquivo SimpleProject.vsct com o código a seguir.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CommandTable  
      xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable">  
    </CommandTable>  
    ```  
  
3.  Definir o **ação de compilação** deste arquivo **VSCTCompile**. Você pode fazer isso apenas no arquivo. csproj, não no **propriedades** janela. Verifique se o **ação de compilação** desse arquivo é definido como **nenhum** neste momento.  
  
    1.  Com o botão direito no nó SimpleProject e, em seguida, clique em **SimpleProject.csproj editar**.  
  
    2.  No arquivo. csproj, localize o item SimpleProject.vsct.  
  
        ```  
        <None Include="SimpleProject.vsct" />  
        ```  
  
    3.  Altere a ação de compilação para **VSCTCompile**.  
  
        ```  
        <VSCTCompile Include="SimpleProject.vsct" />  
        ```  
  
    4.  o arquivo de projeto e feche o editor.  
  
    5.  Salve o nó SimpleProject e, em seguida, no **Solution Explorer** clique **recarregar projeto**.  
  
## <a name="examining-the-visual-studio-template-build-steps"></a>Examinando as etapas de criação de modelo do Visual Studio  
 O sistema de compilação de projeto VSPackage normalmente executa o Visual Studio no modo de instalação quando o arquivo. vstemplate é alterado ou o projeto que contém o arquivo. vstemplate é recompilado. Você pode acompanhá-lo definindo o nível de detalhamento do MSBuild como Normal ou superior.  
  
1.  No menu **Ferramentas**, clique em **Opções**.  
  
2.  Expanda o **projetos e soluções** nó e selecione **compilar e executar**.  
  
3.  Definir **detalhamento da saída de compilação de projeto MSBuild** para **Normal**. Clique em **OK**.  
  
4.  Recompile o projeto SimpleProject.  
  
 A etapa de compilação para criar o arquivo de projeto. zip deve se parecer com o exemplo a seguir.  
  
```  
ZipProjects:  
1>  Zipping ProjectTemplates  
1>  Zipping <path>\SimpleProject\SimpleProject\obj\Debug\SimpleProject.zip...  
1>  Copying file from "<path>\SimpleProject\SimpleProject\obj\Debug\SimpleProject.zip" to "<%LOCALAPPDATA%>\Microsoft\VisualStudio\14.0Exp\ProjectTemplates\\\\SimpleProject.zip".  
1>  Copying file from "<path>\SimpleProject\SimpleProject\obj\Debug\SimpleProject.zip" to "bin\Debug\\ProjectTemplates\\\\SimpleProject.zip".  
1>  SimpleProject -> <path>\SimpleProject\SimpleProject\bin\Debug\ProjectTemplates\SimpleProject.zip  
1>ZipItems:  
1>  Zipping ItemTemplates  
1>  SimpleProject ->  
```  
  
## <a name="deploying-a-visual-studio-template"></a>Implantando um modelo do Visual Studio  
 Modelos do Visual Studio não contêm informações de caminho. Portanto, o arquivo. zip de modelo deve ser implantado em um local conhecido para o Visual Studio. O local da pasta ProjectTemplates é normalmente  **\<% LOCALAPPDATA % > \Microsoft\VisualStudio\14.0Exp\ProjectTemplates**.  
  
 Para implantar sua fábrica de projeto, o programa de instalação deve ter privilégios de administrador. Implanta modelos sob o nó de instalação do Visual Studio: **...\Microsoft Visual Studio 14.0\Common7\IDE\ProjectTemplates**.  
  
## <a name="testing-a-visual-studio-template"></a>Testando um modelo do Visual Studio  
 Teste sua fábrica de projeto para ver se ele cria uma hierarquia de projeto usando o modelo do Visual Studio.  
  
1.  Redefina a instância experimental do Visual Studio SDK.  
  
     Em [!INCLUDE[win7](../debugger/includes/win7_md.md)]: no menu Iniciar, localize o **Microsoft Visual Studio para o Microsoft Visual Studio/ferramentas SDK** pasta e, em seguida, selecione **redefinir a instância Experimental do Visual Studio Microsoft**.  
  
     Em versões posteriores do Windows: sobre a tela Iniciar, digite **redefinir o Microsoft Visual Studio \<versão > instância Experimental**.  
  
2.  É exibida uma janela de prompt de comando. Quando você vir as palavras `Press any key to continue`, clique em ENTER. Depois de fecha a janela, abra o Visual Studio.  
  
3.  Recompile o projeto SimpleProject e iniciar a depuração. A instância experimental aparece.  
  
4.  Na instância experimental, crie um projeto de SimpleProject. No **novo projeto** caixa de diálogo, selecione **SimpleProject**.  
  
5.  Você deve ver uma nova instância da SimpleProject.  
  
 ![](../extensibility/media/simpproj2_newproj.png "SimpProj2_NewProj")  
  
 ![](../extensibility/media/simpproj2_myproj.png "SimpProj2_MyProj")  
  
## <a name="creating-a-project-type-child-node"></a>Criar um nó de filho do tipo de projeto  
 Você pode adicionar um nó filho em um nó de tipo de projeto no **novo projeto** caixa de diálogo.  Por exemplo, para o tipo de projeto SimpleProject, você pode ter nós filho para aplicativos de console, aplicativos de janela, aplicativos web e assim por diante.  
  
 Nós filho são criados, alterando o arquivo de projeto e adicionando \<OutputSubPath > filho para o \<ZipProject > elementos. Quando um modelo é copiado durante a compilação ou implantação, cada nó filho se torna uma subpasta da pasta de modelos de projeto.  
  
 Esta seção mostra como criar um nó filho de Console para o tipo de projeto SimpleProject.  
  
1.  Renomeie a pasta \Templates\Projects\SimpleProject\ para \Templates\Projects\ConsoleApp\\.  
  
2.  No **propriedades** janela, selecione todos os cinco arquivos na pasta \Templates\Projects\ConsoleApp\ e verifique se o **ação de compilação** é definido como **ZipProject**.  
  
3.  No arquivo SimpleProject.vstemplate, adicione a seguinte linha no final de \<TemplateData > seção antes da marca de fechamento.  
  
    ```  
    <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
    ```  
  
     Isso faz com que o modelo de aplicativo de Console seja exibido no nó filho Console e o nó pai SimpleProject, que é um nível acima do nó filho.  
  
4.  Salve o arquivo SimpleProject.vstemplate.  
  
5.  No arquivo. csproj, adicione \<OutputSubPath > para cada um dos elementos ZipProject. Descarregue o projeto, como antes e edite o arquivo de projeto.  
  
6.  Localize o \<ZipProject > elementos. Para cada \<ZipProject > elemento, adicionar um \<OutputSubPath > elemento e dê a ele o valor de Console. O ZipProject  
  
    ```  
    <ZipProject Include="Templates\Projects\ConsoleApp\AssemblyInfo.cs">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\Program.cs">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\SimpleProject.myproj">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\SimpleProject.vstemplate">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\SimpleProject.ico">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>  
    ```  
  
7.  Adicione esse \<PropertyGroup > ao arquivo de projeto:  
  
    ```  
    <PropertyGroup>  
      <VsTemplateLanguage>SimpleProject</VsTemplateLanguage>  
    </PropertyGroup>  
    ```  
  
8.  Salve o arquivo de projeto e recarregar o projeto.  
  
## <a name="testing-the-project-type-child-node"></a>O nó de filho do tipo de projeto de teste  
 Testar o arquivo de projeto modificado para ver se o **Console** nó filho aparece no **novo projeto** caixa de diálogo.  
  
1.  Execute o **redefinir a instância de Experimental Microsoft Visual Studio** ferramenta.  
  
2.  Recompile o projeto SimpleProject e iniciar a depuração. A instância experimental deve aparecer  
  
3.  No **novo projeto** caixa de diálogo, clique o **SimpleProject** nó. O **aplicativo de Console** modelo deve aparecer no **modelos** painel.  
  
4.  Expanda o **SimpleProject** nó. O **Console** nó filho deve aparecer. O **SimpleProject aplicativo** modelo continuará aparecendo no **modelos** painel.  
  
5.  . Clique em **Cancelar** e parar a depuração  
  
 ![](../extensibility/media/simpproj2_rollup.png "SimpProj2_Rollup")  
  
 ![](../extensibility/media/simpproj2_subfolder.png "SimpProj2_Subfolder")  
  
## <a name="substituting-project-template-parameters"></a>Substituição de parâmetros de modelo de projeto  
 [Criando um sistema básico de projeto, parte 1](../extensibility/creating-a-basic-project-system-part-1.md) mostrou como substituir o `ProjectNode.AddFileFromTemplate` método de fazer um tipo básico de substituição de parâmetro de modelo. Esta seção ensina como usar os parâmetros de modelo do Visual Studio mais sofisticados.  
  
 Quando você cria um projeto usando um modelo do Visual Studio no **novo projeto** caixa de diálogo modelo de parâmetros são substituídos por cadeias de caracteres para personalizar o projeto. Um parâmetro de modelo é um token especial que começa e termina com um sinal de cifrão, por exemplo, $time$. Os dois parâmetros seguintes são especialmente úteis para habilitar a personalização em projetos que são baseados no modelo:  
  
-   $ $GUID [1-10] é substituído por um novo Guid. Você pode especificar até 10 GUIDs exclusivos, por exemplo, guid1 $$.  
  
-   $ $safeprojectname é o nome fornecido pelo usuário no **novo projeto** caixa de diálogo, modificada para remover todos os caracteres inseguros e espaços.  
  
 Para ver uma lista completa dos parâmetros de modelo, consulte [Parâmetros de Modelo](../ide/template-parameters.md).  
  
#### <a name="to-substitute-project-template-parameters"></a>Substituir parâmetros de modelo de projeto  
  
1.  No arquivo SimpleProjectNode.cs, remova o `AddFileFromTemplate` método.  
  
2.  No arquivo \Templates\Projects\ConsoleApp\SimpleProject.myproj, localize o \<RootNamespace > propriedade e alterar seu valor para $safeprojectname$.  
  
    ```  
    <RootNamespace>$safeprojectname$</RootNamespace>  
    ```  
  
3.  No arquivo \Templates\Projects\SimpleProject\Program.cs, substitua o conteúdo do arquivo com o código a seguir:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Runtime.InteropServices;    // Guid  
  
    namespace $safeprojectname$  
    {  
        [Guid("$guid1$")]  
        public class $safeprojectname$  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
4.  Recompile o projeto SimpleProject e iniciar a depuração. A instância experimental deve aparecer.  
  
5.  Crie um novo aplicativo de SimpleProject Console. (No **tipos de projeto** painel, selecione **SimpleProject**. Em **modelos instalados do Visual Studio**, selecione **aplicativo de Console**.)  
  
6.  No projeto recém-criado, abra Program.cs. Deve ser algo semelhante ao seguinte (valores GUID no arquivo serão diferentes.):  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Runtime.InteropServices;    // Guid  
  
    namespace Console_Application1  
    {  
        [Guid("00000000-0000-0000-00000000-00000000)"]  
        public class Console_Application1  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
## <a name="creating-a-project-property-page"></a>Criando uma página de propriedades do projeto  
 Você pode criar uma página de propriedades para o tipo de projeto para que os usuários podem exibir e alterar as propriedades em projetos que são baseados no modelo. Esta seção mostra como criar uma página de propriedades de configuração independente. Esta página de propriedades básicas usa uma grade de propriedades para exibir as propriedades públicas que expõem em sua classe de página de propriedade.  
  
 Derive sua classe de página de propriedade do `SettingsPage` classe base. A grade de propriedades fornecida pelo `SettingsPage` classe reconhece mais primitivos de tipos de dados e sabe como exibi-los.  Além disso, a `SettingsPage` classe sabe como manter valores de propriedade para o arquivo de projeto.  
  
 A página de propriedades que você criar nessa seção lhe permite alterar e salvar essas propriedades do projeto:  
  
-   AssemblyName  
  
-   OutputType  
  
-   RootNamespace.  
  
1.  No arquivo SimpleProjectPackage.cs, adicionar `ProvideObject` de atributo para o `SimpleProjectPackage` classe:  
  
    ```  
    [ProvideObject(typeof(GeneralPropertyPage))]  
    public sealed class SimpleProjectPackage : ProjectPackage  
    ```  
  
     Isso registra a classe de página de propriedade `GeneralPropertyPage` com COM.  
  
2.  No arquivo SimpleProjectNode.cs, adicionar esses dois métodos de substituição para o `SimpleProjectNode` classe:  
  
    ```  
    protected override Guid[] GetConfigurationIndependentPropertyPages()  
    {  
        Guid[] result = new Guid[1];  
        result[0] = typeof(GeneralPropertyPage).GUID;  
        return result;  
    }  
    protected override Guid[] GetPriorityProjectDesignerPages()  
    {  
        Guid[] result = new Guid[1];  
        result[0] = typeof(GeneralPropertyPage).GUID;  
         return result;  
    }  
    ```  
  
     Ambos os métodos retornam uma matriz de GUIDs de página de propriedades.  O GeneralPropertyPage GUID é o único elemento na matriz, portanto, o **páginas de propriedade** caixa de diálogo mostrará apenas uma página.  
  
3.  Adicione um arquivo de classe chamado GeneralPropertyPage.cs ao projeto SimpleProject.  
  
4.  Substitua o conteúdo desse arquivo, usando o código a seguir:  
  
    ```  
    using System;  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Project;  
    using System.ComponentModel;  
  
    namespace SimpleProject  
    {  
        [ComVisible(true)]  
        [Guid("6BC7046B-B110-40d8-9F23-34263D8D2936")]  
        public class GeneralPropertyPage : SettingsPage  
        {  
            private string assemblyName;  
            private OutputType outputType;  
            private string defaultNamespace;  
  
            public GeneralPropertyPage()  
            {  
                this.Name = "General";  
            }  
  
            [Category("AssemblyName")]  
            [DisplayName("AssemblyName")]  
            [Description("The output file holding assembly metadata.")]  
            public string AssemblyName  
            {  
                get { return this.assemblyName; }  
            }  
            [Category("Application")]  
            [DisplayName("OutputType")]  
            [Description("The type of application to build.")]  
            public OutputType OutputType  
            {  
                get { return this.outputType; }  
                set { this.outputType = value; this.IsDirty = true; }  
            }  
            [Category("Application")]  
            [DisplayName("DefaultNamespace")]  
            [Description("Specifies the default namespace for added items.")]  
            public string DefaultNamespace  
            {  
                get { return this.defaultNamespace; }  
                set { this.defaultNamespace = value; this.IsDirty = true; }  
            }  
  
            protected override void BindProperties()  
            {  
                this.assemblyName = this.ProjectMgr.GetProjectProperty(  
    "AssemblyName", true);  
                this.defaultNamespace = this.ProjectMgr.GetProjectProperty(  
    "RootNamespace", false);  
  
                string outputType = this.ProjectMgr.GetProjectProperty(  
    "OutputType", false);  
                this.outputType =   
    (OutputType)Enum.Parse(typeof(OutputType), outputType);  
            }  
  
            protected override int ApplyChanges()  
            {  
                this.ProjectMgr.SetProjectProperty(  
    "AssemblyName", this.assemblyName);  
                this.ProjectMgr.SetProjectProperty(  
    "OutputType", this.outputType.ToString());  
                this.ProjectMgr.SetProjectProperty(  
    "RootNamespace", this.defaultNamespace);  
                this.IsDirty = false;  
  
                return VSConstants.S_OK;  
            }  
        }  
    }  
    ```  
  
     O `GeneralPropertyPage` classe expõe três propriedades públicas AssemblyName OutputType e RootNamespace. Porque o AssemblyName não tem nenhum método de conjunto, ele será exibido como uma propriedade somente leitura. OutputType é uma constante enumerada, então ele aparece como a lista suspensa.  
  
     O `SettingsPage` classe base fornece `ProjectMgr` para persistir as propriedades. O `BindProperties` método usa `ProjectMgr` para recuperar os valores de propriedade persistente e definir as propriedades correspondentes.  O `ApplyChanges` método usa `ProjectMgr` para obter os valores das propriedades e mantê-las ao arquivo de projeto. A propriedade de conjunto de conjuntos de método `IsDirty` como true para indicar que as propriedades precisam ser mantidos.  Persistência ocorre quando você salvar o projeto ou solução.  
  
5.  Recompile a solução SimpleProject e iniciar a depuração. A instância experimental deve aparecer.  
  
6.  Na instância experimental, crie um novo aplicativo SimpleProject.  
  
7.  O Visual Studio chama sua fábrica de projeto para criar um projeto usando o modelo do Visual Studio. O novo arquivo Program.cs é aberto no editor de códigos.  
  
8.  Clique com botão direito no nó do projeto no **Solution Explorer**e, em seguida, clique em **propriedades**. A caixa de diálogo **Páginas de Propriedades** é exibida.  
  
 ![](../extensibility/media/simpproj2_proppage.png "SimpProj2_PropPage")  
  
## <a name="testing-the-project-property-page"></a>A página de propriedades do projeto de teste  
 Agora você pode testar se você pode modificar e altere os valores de propriedade.  
  
1.  No **páginas de propriedade MyConsoleApplication** caixa de diálogo, altere o **DefaultNamespace** para **MyApplication**.  
  
2.  Selecione o **OutputType** propriedade e, em seguida, selecione **biblioteca de classes**.  
  
3.  Clique em **aplicar**e, em seguida, clique em **Okey**.  
  
4.  Reabra o **páginas de propriedade** caixa de diálogo caixa e verifique se as alterações foram persistidas.  
  
5.  Feche a instância experimental do Visual Studio.  
  
6.  Abra a instância experimental.  
  
7.  Reabra o **páginas de propriedade** caixa de diálogo caixa e verifique se as alterações foram persistidas.  
  
8.  Feche a instância experimental do Visual Studio.  
  
 ![](../extensibility/media/simpproj2_proppage2.png "SimpProj2_PropPage2")