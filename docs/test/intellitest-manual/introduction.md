---
title: "Visão geral | Ferramenta de teste do desenvolvedor do Microsoft IntelliTest | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliTest, Visual Studio IntelliTest developer testing tool
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 65f14d96bd495a1b3f8ca138176fbf805fdfeb67
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2018
---
# <a name="overview-of-microsoft-intellitest"></a>Visão geral do Microsoft IntelliTest

O IntelliTest permite localizar bugs no início e reduz os custos de manutenção de teste. Usando uma abordagem de teste transparente e automatizada, o IntelliTest pode gerar um conjunto de testes candidato para seu código .NET. A geração de conjunto de testes pode ser ainda mais orientada por *propriedades de correção* especificadas por você. O IntelliTest até mesmo evoluirá o conjunto de testes automaticamente à medida que o código em teste evolui.

**Testes de caracterização**  
O IntelliTest permite que você determine o comportamento do código em termos de um conjunto de testes de unidade tradicional. Esse conjunto de testes pode ser usado como um pacote de regressão, formando a base para lidar com a complexidade associados à refatoração do código herdado ou desconhecido.

**Geração de entrada de teste guiada**  
O IntelliTest usa uma abordagem de resolução de restrição e análise de código aberta para gerar automaticamente valores de entrada de teste precisos, normalmente sem necessidade de intervenção do usuário. Para tipos de objeto complexos, ele gera automaticamente as fábricas. Você pode guiar a geração de entrada de teste estendendo e configurando as fábricas para atender aos seus requisitos. Propriedades de correção especificadas como declarações no código também serão usadas automaticamente para orientar ainda mais a geração de entrada de teste.

**Integração com IDE**  
O IntelliTest está totalmente integrado ao Visual Studio IDE. Todas as informações coletadas durante a geração do conjunto de testes (como as entradas geradas automaticamente, a saída do código, os casos de teste gerados e seu status de aprovação ou falha) aparecem no Visual Studio IDE. Você pode iterar facilmente entre corrigir seu código e executar novamente o IntelliTest, sem sair do Visual Studio IDE. Os testes podem ser salvos na solução como um Projeto de Teste de Unidade e serão automaticamente detectados posteriormente pelo Gerenciador de Testes do Visual Studio.

**Complementar práticas de teste existentes**  
Use o IntelliTest para complementar qualquer prática de teste existente que você já pode seguir.

Se desejar testar:

