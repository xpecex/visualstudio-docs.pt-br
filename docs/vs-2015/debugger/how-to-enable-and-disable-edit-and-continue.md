---
title: 'Como: habilitar e desabilitar editar e continuar | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 57a9ec8b8e25da6edb36e1983e45f7bb78251208
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47463994"
---
# <a name="how-to-enable-and-disable-edit-and-continue"></a>Como habilitar e desabilitar Editar e Continuar
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [como: habilitar e desabilitar editar e continuar](https://docs.microsoft.com/visualstudio/debugger/how-to-enable-and-disable-edit-and-continue).  
  
Você pode desabilitar ou habilitar editar e continuar na **opções** caixa de diálogo em tempo de design. Não é possível alterar essa configuração enquanto você está depurando.  
  
 Editar e Continuar só funciona em compilações de depuração. Para o C++ nativo, Editar e Continuar exige o uso da opção /INCREMENTAL.  
  
## <a name="procedures"></a>Procedimentos  
  
#### <a name="to-enabledisable-edit-and-continue"></a>Para habilitar/desabilitar a função Editar e Continuar  
  
1.  Abrir página de opções de depuração (**Ferramentas / opções / depuração**).  
  
2.  Role para baixo até **editar e continuar** categoria.  
  
3.  Para habilitar, selecione a **habilitar editar e continuar** caixa de seleção. Para desabilitar, desmarque a caixa de seleção.  
  
    > [!NOTE]
    >  Se IntelliTrace estiver habilitado e você coletar eventos de IntelliTrace e informações de chamada, Editar e Continuar estará desabilitado. Para obter mais informações, consulte [configurar o IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
4.  Clique em **OK**.  
  
 Para obter mais informações sobre essas opções, consulte [geral, depuração, caixa de diálogo Opções](../debugger/general-debugging-options-dialog-box.md).  
  
## <a name="see-also"></a>Consulte também  
 [Editar e continuar](../debugger/edit-and-continue.md)



