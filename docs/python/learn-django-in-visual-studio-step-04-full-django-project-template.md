---
title: Tutorial – Saiba mais sobre Django no Visual Studio, etapa 4
description: Um passo a passo dos conceitos básicos do Django no contexto dos projetos do Visual Studio, especificamente os recursos fornecidos pelo modelo Projeto Web do Django.
ms.date: 04/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 387077f8845d4e070d4ad0a07f6549a97552a233
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
---
# <a name="tutorial-step-4-use-the-full-django-web-project-template"></a>Tutorial, etapa 4: Usar o modelo Projeto Web completo do Django

**Etapa anterior: [Fornecer arquivos estáticos, adicionar páginas e usar a herança do modelo](learn-django-in-visual-studio-step-03-serve-static-files-and-add-pages.md)**

Agora que você explorou as Noções básicas de Django ao criar um aplicativo com o modelo "Projeto de Aplicativo em Branco do Django" no Visual Studio, você pode compreender facilmente o aplicativo mais completo que é produzido pelo modelo "Projeto Web do Django".

Nesta etapa, agora você poderá:

> [!div class="checklist"]
> - Criar um aplicativo Web do Django mais completo usando o modelo "Projeto Web do Django" e examinar a estrutura do projeto (etapa 4-1)
> - Entender os modos de exibição e os modelos de página criados pelo modelo de projeto, que consistem em três páginas que são herdadas a partir de um modelo de página de base e que emprega bibliotecas JavaScript estáticas como jQuery e Bootstrap (etapa 4-2)
> - Entender o roteamento de URL fornecido pelo modelo (etapa 4-3)

O modelo também fornece autenticação básica, que é abordada na etapa 5.

## <a name="step-4-1-create-a-project-from-the-template"></a>Etapa 4-1: Criar um projeto com base no modelo

1. No Visual Studio, vá até **Gerenciador de Soluções**, clique com o botão direito na solução "LearningDjango" criada anteriormente neste tutorial e selecione **Adicionar** > **Novo Projeto**. (Como alternativa, se você quiser usar uma nova solução, selecione **Arquivo** > **Novo** > **Projeto**).

1. Na caixa de diálogo Novo Projeto, procure e selecione o modelo "Projeto Web do Django", nomeie o projeto "DjangoWeb" e selecione **OK**.

1. Como o modelo novamente inclui um arquivo `requirements.txt`, o Visual Studio solicita onde instalar essas dependências. Escolha a opção **Instalar em um ambiente virtual** e, na caixa de diálogo **Adicionar Ambiente Virtual**, selecione **Criar** para aceitar os padrões.

1. Quando o Python termina a configuração do ambiente virtual, siga as instruções no `readme.html` exibido para criar um superusuário Django (ou seja, um administrador). Basta clicar com o botão direito do mouse no projeto do Visual Studio e selecionar o comando **Python** > **Criar Superusuário do Django** e, em seguida, seguir os prompts. Registre seu nome de usuário e senha que usa ao exercitar os recursos de autenticação do aplicativo.

1. Defina o projeto "DjangoWeb" para ser o padrão para a solução do Visual Studio clicando com o botão direito nesse projeto em **Gerenciador de Soluções** e selecionando **Definir como Projeto de Inicialização**. O projeto de inicialização, mostrado em negrito, é o que é executado quando você inicia o depurador.

    ![Gerenciador de Soluções mostrando o projeto DjangoWeb como o projeto de inicialização](media/django/step04-second-project-in-solution-set-as-startup-project.png)

1. Escolha **Depurar** > **Iniciar Depuração** (F5) ou usar o **Servidor Web** na barra de ferramentas para executar o servidor:

    ![Executar o botão da barra de ferramentas do servidor Web no Visual Studio](media/django/run-web-server-toolbar-button.png)

1. O aplicativo criado pelo modelo tem três páginas, Página inicial, Sobre e Contato, que você navega usando a barra de navegação. Levar um minuto ou dois para examinar as diferentes partes do aplicativo. Para autenticar com o aplicativo por meio do comando **Login**, use as credenciais de superusuário criadas anteriormente.

    ![Exibição completa do navegador do aplicativo Projeto Web do Django](media/django/step04-full-app-desktop-view.png)

1. O aplicativo criado pelo modelo "Projeto Web do Django" usa Bootstrap para layout responsivo que acomoda fatores forma móveis. Para ver essa capacidade de resposta, redimensione o navegador para uma exibição específica para que o conteúdo seja renderizado verticalmente e a barra de navegação se transforme em um ícone de menu:

    ![Exibição (estreita) móvel do navegador do aplicativo Projeto Web do Django](media/django/step04-full-app-mobile-view.png)

