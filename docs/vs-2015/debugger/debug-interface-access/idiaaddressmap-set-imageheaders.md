---
title: 'Idiaaddressmap:: Set_imageheaders | Microsoft Docs'
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
- IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6ec20d37f06f5a51ebf83b1212feafd886f84b4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47474262"
---
# <a name="idiaaddressmapsetimageheaders"></a>IDiaAddressMap::set_imageHeaders
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [idiaaddressmap:: Set_imageheaders](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaaddressmap-set-imageheaders).  
  
Conjuntos de cabeçalhos para habilitar a conversão de endereço virtual relativo de imagem.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT set_imageHeaders (   
   DWORD cbData,  
   BYTE  data[],  
   BOOL  originalHeaders  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 cbData  
 [in] Número de bytes de dados de cabeçalho. Deve ser `n*sizeof(IMAGE_SECTION_HEADER)` onde `n` é o número de cabeçalhos de seção no executável.  
  
 [Data]  
 [in] Uma matriz de `IMAGE_SECTION_HEADER` estruturas a ser usado como o cabeçalho de imagem.  
  
 originalHeaders  
 [in] Definido como `FALSE` se os cabeçalhos de imagem forem da nova imagem, `TRUE` se eles refletem a imagem original antes de um upgrade. Normalmente, isso seria definido como `TRUE` apenas em combinação com chamadas para o [idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) método.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retornará `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="remarks"></a>Comentários  
 O `IMAGE_SECTION_HEADER` estrutura é declarada em Winnt. h e representa o formato de cabeçalho de seção de imagem do executável.  
  
 Dependem de cálculos de endereço virtual relativo a `IMAGE_SECTION_HEADER` valores. Normalmente, o DIA recupera esses do arquivo de banco de dados (. PDB) do programa. Se esses valores estiverem ausentes, o DIA não consegue calcular endereços virtuais e o [idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) retorno do método `FALSE`. O cliente deve, em seguida, chamar o [idiaaddressmap:: Put_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) método para habilitar os cálculos de endereço virtual relativo depois de fornecer os cabeçalhos de imagem ausentes da imagem em si.  
  
## <a name="see-also"></a>Consulte também  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [Idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)



