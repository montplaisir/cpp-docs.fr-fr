---
title: Classe de CMFCVisualManagerVS2005 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetDockingTabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetMDITabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetPropertyGridGroupColor
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetTabFrameColors
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawCaptionButton
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawPaneCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawSeparator
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawTab
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawToolBoxFrame
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnEraseTabsArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillHighlightedArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillMiniFrameCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnUpdateSystemColors
dev_langs:
- C++
helpviewer_keywords:
- CMFCVisualManagerVS2005 [MFC], GetDockingTabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetMDITabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetPropertyGridGroupColor
- CMFCVisualManagerVS2005 [MFC], GetTabFrameColors
- CMFCVisualManagerVS2005 [MFC], HasOverlappedAutoHideButtons
- CMFCVisualManagerVS2005 [MFC], OnDrawAutoHideButtonBorder
- CMFCVisualManagerVS2005 [MFC], OnDrawCaptionButton
- CMFCVisualManagerVS2005 [MFC], OnDrawPaneCaption
- CMFCVisualManagerVS2005 [MFC], OnDrawSeparator
- CMFCVisualManagerVS2005 [MFC], OnDrawTab
- CMFCVisualManagerVS2005 [MFC], OnDrawToolBoxFrame
- CMFCVisualManagerVS2005 [MFC], OnEraseTabsArea
- CMFCVisualManagerVS2005 [MFC], OnFillAutoHideButtonBackground
- CMFCVisualManagerVS2005 [MFC], OnFillHighlightedArea
- CMFCVisualManagerVS2005 [MFC], OnFillMiniFrameCaption
- CMFCVisualManagerVS2005 [MFC], OnUpdateSystemColors
ms.assetid: ea39b9ae-327e-4a51-bce7-dc84c78f005b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7282730779360ecc0bb93f0ae827b46ddff19d0
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038059"
---
# <a name="cmfcvisualmanagervs2005-class"></a>Classe de CMFCVisualManagerVS2005
`CMFCVisualManagerVS2005` donne à une application une apparence Microsoft Visual Studio 2005.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCVisualManagerVS2005::GetDockingTabsBordersSize](#getdockingtabsborderssize)|L’infrastructure appelle cette méthode lorsqu’il dessine un volet ancré et à onglets. (Substitue [CMFCVisualManager::GetDockingTabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getdockingtabsborderssize).)|  
|[CMFCVisualManagerVS2005::GetMDITabsBordersSize](#getmditabsborderssize)|L’infrastructure appelle cette méthode pour déterminer la taille de la bordure d’une fenêtre /mditabs avant de dessiner la fenêtre. (Substitue [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize).)|  
|[CMFCVisualManagerVS2005::GetPropertyGridGroupColor](#getpropertygridgroupcolor)|(Substitue [CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#getpropertygridgroupcolor).)|  
|[CMFCVisualManagerVS2005::GetTabFrameColors](#gettabframecolors)|(Substitue [CMFCVisualManagerOffice2003::GetTabFrameColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#gettabframecolors).)|  
|[CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons](#hasoverlappedautohidebuttons)|Retourne si les boutons Masquer automatiquement se chevauchent dans le Gestionnaire visuel actuel. (Substitue [CMFCVisualManager::HasOverlappedAutoHideButtons](../../mfc/reference/cmfcvisualmanager-class.md#hasoverlappedautohidebuttons).)|  
|[CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder](#ondrawautohidebuttonborder)|(Substitue [CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawautohidebuttonborder).)|  
|[CMFCVisualManagerVS2005::OnDrawCaptionButton](#ondrawcaptionbutton)|(Substitue `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`.)|  
|[CMFCVisualManagerVS2005::OnDrawPaneCaption](#ondrawpanecaption)|(Substitue [CMFCVisualManagerOffice2003::OnDrawPaneCaption](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawpanecaption).)|  
|[CMFCVisualManagerVS2005::OnDrawSeparator](#ondrawseparator)|(Substitue [CMFCVisualManagerOffice2003::OnDrawSeparator](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawseparator).)|  
|[CMFCVisualManagerVS2005::OnDrawTab](#ondrawtab)|(Substitue [CMFCVisualManagerOffice2003::OnDrawTab](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawtab).)|  
|[CMFCVisualManagerVS2005::OnDrawToolBoxFrame](#ondrawtoolboxframe)|(Substitue [CMFCVisualManager::OnDrawToolBoxFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawtoolboxframe).)|  
|[CMFCVisualManagerVS2005::OnEraseTabsArea](#onerasetabsarea)|(Substitue [CMFCVisualManagerOffice2003::OnEraseTabsArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onerasetabsarea).)|  
|[CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground](#onfillautohidebuttonbackground)|(Substitue [CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillautohidebuttonbackground).)|  
|[CMFCVisualManagerVS2005::OnFillHighlightedArea](#onfillhighlightedarea)|(Substitue [CMFCVisualManagerOffice2003::OnFillHighlightedArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillhighlightedarea).)|  
|[CMFCVisualManagerVS2005::OnFillMiniFrameCaption](#onfillminiframecaption)|(Substitue `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`.)|  
|[CMFCVisualManagerVS2005::OnUpdateSystemColors](#onupdatesystemcolors)|(Substitue [CMFCVisualManagerOffice2003::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onupdatesystemcolors).)|  
  
## <a name="remarks"></a>Notes  
 La classe CMFCVisualManagerVS2005 vous permet de modifier l’apparence visuelle de votre application pour ressembler à celui de la [!INCLUDE[vsprvsext](../../mfc/reference/includes/vsprvsext_md.md)].  
  
 Tous les membres de cette classe sont des fonctions virtuelles qui sont dérivées de l’ancêtre de cette classe, [CMFCVisualManager classe](../../mfc/reference/cmfcvisualmanager-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le Gestionnaire visuel Visual Studio 2005. Cet extrait de code fait partie de la [exemple de démonstration d’alerte bureau](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagervs2005-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)  
  
 [CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxvisualmanagervs2005.h  
  
##  <a name="getdockingtabsborderssize"></a>  CMFCVisualManagerVS2005::GetDockingTabsBordersSize  

  
```  
virtual int GetDockingTabsBordersSize();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getmditabsborderssize"></a>  CMFCVisualManagerVS2005::GetMDITabsBordersSize  

  
```  
virtual int GetMDITabsBordersSize();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getpropertygridgroupcolor"></a>  CMFCVisualManagerVS2005::GetPropertyGridGroupColor  

  
```  
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *pPropList*  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="gettabframecolors"></a>  CMFCVisualManagerVS2005::GetTabFrameColors  

  
```  
virtual void GetTabFrameColors(
    const CMFCBaseTabCtrl* pTabWnd,  
    COLORREF& clrDark,  
    COLORREF& clrBlack,  
    COLORREF& clrHighlight,  
    COLORREF& clrFace,  
    COLORREF& clrDarkShadow,  
    COLORREF& clrLight,  
    CBrush*& pbrFace,  
    CBrush*& pbrBlack);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *pTabWnd*  
 [in] *clrDark*  
 [in] *clrBlack*  
 [in] *clrHighlight*  
 [in] *clrFace*  
 [in] *clrDarkShadow*  
 [in] *clrLight*  
 [in] *pbrFace*  
 [in] *pbrBlack*  
  
### <a name="remarks"></a>Notes  
  
##  <a name="hasoverlappedautohidebuttons"></a>  CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons  

  
```  
virtual BOOL HasOverlappedAutoHideButtons() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="ondrawautohidebuttonborder"></a>  CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder  

  
```  
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,  
    CRect rectBounds,  
    CRect rectBorderSize,  
    CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *contrôleur de domaine principal*  
 [in] *rectBounds*  
 [in] *rectBorderSize*  
 [in] *pButton*  
  
### <a name="remarks"></a>Notes  
  
##  <a name="ondrawcaptionbutton"></a>  CMFCVisualManagerVS2005::OnDrawCaptionButton  

  
```  
virtual void OnDrawCaptionButton(
    CDC* pDC,  
    CMFCCaptionButton* pButton,  
    BOOL bActive,  
    BOOL bHorz,  
    BOOL bMaximized,  
    BOOL bDisabled,  
    int nImageID = -1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *contrôleur de domaine principal*  
 [in] *pButton*  
 [in] *bActive*  
 [in] *bHorz*  
 [in] *bMaximized*  
 [in] *bDésactiver*  
 [in] *nImageID*  
  
### <a name="remarks"></a>Notes  
  
##  <a name="ondrawpanecaption"></a>  CMFCVisualManagerVS2005::OnDrawPaneCaption  

  
```  
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,  
    CDockablePane* pBar,  
    BOOL bActive,  
    CRect rectCaption,  
    CRect rectButtons);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *contrôleur de domaine principal*  
 [in] *pBar*  
 [in] *bActive*  
 [in] *rectCaption*  
 [in] *rectButtons*  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="ondrawseparator"></a>  CMFCVisualManagerVS2005::OnDrawSeparator  

  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rect,  
    BOOL bIsHoriz);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *contrôleur de domaine principal*  
 [in] *pBar*  
 [in] *rect*  
 [in] *bIsHoriz*  
  
### <a name="remarks"></a>Notes  
  
##  <a name="ondrawtab"></a>  CMFCVisualManagerVS2005::OnDrawTab  

  
```  
virtual void OnDrawTab(
    CDC* pDC,  
    CRect rectTab,  
    int iTab,  
    BOOL bIsActive,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *contrôleur de domaine principal*  
 [in] *rectTab*  
 [in] *iTab*  
 [in] *bIsActive*  
 [in] *pTabWnd*  
  
### <a name="remarks"></a>Notes  
  
##  <a name="ondrawtoolboxframe"></a>  CMFCVisualManagerVS2005::OnDrawToolBoxFrame  

  
```  
virtual void OnDrawToolBoxFrame(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *contrôleur de domaine principal*  
 [in] *rect*  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onerasetabsarea"></a>  CMFCVisualManagerVS2005::OnEraseTabsArea  

  
```  
virtual void OnEraseTabsArea(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *contrôleur de domaine principal*  
 [in] *rect*  
 [in] *pTabWnd*  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onfillautohidebuttonbackground"></a>  CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground  

  
```  
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,  
    CRect rect,  
    CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *contrôleur de domaine principal*  
 [in] *rect*  
 [in] *pButton*  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onfillhighlightedarea"></a>  CMFCVisualManagerVS2005::OnFillHighlightedArea  

  
```  
virtual void OnFillHighlightedArea(
    CDC* pDC,  
    CRect rect,  
    CBrush* pBrush,  
    CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *contrôleur de domaine principal*  
 [in] *rect*  
 [in] *pBrush*  
 [in] *pButton*  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onfillminiframecaption"></a>  CMFCVisualManagerVS2005::OnFillMiniFrameCaption  

  
```  
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,  
    CRect rectCaption,  
    CPaneFrameWnd* pFrameWnd,  
    BOOL bActive);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *contrôleur de domaine principal*  
 [in] *rectCaption*  
 [in] *pFrameWnd*  
 [in] *bActive*  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onupdatesystemcolors"></a>  CMFCVisualManagerVS2005::OnUpdateSystemColors  

  
```  
virtual void OnUpdateSystemColors();
```  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe de CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)   
 [Classe de CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [Classe de CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManagerOffice2003, classe](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)