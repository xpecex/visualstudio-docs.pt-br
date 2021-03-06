---
title: Codificações e quebras de linha | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.Encoding
helpviewer_keywords:
- line breaks
- encoding
- Visual Studio, encoding
- editors, line breaks
- line break characters
- Visual Studio, line break characters
ms.assetid: 8f9b3ffc-7b8d-44f4-87cb-dc29105be12d
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8fd03dba0dfb13723fcb44d489a7b850aebeb1e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47466602"
---
# <a name="encodings-and-line-breaks"></a>Codificações e quebras de linha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [codificações e quebras de linha](https://docs.microsoft.com/visualstudio/ide/encodings-and-line-breaks).  
  
No Visual Studio, é possível usar os configurações **Arquivo/Opções avançadas de salvamento** configurações para determinar o tipo de quebra de linha caracteres que você deseja. Também é possível alterar a codificação de um arquivo com as mesmas configurações.  
  
> [!NOTE]
>  Se você tiver determinados tipos de configurações de desenvolvimento (Visual Basic, F#, Desenvolvimento para a Web), talvez você não veja **Opções avançadas de salvamento** no menu. Para alterar suas configurações (por exemplo para Geral), abra **Ferramentas/Importar e Exportar Configurações**. Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 No Visual Studio, os seguintes caracteres são interpretados como quebras de linha:  
  
-   CRLF: retorno de carro + alimentação de linha, caracteres Unicode 000D + 000A  
  
-   LF: alimentação de linha, caractere Unicode 000A  
  
-   NEL: próxima linha, caractere Unicode 0085  
  
-   LS: separador de linha, caractere Unicode 2028  
  
-   PS: separador de parágrafo, caractere Unicode 2029  
  
 O texto copiado de outros aplicativos mantém a codificação original e os caracteres de quebra de linha. Por exemplo, quando você copia texto do Bloco de notas e o cola em um arquivo de texto no Visual Studio, o texto tem as mesmas configurações que ele tinha no Bloco de notas.  
  
 Quando você abre um arquivo que caracteres com uma quebra de linha diferente, talvez você veja uma caixa de diálogo que pergunta se os caracteres de quebra de linha inconsistentes devem ser normalizados e quais os tipo de quebras de linha você deseja escolher.



