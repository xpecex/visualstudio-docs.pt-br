---
title: Extensibilidade do serviço de linguagem herdado | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- language services
- Visual Studio, language services
ms.assetid: 2700cd4d-5f68-43fc-b62f-dc80c3f3aa85
caps.latest.revision: 43
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ea9ade367c2e10c228b149385fb0c40e3b803ad1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47473988"
---
# <a name="legacy-language-service-extensibility"></a>Extensibilidade do serviço de linguagem herdado
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [extensibilidade de serviço de linguagem herdado](https://docs.microsoft.com/visualstudio/extensibility/internals/legacy-language-service-extensibility).  
  
Um serviço de linguagem fornece suporte de idioma específico para a edição de código-fonte no IDE.  
  
 Serviços de linguagem herdado são implementados como parte de um VSPackage, mas a maneira mais recente para implementar recursos de serviço de linguagem é usar extensões MEF. Para obter mais informações sobre a nova maneira de implementar um serviço de linguagem, consulte [Editor e extensões do serviço de linguagem](../../extensibility/editor-and-language-service-extensions.md).  
  
 Esta seção discute a estrutura e a implementação de um serviço de linguagem herdada.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Migrar um serviço de linguagem herdado](../../extensibility/internals/migrating-a-legacy-language-service.md)  
 Explica como atualizar um serviço de linguagem do Visual Studio 2008 para a versão mais recente.  
  
 [Fundamentos do serviço de linguagem herdado](../../extensibility/internals/legacy-language-service-essentials.md)  
 Fornece informações importantes sobre como desenvolver serviços de linguagem para integrar uma linguagem de programação no Visual Studio.  
  
 [Desenvolver um serviço de linguagem herdado](../../extensibility/internals/developing-a-legacy-language-service.md)  
 Fornece links para tópicos que podem ajudar você a criar um serviço de linguagem.  
  
 [Coloração de sintaxe em um serviço de linguagem herdado](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Fornece informações sobre o suporte a realce de sintaxe em um serviço de linguagem.  
  
 [Implementando um serviço de linguagem herdado](../../extensibility/internals/implementing-a-legacy-language-service1.md)  
 Fornece informações sobre como usar a estrutura de pacote gerenciado (MPF) para implementar um serviço de linguagem completa no código gerenciado.  
  
 [Suporte a ferramentas de navegação por símbolo](../../extensibility/internals/supporting-symbol-browsing-tools.md)  
 Descreve as bibliotecas e ferramentas que permitem que você navegue os modos de exibição de árvore de símbolos no IDE.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Editor e extensões do serviço de linguagem](../../extensibility/editor-and-language-service-extensions.md)  
 Fornece uma visão geral dos editores do Visual Studio.  
  
 [Suporte do serviço de linguagem para depuração](../../extensibility/internals/language-service-support-for-debugging.md)  
 Fornece informações sobre como e um link para o SDK do Visual Studio de depuração, que contém as informações necessárias para criar e personalizar componentes do depurador usados para depurar programas.

