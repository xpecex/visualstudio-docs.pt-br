---
title: Atualizar projetos de teste de unidade do Visual Studio 2010 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1502b51-d6db-4894-9fbf-4a5723e4bb1a
caps.latest.revision: 8
ms.author: gewarren
manager: douge
ms.openlocfilehash: e06a58e6015a99db83bf729d16196551c5126d12
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47461433"
---
# <a name="upgrade-visual-studio-2010-unit-test-projects"></a>Atualizar projetos de teste de unidade do Visual Studio 2010
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] inclui compatibilidade de projeto de teste com projetos de teste [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] do SP1. Por exemplo, projetos de teste criados com o SP1 [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] podem ser abertos com [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] sem qualquer atualização. Portanto, sua equipe pode usar ambos SP1 [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] e [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] para trabalhar com o mesmo projeto de teste. Para obter mais informações, consulte [Atualizar testes no Visual Studio 2010](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52).  
  
 [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] apresenta várias alterações para testes de unidade. Em virtude dessas alterações, é importante entender questões de compatibilidade entre as versões anteriores do Visual Studio e [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. Entre as alterações de teste de unidade, uma alteração significativa é que [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] inclui mais de um modelo de projeto de teste, incluindo um modelo de projeto de teste de unidade. Novos testes de unidade são adicionados ao novo modelo de projeto de teste de unidade. Testes de unidade também podem ser incluídos em outro novo modelo de projeto de teste chamado “modelo de projeto de teste de IU codificado”. Para obter mais informações sobre os novos modelos de projeto de teste, consulte [Atualizar Testes de Versões Anteriores do Visual Studio](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52). Os novos projetos de teste de unidade não incluem um arquivo de configurações de teste padrão. Ao excluir o arquivo de configurações de teste, o desempenho dos testes de unidade melhora. Em relação à compatibilidade, ainda é possível usar os projetos de teste existentes criados com o Visual Studio 2010. No entanto, recomendamos a remoção do arquivo de configurações de teste associado ao projeto de teste por motivos de desempenho, a menos que você tenha uma necessidade específica para o arquivo de configurações de teste. Por exemplo, você pode optar por manter o arquivo de configurações de teste se seus testes de unidade forem executados em um ambiente distribuído ou se precisar coletar dados de diagnóstico específicos. Caso você tenha uma necessidade semelhante ao usar o novo modelo de projeto de teste de unidade ou projeto de teste de IU codificado, também é possível adicionar o arquivo de configurações de teste a eles manualmente.  
  
> [!NOTE]
>  Os testes de unidade existentes nos projetos de teste SP1 [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] funcionarão perfeitamente entre SP1 [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] e [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. Nenhuma alteração será feita nos arquivos de projeto de teste quando um projeto de teste do Visual Studio 2010 que contém seus testes de unidade estiver aberto em [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] ou vice-versa.  
  
> [!CAUTION]
>  O Visual Studio 2010 não pode abrir um projeto C++/CLI que tem como destino o conjunto de ferramentas 11.0, ou seja, um projeto criado no Visual Studio 2012. Essa restrição se aplica a todos os projetos C++/CLI e não apenas a projetos de teste de unidade C++/CLI.  
  
> [!NOTE]
>  É possível executar os novos testes de unidade usando vstest.console.exe na linha de comando. Para obter mais informações sobre como usar vstest.console.exe, consulte [Opções da linha de comando de VSTest.Console.exe](http://msdn.microsoft.com/library/52e1689d-b1a8-4589-bd98-99a55acd0a11) ou execute o comando usando a opção de Ajuda: **vstest.console.exe /?**. Você pode continuar a executar seus testes de unidade existentes usando MStest.exe. Para obter mais informações, consulte [Executar testes automatizados da linha de comando usando o MSTest](http://msdn.microsoft.com/library/39b61ad0-0055-44b5-963f-25d8a6b51581) e [Opções da linha de comando de MSTest.exe](http://msdn.microsoft.com/library/8813ba7f-e790-4e92-9f91-7080508a1c36).  
  
 Outra alteração significativa é o novo Gerenciador de Testes. Em [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], algumas janelas de teste de versões anteriores do Visual Studio com as quais você pode estar familiarizado foram preteridas, como a janela Modo de Teste. O Gerenciador de Testes foi projetado para oferecer um suporte melhor para desenvolvedores e equipes que incorporam testes de unidade em suas práticas de desenvolvimento de software. Para obter mais informações, consulte [Executar testes de unidade com o Gerenciador de Testes](../test/run-unit-tests-with-test-explorer.md).  
  
## <a name="compatibility-issues-between-visual-studio-2010-sp1-and-visual-studio-2012"></a>Problemas de compatibilidade entre o Visual Studio 2010 SP1 e o Visual Studio 2012  
 Estas são algumas questões a serem consideradas ao migrar testes de unidade entre o Visual Studio 2010 SP1 e [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]:  
  
|Funcionalidade do Teste de Unidade|Problema|Solução|  
|-----------------------------|-----------|--------------|  
|Listas de teste (arquivos. vsmdi) foram preteridas no [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)].|Não será possível criar novas listas de testes (arquivos .vsmdi) ou executá-las no Visual Studio. **Dica:** as categorias de teste fornecem mais flexibilidade do que a funcionalidade de listas de teste de versões anteriores do Microsoft Visual Studio. Você pode usar os operadores lógicos com categorias de teste para executar testes junto de várias categorias ou para limitar os testes que executa a testes que pertençam a várias categorias. Além disso, é fácil adicionar categorias de teste à medida que você cria seus métodos de teste, e não é necessário manter listas de testes após você ter criado os métodos de teste. Usando categorias de teste, não será necessário fazer check-in e fazer check-out do **\<nome da solução>.vsmdi** que mantém as listas de teste. Para obter mais informações, consulte [Definir Categorias de Teste para Agrupar seus Testes](http://msdn.microsoft.com/library/2c26a648-f068-4d60-99b6-b9747b7bdbc9).|- Para manter a compatibilidade com seus projetos de teste existentes que usam listas de teste, você ainda pode editar os arquivos .vsmdi usando o Visual Studio.<br />- Embora não seja possível executar listas de testes migradas com o Visual Studio, você ainda pode executá-las usando o mstest.exe da linha de comando. Para obter mais informações, consulte [Executar testes automatizados da linha de comando usando o MSTest](http://msdn.microsoft.com/library/39b61ad0-0055-44b5-963f-25d8a6b51581)<br />- Se estiver usando uma lista de testes na definição de build, você poderá continuar a usá-la. Para obter mais informações, consulte [Como Configurar e Executar Testes Programados Após o build do Aplicativo](http://msdn.microsoft.com/en-us/32acfeb1-b1aa-4afb-8cfe-cc209e6183fd) e [Executar testes no processo de build](http://msdn.microsoft.com/library/d05743a1-c5cf-447e-bed9-bed3cb595e38).|  
|Acessadores particulares foram preteridos no [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)].<br /><br /> Nas versões anteriores do Visual Studio, era possível usar o Publicize para especificar uma API (interface de programação de aplicativo) interna e criar APIs públicas equivalentes que podem ser chamadas em testes que, por sua vez, chamam as APIs internas do seu produto. Então, era possível usar a geração de código para criar stubs de teste e gerar snippets de código dentro desse stub.|Não será mais possível criar assessores particulares.|<ul><li>Os projetos de teste do Visual Studio 2010 compilarão e funcionarão no [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. O build incluirá avisos de saída.</li><li>Se ainda for necessário testar APIs internas, você terá estas opções:<br /><br /> <ul><li>Use a classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject> para auxiliar o acesso às APIs internas e privadas em seu código. Isso é encontrado no assembly Microsoft.VisualStudio.QualityTools.UnitTestFramework.dll.</li><li>Crie uma estrutura de reflexão com a capacidade de refletir o código para fora, a fim de acessar APIs internas ou privadas.</li><li>Se o código que está tentando acessar for interno, você poderá acessar suas APIs usando <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, assim, o código de teste terá acesso às APIs internas.</li></ul></li></ul>|  
|O Impacto de Teste foi removido|||  
|Compartilhamento de resultados de execução por meio de logs TRX do Gerenciador de Testes.||Ainda é possível obter logs TRX da linha de comando e do Team Build.|  
  
## <a name="see-also"></a>Consulte também  
 [Portabilidade, migração e atualização de projetos do Visual Studio](../porting/porting-migrating-and-upgrading-visual-studio-projects.md)   
 [Efetuar teste de unidade em seu código](../test/unit-test-your-code.md)   
 [Atualizar Testes de Versões Anteriores do Visual Studio](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52)   
 [Atualizando testes de IU codificados por meio do Visual Studio 2010](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)