---
title: 'Erro: O usuário não conseguiu executar procedimento armazenado sp_enable_sql_debug | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.sqlde_accessdenied
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 11957495-c238-4cc5-8937-e4026f5e10e1
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 172b7b7870e3bf35b2cda5fc04a894b6c52c70d4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47465791"
---
# <a name="error-user-could-not-execute-stored-procedure-spenablesqldebug"></a>Erro: o usuário não conseguiu executar o procedimento armazenado sp_enable_sql_debug
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [erro: usuário não conseguiu executar procedimento armazenado sp_enable_sql_debug](https://docs.microsoft.com/visualstudio/debugger/error-user-could-not-execute-stored-procedure-sp-enable-sql-debug).  
  
A depuração do Procedimento Armazenado sp_enable_sql_debug não pode ser executada no servidor. Isso pode ser causado por:  
  
-   Um problema de conexão. Você precisa ter uma conexão estável com o servidor.  
  
-   Falta das permissões necessárias no servidor. Para depurar no SQL Server 2005, a conta que executa o Visual Studio e a conta usada para conectar-se ao SQL Server devem ser membros da função sysadmin. A conta usada para se conectar ao SQL Server é sua conta de usuário do Windows (se você estiver usando a autenticação do Windows) ou uma conta com ID de usuário e senha (se você usar a autenticação do SQL).  
  
 Para obter mais informações, consulte [como: definir permissões do SQL Server para depuração](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
## <a name="see-also"></a>Consulte também  
 [Como: definir permissões do SQL Server para depuração](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Configuração de depuração de SQL](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)



