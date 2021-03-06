---
title: 'Como: acessar o esquema de cores e fontes internas | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- fonts, accessing built-in
- font and color control [Visual Studio SDK], categories
- colors, accessing built-in schemes
ms.assetid: 6905845e-e88e-4805-adcf-21da39108ec7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 180dc474b2458ec38a8a76ed8f931a592cf29225
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39500089"
---
# <a name="how-to-access-the-built-in-fonts-and-color-ccheme"></a>Como: acessar as fontes internas e ccheme de cores
O ambiente de desenvolvimento integrado (IDE) do Visual Studio tem um esquema de fontes e cores que está associado com a janela do editor. Você pode acessar esse esquema por meio de <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> interface.

 Para usar o esquema de cores e fontes internas, um VSPackage deve:

-   Defina uma categoria a ser usado com o serviço de fontes e cores padrão.

-   Registre-se a categoria com o servidor de fontes e cores padrão.

-   Aconselhamos o IDE que uma janela específica usa os itens de exibição interna e as categorias usando o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> e <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer> interfaces.

 O IDE usa a categoria resultante como um identificador para a janela. Nome da categoria é exibido na **Mostrar configurações de:** caixa de lista suspensa na **fontes e cores** página de propriedades.

## <a name="to-define-a-category-using-built-in-fonts-and-colors"></a>Para definir uma categoria usando cores e fontes internas

1.  Crie um GUID arbitrário.

     Esse GUID é usado para identificar exclusivamente uma categoria. Esta categoria reutiliza a especificação de cores e fontes de padrão do IDE.

    > [!NOTE]
    >  Ao recuperar dados de fontes e cores com o <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> ou outras interfaces, VSPackages usará esse GUID para fazer referência a informações internas.

2.  Nome da categoria deve ser adicionado a uma tabela de cadeia de caracteres dentro de recursos do VSPackage (*. rc*) de arquivo, para que ele pode ser localizado conforme necessário, quando exibidas no IDE.

     Para obter mais informações, consulte [adicionar ou excluir uma cadeia de caracteres](/cpp/windows/adding-or-deleting-a-string).

### <a name="to-register-a-category-using-built-in-fonts-and-colors"></a>Para registrar uma categoria usando cores e fontes internas

1.  Construa um tipo especial de entrada de registro de categoria no seguinte local:

     *[HKLM\Software\Microsoft. \Visual Studio\\\<versão do Visual Studio > \FontAndColors\\\<categoria >*]

     *\<Categoria >* é o nome não localizado da categoria.

2.  Preencha o registro para usar as fontes de estoque e o esquema de cores com quatro valores:

    |Nome|Tipo|Dados|Descrição|
    |----------|----------|----------|-----------------|
    |Categoria|REG_SZ|GUID|Um GUID arbitrária que identifica uma categoria que contém o esquema de fontes e cores das ações.|
    |Pacote|REG_SZ|GUID|{F5E7E71D-1401-11D1-883B-0000F87579D2}<br /><br /> Esse GUID é usado por todos os VSPackages que usam as configurações de fonte e cor padrão.|
    |NameID|REG_DWORD|ID|A ID de recurso de um nome de categoria localizáveis em VSPackage.|
    |ToolWindowPackage|REG_SZ|GUID|O GUID da implementação de VSPackage o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> interface.|

### <a name="to-initiate-the-use-of-system-provided-fonts-and-colors"></a>Para iniciar o uso de cores e fontes fornecidas pelo sistema

1.  Criar uma instância da <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> interface como parte da implementação e a inicialização da janela.

2.  Chame o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> método para obter uma instância das <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer> interface correspondente ao atual <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> instância.

3.  Chamar <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> duas vezes.

    -   Chamar uma vez com `VSEDITPROPID_ViewGeneral_ColorCategory`como um argumento.

    -   Chamar uma vez com `VSEDITPROPID_ViewGeneral_FontCategory` como um argumento.

     Isso define e expõe os serviços de fontes e cores padrão como uma propriedade da janela.

## <a name="example"></a>Exemplo
 O exemplo a seguir inicia o uso de cores e fontes internas.

```cpp
CComVariant vt;
CComQIPtr<IVsTextEditorPropertyCategoryContainer> spPropCatContainer(m_spView);
if (spPropCatContainer != NULL){
    CComPtr<IVsTextEditorPropertyContainer> spPropContainer;
    if (SUCCEEDED(spPropCatContainer->GetPropertyCategory(GUID_EditPropCategory_View_MasterSettings,
                                                          &spPropContainer))){
        CComVariant vt;CComVariant VariantGUID(bstrGuidText);
        spPropContainer->SetProperty(VSEDITPROPID_ViewGeneral_FontCategory, VariantGUID);
        spPropContainer->SetProperty(VSEDITPROPID_ViewGeneral_ColorCategory, VariantGUID);
    }
}
```

## <a name="see-also"></a>Consulte também

- [Use fontes e cores](../extensibility/using-fonts-and-colors.md)
- [Obter informações de fonte e cor para a colorização do texto](../extensibility/getting-font-and-color-information-for-text-colorization.md)
- [Configurações de fonte e cor armazenados do Access](../extensibility/accessing-stored-font-and-color-settings.md)
- [Visão geral de fontes e cores](../extensibility/font-and-color-overview.md)