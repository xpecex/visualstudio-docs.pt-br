---
title: 'Como: desabilitar a ativação de aplicativos ClickOnce pela URL | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- disallowUrlActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: db31a16b-960f-4264-91d7-c7c40f876068
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: ad43abbafe1d5f70bb2de748154a0066aa3d8927
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47464005"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications"></a>Como desabilitar a ativação de aplicativos ClickOnce pela URL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [como: desabilitar a ativação de URL de aplicativos ClickOnce](https://docs.microsoft.com/visualstudio/deployment/how-to-disable-url-activation-of-clickonce-applications).  
  
Normalmente, um [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicativo será iniciado automaticamente, imediatamente após a instalação de um servidor Web. Por motivos de segurança, você pode optar por desabilitar esse comportamento e diga aos usuários para iniciar o aplicativo a partir de **iniciar** menu em vez disso. O procedimento a seguir descreve como desabilitar a ativação de URL.  
  
 Essa técnica pode ser usada somente para [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplicativos instalados no computador do usuário de um servidor Web. Ele não pode ser usado para aplicativos somente online, que podem ser iniciados apenas por meio de sua URL. Para obter mais informações sobre a diferença entre os aplicativos instalados e somente online, consulte [escolhendo uma estratégia de implantação do ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 Este procedimento usa o [!INCLUDE[winsdklong](../includes/winsdklong-md.md)] MageUI.exe de ferramentas. Para obter mais informações sobre essa ferramenta, consulte [MageUI.exe (Manifest Generation and Editing Tool, cliente gráfico)](http://msdn.microsoft.com/library/f9e130a6-8117-49c4-839c-c988f641dc14). Você também pode executar esse procedimento usando [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
## <a name="procedure"></a>Procedimento  
  
#### <a name="to-disable-url-activation-for-your-application"></a>Para desabilitar a ativação de URL para seu aplicativo  
  
1.  Abra o manifesto de implantação no MageUI.exe. Se você não ainda tiver criado uma, siga as etapas em [instruções passo a passo: Implantando um aplicativo ClickOnce manualmente](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
2.  Selecione o **opções de implantação** guia.  
  
3.  Desmarque a **executar o aplicativo depois de instalar automaticamente** caixa de seleção.  
  
4.  Salve e assinar o manifesto.  
  
## <a name="see-also"></a>Consulte também  
 [Publicando aplicativos ClickOnce](../deployment/publishing-clickonce-applications.md)