1. Você pode deixar o aplicativo em execução para as seções a seguir.

    Se quiser parar o aplicativo e [confirmar as alterações para o controle de origem](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control), primeiro abra a página **Alterações** no **Team Explorer**, clicando com o botão direito na pasta para o ambiente virtual (provavelmente `env`) e selecione **Ignorar esses itens locais**.

### <a name="examine-what-the-template-creates"></a>Examine o que o modelo cria

No nível mais amplo, o modelo "Projeto Web do Django" cria a seguinte estrutura:

- Arquivos na raiz do projeto:
  - `manage.py`, o utilitário administrativo do Django.
  - `db.sqlite3`, um banco de dados padrão SQLite.
  - `requirements.txt` que contém uma dependência no Django 1.x.
  - `readme.html`, um arquivo que é exibido no Visual Studio depois de criar o projeto. Conforme observado na seção anterior, siga as instruções aqui para criar uma conta de superusuário (administrador) para o aplicativo.
- A pasta `app` contém todos os arquivos de aplicativo, incluindo exibições, modelos, testes, formulários, modelos e arquivos estáticos (veja a etapa 4-2). Normalmente, você renomeie esta pasta para usar um nome de aplicativo mais diferente.
- A pasta `DjangoWeb` (projeto do Django) contém os arquivos de projeto típicos do Django: `__init.py__`, `settings.py`, `urls.py` e `wsgi.py`. Usando o modelo de projeto, `settings.py` já está configurado para o aplicativo e o arquivo de banco de dados, e `urls.py` já está configurado com rotas para todas as páginas de aplicativo, incluindo o formulário de logon.

### <a name="question-is-it-possible-to-share-a-virtual-environment-between-visual-studio-projects"></a>Pergunta: É possível compartilhar um ambiente virtual entre projetos do Visual Studio?

Resposta: Sim, mas faça isso sabendo que diferentes projetos provavelmente usam pacotes diferentes ao longo do tempo e, portanto, um ambiente virtual compartilhado deve conter todos os pacotes para todos os projetos que o usam.

No entanto, para usar um ambiente virtual existente, faça o seguinte:

1. Quando for solicitado a instalar dependências no Visual Studio, selecione a opção **Eu os instalarei por conta própria** opção.
1. No **Gerenciador de Soluções**, clique com o botão direito do mouse no nó **Ambientes do Python** e escolha **Adicionar Ambiente Virtual Existente**.
1. Navegue até e selecione a pasta que contém o ambiente virtual e selecione **OK**.

## <a name="step-4-2-understand-the-views-and-page-templates-created-by-the-project-template"></a>Etapa 4-2: Entender os modos de exibição e os modelos de página criados pelo modelo de projeto

Quando você executa o projeto, observe que o aplicativo contém três modos de exibição: Página inicial, Sobre e Contato. O código para esses modos de exibição é encontrado na pasta `app/views`. Cada função de exibição simplesmente chama `django.shortcuts.render` com o caminho para um modelo e um objeto de dicionário simples. Por exemplo, a página Sobre é tratada pela função `about`:

```python
def about(request):
    """Renders the about page."""
    assert isinstance(request, HttpRequest)
    return render(
        request,
        'app/about.html',
        {
            'title':'About',
            'message':'Your application description page.',
            'year':datetime.now().year,
        }
    )
```

Os modelos estão localizados na pasta `templates/app` do aplicativo (e geralmente você deseja renomear `app` para o nome do seu aplicativo real). O modelo de base, `layout.html`, é mais amplo. Ele se refere a todos os arquivos estáticos necessários (JavaScript e CSS), define um bloco nomeado "conteúdo" que outras páginas substituem e fornece outro bloco chamado "scripts". Os seguintes trechos anotados do `layout.html` mostram essas áreas específicas:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />

    <!-- Define a viewport for Bootstrap's responsive rendering -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ title }} - My Django Application</title>

    {% load staticfiles %}
    <link rel="stylesheet" type="text/css" href="{% static 'app/content/bootstrap.min.css' %}" />
    <link rel="stylesheet" type="text/css" href="{% static 'app/content/site.css' %}" />
    <script src="{% static 'app/scripts/modernizr-2.6.2.js' %}"></script>
</head>
<body>
    <!-- Navbar omitted -->

    <div class="container body-content">

