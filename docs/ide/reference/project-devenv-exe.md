---
title: -Project (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /project Devenv switch
- projects [Visual Studio], rebuilding
- projects [Visual Studio], building
- deployment projects, specifying
- project Devenv switch (/project)
- Devenv, /project switch
- projects [Visual Studio], cleaning
ms.assetid: 8b07859c-3439-436d-9b9a-a8ee744eee30
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 588b56c03dbd14b1b7658b92a67b02a6dc3892eb
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704071"
---
# <a name="project-devenvexe"></a>/Project (devenv.exe)
Identifica um único projeto dentro da configuração da solução especificada para ser compilado, limpo, recompilado ou implantado.

## <a name="syntax"></a>Sintaxe

```cmd
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]
```

## <a name="arguments"></a>Arguments
 /build

 Compila o projeto especificado por `/project` `ProjName`.

 /clean

 Limpa todos os arquivos intermediários e diretórios de saída criados durante um build.

 /rebuild

 Limpa e, em seguida, compila o projeto especificado por `/project` `ProjName`.

 /deploy

 Especifica que o projeto será implantado após um build ou uma recompilação.

 `SolnConfigName`

 Necessário. O nome da configuração da solução que será aplicado à solução nomeada em `SolutionName`.

 `SolutionName`

 Necessário. O caminho completo e o nome do arquivo de solução.

 /project `ProjName`

 Opcional. O caminho e o nome de um arquivo de projeto na solução. É possível inserir um caminho relativo da pasta `SolutionName` para o arquivo de projeto ou o nome de exibição do projeto ou o caminho completo e o nome do arquivo de projeto.

 /projectconfig `ProjConfigName`

 Opcional. O nome de uma configuração de build do projeto a ser aplicado ao `/project` nomeado.

## <a name="remarks"></a>Comentários

-   Parte de um comando `devenv /build`, /`clean`, `/rebuild` ou `/deploy` deve ser usada.

-   Coloque as cadeias de caracteres que incluem espaços entre aspas duplas.

-   As informações de resumo para builds, incluindo erros, podem ser exibidas na janela **Comando** ou em qualquer arquivo de log especificado com a opção `/out`.

## <a name="example"></a>Exemplo
 Este exemplo compila o projeto `CSharpConsoleApp`, usando a configuração de build do projeto `Debug` na configuração de solução `Debug` de `MySolution`.

```cmd
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Consulte também

- [Opções de linha de comando devenv](../../ide/reference/devenv-command-line-switches.md)
- [/ProjectConfig (devenv.exe)](../../ide/reference/projectconfig-devenv-exe.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Deploy (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)