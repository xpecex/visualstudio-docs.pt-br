---
title: 'Como: suprimir notificações de alteração de arquivo | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - suppress file change notification
ms.assetid: 891c1eb4-f6d0-4073-8df0-2859dbd417ca
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 312c34b143608cb6d829e2d79b6be2eae724a238
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47465001"
---
# <a name="how-to-suppress-file-change-notifications"></a>Como: suprimir notificações de alteração de arquivo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [como: suprimir notificações de alteração de arquivo](https://docs.microsoft.com/visualstudio/extensibility/how-to-suppress-file-change-notifications).  
  
Quando o arquivo físico que representa o buffer de texto tiver sido alterado, uma caixa de diálogo exibe a mensagem **você deseja salvar as alterações aos seguintes itens?** Isso é conhecido como a notificação de alteração de arquivo. Se muitas alterações serão para o arquivo, no entanto, essa caixa de diálogo exibindo repetidamente pode rapidamente se tornar irritante.  
  
 Programaticamente, você pode suprimir esta caixa de diálogo usando o procedimento a seguir. Ao fazer isso, você pode recarregar um arquivo imediatamente sem a necessidade de solicitar ao usuário para salvar as alterações de cada vez.  
  
### <a name="to-suppress-file-change-notification"></a>Para suprimir a notificação de alteração de arquivo  
  
1.  Chamar o <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> método para determinar qual objeto de buffer de texto está associado a seu arquivo aberto.  
  
2.  Direto a <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objeto que está na memória para ignorar monitorando alterações de arquivo, obtendo o <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl> da interface do <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objeto (dados de documento) e, em seguida, Implementando o <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> método com o `fIgnore` parâmetro definido como `true`.  
  
3.  Chamar os métodos na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> e o <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> interfaces para atualizar a memória de- <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objeto com as alterações de arquivo (por exemplo, quando um campo é adicionado ao seu componente).  
  
4.  Atualize o arquivo no disco com as alterações sem considerar as pendentes edições que o usuário pode ter em andamento.  
  
     Dessa forma, quando você direcionar o <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> as notificações de alteração de objeto para retomar o monitoramento de arquivo, o buffer de texto na memória reflete as alterações que você gerou, bem como todas as outras edições pendentes. O arquivo no disco reflete o código mais recente gerado por você e alterações feitas pelo usuário salvo anteriormente no código editado pelo usuário.  
  
5.  Chame o <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> método para notificar o <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objeto para reiniciar o monitoramento para notificações de alteração de arquivo, definindo o `fIgnore` parâmetro `false`.  
  
6.  Se você planeja fazer várias alterações no arquivo, como no caso do controle do código fonte (SCC), você deve informar o serviço de alteração de arquivo global suspender temporariamente as notificações de alteração de arquivo.  
  
     Por exemplo, se você reescrever o arquivo e, em seguida, alterar o carimbo de hora, você deve suspender as notificações de alteração de arquivo, como as operações de reconfiguração e timestample cada contam, pois o evento de alteração de um arquivo separado. Para habilitar a notificação de alteração de arquivo global em vez disso, você deve chamar o <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx.IgnoreFile%2A> método.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como suprimir a notificação de alteração de arquivo.  
  
```cpp#  
//Misc. helper classes  
  
CSuspendFileChanges::CSuspendFileChanges(  
    /* [in] */ const CString& strMkDocument,   
    /* [in] */ BOOL fSuspendNow /* = TRUE */)   
:  
    m_strMkDocument(strMkDocument),  
    m_fFileChangeSuspended(FALSE)  
{  
    if(fSuspendNow)  
        Suspend();  
}  
CSuspendFileChanges::~CSuspendFileChanges()  
{  
    Resume();  
}  
void CSuspendFileChanges::Suspend()  
{  
    USES_CONVERSION;  
  
    // Prevent suspend from suspending more than once.  
    if(m_fFileChangeSuspended)  
        return;  
  
    IVsRunningDocumentTable* pRDT =   
      _VxModule.GetIVsRunningDocumentTable();  
    ASSERT(pRDT);  
    if (!pRDT)  
        return;  
  
    CComPtr<IUnknown> srpDocData;  
    VSCOOKIE vscookie = VSCOOKIE_NIL;  
    pRDT->FindAndLockDocument(RDT_NoLock, T2COLE(m_strMkDocument),    
      NULL, NULL, &srpDocData, &vscookie);  
    if ( (vscookie == VSCOOKIE_NIL) || !srpDocData)  
        return;  
    CComPtr<IVsFileChangeEx> srpIVsFileChangeEx;  
    HRESULT hr = _VxModule.QueryService(SID_SVsFileChangeEx,   
      IID_IVsFileChangeEx, (void **)&srpIVsFileChangeEx);  
    if (SUCCEEDED(hr) && srpIVsFileChangeEx)  
    {  
        m_fFileChangeSuspended = TRUE;  
        srpIVsFileChangeEx->IgnoreFile(NULL, m_strMkDocument, TRUE);   
        srpDocData->QueryInterface(IID_IVsDocDataFileChangeControl,   
          (void**)&m_srpIVsDocDataFileChangeControl);  
        if(m_srpIVsDocDataFileChangeControl)  
            m_srpIVsDocDataFileChangeControl->IgnoreFileChanges(TRUE);  
    }  
}  
void CSuspendFileChanges::Resume()  
{  
    if(!m_fFileChangeSuspended)  
        return;  
  
    CComPtr<IVsFileChangeEx> srpIVsFileChangeEx;  
    HRESULT hr = _VxModule.QueryService(SID_SVsFileChangeEx,   
      IID_IVsFileChangeEx, (void **)&srpIVsFileChangeEx);  
    if (SUCCEEDED(hr) && srpIVsFileChangeEx)  
  
    srpIVsFileChangeEx->IgnoreFile(NULL, m_strMkDocument, FALSE);   
    if(m_srpIVsDocDataFileChangeControl)  
        m_srpIVsDocDataFileChangeControl->IgnoreFileChanges(FALSE);  
    m_fFileChangeSuspended = FALSE;  
    m_srpIVsDocDataFileChangeControl.Release();  
}  
// Misc. helper classes  
```  
  
## <a name="robust-programming"></a>Programação robusta  
 Se o seu caso envolve várias alterações no arquivo, como no caso do SCC, em seguida, é importante retomar as notificações de alteração de arquivo global antes de enviar o alerta de dados de documento para continuar o monitoramento de alterações do arquivo.

