---
title: 'CA5350: Não usar algoritmos criptográficos fracos | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c51bb8a-fcfa-46aa-ab61-634be84c4a7a
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8321d94bbdcc66bb8e7405f2f3188ba3eeaaabd8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47466133"
---
# <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a>CA5350: não use algoritmos criptográficos fracos
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||  
|-|-|  
|NomeDoTipo|DoNotUseWeakCryptographicAlgorithms|  
|CheckId|CA5350|  
|Categoria|Microsoft.Cryptography|  
|Alteração Significativa|Não separável|  
  
> [!NOTE]
>  Esse aviso foi atualizado pela última vez em novembro de 2015.  
  
## <a name="cause"></a>Causa  
 Algoritmos de criptografia, como <xref:System.Security.Cryptography.TripleDES> e, como os algoritmos de hash <xref:System.Security.Cryptography.SHA1> e <xref:System.Security.Cryptography.RIPEMD160> são considerados fracos.  
  
 Esses algoritmos de criptografia não oferecem tanta garantia de segurança como equivalentes mais modernas. Criptografia de algoritmos de hash <xref:System.Security.Cryptography.SHA1> e <xref:System.Security.Cryptography.RIPEMD160> fornecem menos resistência a colisão de mais moderno de algoritmos de hash. O algoritmo de criptografia <xref:System.Security.Cryptography.TripleDES> fornece menos bits de segurança que algoritmos de criptografia mais modernos.  
  
## <a name="rule-description"></a>Descrição da Regra  
 Algoritmos de criptografia fraca e funções de hash são usadas atualmente por uma série de motivos, mas não deve ser usados para garantir a confidencialidade dos dados que eles protegem.  
  
 A regra dispara quando ele localiza o 3DES, SHA1 ou RIPEMD160 algoritmos no código e gera um aviso ao usuário.  
  
## <a name="how-to-fix-violations"></a>Como Corrigir Violações  
 Use opções criptograficamente mais fortes:  
  
-   Para criptografia TripleDES, use <xref:System.Security.Cryptography.Aes> criptografia.  
  
-   Para funções de hash SHA1 ou RIPEMD160, use os dos [SHA-2](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382459.aspx) família (por exemplo, <xref:System.Security.Cryptography.SHA512>, <xref:System.Security.Cryptography.SHA384>, <xref:System.Security.Cryptography.SHA256>).  
  
## <a name="when-to-suppress-warnings"></a>Quando Suprimir Avisos  
 Suprima um aviso nessa regra, quando o nível de proteção necessário para os dados não requer uma garantia de segurança.  
  
## <a name="pseudo-code-example"></a>Exemplo de pseudocódigo  
 No momento da redação deste artigo, o exemplo de pseudocódigo a seguir ilustra o padrão de detectadas por essa regra.  
  
### <a name="sha-1-hashing-violation"></a>Violação de hash SHA-1  
  
```  
using System.Security.Cryptography;   
...   
var hashAlg = SHA1.Create();  
  
```  
  
### <a name="solution"></a>Solução  
  
```  
using System.Security.Cryptography;   
...   
var hashAlg = SHA256.Create();  
  
```  
  
### <a name="ripemd160-br-br-hashing-violation"></a>RIPEMD160 <br /><br />Violação de hash  
  
```  
using System.Security.Cryptography;   
...   
var hashAlg = RIPEMD160Managed.Create();  
  
```  
  
### <a name="solution"></a>Solução  
  
```  
using System.Security.Cryptography;   
...   
var hashAlg = SHA256.Create();  
  
```  
  
### <a name="tripledes-encryption-violation"></a>Violação de criptografia TripleDES  
  
```  
using System.Security.Cryptography;   
...    
using (TripleDES encAlg = TripleDES.Create())   
{   
  ...   
}  
```  
  
### <a name="solution"></a>Solução  
  
```  
using System.Security.Cryptography;   
...   
using (AesManaged encAlg = new AesManaged())   
{   
  ...   
}  
```