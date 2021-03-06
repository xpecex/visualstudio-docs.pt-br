---
title: Solução de problemas do Visualizador da Ajuda | Microsoft Docs
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
- troubleshooting [Help Viewer 2.0]
- Help Viewer 2.0, troubleshooting
ms.assetid: 461a4553-064a-4142-a2d2-058658b9ba12
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 68946af27925347cee497c237de396d31f214e13
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47474170"
---
# <a name="troubleshooting-the-help-viewer"></a>Solucionando problemas do Visualizador da Ajuda
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [solução de problemas do Help Viewer](https://docs.microsoft.com/visualstudio/ide/troubleshooting-the-help-viewer).  
  
Este tópico aborda problemas que podem ocorrer com o Visualizador da Ajuda.  
  
## <a name="audio-doesnt-work"></a>O áudio não funciona.  
 O Visualizador da Ajuda não inclui um player de áudio. Se você baixar conteúdo que contém áudio e nada acontecer quando você escolher **Reproduzir**, instale um player de áudio.  
  
## <a name="search-doesnt-work-in-windows-server-2008-windows-server-2008-with-sp1-or-windows-server-2008-r2"></a>A pesquisa não funciona no Windows Server 2008, no Windows Server 2008 com SP1 ou no Windows Server 2008 R2.  
 Os recursos de pesquisa e filtro do Visualizador da Ajuda requerem que o serviço Windows Search esteja instalado. Por padrão, esse serviço fica desativado no Windows Server 2008, no Windows Server 2008 com Service Pack 1 (SP1) e no Windows Server 2008 R2.  
  
#### <a name="to-activate-windows-search-service"></a>Para ativar o serviço Windows Search  
  
1.  Inicie o Gerenciador do Servidor.  
  
2.  No painel de navegação esquerdo, escolha **Funções**.  
  
3.  No painel Resumo de Funções, escolha **Adicionar Função**.  
  
4.  Escolha a função Serviços de Arquivo e escolha o botão **Avançar**.  
  
5.  Escolha o serviço de função do Windows Search.  
  
## <a name="additional-resources"></a>Recursos adicionais  
 Você pode obter mais informações e fornecer comentários sobre o Visualizador da Ajuda usando os seguintes recursos:  
  
-   Para fornecer comentários, consulte [Microsoft Connect](http://go.microsoft.com/fwlink/?linkid=243983) no site da Microsoft ou enviar um email para [hlpfdbk@microsoft.com](mailto:hlpfdbk@microsoft.com).  
  
-   Para obter mais informações, consulte o fórum [Documentação do Desenvolvedor e Sistema de Ajuda](http://go.microsoft.com/fwlink/?LinkId=232741) e o blog [The Help Guy](http://go.microsoft.com/fwlink/?LinkId=232743).  
  
## <a name="see-also"></a>Consulte também  
 [Guia do administrador do Help Viewer 2.1](http://go.microsoft.com/fwlink/?LinkId=243985)



