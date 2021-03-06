---
title: Desativar avisos de compatibilidade para Plug-ins de controle do código-fonte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, turning off compatibility warnings
- compatibility warnings, turning off
ms.assetid: ba318e12-921b-4b7a-a8c2-12c712be1dbf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3e096b52bdf6e3e0065eefbba708d7bda18ab189
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39498042"
---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>Como: desativar avisos de compatibilidade para plug-ins de controle de origem
Um usuário pode ver vários avisos de compatibilidade durante o emprego de controle de origem no [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Os avisos apresentados dependem dos recursos de plug-in de controle do código-fonte e podem ser desabilitados como detalhada aqui.  
  
### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>Para desabilitar o aviso: "para garantir a integração de controle de código-fonte ideal com o Visual Studio"  
  
-   Defina a seguinte entrada do registro (adicionando o valor, se necessário):  
  
     **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = DWORD: 00000001**  
  
     Esse aviso é exibido para todos os não -[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] plug-ins.  
  
### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>Para desabilitar o aviso: "o provedor de controle de origem instalado não oferece suporte a todos os recursos"  
  
-   Defina os seguintes valores de registro de dois (adicionando os valores se necessário):  
  
     **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider = DWORD: 00000000**  
  
    **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = DWORD: 00000001**  
  
     Esse aviso é exibido se o plug-in de controle do código-fonte não suporte explicitamente reentrância para vários projetos (ou seja, se ele pode verificar em apenas um arquivo e projeto cada vez).  
  
     É melhor dar suporte a reentrância (`SCC_CAP_REENTRANT` capacidade); portanto, irá remover este aviso. No entanto, se esse suporte não for possível, essas entradas do Registro podem ser definidas.  
  
## <a name="see-also"></a>Consulte também  
 [Sinalizadores de recurso](../extensibility/capability-flags.md)