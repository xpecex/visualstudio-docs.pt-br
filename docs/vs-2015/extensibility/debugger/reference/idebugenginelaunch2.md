---
title: IDebugEngineLaunch2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEngineLaunch2
helpviewer_keywords:
- IDebugEngineLaunch2 interface
ms.assetid: 5eaf2ad8-3fbf-446e-b48b-5327ad3f5255
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3b4f70dac4d8831b02e458be3b8b4e38e5703b5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47465789"
---
# <a name="idebugenginelaunch2"></a>IDebugEngineLaunch2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [IDebugEngineLaunch2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugenginelaunch2).  
  
Usado por um mecanismo de depuração (DE) para iniciar e encerrar programas.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
IDebugEngineLaunch2 : IDebugEngine2  
```  
  
## <a name="notes-for-implementers"></a>Observações para implementadores  
 Essa interface é implementada por uma personalizado DE se ele tiver requisitos especiais para iniciar um processo que não pode ser manipulado inteiramente por uma porta personalizada. Isso normalmente é o caso quando o DE faz parte de um interpretador e o processo que está sendo depurado é um script: o interpretador precisa ser iniciado pela primeira vez e, em seguida, o script é carregado e iniciado. Uma porta pode iniciar o interpretador, mas o script pode exigir tratamento especial (que é onde o DE tem uma função). Essa interface é implementada somente se houver requisitos exclusivos para iniciar um programa que uma porta personalizada não pode manipular.  
  
## <a name="notes-for-callers"></a>Observações para chamadores  
 Essa interface é chamada pelo Gerenciador de depuração de sessão (SDM) se o SDM pode obter essa interface do [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) (usando QueryInterface) de interface. Se essa interface pode ser obtida, o SDM sabe que o DE tem requisitos especiais e chama essa interface para iniciar o programa em vez de ter a porta iniciá-lo.  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable  
 A tabela a seguir mostra os métodos de `IDebugEngineLaunch2`.  
  
|Método|Descrição|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)|Inicia um processo por meio DE.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)|Retoma a execução do processo.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md)|Determina se um processo pode ser encerrado.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)|Finaliza um processo.|  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)