<!-- "content" block that pages are expected to override -->
{% block content %}{% endblock %}
        <hr/>
        <footer>
            <p>&copy; {{ year }} - My Django Application</p>
        </footer>
    </div>

<!-- Additional scripts; use the "scripts" block to add page-specific scripts.  -->
    <script src="{% static 'app/scripts/jquery-1.10.2.js' %}"></script>
    <script src="{% static 'app/scripts/bootstrap.js' %}"></script>
    <script src="{% static 'app/scripts/respond.js' %}"></script>
{% block scripts %}{% endblock %}

</body>
</html>
```

Os modelos de cada página, `about.html`, `contact.html` e `index.html`, cada uma estende o modelo base `layout.html`. `about.html` é o mais simples e mostra as marcas `{% extends %}` e `{% block content %}`:

```html
{% extends "app/layout.html" %}

{% block content %}

<h2>{{ title }}.</h2>
<h3>{{ message }}</h3>

<p>Use this area to provide additional information.</p>

{% endblock %}
```

`index.html` e `contact.html` usam a mesma estrutura e fornecem mais conteúdo no bloco "conteúdo".

Na pasta `templates/app` também está uma quarta página `login.html`, juntamente com `loginpartial.html` que é colocada em `layout.html` usando `{% include %}`. Esses arquivos de modelo são discutidos na etapa 5 na autenticação.

### <a name="question-can--block--and--endblock--be-indented-in-the-django-page-template"></a>Pergunta: {% block %} e {% endblock %} podem ser recuados no modelo de página do Django?

Resposta: Sim, os modelos de página do Django funcionam bem se você recuar marcas de bloco, talvez para alinhá-los em seus elementos pai apropriados. Eles não estão recuados nos modelos de página gerados pelo modelo de projeto do Visual Studio para que você possa ver claramente onde eles estão colocados.

## <a name="step-4-3-understand-the-url-routing-created-by-the-template"></a>Etapa 4-3: Entender o roteamento de URL criado pelo modelo

O arquivo `urls.py` do projeto do Django conforme criados pelo modelo "Projeto Web do Django" contém o seguinte código:

```python
from datetime import datetime
from django.conf.urls import url
import django.contrib.auth.views

import app.forms
import app.views

urlpatterns = [
    url(r'^$', app.views.home, name='home'),
    url(r'^contact$', app.views.contact, name='contact'),
    url(r'^about$', app.views.about, name='about'),
    url(r'^login/$',
        django.contrib.auth.views.login,
        {
            'template_name': 'app/login.html',
            'authentication_form': app.forms.BootstrapAuthenticationForm,
            'extra_context':
            {
                'title': 'Log in',
                'year': datetime.now().year,
            }
        },
        name='login'),
    url(r'^logout$',
        django.contrib.auth.views.logout,
        {
            'next_page': '/',
        },
        name='logout'),
]
```

Os três primeiros padrões de URL mapeiam diretamente para os modos de exibição `home`, `contact` e `about` no arquivo `views.py` do aplicativo. Os padrões `^login/$` e `^logout$`, por outro lado, usam modos de exibição internos do Django em vez de exibições definidas pelo aplicativo. As chamadas para o método `url` também incluem dados adicionais para personalizar o modo de exibição. A Etapa 5 explora essas chamadas.

### <a name="question-in-the-project-i-created-why-does-the-about-url-pattern-uses-about-instead-of-about-as-shown-here"></a>Pergunta: No projeto que criei, por que o padrão de URL "sobre" usa '^about' em vez de '^about$' como mostrado aqui?

Resposta: A falta do '$' à direita na expressão regular foi um erro simples em várias versões do modelo do projeto. O padrão de URL funciona perfeitamente bem para uma página chamada "sobre", mas sem o '$' à direita, o padrão de URL também corresponde a URLs como "about=django", "about09876", "aboutoflaughter" e assim por diante. O '$' à direita é mostrado aqui para criar um padrão de URL que corresponde a *somente* "sobre".

## <a name="next-steps"></a>Próximas etapas

> [!div class="nextstepaction"]
> [Autenticar usuários no Django](learn-django-in-visual-studio-step-05-django-authentication.md)

## <a name="going-deeper"></a>Aprofundando-se

- [Como gravar seu primeiro aplicativo do Django, parte 4 – Modos de exibição genéricos e formulários](https://docs.djangoproject.com/en/2.0/intro/tutorial04/) (docs.djangoproject.com)
- Código-fonte do tutorial no GitHub: [Microsoft/python-sample-vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django)