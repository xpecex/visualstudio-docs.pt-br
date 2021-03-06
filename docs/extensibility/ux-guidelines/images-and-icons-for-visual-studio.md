---
title: Imagens e ícones para o Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: f410325e-9cf2-4f39-b6d7-b672121c2691
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3fae6a5350d5204219edcb14732c7686984035e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31148500"
---
# <a name="images-and-icons-for-visual-studio"></a>Imagens e ícones para o Visual Studio
##  <a name="BKMK_ImageUseInVisualStudio"></a> Uso de imagem no Visual Studio  
 Antes de criar a arte final, considere fazer uso das imagens de 1.000 no [biblioteca de imagens do Visual Studio](http://www.microsoft.com/en-my/download/details.aspx?id=35825).  
  
### <a name="types-of-images"></a>Tipos de imagens  
  
-   **Ícones**. Imagens pequenas que aparecem em comandos, hierarquias, modelos e assim por diante. O tamanho do ícone padrão usado no Visual Studio é um arquivo PNG 16 x 16. Ícones produzidos pelo serviço de imagem automaticamente geram o formato XAML para suporte HDPI.  
  
     **Observação:** enquanto imagens são usadas no sistema de menus, você não deve criar um ícone para cada comando. Consulte [Menus e comandos para o Visual Studio](../../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md) para ver se o comando deve obter um ícone.  
  
-   **Miniaturas.** Imagens usadas na área de visualização da caixa de diálogo, como a caixa de diálogo Novo projeto.  
  
-   **Imagens da caixa de diálogo.** Imagens que aparecem em caixas de diálogo ou assistentes, como gráficos descritivos ou indicadores de mensagem. Use raramente e somente quando necessário para ilustrar um conceito difícil ou obter a atenção do usuário (aviso de alerta,).  
  
-   **Imagens animadas.** Usado em caixas de diálogo de operação, barras de status e indicadores de progresso.  
  
-   **Cursores.** Usado para indicar se uma operação é permitida com o mouse, onde um objeto pode ser descartado e assim por diante.  
  
##  <a name="BKMK_IconDesign"></a> Design de ícone  
  
### <a name="overview"></a>Visão geral  
 O Visual Studio usa ícones de estilo moderno, que tiverem geometry limpa e um saldo 50/50 de positivo/negativo (claro escuro) e usam metáforas diretas, compreensíveis. Design de ícone crucial pontos giram em torno de clareza, simplificação e contexto.  
  
-   **Esclarecimento:** enfocam a metáfora de núcleo que fornece um ícone seu significado e individualidade.  
  
-   **Simplificação:** reduzir o ícone para seu significado core - transmitir o tema com apenas os elementos necessários e sem sofisticações.  
  
-   **Contexto:** considerar todos os aspectos da função de um ícone durante o desenvolvimento de conceito, que é essencial ao decidir quais elementos constituem a metáfora de núcleo do ícone.  
  
 Com ícones, há um número de pontos de design para evitar:  
  
-   Não use os ícones que representam os elementos de interface do usuário, exceto quando apropriado. Escolha uma abordagem mais abstrata ou simbólica quando o elemento de interface do usuário não é comum, evidente, nem exclusivo.  
  
-   Não uso excessivo de elementos comuns, como documentos, pastas, setas e na Lupa. Use esses elementos apenas quando essenciais para o significado do ícone. Por exemplo, na lupa para a direita deve indicar somente pesquisar, navegar e localizar.  
  
-   Embora alguns elementos de ícone herdado mantém o uso da perspectiva, não crie novos ícones com perspectiva, a menos que o elemento não tem a maior clareza sem ele.  
  
-   Não acumular muitas informações em um ícone. Uma imagem simples que pode ser facilmente reconhecida ou aprendeu como um símbolo reconhecível é muito mais útil que uma imagem excessivamente complexa. Um ícone não pode determinar a história completa.  
  
### <a name="icon-creation"></a>Criação de ícone  
  
#### <a name="concept-development"></a>Desenvolvimento de conceito  
 Visual Studio tem dentro de sua interface de usuário uma ampla variedade de tipos de ícones. Considere cuidadosamente o tipo de ícone durante o desenvolvimento. Não use objetos de interface do usuário claras ou incomuns para elementos de ícone. Optar por simbólicos nesses casos, como com o ícone de marca inteligente. Observe que o significado da marca abstrata à esquerda é mais óbvio que a versão com base na interface do usuário, vaga à direita:  
  
|||  
|-|-|  
|**Uso correto de imagens simbólico**|**Uso incorreto de imagens simbólico**|  
|![Ícone de marca inteligente correto](../../extensibility/ux-guidelines/media/0404-01_smarttagcorrect.png "01_SmartTagCorrect 0404")|![Ícone de marca inteligente incorreto](../../extensibility/ux-guidelines/media/0404-02_smarttagincorrect.png "02_SmartTagIncorrect 0404")|  
  
 Há ocasiões em que os elementos de interface do usuário padrão, facilmente reconhecíveis funcionam bem para ícones. Adicione que janela é um exemplo:  
  
|||  
|-|-|  
|**Elemento de interface de usuário correto em um ícone**|**Elemento de interface de usuário incorreto em um ícone**|  
|![Ícone de janela Adicionar correto](../../extensibility/ux-guidelines/media/0404-03_addwindowcorrect.png "03_AddWindowCorrect 0404")|![Ícone de janela Adicionar incorreto](../../extensibility/ux-guidelines/media/0404-04_addwindowincorrect.png "04_AddWindowIncorrect 0404")|  
  
 Não use um documento como um elemento base, a menos que é essencial para o significado do ícone. Sem o documento de elemento no documento de adicionar (o significado abaixo) é perdido, enquanto a atualização o elemento do documento é desnecessário comunicar o significado.  
  
|||  
|-|-|  
|**Uso correto do ícone do documento**|**Uso incorreto do ícone do documento**|  
|![Ícone de documento correto](../../extensibility/ux-guidelines/media/0404-05_documenticoncorrect.png "05_DocumentIconCorrect 0404")|![Ícone de documento incorreto](../../extensibility/ux-guidelines/media/0404-06_documenticonincorrect.png "06_DocumentIconIncorrect 0404")|  
  
 O conceito de "Mostrar" deve ser representado por um ícone que ilustra melhor o que está sendo exibido, tais como ocorre com o exemplo de mostrar todos os arquivos. Uma metáfora de Lente pode ser usada para indicar o conceito de "exibição" se necessário, como no exemplo de modo de exibição de recursos.  
  
|||  
|-|-|  
|**"Show"**|**"View"**|  
|![Mostrar ícone de](../../extensibility/ux-guidelines/media/0404-07_show.png "07_Show 0404")|![Ícone do modo de exibição](../../extensibility/ux-guidelines/media/0404-08_view.png "08_View 0404")|  
  
 O para a direita ampliar o ícone de deve representam apenas pesquisar, localizar e procurar. A variante voltado para a esquerda com o sinal de adição ou subtração deve representar apenas zoom em / zoom.  
  
|||  
|-|-|  
|**"Search"**|**"Zoom"**|  
|![Ícone de pesquisa](../../extensibility/ux-guidelines/media/0404-09_search.png "09_Search 0404")|![Ícone de zoom](../../extensibility/ux-guidelines/media/0404-10_zoom.png "10_Zoom 0404")|  
  
 Nos modos de exibição de árvore, não use o ícone de pasta e um modificador. Quando disponível, use somente o modificador.  
  
|||  
|-|-|  
|**Ícones de exibição de árvore correto**|**Ícones de exibição de árvore incorreto**|  
|![Ícone do modo de exibição de árvore correto &#40;1&#41;](../../extensibility/ux-guidelines/media/0404-11_treeviewcorrect1.png "0404 11_TreeViewCorrect1") ![ícone do modo de exibição de árvore correto &#40;2&#41;](../../extensibility/ux-guidelines/media/0404-12_treeviewcorrect2.png "12_TreeViewCorrect2 0404")|![Ícone do modo de exibição de árvore incorreto &#40;1&#41;](../../extensibility/ux-guidelines/media/0404-13_treeviewincorrect1.png "0404 13_TreeViewIncorrect1") ![ícone do modo de exibição de árvore incorreto &#40;2&#41;](../../extensibility/ux-guidelines/media/0404-14_treeviewincorrect2.png "14_ 0404 TreeViewIncorrect2")|  
  
### <a name="style-details"></a>Detalhes de estilo  
  
#### <a name="layout"></a>Layout  
 Elementos da pilha conforme mostrado para os ícones de 16 x 16 padrão:  
  
 ![Pilha de layout para os ícones de 16 x 16](../../extensibility/ux-guidelines/media/0404-15_layoutstack.png "15_LayoutStack 0404")<br />Pilha de layout para os ícones de 16 x 16
  
 Elementos de notificação de status são mais usados como ícones autônomo. Há contextos, no entanto, no qual uma notificação deve ser empilhada no elemento base, como com o ícone de tarefa concluída:  
  
 ![Notificações de autônomo no Visual Studio](../../extensibility/ux-guidelines/media/0404-16_standalonenotificationicons.png "16_StandaloneNotificationIcons 0404")<br />Ícones de notificação autônomo
  
 ![Ícone de tarefa concluída](../../extensibility/ux-guidelines/media/0404-17_taskcomplete.png "17_TaskComplete 0404")<br />Ícone de tarefa concluída
  
 Ícones de projeto geralmente são arquivos. ico que contêm vários tamanhos. A maioria dos ícones de 16 x 16 contêm os mesmos elementos. As versões de 32 x 32 tem mais detalhes, incluindo o tipo de projeto, quando aplicável.  
  
 ![Projeto ícones no Visual Studio](../../extensibility/ux-guidelines/media/0404-18_iconprojectthreesizes.png "18_IconProjectThreeSizes 0404")<br />Ícones de projeto de biblioteca de controle de Windows VB, 16 x 16 e 32 x 32 
  
 Centro de um ícone em sua estrutura de pixel. Se não for possível, alinhe o ícone para a parte superior e/ou à direita do quadro.  
  
 ![Ícone centralizado dentro do quadro de pixel](../../extensibility/ux-guidelines/media/0404-19_iconcentered.png "19_IconCentered 0404")<br />Ícone centralizado dentro do quadro de pixel
  
 ![Ícone alinhado à parte superior direita do quadro de pixel](../../extensibility/ux-guidelines/media/0404-20_icontopright.png "20_IconTopRight 0404")<br />Ícone alinhado na parte superior direita do quadro
  
 ![Ícone centralizada e alinhado à parte superior do quadro de pixel](../../extensibility/ux-guidelines/media/0404-21_icontopalign.png "21_IconTopAlign 0404")<br />Ícone centralizada e alinhado à parte superior do quadro
  
 Para obter o equilíbrio e alinhamento ideal, evite obstruindo o elemento de base do ícone com glifos de ação. Posicione o glifo na parte superior esquerdo do elemento base. Ao adicionar um elemento adicional, considere o alinhamento e o saldo do ícone.  
  
|||  
|-|-|  
|**Saldo e alinhamento correto**|**Saldo e alinhamento incorreto**|  
|![Corrija o saldo de ícone e o alinhamento](../../extensibility/ux-guidelines/media/0404-22_alignbalancecorrect.png "22_AlignBalanceCorrect 0404")|![Saldo de ícone incorreto e alinhamento](../../extensibility/ux-guidelines/media/0404-23_alignbalanceincorrect.png "23_AlignBalanceIncorrect 0404")|  
  
 Certifique-se de paridade do tamanho dos ícones que compartilham elementos e são usados em conjuntos. Observe que no emparelhamento incorreto, a seta e círculo forem muito grandes e não são correspondentes.  
  
|||  
|-|-|  
|**Paridade de tamanho correto**|**Paridade de tamanho incorreto**|  
|![Corrija o tamanho de ícone e paridade](../../extensibility/ux-guidelines/media/0404-24_sizeparitycorrect.png "24_SizeParityCorrect 0404")|![Tamanho do ícone incorreto e paridade](../../extensibility/ux-guidelines/media/0404-25_sizeparityincorrect.png "25_SizeParityIncorrect 0404")|  
  
 Use linha consistentes e pesos visual. Avalie como o ícone que você está criando compara a outros ícones usando uma comparação lado a lado. Nunca use toda a 16x16 estrutura, use 15 x 15 ou menor. A taxa de (escuro para claro) negativo ao positivo deve ser 50/50.  
  
|||  
|-|-|  
|**Taxa de negativo ao positivo correta**|**Taxa de negativo ao positivo incorretova**|  
|![Corrija o peso visual dos ícones &#40;1&#41;](../../extensibility/ux-guidelines/media/0404-26_visualweightcorrect1.png "26_VisualWeightCorrect1 0404")<br /><br /> ![Corrija o peso visual dos ícones &#40;2&#41;](../../extensibility/ux-guidelines/media/0404-27_visualweightcorrect2.png "27_VisualWeightCorrect2 0404")<br /><br /> ![Corrija o peso visual dos ícones &#40;3&#41;](../../extensibility/ux-guidelines/media/0404-28_visualweightcorrect3.png "28_VisualWeightCorrect3 0404")|![Peso visual incorreto para ícones](../../extensibility/ux-guidelines/media/0404-29_visualweightincorrect.png "29_VisualWeightIncorrect 0404")|  
  
 Use formas simples, comparáveis e ângulos complementares para criar os elementos sem sacrificar a integridade do elemento. Use os ângulos de 45° ou 90° sempre que possível.  
  
 ![Corrija os ângulos de ícone](../../extensibility/ux-guidelines/media/0404-30_iconanglescorrect.png "30_IconAnglesCorrect 0404")  
  
#### <a name="perspective"></a>Perspectiva  
 Manter o ícone claro e compreensível. Use a perspectiva e uma fonte de luz somente quando necessário. Embora usando a perspectiva em elementos de ícone deve ser evitado, alguns elementos são irreconhecíveis sem ele. Nesses casos, uma perspectiva estilizada se comunica a clareza do elemento.  
  
 ![perspectiva de ponto 3](../../extensibility/ux-guidelines/media/0404-31_3pointperspective.png "31_3PointPerspective 0404")<br />perspectiva de ponto de 3
  
 ![1 ponto perspectiva](../../extensibility/ux-guidelines/media/0404-32_1pointperspective.png "32_1PointPerspective 0404")<br />1 ponto de perspectiva
  
 A maioria dos elementos devem ser voltados para ou diagonal à direita:  
  
 ![Ícones angular direito](../../extensibility/ux-guidelines/media/0404-33_angledright.png "33_AngledRight 0404")  
  
 Use fontes de luz somente ao adicionar clareza necessária a um objeto.  
  
|||  
|-|-|  
|**Fonte de luz correto**|**Fonte de luz incorreto**|  
|![Corrija as fontes de luz para os ícones](../../extensibility/ux-guidelines/media/0404-34_lightsourcescorrect.png "34_LightSourcesCorrect 0404")|![Fontes de luz incorretos para ícones](../../extensibility/ux-guidelines/media/0404-35_lightsourcesincorrect.png "35_LightSourcesIncorrect 0404")|  
  
 Use contornos somente para melhorar a legibilidade ou comunicar melhor a metáfora. O saldo de (claro-escuro) negativo positivo deve ser 50/50.  
  
|||  
|-|-|  
|**Uso correto de estruturas de tópicos**|**Uso incorreto de estruturas de tópicos**|  
|![Corrigir contornos](../../extensibility/ux-guidelines/media/0404-36_outlinescorrect.png "36_OutlinesCorrect 0404")|![Descreve incorreto](../../extensibility/ux-guidelines/media/0404-37_outlinesincorrect.png "37_OutlinesIncorrect 0404")|  
  
#### <a name="icon-types"></a>Tipos de ícone  
 **Barra de comandos e shell** ícones consistem em não mais do que três dos seguintes elementos: uma base, um modificador, uma ação ou um status.  
  
 ![Exemplos de shell e ícones da barra de comando](../../extensibility/ux-guidelines/media/0404-38_shellicons.png "38_ShellIcons 0404")<br />Exemplos de shell e ícones da barra de comando
  
 **Barra de comandos de janela de ferramenta** ícones consistem em não mais do que três dos seguintes elementos: uma base, um modificador, uma ação ou um status.  
  
 ![Ícones da barra de comandos de exemplos da janela de ferramenta](../../extensibility/ux-guidelines/media/0404-39_toolwindowcommandbaricons.png "39_ToolWindowCommandBarIcons 0404")<br />Exemplos de ícones da barra de ferramenta janela comando
  
 **Desambiguador de exibição de árvore** ícones consistem em não mais do que três dos seguintes elementos: uma base, um modificador, uma ação ou um status.  
  
 ![Exemplos de árvore exibir ícones de desambiguador](../../extensibility/ux-guidelines/media/0404-40_treeviewicons.png "40_TreeViewIcons 0404")<br />Exemplos de árvore exibir ícones de desambiguador
  
 **Taxonomia de valor com base no estado** ícones existem nos seguintes estados: ativo, ativo desativado e desabilitado inativo.  
  
 ![Exemplos de ícones de taxonomia de valor com base no estado](../../extensibility/ux-guidelines/media/0404-41_statebasedtaxonomy.png "41_StateBasedTaxonomy 0404")<br />Exemplos de ícones de taxonomia de valor com base no estado
  
 **IntelliSense** ícones consistem em não mais do que três dos seguintes elementos: uma base de dados de um modificador e um status.  
  
 ![Exemplos de ícones de IntelliSense](../../extensibility/ux-guidelines/media/0404-42_intellisenseicons.png "42_IntelliSenseIcons 0404")<br />Exemplos de ícones do IntelliSense
  
 **Pequeno (16x16) projeto** ícones devem ter não mais do que dois elementos: uma base e um modificador.  
  
 ![Ícones de projeto de exemplos de pequeno (16 x 16)](../../extensibility/ux-guidelines/media/0404-43_16x16project1.png "0404 43_16x16Project1") ![ícone 16x16 projeto &#40;2&#41;](../../extensibility/ux-guidelines/media/0404-44_16x16project2.png "0404 44_16x16Project2") ![ícone 16x16 projeto &#40;3&#41;](../../extensibility/ux-guidelines/media/0404-45_16x16project3.png "45_16x16Project3 0404")<br />Exemplos de ícones pequenos do projeto (16x16)
  
 **Grande (32x32) projeto** ícones consistem em não mais do que quatro dos seguintes elementos: uma base, modificadores de uma ou duas e um idioma de sobreposição.  
  
 ![Ícones de projeto de exemplos de grande (32x32)](../../extensibility/ux-guidelines/media/0404-46_32x32project.png "46_32x32Project 0404")<br />Ícones de projeto de exemplos de grande (32x32)
  
### <a name="production-details"></a>Detalhes de produção  
 Todos os novos elementos de interface do usuário devem ser criados usando o Windows Presentation Foundation (WPF) e todos os novos ícones para WPF devem estar no formato PNG de 32 bits. O PNG de 24 bits é um formato herdado que não oferece suporte a transparência e, portanto, não é recomendado para ícones.  
  
 Salve a resolução de 96 DPI.  
  
#### <a name="file-types"></a>Tipos de arquivo  
  
-   **PNG de 32 bits:** o formato preferencial para ícones. Um formato de arquivo de compactação sem perda de dados que pode armazenar uma imagem de varredura única (pixel). arquivos PNG de 32 bits oferecem suporte a transparência de canal alfa, correção gama e entrelaçamento.  
  
-   **BMP de 32 bits:** para controles do WPF não. Também chamado de XP ou cor alta, BMP de 32 bits é um formato de imagem RGB/A, uma imagem true color com uma transparência de canal alfa. O canal alfa é uma camada de transparência designada no Adobe Photoshop é salvo, em seguida, dentro do bitmap como um adicional (quarto) canal de cor. Um plano de fundo preto é adicionado durante a produção de arte final para todos os arquivos BMP de 32 bits para fornecer uma indicação visual rápida sobre a profundidade de cor. Este plano de fundo preto representa a área a ser ocultada na interface de usuário.  
  
-   **ICO de 32 bits:** de ícones de projeto e Adicionar Item. Todos os arquivos ICO estão cor verdadeiro de 32 bits com transparência de canal alfa (RGB/A). Como arquivos ICO podem armazenar vários tamanhos e intensidades de cor, ícones do Vista costumam ser em formato ICO contendo 16 x 16, 32 x 32, 48 x 48 e 256 x 256 tamanhos de imagem. Para exibir corretamente no Windows Explorer, arquivos ICO devem ser salvo para baixo a intensidade de cor de 24 bits e de 8 bits para cada tamanho de imagem.  
  
-   **XAML:** para superfícies de design e adornos do Windows. Ícones XAML são arquivos de imagem baseada em vetor que dão suporte ao dimensionamento, rotação, arquivamento e transparência. Eles não são comuns no Visual Studio hoje, mas estão se tornando mais populares devido a sua flexibilidade.  
  
-   **SVG**  
  
-   **24 bits BMP:** para a barra de comando do Visual Studio. Um formato de imagem true cor RGB, BMP 24 bits é uma convenção de ícone que cria uma camada de transparência usando magenta (R = 255, G = 0, B = 255) como uma chave de cor para uma camada de transparência de limite crítica. Em um BMP de 24 bits, todas as superfícies magenta são exibidas usando a cor do plano de fundo.  
  
-   **24 bits GIF:** para a barra de comando do Visual Studio. Um formato de imagem RGB true color que oferece suporte à transparência. Arquivos GIF geralmente são usados em arte final do assistente e animações GIF.  
  
### <a name="icon-construction"></a>Construção de ícone  
 O menor tamanho de ícone no Visual Studio é 16 x 16. A maior em comum usar é 32 x 32. Tenha em mente não para preencher todo o quadro de 16 x 16, 24 x 24 ou 32 x 32 durante a criação de um ícone. Construção de ícone uniforme, legível, é essencial para o reconhecimento de usuário. Cumprir os seguintes pontos quando estiver criando ícones.  
  
-   Ícones devem ser criptografado, compreensível e consistente.  
  
-   É melhor usar os elementos de notificação de status como ícones único e não para organizá-las na parte superior de um elemento de ícone base. Em determinados contextos, a interface do usuário pode exigir que o elemento de status a ser emparelhada com um elemento base.  
  
-   Ícones de projeto geralmente são arquivos. ico que contêm vários tamanhos. Somente os ícones de 16 x 16, 24 x 24 e 32 x 32 estão sendo atualizados. A maioria dos ícones de 16 x 16 e 24 x 24 conterá os mesmos elementos. Os ícones de 32 x 32 contêm mais detalhes, incluindo o tipo de idioma do projeto quando aplicável.  
  
-   Para os ícones de 32 x 32, os elementos de base geralmente têm um peso de linha com 2 pixels. Um peso de linha de pixel de 1 ou 2 pode ser usado para elementos de detalhe. Use seu bom senso para determinar qual é mais adequado.  
  
-   Ter pelo menos um espaçamento de 1 pixel entre elementos de 16x16 e ícones de 24 x 24. Para os ícones de 32 x 32, use 2 pixels espaçamento entre elementos e entre o modificador e o elemento base.  
  
 ![Elemento espaçamento para tamanho de ícones de 16 x 16, 24 x 24 e 32 x 32](../../extensibility/ux-guidelines/media/0404-47_elementspacing.png "47_ElementSpacing 0404")<br />Espaçamento de elementos para ícones dimensionado 16 x 16, 24 x 24 e 32 x 32
  
#### <a name="color-and-accessibility"></a>Cor e acessibilidade  
 Diretrizes de conformidade do Visual Studio requerem que todos os ícones no produto passam os requisitos de acessibilidade para cor e contraste. Isso é conseguido por meio de inversão de ícone e, quando você está criando, você deve estar ciente que será ser invertidas programaticamente no produto.  
  
 Para obter mais informações sobre como usar cores de ícones do Visual Studio, consulte [usando cores nas imagens](../../extensibility/ux-guidelines/images-and-icons-for-visual-studio.md#BKMK_UsingColorInImages).  
  
##  <a name="BKMK_UsingColorInImages"></a> Usando cores de imagens  
  
### <a name="overview"></a>Visão geral  
 Ícones no Visual Studio são principalmente monocromáticos. Cor é reservada para transmitir informações específicas e nunca para a decoração. Cor é usada:  
  
-   para indicar uma ação  
  
-   para alertar o usuário para uma notificação de status  
  
-   para designar afiliação de linguagem  
  
-   para diferenciar os itens dentro do IntelliSense  
  
### <a name="accessibility"></a>Acessibilidade  
 Diretrizes de conformidade do Visual Studio requerem que todos os ícones marcado para a passagem de produto os requisitos de acessibilidade para cor e contraste. Cores da paleta de linguagem visual foram testadas e atendem a esses requisitos.  
  
#### <a name="color-inversion-for-dark-themes"></a>Inversão de cores de temas escuros  
 Para exibir ícones com a taxa de contraste correto no tema escuro Visual Studio, uma inversão é aplicada por meio de programação. As cores neste guia foram escolhidas em parte para que eles Inverter corretamente. Restringir o uso de cor para essa paleta, ou você obterá resultados imprevisíveis quando a inversão é aplicado.  
  
 ![Exemplos de ícones que tiveram suas cores invertidas](../../extensibility/ux-guidelines/media/0405-01_darkthemeinversion.png "01_DarkThemeInversion 0405")<br />Exemplos de ícones que tiveram suas cores invertidas
  
### <a name="base-palette"></a>Paleta de base  
 Todos os ícones padrão contém três cores base. Ícones não contenham nenhuma gradientes ou sombras, com uma ou duas exceções para os ícones de ferramenta 3D.  
  
|Uso|Nome|Valor (tema claro)|Amostra|Exemplo|  
|-----------|----------|---------------------------|------------|-------------|  
|Plano de fundo/escuro|VS BG|424242 / 66,66,66|![Swatch 424242](../../extensibility/ux-guidelines/media/0405_424242.png "0405_424242")|![Exemplo de paleta base](../../extensibility/ux-guidelines/media/0405-02_basepaletteexample.png "02_BasePaletteExample 0405")|  
|Primeiro plano/leve|VS FG|F0EFF1 / 240,239,241|![Swatch F0EFF1](../../extensibility/ux-guidelines/media/0405_f0eff1.png "0405_F0EFF1")||  
|Contorno|VS-Out|F6F6F6 / 246,246,246|![Swatch F6F6F6](../../extensibility/ux-guidelines/media/0405_f6f6f6.png "0405_F6F6F6")||  
  
 Além das cores base, cada ícone pode conter adicionais em uma cor de paleta estendida.  
  
### <a name="extended-palette"></a>Paleta estendida  
  
#### <a name="action-modifiers"></a>Modificadores de ação  
 Quatro cores indicam os tipos de ações necessárias por modificadores de ação:  
  
|Uso|Nome|Valor (todos os temas)|Amostra|  
|-----------|----------|--------------------------|------------|  
|Positivo|Verde de ação do VS|388A34 / 56,138,52|![Swatch 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|Negativo|Vermelho de ação do VS|A1260D / 161,38,13|![Swatch A1260D](../../extensibility/ux-guidelines/media/0405_a1260d.png "0405_A1260D")|  
|Neutro|Azul de ação do VS|00539C / 0,83,156|![Swatch 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|Criar/novo|VS ação laranja|C27D1A / 194,156,26|![Swatch C27D1A](../../extensibility/ux-guidelines/media/0405_c27d1a.png "0405_C27D1A")|  
  
##### <a name="examples"></a>Exemplos  
 Verde é usado para modificadores de ação positiva como "Adicionar", "Executar", "Play" e "Validação".  
  
|||||  
|-|-|-|-|  
|![Ícone executar](../../extensibility/ux-guidelines/media/0405-03_actionmodifierrun.png "03_ActionModifierRun 0405")<br />Executar|![Ícone de consulta de execução](../../extensibility/ux-guidelines/media/0405-04_executequery.png "04_ExecuteQuery 0405")<br />Executar consulta|![Executar todos os ícone de etapas](../../extensibility/ux-guidelines/media/0405-05_playallsteps.png "05_PlayAllSteps 0405")<br />Executar todas as etapas|![Adicionar ícone controle](../../extensibility/ux-guidelines/media/0405-06_addcontrol.png "06_AddControl 0405")<br />Adicionar controle|  
  
 Vermelho é usado para modificadores de ação negativo como "Excluir", "Stop", "Cancelar" e "Fechar".  
  
|||||  
|-|-|-|-|  
|![Excluir relação ícone](../../extensibility/ux-guidelines/media/0405-07_deleterelationship.png "07_DeleteRelationship 0405")<br />Excluir relação|![Excluir coluna de ícone](../../extensibility/ux-guidelines/media/0405-08_deletecolumn.png "08_DeleteColumn 0405")<br />Excluir coluna|![Ícone de consulta de parada](../../extensibility/ux-guidelines/media/0405-09_stopquery.png "09_StopQuery 0405")<br />Parar consulta|![Ícone de Conexão offline](../../extensibility/ux-guidelines/media/0405-10_connectionoffline.png "10_ConnectionOffline 0405")<br />Conexão Offline|  
  
 Azul é aplicada à ação neutra modificadores geralmente representado como setas, como "Abrir," "Próximo", "Anterior", "Importar" e "Exportar".  
  
|||||  
|-|-|-|-|  
|![Vá para o ícone de campo](../../extensibility/ux-guidelines/media/0405-11_gotofield.png "11_GoToField 0405")<br />Vá para o campo|![Em lotes seleção&#45;no ícone](../../extensibility/ux-guidelines/media/0405-12_batchedcheckin.png "12_BatchedCheckIn 0405")<br />Check-In em lotes|![Ícone do editor de endereço](../../extensibility/ux-guidelines/media/0405-13_addresseditor.png "13_AddressEditor 0405")<br />Editor de endereço|![Ícone do editor de associação](../../extensibility/ux-guidelines/media/0405-14_associationeditor.png "14_AssociationEditor 0405")<br />Editor de associação|  
  
 Ouro escuro é usado principalmente para o modificador "New".  
  
|||||  
|-|-|-|-|  
|![Ícone do novo projeto](../../extensibility/ux-guidelines/media/0405-15_newproject.png "15_NewProject 0405")<br />Novo Projeto|![Criar um novo ícone de gráfico](../../extensibility/ux-guidelines/media/0405-16_createnewgraph.png "16_CreateNewGraph 0405")<br />Criar novo gráfico|![Novo ícone de teste de unidade](../../extensibility/ux-guidelines/media/0405-17_newunittest.png "17_NewUnitTest 0405")<br />Novo teste de unidade|![Novo ícone de item de lista](../../extensibility/ux-guidelines/media/0405-18_newlistitem.png "18_NewListItem 0405")<br />Novo Item de lista|  
  
#### <a name="special-cases"></a>Casos especiais  
 Em alguns casos, um modificador de ação colorido pode ser usado independentemente como um ícone de autônomo. A cor usada para o ícone reflete as ações que o ícone associado. Esse uso é limitado a um pequeno subconjunto dos ícones, incluindo:  
  
||||||  
|-|-|-|-|-|  
|![Ícone executar](../../extensibility/ux-guidelines/media/0405-03_actionmodifierrun.png "03_ActionModifierRun 0405")<br />Executar|![Ícone de parada](../../extensibility/ux-guidelines/media/0405-19_stop.png "19_Stop 0405")<br />Stop|![Excluir ícone](../../extensibility/ux-guidelines/media/0405-20_delete.png "20_Delete 0405")<br />Excluir|![Ícone Salvar](../../extensibility/ux-guidelines/media/0405-21_save.png "21_Save 0405")<br />Salvar|![Ícone de voltar de navegar](../../extensibility/ux-guidelines/media/0405-22_navigateback.png "22_NavigateBack 0405")<br />Navegação regressiva|  
  
### <a name="code-hierarchy-palette"></a>Paleta de hierarquia de código  
  
#### <a name="folder"></a>Pasta  
  
|Uso|Nome|Valor (todos os temas)|Amostra|Exemplo|  
|-----------|----------|--------------------------|------------|-------------|  
|Pastas|Pasta|DCB67A / 220,182,122|![Swatch DCB67A](../../extensibility/ux-guidelines/media/0405_dcb67a.png "0405_DCB67A")|![Ícone de cor da pasta](../../extensibility/ux-guidelines/media/0405-23_foldercolor.png "23_FolderColor 0405")|  
  
#### <a name="visual-studio-languages"></a>Idiomas do Visual Studio  
 Cada um dos idiomas ou plataformas disponíveis no Visual Studio comum tem uma cor associada. Essas cores são usadas no ícone de base, ou em modificadores de linguagem que aparecem no canto superior direito dos ícones compostas.  
  
|Uso|Nome|Valor (todos os temas)|Amostra|  
|-----------|----------|--------------------------|------------|  
|ASP, HTML, WPF|ASP HTML WPF azul|7 DE 0095D / 0,149,215|![Swatch 0095D7](../../extensibility/ux-guidelines/media/0405_0096d7.png "0405_0096D7")|  
|C++|Roxo CPP|9B4F96 / 155,79,150|![Swatch 9B4F96](../../extensibility/ux-guidelines/media/0405_9b4f96.png "0405_9B4F96")|  
|C#|CS verde (VS ação verde)|388A34 / 56,138,52|![Swatch 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|CSS|Vermelho CSS|BD1E2D / 189,30,45|![Swatch BD1E2D](../../extensibility/ux-guidelines/media/0405_bd1e2d.png "0405_BD1E2D")|  
|F#|FS roxo|672878 / 103,40,120|![Swatch 672878](../../extensibility/ux-guidelines/media/0405_672878.png "0405_672878")|  
|JavaScript|JS laranja|F16421 / 241,100,33|![Swatch F16421](../../extensibility/ux-guidelines/media/0405_f16421.png "0405_F16421")|  
|VB|VB Blue (azul de ação do VS)|00539C / 0,83,156|![Swatch 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|TypeScript|TS laranja|E04C06 / 224,76,6|![Swatch E04C06](../../extensibility/ux-guidelines/media/0405_e04c06.png "0405_E04C06")|  
|Python|PIAR verde|879636 / 135,150,54|![Swatch 879636](../../extensibility/ux-guidelines/media/0405_879636.png "0405_879636")|  
  
##### <a name="examples-of-icons-with-language-modifiers"></a>Exemplos de ícones com modificadores de linguagem  
  
|||||||  
|-|-|-|-|-|-|  
|![Ícone do Visual Basic](../../extensibility/ux-guidelines/media/0405-25_vb.png "25_VB 0405")<br />VB|![C&#35; ícone](../../extensibility/ux-guidelines/media/0405-26_csharp.png "26_CSharp 0405")<br />C#|![C&#43; &#43; ícone](../../extensibility/ux-guidelines/media/0405-27_cplusplus.png "27_CPlusPlus 0405")<br />C++|![F&#35; ícone](../../extensibility/ux-guidelines/media/0405-28_fsharp.png "28_FSharp 0405")<br />F#|![Ícone de JavaScript](../../extensibility/ux-guidelines/media/0405-29_javascript.png "29_JavaScript 0405")<br />JavaScript|![Ícone de Python](../../extensibility/ux-guidelines/media/0405-30_python.png "30_Python 0405")<br />Python|  
|![Ícone HTML](../../extensibility/ux-guidelines/media/0405-31_html.png "31_HTML 0405")<br />HTML|![Ícone WPF](../../extensibility/ux-guidelines/media/0405-32_wpf.png "32_WPF 0405")<br />WPF|![ASP icon](../../extensibility/ux-guidelines/media/0405-33_asp.png "0405-33_ASP")<br />ASP|![Ícone CSS](../../extensibility/ux-guidelines/media/0405-34_css.png "34_CSS 0405")<br />CSS|![Ícone de typeScript](../../extensibility/ux-guidelines/media/0405-35_typescript.png "35_TypeScript 0405")<br />TypeScript||  
  
#### <a name="intellisense"></a>IntelliSense  
 Ícones de IntelliSense usam uma paleta de cores exclusivas. Essas cores são usadas para ajudar os usuários a diferenciar rapidamente itens diferentes na lista pop-up do IntelliSense.  
  
|Uso|Nome|Valor (todos os temas)|Amostra|  
|-----------|----------|--------------------------|------------|  
|Classe de evento|VS ação laranja|C27D1A / 194,125,26|![Swatch C27D1A](../../extensibility/ux-guidelines/media/0405_c27d1a.png "0405_C27D1A")|  
|Método de extensão, o método, o módulo, delegado|Roxo de ação do VS|652 90 DE D / 101,45,144|![Swatch 652D90](../../extensibility/ux-guidelines/media/0405_652d90.png "0405_652D90")|  
|Campo de Item de Enum, Macro, estrutura, tipo de valor de união, operador, Interface|Azul de ação do VS|00539C / 0,83,156|![Swatch 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|Objeto|Verde de ação do VS|388A34 / 56,138,52|![Swatch 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|Constante, exceção, Item de Enum, mapa, Item de mapa, Namespace, modelo, definição de tipo|Plano de fundo (VS BG)|424242 / 66,66,66|![Swatch 424242](../../extensibility/ux-guidelines/media/0405_424242.png "0405_424242")|  
  
##### <a name="examples-of-intellisense-icons"></a>Exemplos de ícones do IntelliSense  
  
||||||  
|-|-|-|-|-|  
|![Ícone de classe IntelliSense](../../extensibility/ux-guidelines/media/0405-36_intellisenseclass.png "36_IntelliSenseClass 0405")<br />Classe|![Ícone de evento particular IntelliSense](../../extensibility/ux-guidelines/media/0405-37_intellisenseprivateevent.png "37_IntelliSensePrivateEvent 0405")<br />Evento particular|![Ícone de delegado do IntelliSense](../../extensibility/ux-guidelines/media/0405-38_intellisensedelegate.png "38_IntelliSenseDelegate 0405")<br />delegado|![Ícone de amigo do IntelliSense método](../../extensibility/ux-guidelines/media/0405-39_intellisensemethodfriend.png "39_IntelliSenseMethodFriend 0405")<br />Método Friend|![Ícone de campo](../../extensibility/ux-guidelines/media/0405-40_field.png "40_Field 0405")<br />Campo|  
|![IntelliSense protegido ícone do item de enum](../../extensibility/ux-guidelines/media/0405-41_intellisenseprotectedenumitem.png "41_IntelliSenseProtectedEnumItem 0405")<br />Item de Enum protegido|![Ícone do objeto IntelliSense](../../extensibility/ux-guidelines/media/0405-42_intellisenseobject.png "42_IntelliSenseObject 0405")<br />Objeto|![Ícone de modelo do IntelliSense](../../extensibility/ux-guidelines/media/0405-43_intellisensetemplate.png "43_IntelliSenseTemplate 0405")<br />Modelo|![Ícone de atalho do IntelliSense exceção](../../extensibility/ux-guidelines/media/0405-44_intellisenseexceptionshortcut.png "44_IntelliSenseExceptionShortcut 0405")<br />Atalho de exceção||  
  
### <a name="notifications"></a>Notificações  
 Notificações no Visual Studio são usadas para indicar o status. A paleta de notificação usa os seguintes quatro cores, bem como opções de preenchimento de primeiro plano preto e branco para definir notificações com os seguintes níveis de status.  
  
|Uso|Nome|Valor (todos os temas)|Amostra|  
|-----------|----------|--------------------------|------------|  
|Status: neutro|Notificação Blue (azul VS)|1BA1E2 / 27,161,226|![Amostra 1BA1E2](../../extensibility/ux-guidelines/media/0405_1ba1e2.png "0405_1BA1E2")|  
|Status: positivo|Notificação verde (VS verde)|339933 / 51,153,51|![Swatch 339933](../../extensibility/ux-guidelines/media/0405_339933.png "0405_339933")|  
|Status: negativo|Notificação vermelho (VS vermelho)|E51400 / 229,20,0|![Swatch E51400](../../extensibility/ux-guidelines/media/0405_e51400.png "0405_E51400")|  
|Status: aviso|Notificação amarelo (VS laranja)|FFCC00 / 255,204,0|![Swatch FFCC00](../../extensibility/ux-guidelines/media/0405_ffcc00.png "0405_FFCC00")|  
|Preenchimento de primeiro plano|Notificação preto (preto)|000000 / 0,0,0|![Swatch &#35;000000](../../extensibility/ux-guidelines/media/0405_000000.png "0405_000000")|  
|Preenchimento de primeiro plano|Notificação branco (branco)|FFFFFF / 255,255,255|![Swatch FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
  
#### <a name="examples-of-notification-icons"></a>Exemplos de ícones de notificação  
  
|||||  
|-|-|-|-|  
|![Ícone de alerta](../../extensibility/ux-guidelines/media/0405-45_alert.png "45_Alert 0405")<br />Alerta|![Ícone de aviso](../../extensibility/ux-guidelines/media/0405-48_warning.png "48_Warning 0405")<br />Aviso|![Ícone completa](../../extensibility/ux-guidelines/media/0405-46_complete.png "46_Complete 0405")<br />Concluir|![Ícone de parada](../../extensibility/ux-guidelines/media/0405-47_stop.png "47_Stop 0405")<br />Stop|  
  
### <a name="visual-studio-online"></a>Visual Studio Online  
 Em geral, o Visual Studio Online consiste em recursos hospedados em um navegador. A cor varia em ambientes diferentes, mas o estilo permanece o mesmo.  
  
|Grupo|Uso|Nome|Valor (todos os temas)|Amostra|  
|-----------|-----------|----------|--------------------------|------------|  
|TFS|Informações preliminares|TFSO BG|656565/ 101, 101, 101|![Amostra de 656565](../../extensibility/ux-guidelines/media/0405_656565.png "0405_656565")|  
|TFS|Contorno|TFSO-OUT|FFFFFF / 255, 255, 255|![Swatch FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|Napa|Informações preliminares|Branco|FFFFFF / 255, 255, 255|![Swatch FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|Monaco|Informações preliminares|Branco|FFFFFF / 255, 255, 255|![Swatch FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|F12|Informações preliminares|Branco|FFFFFF / 255, 255, 255|![Swatch FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|F12|Normal|Grey_Primary F12|555555 / 85, 85, 85|![Amostra de 555555](../../extensibility/ux-guidelines/media/0405_555555.png "0405_555555")|  
|F12|Passe o mouse|Blue_Hover F12|2279BF / 34,121,191|![Swatch 2279BF](../../extensibility/ux-guidelines/media/0405_2279bf.png "0405_2279BF")|  
|F12|Disabled|F12 LtGrey_Disabled|ABABAC / 171,171,172|![Swatch ABABAC](../../extensibility/ux-guidelines/media/0405_ababac.png "0405_ABABAC")|  
|F12|Passe o mouse em segundo plano|Passe o mouse bg|D9EBF7 / 217,235,247|![Swatch D9EBF7](../../extensibility/ux-guidelines/media/0405_d9ebf7.png "0405_D9EBF7")|  
|F12|Plano de fundo pressionado|Bg pressionado|B2D7F0 / 178,215,240|![Swatch B2D7F0](../../extensibility/ux-guidelines/media/0405_b2d7f0.png "0405_B2D7F0")|  
|F12|Contorno|VS-OUT|F6F6F6 / 246,246,246|![Swatch F6F6F6](../../extensibility/ux-guidelines/media/0405_f6f6f6.png "0405_F6F6F6")|  
|F12|Informações|Informações|00BCF2 / 0,188,242|![Swatch 00BCF2](../../extensibility/ux-guidelines/media/0405_00bcf2.png "0405_00BCF2")|  
|F12|Aviso|Aviso|F28300 / 242,131,0|![Swatch F28300](../../extensibility/ux-guidelines/media/0405_f28300.png "0405_F28300")|  
|F12|Erro / negativo|Error_Negative|E81123 / 232,17,35|![Swatch E81123](../../extensibility/ux-guidelines/media/0405_e81123.png "0405_E81123")|  
|F12|Iniciar / positivo|Start_Positive|009E49 / 0,158,73|![Swatch 009E49](../../extensibility/ux-guidelines/media/0405_009e49.png "0405_009E49")|  
|F12|Tipo de intervalo|Tipo de intervalo|9B4F96 / 155,79,150|![Swatch 9B4F96](../../extensibility/ux-guidelines/media/0405_9b4f96.png "0405_9B4F96")|  
|F12|Marca de evento|Marca de evento|A51F00 / 165,31,0|![Swatch A51F00](../../extensibility/ux-guidelines/media/0405_a51f00.png "0405_A51F00")|  
|F12|Marca de usuário|Marca de usuário|F16220 / 241,98,32|![Swatch F16220](../../extensibility/ux-guidelines/media/0405_f16220.png "0405_F16220")|  
  
#### <a name="examples-of-visual-studio-online-icons"></a>Exemplos de ícones do Visual Studio Online  
  
|TFS Online||||  
|----------------|-|-|-|  
|![Ícone de equipe TFS Online](../../extensibility/ux-guidelines/media/0405-49_tfsonlineteam.png "49_TFSOnlineTeam 0405")<br />Equipe online|![Ícone de informações do TFS](../../extensibility/ux-guidelines/media/0405-50_tfsinformation.png "50_TFSInformation 0405")<br />Informações|![Ícone de histórico do TFS](../../extensibility/ux-guidelines/media/0405-51_tfshistory.png "51_TFSHistory 0405")<br />Histórico|![Ícone de ramificação do TFS](../../extensibility/ux-guidelines/media/0405-52_tfsbranch.png "52_TFSBranch 0405")<br />Ramificação|  
  
|Napa||||  
|----------|-|-|-|  
|![Ícone de conteúdo Napa](../../extensibility/ux-guidelines/media/0405-53_napacontent.png "53_NapaContent 0405")<br />Conteúdo|![Ícone de email do office Napa](../../extensibility/ux-guidelines/media/0405-54_napaofficemail.png "54_NapaOfficeMail 0405")<br />Mensagem do Office|![Ícone do SharePoint de Napa](../../extensibility/ux-guidelines/media/0405-55_napasharepoint.png "55_NapaSharePoint 0405")<br />SharePoint|![Ícone do painel de tarefas Napa](../../extensibility/ux-guidelines/media/0405-56_napataskpane.png "56_NapaTaskPane 0405")<br />Painel de tarefas|  
  
|Monaco||||  
|------------|-|-|-|  
|![Ícone de arquivos Monaco](../../extensibility/ux-guidelines/media/0405-57_monacofiles.png "57_MonacoFiles 0405")<br />Arquivos|![Ícone de Git Monaco](../../extensibility/ux-guidelines/media/0405-58_monacogit.png "58_MonacoGit 0405")<br />Git|![Ícone de pesquisa Monaco](../../extensibility/ux-guidelines/media/0405-59_monacosearch.png "59_MonacoSearch 0405")<br />Pesquisar|![Ícone de texto Monaco](../../extensibility/ux-guidelines/media/0405-60_monacotext.png "60_MonacoText 0405")<br />Texto|  
  
|F12|||  
|---------|-|-|  
|![Ícone de código muito F12](../../extensibility/ux-guidelines/media/0405-61_f12prettycode.png "61_F12PrettyCode 0405")<br />Código muito|![Ícone de aviso F12](../../extensibility/ux-guidelines/media/0405-62_f12warning.png "62_F12Warning 0405")<br />Aviso|![Ícone F12 emular](../../extensibility/ux-guidelines/media/0405-63_f12emulate.png "63_F12Emulate 0405")<br />Emular|