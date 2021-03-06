---
title: Cmfccaptionbutton, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 356aa3448c3912c1842d5e04c697fc86fc9714c0
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338397"
---
# <a name="cmfccaptionbutton-class"></a>Cmfccaptionbutton, classe
Le `CMFCCaptionButton` classe implémente un bouton qui s’affiche sur la barre de légende pour un volet d’ancrage ou une fenêtre mini-frame. En général, l'infrastructure crée les boutons de légende automatiquement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="constructors"></a>Constructeurs  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|Construit un objet CMFCCaptionButton.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|Retourne la commande représentée par le bouton.|  
|[CMFCCaptionButton::GetIconID](#geticonid)|Retourne l’ID de l’image associée au bouton.|  
|[CMFCCaptionButton::GetRect](#getrect)|Retourne le rectangle occupé par le bouton.|  
|[CMFCCaptionButton::GetSize](#getsize)|Retourne la largeur et la hauteur du bouton.|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Indique si la hauteur de barre de titre est définie à une taille miniature.|  
|[CMFCCaptionButton::Move](#move)|Définit l’emplacement du bouton de dessin et afficher l’état fenêtre.|  
|[CMFCCaptionButton::OnDraw](#ondraw)|Dessine le bouton de légende.|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Définit la taille miniature de la barre de titre.|  
  
## <a name="remarks"></a>Notes  
 Vous pouvez dériver une classe à partir de [cpaneframewnd, classe](../../mfc/reference/cpaneframewnd-class.md) et utiliser la méthode protégée, `AddButton`, pour ajouter des boutons de légende à une fenêtre frame mini.  
  
 CPaneFrameWnd.h définit l’ID de commande pour les deux types de boutons de légende :  
  
- AFX_CAPTION_BTN_PIN, qui affiche un bouton de code confidentiel lorsque le volet d’ancrage prend en charge le mode de masquage automatique.  
  
- AFX_CAPTION_BTN_CLOSE, qui affiche un **fermer** bouton lorsque le volet peut être fermé ou masqué.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un `CMFCCaptionButton` de l’objet et définissez la taille miniature de la barre de titre.  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxcaptionbutton.h  
  
##  <a name="cmfccaptionbutton"></a>  CMFCCaptionButton::CMFCCaptionButton  
 Construit un objet `CMFCCaptionButton`.  
  
```  
CMFCCaptionButton();

 
CMFCCaptionButton(
    UINT nHit,  
    BOOL bLeftAlign = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *nHit*  
 La commande associée au bouton.  
  
 [in] *bLeftAlign*  
 Spécifie si le bouton est aligné à gauche.  
  
 Le tableau suivant répertorie les valeurs possibles pour le *nHit* paramètre.  
  
|Value|Commande|  
|-----------|-------------|  
|AFX_HTCLOSE|Bouton Fermer.|  
|HTMINBUTTON|Bouton de réduction.|  
|HTMAXBUTTON|Bouton Agrandir.|  
|AFX_HTLEFTBUTTON|Bouton de flèche gauche.|  
|AFX_HTRIGHTBUTTON|Bouton de flèche droite.|  
|AFX_HTMENU|Le bouton de menu de flèche.|  
|HTNOWHERE|La valeur par défaut ; ne représente un aucun commande.|  
  
### <a name="remarks"></a>Notes  
 Par défaut, les boutons de légende ne sont pas associés à une commande.  
  
 Boutons de légende sont alignés sur la droite ou gauche.  
  
##  <a name="gethit"></a>  CMFCCaptionButton::GetHit  
 Retourne la commande représentée par le bouton.  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La commande représentée par le bouton.  
  
 Le tableau suivant répertorie les valeurs de retour possibles.  
  
|Value|Commande|  
|-----------|-------------|  
|AFX_HTCLOSE|Bouton Fermer.|  
|HTMINBUTTON|Bouton de réduction.|  
|HTMAXBUTTON|Bouton Agrandir.|  
|AFX_HTLEFTBUTTON|Bouton de flèche gauche.|  
|AFX_HTRIGHTBUTTON|Bouton de flèche droite.|  
|AFX_HTMENU|Le bouton de menu de flèche.|  
|HTNOWHERE|La valeur par défaut ; ne représente un aucun commande.|  
  
##  <a name="geticonid"></a>  CMFCCaptionButton::GetIconID  
 Retourne l’ID de l’image associée au bouton.  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *bHorz*  
 TRUE pour une image de flèche gauche ou droite ID ; FALSE pour monter ou Descendre les identifiants d’images de flèche.  
  
 [in] *bMaximized*  
 TRUE pour un ID d’image agrandir ; FALSE pour un ID d’image de réduire.  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de l’image.  
  
### <a name="remarks"></a>Notes  
 Les paramètres de spécifient l’ID d’image pour réduire ou agrandir des boutons de légende.  
  
##  <a name="getrect"></a>  CMFCCaptionButton::GetRect  
 Retourne le rectangle occupé par le bouton.  
  
```  
virtual CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le rectangle qui représente l’emplacement du bouton.  
  
### <a name="remarks"></a>Notes  
 Si vous ne voyez pas le bouton, la taille retournée est 0.  
  
##  <a name="getsize"></a>  CMFCCaptionButton::GetSize  
 Retourne la largeur et la hauteur du bouton.  
  
```  
static CSize GetSize();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les dimensions externes du bouton.  
  
### <a name="remarks"></a>Notes  
 La taille retournée inclut des bordures et des marges du bouton.  
  
##  <a name="isminiframebutton"></a>  CMFCCaptionButton::IsMiniFrameButton  
 Indique si la hauteur de barre de titre est définie à une taille miniature.  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la légende est définie sur la taille mini ; Sinon, FALSE.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="move"></a>  CMFCCaptionButton::Move  
 Définit l’emplacement du bouton de dessin et afficher l’état fenêtre.  
  
```  
void Move(
    const CPoint& ptTo,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *ptTo*  
 Nouvel emplacement.  
  
 [in] *bHide*  
 Si vous souhaitez afficher le bouton.  
  
##  <a name="ondraw"></a>  CMFCCaptionButton::OnDraw  
 Dessine le bouton de légende.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    BOOL bActive,  
    BOOL bHorz = TRUE,  
    BOOL bMaximized = TRUE,  
    BOOL bDisabled = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *pDC*  
 Pointeur vers un contexte de périphérique pour le bouton.  
  
 [in] *bActive*  
 Si vous souhaitez dessiner une image de bouton actif.  
  
 [in] *bHorz*  
 Réservé pour une utilisation dans une classe dérivée.  
  
 [in] *bMaximized*  
 Si vous souhaitez dessiner une image du bouton agrandie.  
  
 [in] *bDésactivé*  
 Si vous souhaitez dessiner une image de bouton activé.  
  
### <a name="remarks"></a>Notes  
 Le *bMaximized* paramètre est utilisé lorsque le bouton est un agrandir ou réduire le bouton.  
  
##  <a name="setminiframebutton"></a>  CMFCCaptionButton::SetMiniFrameButton  
 Définit la taille miniature de la barre de titre.  
  
```  
void SetMiniFramebutton(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] *bSet*  
 TRUE pour la hauteur de barre de titre mini ; Si la valeur est FALSE, hauteur par défaut de la barre de titre.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Cpaneframewnd, classe](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane, classe](../../mfc/reference/cdockablepane-class.md)
