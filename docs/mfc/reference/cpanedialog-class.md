---
title: Cpanedialog, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
dev_langs:
- C++
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0edc3a255d3778711b2b8e74bde448dc34c814c
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849086"
---
# <a name="cpanedialog-class"></a>Cpanedialog, classe
Le `CPaneDialog` classe prend en charge une boîte de dialogue non modale et Ancrable.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CPaneDialog::CPaneDialog`|Constructeur par défaut.|  
|`CPaneDialog::~CPaneDialog`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CPaneDialog::Create](#create)|Crée une boîte de dialogue « dockable » et l’attache à un `CPaneDialog` objet.|  
|`CPaneDialog::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CPaneDialog::GetThisClass`|Utilisé par l’infrastructure pour obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet qui est associé à ce type de classe.|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|Gère la [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) message. (Redéfinit `CBasePane::HandleInitDialog`.)|  
|`CPaneDialog::OnEraseBkgnd`|Gère la [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) message. (Redéfinit [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|  
|`CPaneDialog::OnLButtonDblClk`|Gère la [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) message. (Redéfinit [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|  
|`CPaneDialog::OnLButtonDown`|Gère la [WM_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) message. (Redéfinit [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|  
|`CPaneDialog::OnUpdateCmdUI`|Appelé par l’infrastructure pour mettre à jour de la fenêtre de boîte de dialogue. (Substitue [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/5dd61606-1c12-40d4-b024-f3839aa5e2e0).)|  
|`CPaneDialog::OnWindowPosChanging`|Gère la [WM_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) message. (Redéfinit [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|Spécifie le modèle pour une boîte de dialogue est un conteneur de contrôle OLE.|  
  
## <a name="remarks"></a>Notes  
 Construire un `CPaneDialog` objet en deux étapes. Tout d’abord, construisez l’objet dans votre code. Ensuite, appelez [CPaneDialog::Create](#create). Vous devez spécifier un ID de nom ou du modèle modèle de ressource valide et passer un pointeur vers la fenêtre parente. Sinon, le processus de création échoue. La boîte de dialogue doit spécifier le style WS_CHILD et WS_VISIBLE. Nous vous recommandons d’également spécifier les styles WS_CLIPCHILDREN et WS_CLIPSIBLINGS. Pour plus d’informations, consultez [Styles de fenêtre](styles-used-by-mfc.md#window-styles).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxpanedialog.h  
  
##  <a name="create"></a>  CPaneDialog::Create  
 Crée une boîte de dialogue d’ancrage et l’attache à un `CPaneDialog` objet.  
  
```  
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID,  
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

 
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *lpszWindowName*  
 Le nom de la boîte de dialogue d’accueil.  
  
 [in] *pParentWnd*  
 Pointe vers la fenêtre parente.  
  
 [in] *bHasGripper*  
 TRUE pour créer la boîte de dialogue d’ancrage avec une légende (barre de redimensionnement) ; Sinon, FALSE.  
  
 [in] *lpszTemplateName*  
 Le nom du modèle de boîte de dialogue de ressource.  
  
 [in] *nStyle*  
 Le style Windows.  
  
 [in] *nID*  
 L’ID du contrôle.  
  
 [in] *nIDTemplate*  
 L’ID de ressource du modèle de boîte de dialogue.  
  
 [in] *dwTabbedStyle*  
 Le style de la fenêtre à onglets qui se produit lorsque l’utilisateur fait glisser un autre volet de contrôle sur la légende du volet de ce contrôle. La valeur par défaut est AFX_CBRS_REGULAR_TABS. Pour plus d’informations, consultez la section Notes de la [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) (méthode).  
  
 [in] *dwControlBarStyle*  
 Attributs de style supplémentaires. La valeur par défaut est AFX_DEFAULT_DOCKING_PANE_STYLE. Pour plus d’informations, consultez la section Notes de la [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) (méthode).  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si cette méthode réussit ; Sinon, FALSE.  
  
### <a name="remarks"></a>Notes  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le `Create` méthode dans la `CPaneDialog` classe. Cet exemple fait partie de la [exemple de définir la taille du volet](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]  
  
##  <a name="handleinitdialog"></a>  CPaneDialog::HandleInitDialog  
 Gère la [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) message.  
  
```  
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *wParam*  
 Handle sur le contrôle qui doit recevoir le focus du clavier par défaut.  
  
 [in] *lParam*  
 Spécifie les données d’initialisation supplémentaires.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si cette méthode a réussi ; Sinon, FALSE. En outre, la valeur TRUE définit le focus clavier au contrôle spécifié par le *wParam* paramètre ; FALSE empêche de définir le focus du clavier par défaut.  
  
### <a name="remarks"></a>Notes  
 Le framework utilise cette méthode pour initialiser les contrôles et l’apparence d’une boîte de dialogue. L’infrastructure appelle cette méthode avant d’afficher la boîte de dialogue.  
  
##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo  
 Spécifie le modèle pour une boîte de dialogue est un conteneur de contrôle OLE.  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *pOccDialogInfo*  
 Pointeur vers un modèle de boîte de dialogue qui permet de créer l’objet de boîte de dialogue. La valeur de ce paramètre est passée par la suite dans le [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) (méthode).  
  
### <a name="return-value"></a>Valeur de retour  
 Toujours TRUE.  
  
### <a name="remarks"></a>Notes  
 Cette méthode prend en charge la [COccManager](../../mfc/reference/coccmanager-class.md) (classe), qui gère les contrôles ActiveX et les sites de contrôle OLE. La structure _AFX_OCC_DIALOG_INFO est définie dans le fichier d’en-tête afxocc.h.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CDockablePane, classe](../../mfc/reference/cdockablepane-class.md)   
 [Styles de fenêtre](../../mfc/reference/styles-used-by-mfc.md#window-styles)



