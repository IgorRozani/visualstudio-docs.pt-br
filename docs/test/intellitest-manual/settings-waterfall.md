---
title: Cascata de configurações | Ferramenta de teste para desenvolvedores do Microsoft IntelliTest
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: ec6364b3d130ab3ca333838c7e1b6eb2fdcb4a3d
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815045"
---
# <a name="settings-waterfall"></a>Cascata de configurações

O conceito de cascata de configurações significa que o usuário pode especificar as configurações no nível do **Assembly**, do **Acessório** e da **Exploração**:

* Assembly – [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* Acessório – [PexClass](attribute-glossary.md#pexclass)
* Exploração – [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

As configurações especificadas no nível do **Assembly** afetam todos os acessórios e as explorações sob esse assembly. As configurações especificadas no nível do **Acessório** afetam todas as explorações sob esse acessório. As configurações filho têm prioridade: se uma configuração for definida nos níveis do **Assembly** e do **Acessório**, serão usadas as configurações do **Acessório**.

Observe que algumas configurações são específicas para o nível do **Assembly** ou para o nível do **Acessório**.

**Exemplo**

```csharp
using Microsoft.Pex.Framework;

[assembly: PexAssemblySettings(MaxBranches = 1000)] // we override the default value of maxbranches

namespace MyTests
{
    [PexClass(MaxBranches = 500)] // we override the 1000 value and set maxbranches to 500 
    public partial class MyTests
    {
        [PexMethod(MaxBranches = 100)] // we override again, maxbranches = 100
        public void MyTest(...) { ... }
    }
}
```

## <a name="got-feedback"></a>Recebeu comentários?

Poste suas ideias e solicitações de recursos em [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest).
