---
title: IntelliSense específico do Visual Basic | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
ms.assetid: 4dec8753-05e5-4f74-b304-5f8c4ed8723b
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9bae55b10695ba73fec86d7ab63943e3440e3f05
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47474760"
---
# <a name="visual-basic-specific-intellisense"></a>IntelliSense específico do Visual Basic
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [específico do Visual Basic IntelliSense](https://docs.microsoft.com/visualstudio/ide/visual-basic-specific-intellisense).  
  
O editor de código-fonte do Visual Basic oferece os seguintes recursos de IntelliSense:  
  
-   Dicas de sintaxe  
  
     Dicas de sintaxe são exibidas na sintaxe da instrução que você está digitando. Isso é útil para instruções de como [Declare](http://msdn.microsoft.com/library/d3f21fb0-b804-4c99-97ed-583b23894cf1).  
  
## <a name="automatic-completion"></a>Conclusão automática  
  
-   Conclusão em várias palavras-chave  
  
     Por exemplo, se você digitar `goto` e um espaço, o IntelliSense exibirá uma lista dos rótulos definidos em um menu suspenso. Outras palavras-chave com suporte incluem `Exit`, `Implements`, `Option` e `Declare`.  
  
-   Conclusão em `Enum` e `Boolean`  
  
     Quando uma instrução fizer referência a um membro de uma enumeração, o IntelliSense exibirá uma lista dos membros de `Enum`. Quando uma instrução fizer referência a um `Boolean`, o IntelliSense exibirá um menu suspenso de verdadeiro ou falso.  
  
 A conclusão pode ser desativada por padrão desmarcando **Listar membros automaticamente** na página de propriedades **Geral** na pasta **Visual Basic**.  
  
 Você pode invocar manualmente a conclusão invocando Listar Membros, Completar Palavra ou ALT + SETA PARA A DIREITA. Para obter mais informações, veja [Usando o IntelliSense](../ide/using-intellisense.md).  
  
## <a name="intellisense-in-zone"></a>IntelliSense por Zona  
 O IntelliSense por Zona ajuda desenvolvedores de Visual Basic que precisam implantar aplicativos por meio de [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] e que estão restritos a configurações de confiança parcial. Este recurso:  
  
-   Permite escolher as permissões com que o aplicativo será executado.  
  
-   Exibe APIs na Zona escolhida como disponíveis em Listar Membros e exibe APIs que requerem permissões adicionais como não disponíveis.  
  
 Para obter mais informações, consulte [Segurança de acesso do código para aplicativos ClickOnce](../deployment/code-access-security-for-clickonce-applications.md).  
  
## <a name="see-also"></a>Consulte também  
 [Usando o IntelliSense](../ide/using-intellisense.md)



