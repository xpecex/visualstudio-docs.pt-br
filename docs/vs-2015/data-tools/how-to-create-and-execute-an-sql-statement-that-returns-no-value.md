---
title: 'Como: criar e executar uma instrução SQL que não retorna nenhum valor | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- method calls, examples
- calling methods, examples
- SQL statements, executing
- SQL statements, creating
ms.assetid: 612d3046-0cfa-4d90-be6e-c4d6bcbd5aee
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 2dd78fe0144718337fc589e0d8f8948d5353dd6c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47466123"
---
# <a name="how-to-create-and-execute-an-sql-statement-that-returns-no-value"></a>Como criar e executar uma instrução SQL que não retorna nenhum valor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para executar uma instrução SQL que não retorna nenhum valor, você pode executar uma consulta TableAdapter que está configurada para executar uma instrução SQL (por exemplo, `CustomersTableAdapter.UpdateTableData(CustomersDataTable)`).  
  
 Se seu aplicativo não usar TableAdapters, chame o `ExecuteNonQuery` método em um objeto de comando, definindo seu `CommandType` propriedade <xref:System.Data.CommandType>. ("Objeto de comando" refere-se ao comando específico para o [.NET Framework Data Provider](http://msdn.microsoft.com/library/03a9fc62-2d24-491a-9fe6-d6bdb6dcb131) seu aplicativo está usando. Por exemplo, se seu aplicativo estiver usando o .NET Framework Data Provider para SQL Server, o objeto de comando seria <xref:System.Data.SqlClient.SqlCommand>.)  
  
 Os exemplos a seguir mostram como executar instruções SQL que não retornam nenhum valor de um banco de dados usando o TableAdapters ou objetos de comando. Para obter mais informações sobre como consultar com TableAdapters e comandos, consulte [preencher conjuntos de dados usando TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md).  
  
## <a name="executing-sql-statements-that-return-no-values-using-a-tableadapter"></a>Executar instruções SQL que não retornam valores usando um TableAdapter  
 Este exemplo mostra como criar uma consulta TableAdapter usando o [editando TableAdapters](../data-tools/editing-tableadapters.md), e, em seguida, ele fornece informações sobre como declarar uma instância do TableAdapter e executar a consulta.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-create-an-sql-statement-that-returns-no-value-using-a-tableadapter"></a>Para criar uma instrução SQL que não retorna nenhum valor usando um TableAdapter  
  
1.  Abrir em um conjunto de dados do **Dataset Designer**. Para obter mais informações, consulte [como: abrir um conjunto de dados no Designer de conjunto de dados](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3).  
  
2.  Se você não tiver uma, crie um TableAdapter. Para obter mais informações sobre como criar TableAdapters, consulte [criar e configurar TableAdapters](../data-tools/create-and-configure-tableadapters.md).  
  
3.  Se você já tiver uma consulta no seu TableAdapter que usa uma instrução SQL que não retorna nenhum valor, em seguida, vá para o próximo procedimento, "para"declarar uma instância do TableAdapter e executar a consulta. Caso contrário, continue na etapa 4 para criar uma nova consulta que não retorna nenhum valor.  
  
4.  Clique com botão direito do TableAdapter que você deseja e use o menu de atalho para adicionar uma consulta.  
  
     O **Assistente de configuração de consulta do TableAdapter** é aberta.  
  
5.  Deixe o valor padrão de **usar instruções SQL**e, em seguida, clique em **próxima**.  
  
6.  Escolha o **atualização**, **inserir** ou **excluir** opção e, em seguida, clique em **Avançar**.  
  
7.  Digite a instrução SQL ou use o **construtor de consultas** para auxiliar na criação de uma e, em seguida, clique em **próxima**.  
  
8.  Forneça um nome para a consulta.  
  
9. Conclua o Assistente; a consulta é adicionada ao TableAdapter.  
  
10. Criar o projeto.  
  
#### <a name="to-declare-an-instance-of-the-tableadapter-and-execute-the-query"></a>Para declarar uma instância do TableAdapter e executar a consulta  
  
1.  Declare uma instância do TableAdapter que contém a consulta que você deseja executar.  
  
    -   Para criar uma instância usando as ferramentas de tempo de design, arraste o TableAdapter que você deseja do **caixa de ferramentas**. (Os componentes no seu projeto agora aparecem na **caixa de ferramentas** sob um título que corresponda ao nome do projeto.) Se o TableAdapter não aparecer na **caixa de ferramentas**, talvez seja necessário compilar seu projeto.  
  
         -ou-  
  
    -   Para criar uma instância no código, substitua o código a seguir com os nomes dos seus <xref:System.Data.DataSet> e TableAdapter.  
  
         `Dim tableAdapter As New DataSetTableAdapters.TableAdapter`  
  
        > [!NOTE]
        >  TableAdapters não são realmente estão localizadas dentro de suas classes de conjunto de dados associado. Cada conjunto de dados tem uma coleção correspondente de TableAdapters em seu próprio namespace. Por exemplo, se você tiver um conjunto de dados denominado `SalesDataSet`, deve haver um `SalesDataSetTableAdapters` namespace que contém seus TableAdapters.  
  
2.  Chame sua consulta, como você poderia chamar qualquer outro método no código. Sua consulta é um método no TableAdapter. Substitua o código a seguir com os nomes de seu TableAdapter e a consulta. Você também precisará passar os parâmetros necessários para sua consulta. Se você não tiver certeza se sua consulta exigir parâmetros, ou que parâmetros requer, em seguida, verifique o IntelliSense para a assinatura necessária da consulta. Dependendo se sua consulta usa parâmetros ou não, o código seria semelhante a um dos exemplos a seguir:  
  
     `TableAdapter.Query()`  
  
     `TableAdapter.Query(Parameters)`  
  
     Consultas que nós pensamos que não retornam nenhum valor, na verdade, retornam um valor — um inteiro que contém o número de linhas afetadas pela consulta. O código completo para declarar uma instância de um TableAdapter e executar uma consulta deve ser semelhante ao seguinte:  
  
     [!code-csharp[VbRaddataFillingAndExecuting#11](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#11)]
     [!code-vb[VbRaddataFillingAndExecuting#11](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#11)]  
  
## <a name="executing-sql-statements-that-return-no-value-using-a-command-object"></a>Executar instruções SQL que não retornam nenhum valor usando um objeto de comando  
 O exemplo a seguir mostra como criar um comando e executar uma instrução SQL que não retorna nenhum valor. Para obter informações sobre como definir e obter valores de parâmetro para um comando, consulte [como: definir e obter parâmetros para objetos de comando](http://msdn.microsoft.com/library/10110ecc-d2ed-4796-bb8f-74f2ecd40787).  
  
 Este exemplo usa o <xref:System.Data.SqlClient.SqlCommand> do objeto e requer:  
  
-   Referências para o <xref:System>, <xref:System.Data>, e <xref:System.Xml> namespaces.  
  
-   Uma conexão de dados denominado `SqlConnection1`.  
  
-   Uma tabela denominada `Customers` na fonte de dados que `SqlConnection1` se conecta ao. (Caso contrário, você precisa de uma instrução SQL válida para sua fonte de dados).  
  
#### <a name="to-execute-an-sql-statement-that-returns-no-value-using-a-datacommand"></a>Para executar uma instrução SQL que não retorna nenhum valor usando um DataCommand  
  
-   Adicione o seguinte código para um método que você deseja executar a instrução SQL de. Chame o `ExecuteNonQuery` método de um comando para não retornar nenhum valor (por exemplo, <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A?displayProperty=fullName>).  
  
     [!code-csharp[VbRaddataFillingAndExecuting#12](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#12)]
     [!code-vb[VbRaddataFillingAndExecuting#12](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#12)]  
  
## <a name="net-framework-security"></a>Segurança do .NET Framework  
 O aplicativo requer permissão para acessar o banco de dados e executar a instrução SQL.  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A?displayProperty=fullName>   
 <xref:System.Data.OleDb.OleDbCommand.ExecuteNonQuery%2A?displayProperty=fullName>   
 <xref:System.Data.Odbc.OdbcCommand.ExecuteNonQuery%2A?displayProperty=fullName>   
 <xref:System.Data.OracleClient.OracleCommand.ExecuteNonQuery%2A?displayProperty=fullName>   
 [Como: criar consultas TableAdapter](../data-tools/how-to-create-tableadapter-queries.md)   
 [Como: editar consultas TableAdapter](../data-tools/how-to-edit-tableadapter-queries.md)   
 [Como: preencher um conjunto de dados com dados](../data-tools/how-to-fill-a-dataset-with-data.md)   
 [Preencher conjuntos de dados usando TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)   
 [Como: definir e obter parâmetros para objetos de comando](http://msdn.microsoft.com/library/10110ecc-d2ed-4796-bb8f-74f2ecd40787)