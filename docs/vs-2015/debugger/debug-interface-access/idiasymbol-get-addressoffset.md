---
title: 'Idiasymbol:: Get_addressoffset | Microsoft Docs'
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
- C++
helpviewer_keywords:
- IDiaSymbol::get_addressOffset method
ms.assetid: c15639b0-7f37-46c7-891b-40273b7f6319
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 810d9e90c5b1313db5714dfc476a99ceb50149ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47461499"
---
# <a name="idiasymbolgetaddressoffset"></a>IDiaSymbol::get_addressOffset
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [idiasymbol:: Get_addressoffset](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-addressoffset).  
  
Recupera a parte do deslocamento de um local de endereço. Usado quando o [enumeração LocationType](../../debugger/debug-interface-access/locationtype.md) é definido como `LocIsStatic`.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT get_addressOffset (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pRetVal`  
 [out] Retorna a parte do deslocamento de um local de endereço.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna `S_FALSE` ou um código de erro.  
  
> [!NOTE]
>  Um valor de retorno `S_FALSE` significa que a propriedade não está disponível para o símbolo.  
  
## <a name="remarks"></a>Comentários  
 Para membros estáticos localizados em uma DLL externa, o deslocamento retornado por esse método pode ser 0, como esse método depende na obtenção do endereço virtual do membro. Endereços virtuais são válidos somente se o [idiasession:: Put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) método o [IDiaSession](../../debugger/debug-interface-access/idiasession.md) interface foi chamado com um parâmetro diferente de zero, especificando o endereço de carregamento da DLL.  
  
 Para obter a parte da seção de um endereço, chame o [idiasymbol:: Get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md) método.  
  
## <a name="requirements"></a>Requisitos  
  
|Requisito|Descrição|  
|-----------------|-----------------|  
|Cabeçalho:|dia2.h|  
|Versão:|DIA SDK v7.0|  
  
## <a name="see-also"></a>Consulte também  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Enumeração LocationType](../../debugger/debug-interface-access/locationtype.md)   
 [Idiasymbol:: Get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)   
 [Idiasession:: Put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)



