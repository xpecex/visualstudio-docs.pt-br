---
title: IDebugModule2 | Microsoft Docs
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
- IDebugModule2
helpviewer_keywords:
- IDebugModule2 interface
ms.assetid: 24c2a126-f4ab-4891-8509-8ef99b994c08
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 41ace88c884126ee293a379f0ed1f7dce030e29a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47460608"
---
# <a name="idebugmodule2"></a>IDebugModule2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [IDebugModule2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmodule2).  
  
Essa interface representa um módulo — ou seja, uma unidade executável de um programa, tal como uma DLL.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
IDebugModule2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Observações para implementadores  
 O mecanismo de depuração (DES) implementa essa interface para representar um módulo e para fornecer acesso a informações sobre esse módulo.  
  
## <a name="notes-for-callers"></a>Observações para chamadores  
 Uma chamada para [GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md) retorna essa interface. O envia do [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md) interface com o Gerenciador de depuração de sessão (SDM) usando o [evento](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) método.  
  
 Essa interface também pode ser retornada em uma [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) estrutura (que é retornado por uma chamada para [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)).  
  
 [Próxima](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md) também retorna essa interface ([EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) retorna o [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md) interface).  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable  
 A tabela a seguir mostra os métodos de `IDebugModule2`.  
  
|Método|Descrição|  
|------------|-----------------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)|Obtém o [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) que descreve esse módulo.|  
|[ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md)|OBSOLETO. NÃO USE. Recarrega os símbolos para esse módulo.|  
  
## <a name="remarks"></a>Comentários  
 Informações de módulo podem ser exibidas na **módulos** janela do IDE.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Principais Interfaces](../../../extensibility/debugger/reference/core-interfaces.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)   
 [GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)   
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)

