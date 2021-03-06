---
title: 'Etapa 1: Criar um projeto e adicionar rótulos ao formulário'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: f44e50be-a5f5-4d77-9cff-dd52374c3f74
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7a34a49a3a66cebb81553f3e2786f281758c4dee
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747571"
---
# <a name="step-1-create-a-project-and-add-labels-to-your-form"></a>Etapa 1: Criar um projeto e adicionar rótulos ao formulário
Nas primeiras etapas do desenvolvimento deste teste, você o cria o projeto, e adiciona rótulos, um botão, e outros controles a um formulário. Você também define as propriedades para cada controle adicionado. O projeto conterá o formulário, controles e (posteriormente neste tutorial) o código. O botão inicia o teste, os rótulos mostram os problemas do teste e outros controles mostram as respostas dos teste e o tempo permanece para concluir o teste.

> [!NOTE]
>  Esse tópico faz parte de uma série de tutoriais sobre conceitos de codificação básica. Para obter uma visão geral do tutorial, confira [Tutorial 2: Criar um teste de matemática temporizado](../ide/tutorial-2-create-a-timed-math-quiz.md).

## <a name="to-create-a-project-and-set-properties-for-a-form"></a>Para criar um projeto e definir propriedades para um formulário

1.  Na barra de menus, selecione **Arquivo** > **Novo** > **Projeto**.

2.  Na lista **Modelos Instalados** escolha **C#** ou **Visual Basic**.

3.  Na lista de modelos, escolha o modelo de **Aplicativo do Windows Forms**, nomeie-o como **Teste de matemática** e então clique no botão **OK**.

     Um formulário chamado *Form1.cs* ou *Form1.vb* aparece, dependendo da linguagem de programação que você escolheu.

4.  Escolha o formulário e, em seguida, altere sua propriedade **Text** para **Teste de matemática**.

     A janela **Propriedades** contém propriedades para o formulário.

5.  Altere o tamanho do formulário para 500 pixels de largura por 400 pixels de altura.

     É possível redimensionar o formulário arrastando as bordas até que o tamanho correto apareça no canto inferior esquerdo do ambiente de desenvolvimento integrado (IDE). Como alternativa, você pode alterar os valores da propriedade **Size**.

6.  Altere o valor da propriedade **FormBorderStyle** para **Fixed3D** e defina a propriedade **MaximizeBox** para **False**.

     Esses valores impedem que os participantes de teste redimensionem o formulário.

## <a name="to-create-the-time-remaining-box"></a>Para criar a caixa tempo restante

1.  Adicione um controle <xref:System.Windows.Forms.Label> da **caixa de ferramentas** e, em seguida, defina o valor de sua propriedade **(Name)** para **timeLabel**.

     Este rótulo se tornará uma caixa no canto superior direito que mostra o número de segundos que permanece em teste.

2.  Altere a propriedade **AutoSize** para **False** de modo que você possa redimensionar a caixa.

3.  Altere a propriedade **BorderStyle** para **FixedSingle** para desenhar uma linha em torno da caixa.

4.  Defina a propriedade **Size** como **200, 30**.

5.  Mova o rótulo para o canto superior direito do formulário, onde as linhas espaçadoras azuis serão exibidas.

     Essas linhas ajudam você a alinhar controles no formulário.

6.  Na janela **Propriedades**, escolha a propriedade **Text** e pressione a tecla **Backspace** para apagar o seu valor.

7.  Escolha o sinal de mais (**+**) ao lado da propriedade **Font** e, em seguida, altere o valor da propriedade **Size** para **15,75**.

     É possível alterar várias propriedades de fonte, como mostra a imagem a seguir.

     ![Janela Propriedades mostrando o tamanho da fonte](../ide/media/express_setfontsize.png)
Janela **Propriedades** mostrando o tamanho da fonte

8.  Adicione outro controle Label da **caixa de ferramentas** e, em seguida, defina seu tamanho da fonte para **15,75**.

9. Defina a propriedade **Text** como **Time Left**.

10. Mova o rótulo de modo que ele alinhe apenas à esquerda do rótulo **timeLabel**.

### <a name="to-add-controls-for-the-addition-problems"></a>Para adicionar controles para os problemas de adição

1.  Adicione um controle Label da **caixa de ferramentas** e, em seguida, defina sua propriedade **Text** para **?** (ponto de interrogação).

2.  Defina a propriedade **AutoSize** para **False**.

3.  Defina a propriedade **Size** como **60, 50**.

4.  Defina o tamanho da fonte como **18**.

5.  Defina a propriedade **TextAlign** como **MiddleCenter**.

6.  Defina a propriedade **Location** para **50, 75** para posicionar o controle no formulário.

7.  Defina a propriedade **(Name)** como **plusLeftLabel**.

8.  Escolha o rótulo **plusLeftLabel** e, em seguida, pressione as teclas **Ctrl**+**C** ou **Copiar** no menu **Editar**.

9. Cole o rótulo três vezes usando as teclas **Ctrl**+**V** ou a opção **Colar** no menu **Editar**.