* Algoritmos através de dados primitivos ou matrizes de dados primitivos:
  * escreva [testes de unidade parametrizados](test-generation.md#parameterized-unit-testing)
* Algoritmos de dados complexos, como o compilador:
  * permita que o IntelliTest primeiro gere uma representação abstrata dos dados e, em seguida, inseri-a no algoritmo
  * permita que o IntelliTest crie instâncias usando [criação de objeto personalizado](input-generation.md#objects) e invariáveis de dados e, em seguida, invoque o algoritmo
* Contêineres de dados:
  * escreva [testes de unidade parametrizados](test-generation.md#parameterized-unit-testing)
  * permita que o IntelliTest crie instâncias usando [criação de objeto personalizado](input-generation.md#objects) e invariáveis de dados e, em seguida, invoque o método do contêiner e verifique novamente as invariáveis posteriormente
  * grave [testes de unidade parametrizados](test-generation.md#parameterized-unit-testing) que chamam métodos diferentes da implementação, dependendo dos valores de parâmetro
* Uma base de código existente:
  * use o Assistente do IntelliTest do Visual Studio para começar gerando um conjunto de [PUTs (unidades de teste parametrizadas)](test-generation.md#parameterized-unit-testing)

<a name="hello-world"></a>
## <a name="the-hello-world-of-intellitest"></a>O Olá, Mundo do IntelliTest

O IntelliTest localiza entradas relevantes para o programa testado, o que significa que você pode usá-lo para gerar a famosa cadeia de caracteres **Olá, Mundo!** . Isso pressupõe que você criou um projeto de teste com base em MSTest do C# e adicionou uma referência ao **Microsoft.Pex.Framework**. Se você estiver usando uma estrutura de teste diferente, crie uma biblioteca de classes do C# e consulte a documentação da estrutura de teste sobre como configurar o projeto.

O exemplo a seguir cria duas restrições no parâmetro chamado **valor** de forma que o IntelliTest gerará a cadeia de caracteres necessária.

```csharp
using System;
using Microsoft.Pex.Framework; 
using Microsoft.VisualStudio.TestTools.UnitTesting; 

[TestClass]
public partial class HelloWorldTest {
    [PexMethod]
    public void HelloWorld([PexAssumeNotNull]string value) {
        if (value.StartsWith("Hello")
            && value.EndsWith("World!")
            && value.Contains(" "))
            throw new Exception("found it!");
    }
}
```

Depois de compilado e executado, o IntelliTest gera um conjunto de testes, como o seguinte:

1. ""
2. "\0\0\0\0\0"
3. "Olá"
4. "\0\0\0\0\0\0"
5. "Olá\0"
6. "Olá\0\0"
7. "Olá\0Mundo!"
8. "Olá, Mundo!"

Leia [Gerar testes de unidade para seu código com IntelliTest](../../test/generate-unit-tests-for-your-code-with-intellitest.md) para entender onde os testes gerados são salvos. O código de teste gerado deve incluir um teste como o seguinte:

```csharp
[TestMethod]
[PexGeneratedBy(typeof(global::HelloWorldTest))]
[PexRaisedException(typeof(Exception))]
public void HelloWorldThrowsException167()
{
    this.HelloWorld("Hello World!");
}
```

É fácil assim!

## <a name="limitations"></a> Limitações

Esta seção descreve as limitações do IntelliTest:

* [Não determinismo](#nondeterminism)
* [Simultaneidade](#concurrency)
* [Código .NET nativo](#native-code)
* [Plataforma](#platform)
* [Linguagem](#language)
* [Raciocínio simbólico](#symbolic-reasoning)
* [Rastreamentos de pilha](#incorrect-stack)

<a name="nondeterminism"></a>
### <a name="nondeterminism"></a>Não determinismo

O IntelliTest pressupõe que o programa analisado é determinístico. Se não for, o IntelliTest rodará até chegar a um limite de exploração.

O IntelliTest considera um programa como não determinístico se ele depende de entradas que o IntelliTest não pode controlar.

O IntelliTest controla entradas fornecidas para [testes de unidade parametrizados](test-generation.md#parameterized-unit-testing) e obtidas de [PexChoose](static-helper-classes.md#pexchoose). Nesse sentido, os resultados de chamadas para código não gerenciado ou não instrumentado também são consideradas como "entradas" para o programa instrumentado, mas o IntelliTest não pode controlá-las. Se o fluxo de controle do programa depende de valores específicos provenientes dessas fontes externas, IntelliTest não pode "direcionar" o programa para áreas descobertas anteriormente. 

Além disso, o programa é considerado não determinístico se os valores das fontes externas mudam ao executar o programa novamente. Em tais casos o IntelliTest perde o controle sobre a execução do programa e a pesquisa se torna muito ineficiente.

Às vezes, não é óbvio quando isso acontece. Considere os exemplos a seguir:

* O resultado do método **GetHashCode()** é fornecido pelo código não gerenciado e não é previsível.
* A classe **System.Random** usa a hora atual do sistema para entregar valores aleatórios.
* A classe **System.DateTime** fornece a hora atual, que obviamente não está sob o controle do IntelliTest.

<a name="concurrency"></a>
### <a name="concurrency"></a>Concorrência

O IntelliTest não trata de programas multithread.

<a name="native-code"></a>
### <a name="native-code-net-code-that-is-not-instrumented"></a>Código nativo, código .NET que não é instrumentado

O IntelliTest não entende o código nativo, como instruções x86 chamadas por meio de **P/Invoke**. Ele não sabe como converter essas chamadas em restrições que podem ser passadas para o [solver de restrição](input-generation.md#constraint-solver). Mesmo para o código .NET, ele pode analisar somente o código que ele instrumenta. O IntelliTest não pode instrumentar certas partes do **mscorlib**, incluindo a biblioteca de reflexão. O **DynamicMethod** não pode ser instrumentado. 

A solução alternativa sugerida é ter um modo de teste em que esses métodos estão localizados em tipos em um assembly dinâmico. No entanto, mesmo se alguns métodos não forem instrumentados, o IntelliTest tentará abranger o máximo de código instrumentado possível.

<a name="platform"></a>
### <a name="platform"></a>Plataforma

O IntelliTest tem suporte apenas no .NET Framework X86 de 32 bits.

<a name="language"></a>
### <a name="language"></a>Idioma

Em princípio, o IntelliTest pode analisar programas .NET arbitrários, gravados em qualquer linguagem .NET. No entanto, no Visual Studio ele dá suporte apenas a C#.

<a name="symbolic-reasoning"></a>
### <a name="symbolic-reasoning"></a>Raciocínio simbólico

O IntelliTest usa um [solver de restrições](input-generation.md#constraint-solver) automático para determinar quais valores são relevantes para o teste e o programa em teste. No entanto, as habilidades do solver de restrição são, e sempre serão, limitadas.

<a name="incorrect-stack"></a>
### <a name="slightly-incorrect-stack-traces"></a>Rastreamentos de pilha (um pouco) incorretos

Como o IntelliTest captura e "relança" exceções em cada método instrumentado, os números de linha em rastreamentos de pilha não estarão corretos. Essa é uma limitação pelo design da instrução "relançar".

<a name="further-reading"></a>
## <a name="further-reading"></a>Leitura adicional

* [Postagem do blog introdutória](https://blogs.msdn.microsoft.com/visualstudioalm/2014/11/19/introducing-smart-unit-tests/) no MSDN.
* [Gerar testes de unidade para seu código com IntelliTest](../../test/generate-unit-tests-for-your-code-with-intellitest.md)

## <a name="got-feedback"></a>Recebeu comentários?

Poste suas ideias e solicitações de recursos no  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
