---
title: 'CA2131: os tipos críticos de segurança podem não participar da equivalência de tipo'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2131
ms.assetid: 4170f3b1-6086-430d-8fba-837d5538c573
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 681b2916ef6e6e5c90d98b7a88874a7fb0166549
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546701"
---
# <a name="ca2131-security-critical-types-may-not-participate-in-type-equivalence"></a>CA2131: os tipos críticos de segurança podem não participar da equivalência de tipo
|||
|-|-|
|NomeDoTipo|CriticalTypesMustNotParticipateInTypeEquivalence|
|CheckId|CA2131|
|Categoria|Microsoft.Security|
|Alteração Significativa|Quebra|

## <a name="cause"></a>Causa
 Um tipo participa da equivalência de tipo e um o tipo em si, ou um membro ou campo do tipo, é marcado com o <xref:System.Security.SecurityCriticalAttribute> atributo.

## <a name="rule-description"></a>Descrição da regra
 Esta regra é acionada em qualquer tipo crítico ou em tipos que contenham métodos críticos ou campos que estejam participando da equivalência do tipo. Quando o CLR detecta desse tipo, não consiga carregá-lo com um <xref:System.TypeLoadException> em tempo de execução. Normalmente, essa regra só é acionada quando usuários implementam equivalência de tipo manualmente, em vez de depender de tlbimp e dos compiladores para fazer a equivalência do tipo.

## <a name="how-to-fix-violations"></a>Como corrigir violações
 Para corrigir uma violação dessa regra, remova o atributo SecurityCritical.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos
 Não suprima um aviso nessa regra.

## <a name="example"></a>Exemplo
 Os exemplos a seguir demonstram uma interface, um método e um campo que fará com que a regra seja disparada.

 [!code-csharp[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../code-quality/codesnippet/CSharp/ca2131-security-critical-types-may-not-participate-in-type-equivalence_1.cs)]

## <a name="see-also"></a>Consulte também
 [Código transparente de segurança, nível 2](/dotnet/framework/misc/security-transparent-code-level-2)