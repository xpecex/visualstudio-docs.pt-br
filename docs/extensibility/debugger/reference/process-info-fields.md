---
title: PROCESS_INFO_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PROCESS_INFO_FIELDS
helpviewer_keywords:
- PROCESS_INFO_FIELDS enumeration
ms.assetid: 0d9cc345-3d3a-44d8-ae15-a67acb97a828
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3376db379e4e911bcaa8e865a16c63d1251229f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126380"
---
# <a name="processinfofields"></a>PROCESS_INFO_FIELDS
Especificar o tipo de informações para recuperar para um processo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
enum enum_PROCESS_INFO_FIELDS {   
   PIF_FILE_NAME             = 0x00000001,  
   PIF_BASE_NAME             = 0x00000002,  
   PIF_TITLE                 = 0x00000004,  
   PIF_PROCESS_ID            = 0x00000008,  
   PIF_SESSION_ID            = 0x00000010,  
   PIF_ATTACHED_SESSION_NAME = 0x00000020,  
   PIF_CREATION_TIME         = 0x00000040,  
   PIF_FLAGS                 = 0x00000080,  
   PIF_ALL                   = 0x000000ff  
};  
typedef DWORD PROCESS_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_PROCESS_INFO_FIELDS {   
   PIF_FILE_NAME             = 0x00000001,  
   PIF_BASE_NAME             = 0x00000002,  
   PIF_TITLE                 = 0x00000004,  
   PIF_PROCESS_ID            = 0x00000008,  
   PIF_SESSION_ID            = 0x00000010,  
   PIF_ATTACHED_SESSION_NAME = 0x00000020,  
   PIF_CREATION_TIME         = 0x00000040,  
   PIF_FLAGS                 = 0x00000080,  
   PIF_ALL                   = 0x000000ff  
};  
```  
  
## <a name="members"></a>Membros  
 PIF_FILE_NAME  
 Inicializar/usar o `bstrFileName` campo o [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) estrutura.  
  
 PIF_BASE_NAME  
 Inicializar/usar o `bstrBaseName` campo o `PROCESS_INFO` estrutura.  
  
 PIF_TITLE  
 Inicializar/usar o `bstrTitle` campo o `PROCESS_INFO` estrutura.  
  
 PIF_PROCESS_ID  
 Inicializar/usar o `ProcessId` campo o `PROCESS_INFO` estrutura.  
  
 PIF_SESSION_ID  
 Inicializar/usar o `dwSessionId` campo o `PROCESS_INFO` estrutura.  
  
 PIF_ATTACHED_SESSION_NAME  
 Inicializar/usar o `bstrAttachedSessionName` campo o `PROCESS_INFO` estrutura.  
  
 PIF_CREATION_TIME  
 Inicializar/usar o `CreationTime` campo o `PROCESS_INFO` estrutura.  
  
 PIF_FLAGS  
 Inicializar/usar o `Flags` campo o `PROCESS_INFO` estrutura.  
  
 PIF_ALL  
 Preenche todos os campos.  
  
## <a name="remarks"></a>Comentários  
 Passado para o [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) método para indicar quais campos do [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) estrutura devem ser inicializado.  
  
 Também é usado em `Fields` campo o `PROCESS_INFO` estrutura para indicar quais campos são usados e válido.  
  
 Esses sinalizadores podem ser combinados com um bit a bit `OR`.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Enumerações](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)