---
title: Exibição de Linhas – Dados de Contenção | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Lines view
ms.assetid: 859b02d2-eddf-4ad3-95de-0df67ee2ab03
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 09149f44e80155a13986d42d2b3279e5c39c8884
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47466549"
---
# <a name="lines-view---contention-data"></a>Exibição de Linhas – Dados de Contenção
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [exibição de linhas – dados de contenção](https://docs.microsoft.com/visualstudio/profiling/lines-view-contention-data).  
  
A exibição de Linhas de dados de contenção lista os dados de desempenho das instruções que estavam em execução quando as amostras foram coletadas na criação de perfil. Em um arquivo de origem, uma instrução pode abranger mais de uma linha em um arquivo de origem, e uma única linha pode incluir mais de uma instrução.  
  
 Uma instrução é identificada pelos seguintes dados:  
  
-   O arquivo de origem que contém a instrução da função.  
  
-   A função que contém a instrução.  
  
-   A linha de origem em que a instrução se inicia.  
  
-   O caractere na linha de origem em que a instrução se inicia.  
  
-   A linha de origem em que a instrução termina.  
  
-   O caractere na linha de origem em que a instrução termina.  
  
 A coluna de Nome de Linha fornece uma concatenação classificável dos dados do identificador.  
  
 A tabela a seguir descreve as colunas do relatório de Exibição de Linhas.  
  
|Column|Descrição|  
|------------|-----------------|  
|**Tempo Bloqueado Exclusivo**|A quantidade de tempo durante o qual a instrução foi impedida de executar o código na instrução em virtude de um evento de contenção. O tempo bloqueado em funções chamadas pela instrução não está incluído.|  
|**% de Tempo Bloqueado Exclusivo**|O percentual de todo o tempo bloqueado no processo de tempo bloqueado exclusivo da instrução.|  
|**Contenções Exclusivas**|O número de vezes que essa instrução foi impedida de executar o código na instrução em virtude de um evento de contenção. Os eventos de contenção em funções chamadas pela instrução não estão incluídos.|  
|**% de Contenções Exclusivas**|O percentual de todos os eventos de contenção no processo que eram contenções exclusivas da instrução.|  
|**Endereço da Função**|O endereço da função que contém essa instrução.|  
|**Nome da Função**|O nome totalmente qualificado da função que contém a instrução.|  
|**Tempo Bloqueado Inclusivo**|O tempo bloqueado na instrução e funções chamadas na instrução.|  
|**% de Tempo Bloqueado Inclusivo**|O percentual de todo o tempo bloqueado no processo de tempo bloqueado inclusivo da instrução.|  
|**Contenções Inclusivas**|O número de vezes que a execução da instrução e das funções que foram chamadas nela foi impedida.|  
|**% de Contenções Inclusivas**|O percentual de todos os eventos de contenção no processo que eram contenções inclusivas da instrução.|  
|**Nome da Linha**|Um identificador gerado pelo criador de perfil da linha. O identificador usa a seguinte sintaxe:`SourceFile`**;[**`LineNumberStart`**,**`CharacterStart`**]->;[**`LineNumberEnd`**,**`CharacterEnd`**]**|  
|**Número de linha da função**|O número de linha do início dessa função no arquivo de origem.|  
|**Nome do Módulo**|O nome do módulo que contém a instrução.|  
|**Caminho do Módulo**|O caminho do módulo que contém a instrução.|  
|**ID do Processo**|A PID (ID do processo) do processo analisado.|  
|**Nome do Processo**|O nome do processo.|  
|**Início do Caractere de Origem**|O deslocamento do caractere inicial na linha do arquivo de origem em que a instrução se inicia.|  
|**Final do Caractere de Origem**|O deslocamento do caractere inicial na linha do arquivo de origem em que a instrução termina.|  
|**Arquivo de Origem**|O nome do arquivo de origem que contém a instrução da função.|  
|**Início da Linha de Origem**|O número de linha no arquivo de origem na qual a instrução se inicia.|  
|**Final da Linha de Origem**|O número da linha no arquivo de origem na qual a instrução termina.|  
  
## <a name="see-also"></a>Consulte também  
 [Como personalizar as colunas de exibição do relatório](../profiling/how-to-customize-report-view-columns.md)   
 [Exibição de Linhas](../profiling/lines-view.md)   
 [Exibição de Linhas – Amostragem](../profiling/lines-view-dotnet-memory-sampling-data.md)   
 [Exibição de Linhas](../profiling/lines-view-sampling-data.md)


