---
title: 'Como: implementar o localizar e substituir o mecanismo | Microsoft Docs'
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
- editors [Visual Studio SDK], legacy - find and replace
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: eaae77979fc15954b4480a038c791a15bd95ab65
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47462425"
---
# <a name="how-to-implement-the-find-and-replace-mechanism"></a>Como: implementar o localizar e substituir o mecanismo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [como: implementar a localizar e substituir o mecanismo](https://docs.microsoft.com/visualstudio/extensibility/how-to-implement-the-find-and-replace-mechanism).  
  
Visual Studio fornece duas maneiras de localizar/substituir a implementação. Uma maneira é passar uma imagem de texto para o shell e deixá-lo a lidar com a pesquisa, realce e substituindo texto. Isso permite aos usuários especificar vários intervalos de texto. Como alternativa, o VSPackage pode controlar essa funcionalidade em si. Em ambos os casos, você deve notificar o shell sobre o destino atual e as metas para todos os documentos abertos.  
  
### <a name="to-implement-findreplace"></a>Para implementar localizar/substituir  
  
1.  Implemente a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget> interface em um dos objetos retornados pelas propriedades quadro <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> ou <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>. Se você estiver criando um editor personalizado, você deve implementar essa interface como parte da classe editor personalizado.  
  
2.  Use o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A> método para especificar as opções que dá suporte a seu editor e indicar se ele implementa a pesquisa de imagem de texto.  
  
     Se seu editor dá suporte à pesquisa de imagem de texto, implementar <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>.  
  
     Caso contrário, implementar <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> e <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>.  
  
3.  Se você implementar o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> e <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A> métodos, você pode simplificar as tarefas de pesquisa, chamando o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper> interface.  
  
## <a name="see-also"></a>Consulte também  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>