10. Organize os três novos rótulos de modo que fiquem em uma linha à direita do rótulo **plusLeftLabel**.

     É possível as linhas separadoras para separá-las e alinhá-las.

11. Defina o valor da segunda propriedade **Text** do rótulo para **+** (sinal de mais).

12. Defina o valor da propriedade **(Name)** do terceiro rótulo como **plusRightLabel**.

13. Defina o valor da propriedade **Text** do rótulo para **=** (sinal de igual).

14. Adicione um controle <xref:System.Windows.Forms.NumericUpDown> da **caixa de ferramentas**, defina seu tamanho da fonte para **18** e sua largura para **100**.

     Você aprenderá mais sobre esse tipo de controle posteriormente.

15. Alinhe o controle NumericUpDown com os controles Label para o problema de adição.

16. Altere o valor da propriedade **(Name)** do controle NumericUpDown para **sum**.

     Você criou a primeira linha, como mostra a imagem a seguir.

     ![Primeira linha do teste de matemática](../ide/media/express_firstrow.png) Primeira linha do teste de matemática

## <a name="to-add-controls-for-the-subtraction-multiplication-and-division-problems"></a>Para adicionar controles para subtração, multiplicação e problemas de divisão

1.  Copiar todos os cinco controles para o problema de adição (os quatro controles de rótulo e o controle NumericUpDown) e, em seguida, cola-os.

     O formulário contém cinco novos controles, que ainda são selecionados.

2.  Mova todos os controles no local de modo que eles se alinhem abaixo dos controles de adição.

     É possível usar as linhas separadoras para fornecer distância suficiente entre as duas linhas.

3.  Altere o valor da propriedade **Text** do segundo rótulo para **-** (sinal de subtração).

4.  Nomeie o primeiro rótulo de interrogação **minusLeftLabel**.

5.  Nomeie o segundo rótulo de interrogação **minusRightLabel**.

6.  Nomeie o controle NumericUpDown como **difference**.

7.  Cole os cinco controles mais duas vezes.

8.  Para a terceira linha, nomeie o primeiro rótulo como **timesLeftLabel**, altere a propriedade **Text** para **x** (sinal de multiplicação), nomeie o terceiro rótulo como **timesRightLabel** e nomeie o controle NumericUpDown como **product**.

9. Para a quarta linha, nomeie o primeiro rótulo como **dividedLeftLabel**, altere a propriedade **Text** para **÷** (sinal de divisão), nomeie o terceiro rótulo como **dividedRightLabel** e nomeie o controle NumericUpDown como **quotient**.

    > [!NOTE]
    >  É possível copiar os sinais de multiplicação × e de divisão ÷ deste tutorial e colá-los no formulário.

## <a name="to-add-a-start-button-and-set-the-tab-index-order"></a>Para adicionar um botão Iniciar e definir a ordem do índice de guias

1.  Adicione um controle de <xref:System.Windows.Forms.Button> da **caixa de ferramentas** e, em seguida, defina sua propriedade **(Name)** para **startButton**.

2.  Defina a propriedade **Text** como **Iniciar o teste**.

3.  Defina o tamanho da fonte como **14**.

4.  Defina a propriedade **AutoSize** como **True**, o que faz com que o botão seja redimensionado automaticamente para se ajustar ao texto.

5.  Centralize o botão próximo à parte inferior do formulário.

6.  Defina o valor da propriedade **TabIndex** para o controle **startButton** como **1**.

    > [!NOTE]
    >  A propriedade **TabIndex** define a ordem dos controles quando a pessoa realizando o teste escolhe a tecla **Tab**. Para ver como funciona, abra qualquer caixa de diálogo (por exemplo, na barra de menus, escolha **Arquivo** > **Abrir**) e escolha a tecla **Tab** algumas vezes. Inspecione como o cursor move o controle para controlar cada vez que você escolhe a tecla **Tab**. Um programador decidiu a ordem ao criar o formulário.

7.  Defina o valor da propriedade de **TabIndex** para o controle de soma NumericUpDown como **2**, o controle da diferença como **3**, o controle do produto como **4** e o controle do quociente como **5**.

     O formulário deve parecer com a ilustração a seguir.

     ![Forma do teste de matemática inicial](../ide/media/express_formlaidout.png) Forma do teste de matemática inicial

8.  Para verificar se a propriedade **TabIndex** funciona como você espera, salve e execute seu programa escolhendo a tecla **F5** ou a barra de menus **Depurar** > **Iniciar Depuração** na barra de menus. Em seguida, escolha a tecla **Tab** algumas vezes.

## <a name="to-continue-or-review"></a>Para continuar ou revisar

-   Para ir para a próxima etapa do tutorial, veja [Etapa 2: Criar um problema de adição aleatório](../ide/step-2-create-a-random-addition-problem.md).

-   Para retornar ao tópico de visão geral, veja [Tutorial 2: Criar um teste de matemática temporizado](../ide/tutorial-2-create-a-timed-math-quiz.md).
