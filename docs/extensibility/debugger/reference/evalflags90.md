---
title: EVALFLAGS90 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 120bf38afbf05f367757de3a5e453cab8b4311b1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102701"
---
# <a name="evalflags90"></a>EVALFLAGS90
Enumera os valores válidos para sinalizadores que controlam a avaliação da expressão. Esta enumeração estende o [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) enumeração.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
typedef DWORD EVALFLAGS90;  
```  
  
```csharp  
public enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
```  
  
#### <a name="parameters"></a>Parâmetros  
 EVAL90_RETURNVALUE  
 Especifica que o valor de retorno, se houver, deve ser avaliada.  
  
 EVAL90_NOSIDEEFFECTS  
 Especifica que efeitos colaterais não serão permitidas.  
  
 EVAL90_ALLOWBPS  
 Especifica a parada em pontos de interrupção.  
  
 EVAL90_ALLOWERRORREPORT  
 Especifica que esse relatório de erros para o host a ser permitido. Usado principalmente para a avaliação da expressão no script no Internet Explorer.  
  
 EVAL90_FUNCTION_AS_ADDRESS  
 Funções de força a ser avaliada como endereços, em vez de invocar a função.  
  
 EVAL90_NOFUNCEVAL  
 Impede que a função que está sendo avaliada. Por exemplo, considere o `int` token na expressão `myExpression(int) + 10`. Essa função pode ser avaliada corretamente como um endereço, mas não como um valor.  
  
 EVAL90_NOEVENTS  
 Sinalizador para indicar que os eventos que ocorrem durante a avaliação de expressão não devem ser enviados para o Gerenciador de sessão de depuração (SDM) ou para o IDE.  
  
 EVAL90_DESIGN_TIME_EXPR_EVAL  
 Permite que a avaliação da expressão de tempo de design.  
  
 EVAL90_ALLOW_IMPLICIT_VARS  
 Permite a criação da variável implícita.  
  
 EVAL90_FORCE_EVALUATION_NOW  
 Avaliação de força ocorra imediatamente. Isso é útil quando uma solicitação, como uma solicitação de usuário de serviço.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Enumerações](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)