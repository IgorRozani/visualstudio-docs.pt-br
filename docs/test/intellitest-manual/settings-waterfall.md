---
title: "Cascata de configurações | Ferramenta de teste do desenvolvedor do Microsoft IntelliTest | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest, Settings waterfall
ms.assetid: 45777037-9E16-4ABF-BD26-5AF4E740D4E6
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: a56062f68fb0952d2b18726e1edecc26432e3fc3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="settings-waterfall"></a>Cascata de configurações

O conceito de cascata de configurações significa que o usuário pode especificar configurações no nível do **Assembly**, **Acessório** e **Exploração**: 

* Assembly – [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* Acessório – [PexClass](attribute-glossary.md#pexclass)
* Exploração – [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

As configurações especificadas no nível do **Assembly** afetarão todos os acessórios e explorações abaixo desse assembly. As configurações especificadas no nível do **Acessório** afetarão todas as explorações abaixo desse acessório. Ganho de configurações de filho: se uma configuração for definida nos níveis do **Assembly** e do **Acessório**, as configurações do **Acessório** serão usadas.

Observe que algumas configurações são específicas para o nível do **Assembly** ou para o nível do **Acessório**. 

**Exemplo**

```
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

Poste suas ideias e solicitações de recursos no  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
