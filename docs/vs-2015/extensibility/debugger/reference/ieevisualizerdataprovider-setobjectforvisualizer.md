---
title: IEEVisualizerDataProvider::SetObjectForVisualizer | Microsoft Docs
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
- IEEVisualizerDataProvider::SetObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer method
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f0fdb66e3bae4e485109a4a5d6a8e808d27ffeed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47473979"
---
# <a name="ieevisualizerdataprovidersetobjectforvisualizer"></a>IEEVisualizerDataProvider::SetObjectForVisualizer
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [IEEVisualizerDataProvider::SetObjectForVisualizer](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieevisualizerdataprovider-setobjectforvisualizer).  
  
Esse método altera o objeto que representa o visualizador.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetObjectForVisualizer(  
   IDebugObject*  pNewObject,  
   BSTR*          error,  
   IDebugObject** pException  
);  
```  
  
```csharp  
int SetObjectForVisualizer(  
   IDebugObject     pNewObject,  
   out string       error,  
   out IDebugObject pException  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pNewObject`  
 [in] O objeto a ser definido.  
  
 `error`  
 [out] Se houver um erro ao configurar o objeto, essa cadeia de caracteres contém a mensagem de erro.  
  
 `pException`  
 [out] Se houver um erro, esse objeto contém as informações de exceção.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="remarks"></a>Comentários  
 Cabe ao implementador para determinar como as informações de erro são retornadas. No entanto, é possível que alguns os chamadores podem ser somente olhada para ver se um objeto de exceção foi retornado, sabemos que existe foi um erro, portanto, esse método sempre deve retornar um objeto de exceção se ocorreu um erro. A cadeia de caracteres de erro também deve ser fornecida, caso o chamador deseja tornar usá-lo.  
  
## <a name="see-also"></a>Consulte também  
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)

