---
title: CReBarCtrl, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
dev_langs:
- C++
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37bd71ae328af76a01106d2efe6cd3945ddb25b9
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853535"
---
# <a name="crebarctrl-class"></a>CReBarCtrl (classe)
Encapsule les fonctionnalités d'un contrôle rebar, qui est un conteneur de fenêtre enfant.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|Construit un objet `CReBarCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CReBarCtrl::BeginDrag](#begindrag)|Place le contrôle rebar en mode de glisser-déplacer.|  
|[CReBarCtrl::Create](#create)|Crée le contrôle rebar et l’attache à la `CReBarCtrl` objet.|  
|[CReBarCtrl::CreateEx](#createex)|Crée un contrôle rebar avec les styles étendus Windows spécifiés et l’attache à un `CReBarCtrl` objet.|  
|[CReBarCtrl::DeleteBand](#deleteband)|Supprime une bande d’un contrôle rebar.|  
|[CReBarCtrl::DragMove](#dragmove)|Met à jour la position de glissement dans le contrôle rebar après un appel à `BeginDrag`.|  
|[CReBarCtrl::EndDrag](#enddrag)|Termine l’opération de glisser-déplacer du contrôle rebar.|  
|[CReBarCtrl::GetBandBorders](#getbandborders)|Récupère les bordures d’une bande.|  
|[CReBarCtrl::GetBandCount](#getbandcount)|Récupère le nombre de bandes actuellement dans le contrôle rebar.|  
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Récupère des informations sur une bande spécifiée dans un contrôle rebar.|  
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Récupère les marges d’une bande.|  
|[CReBarCtrl::GetBarHeight](#getbarheight)|Récupère la hauteur du contrôle rebar.|  
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Récupère des informations sur le contrôle rebar et il utilise la liste d’images.|  
|[CReBarCtrl::GetBkColor](#getbkcolor)|Récupère la couleur d’arrière-plan par défaut d’un contrôle rebar.|  
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Récupère le [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) structure associé au contrôle rebar.|  
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Récupère un contrôle rebar `IDropTarget` pointeur d’interface.|  
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Obtient le style étendu du contrôle rebar actuel.|  
|[CReBarCtrl::GetImageList](#getimagelist)|Récupère la liste d’images associée à un contrôle rebar.|  
|[CReBarCtrl::GetPalette](#getpalette)|Récupère la palette actuelle du contrôle rebar.|  
|[CReBarCtrl::GetRect](#getrect)|Récupère le rectangle englobant d’une bande de donnée dans un contrôle rebar.|  
|[CReBarCtrl::GetRowCount](#getrowcount)|Récupère le nombre de lignes de bandes dans un contrôle rebar.|  
|[CReBarCtrl::GetRowHeight](#getrowheight)|Récupère la hauteur d’une ligne spécifiée dans un contrôle rebar.|  
|[CReBarCtrl::GetTextColor](#gettextcolor)|Récupère la couleur du texte par défaut d’un contrôle rebar.|  
|[CReBarCtrl::GetToolTips](#gettooltips)|Récupère le handle à n’importe quel contrôle info-bulle associé au contrôle rebar.|  
|[CReBarCtrl::HitTest](#hittest)|Détermine quelle partie d’une bande rebar est à un moment donné dans l’écran, si une bande rebar existe à ce stade.|  
|[CReBarCtrl::IDToIndex](#idtoindex)|Convertit un identificateur (ID) de la bande vers un index de la bande dans un contrôle rebar.|  
|[CReBarCtrl::InsertBand](#insertband)|Insère une nouvelle bande dans un contrôle rebar.|  
|[CReBarCtrl::MaximizeBand](#maximizeband)|Redimensionne une bande dans un contrôle rebar à sa taille maximale.|  
|[CReBarCtrl::MinimizeBand](#minimizeband)|Redimensionne une bande dans un contrôle rebar à sa taille plus petite.|  
|[CReBarCtrl::MoveBand](#moveband)|Déplace une bande d’un index vers un autre.|  
|[CReBarCtrl::PushChevron](#pushchevron)|Exécute un push d’un chevron par programmation.|  
|[CReBarCtrl::RestoreBand](#restoreband)|Redimensionne une bande dans un contrôle rebar à sa taille idéale.|  
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Définit les caractéristiques d’une bande existante dans un contrôle rebar.|  
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Définit la largeur de la bande spécifiée ancrée dans le contrôle rebar en cours.|  
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Définit les caractéristiques d’un contrôle rebar.|  
|[CReBarCtrl::SetBkColor](#setbkcolor)|Définit la couleur d’arrière-plan par défaut d’un contrôle rebar.|  
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Définit le jeu de couleurs pour les boutons sur un contrôle rebar.|  
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Définit les styles étendus pour le contrôle rebar actuel.|  
|[CReBarCtrl::SetImageList](#setimagelist)|Définit la liste d’images d’un contrôle rebar.|  
|[CReBarCtrl::SetOwner](#setowner)|Définit la fenêtre de propriétaire d’un contrôle rebar.|  
|[CReBarCtrl::SetPalette](#setpalette)|Définit la palette actuelle du contrôle rebar.|  
|[CReBarCtrl::SetTextColor](#settextcolor)|Définit la couleur du texte par défaut d’un contrôle rebar.|  
|[CReBarCtrl::SetToolTips](#settooltips)|Associe un contrôle info-bulle du contrôle rebar.|  
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Définit le style visuel du contrôle rebar.|  
|[CReBarCtrl::ShowBand](#showband)|Affiche ou masque une bande de donnée dans un contrôle rebar.|  
|[CReBarCtrl::SizeToRect](#sizetorect)|Correspond à un contrôle rebar à un rectangle spécifié.|  
  
## <a name="remarks"></a>Notes  
 L’application dans laquelle réside le contrôle rebar affecte la fenêtre enfant contenue par le contrôle rebar à la bande rebar. La fenêtre enfant est généralement un autre contrôle commun.  
  
 Les contrôles rebar contiennent une ou plusieurs bandes. Chaque bande peut contenir une combinaison d’une barre de redimensionnement, une image bitmap, une étiquette de texte et une fenêtre enfant. La bande peut contenir qu’un seul de ces éléments.  
  
 Le contrôle rebar peut afficher la fenêtre enfant sur une image bitmap d’arrière-plan spécifiée. Toutes les bandes du contrôle rebar peuvent être redimensionnées à l’exception de celles qui utilisent le style RBBS_FIXEDSIZE. Lorsque vous repositionnez ou que vous redimensionnez une bande de contrôle rebar, le contrôle rebar gère la taille et la position de la fenêtre enfant affectée à cette bande. Pour redimensionner ou modifier l’ordre des bandes dans le contrôle, cliquez et faites glisser la barre de redimensionnement d’une bande.  
  
 L’illustration suivante montre un contrôle rebar qui a trois bandes :  
  
-   Bande 0 contienne un contrôle de barre d’outils plate et transparente.  
  
-   Bande 1 contient les deux boutons transparent déroulante standard et transparente.  
  
-   Bande 2 contient une zone de liste déroulante et quatre boutons standards.  
  
     ![Exemple d’un menu Rebar](../../mfc/reference/media/vc4scc1.gif "vc4scc1")  
  
## <a name="rebar-control"></a>Contrôle rebar  
 Prise en charge des contrôles de barre :  
  
-   Listes d’images.  
  
-   Gestion des messages.  
  
-   Fonctionnalités de dessin personnalisé.  
  
-   De nombreux styles de contrôle en plus de styles de fenêtre standard. Pour obtenir la liste de ces styles, consultez [Styles de contrôle Rebar](http://msdn.microsoft.com/library/windows/desktop/bb774377) dans le SDK Windows.  
  
 Pour plus d’informations, consultez [à l’aide de CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxcmn.h  
  
##  <a name="begindrag"></a>  CReBarCtrl::BeginDrag  
 Implémente le comportement du message Win32 [RB_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774429), comme décrit dans le SDK Windows.  
  
```  
void BeginDrag(
    UINT uBand,  
    DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro de la bande qui affecte l’opération de glisser-déplacer.  
  
 *dwPos*  
 Une valeur DWORD qui contient le démarrage de coordonnées de la souris. La coordonnée horizontale est contenue dans le LOWORD et la coordonnée verticale est contenue dans le HIWORD. Si vous passez (DWORD) -1, le contrôle rebar utilise la position de la souris sur la dernière fois où le thread du contrôle appelé `GetMessage` ou `PeekMessage`.  
  
##  <a name="create"></a>  CReBarCtrl::Create  
 Crée le contrôle rebar et l’attache à la `CReBarCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwStyle*  
 Spécifie la combinaison de styles de contrôle rebar appliqué au contrôle. Consultez [Styles de contrôle Rebar](http://msdn.microsoft.com/library/windows/desktop/bb774377) dans le SDK Windows pour obtenir la liste des styles pris en charge.  
  
 *Rect*  
 Une référence à un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure, qui est la position et la taille du contrôle rebar.  
  
 *pParentWnd*  
 Un pointeur vers un [CWnd](../../mfc/reference/cwnd-class.md) objet qui est la fenêtre parente du contrôle rebar. Il ne doit pas être NULL.  
  
 *nID*  
 Spécifie l’ID de contrôle. du contrôle rebar  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet a été créé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Créer un contrôle rebar en deux étapes :  
  
1.  Appelez [CReBarCtrl](#crebarctrl) pour construire un `CReBarCtrl` objet.  
  
2.  Appelez cette fonction membre, ce qui crée le contrôle rebar de Windows et l’attache à la `CReBarCtrl` objet.  
  
 Lorsque vous appelez `Create`, les contrôles communs sont initialisés.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CReBarCtrl::CreateEx  
 Crée un contrôle (une fenêtre enfant) et l’associe le `CReBarCtrl` objet.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwExStyle*  
 Spécifie le style étendu du contrôle en cours de création. Pour obtenir la liste des styles étendus de Windows, consultez le *dwExStyle* paramètre pour [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) dans le SDK Windows.  
  
 *dwStyle*  
 Spécifie la combinaison de styles de contrôle rebar appliqué au contrôle. Pour obtenir la liste des styles pris en charge, consultez [Styles de contrôle Rebar](http://msdn.microsoft.com/library/windows/desktop/bb774377) dans le SDK Windows.  
  
 *Rect*  
 Une référence à un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure décrivant la taille et la position de la fenêtre doit être créée, dans les coordonnées clientes de *pParentWnd*.  
  
 *pParentWnd*  
 Pointeur vers la fenêtre qui est le parent du contrôle.  
  
 *nID*  
 ID de fenêtre enfant. du contrôle  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Utilisez `CreateEx` au lieu de [créer](#create) pour appliquer des styles étendus de Windows, spécifiés par la préface de style étendu Windows **WS_EX_**.  
  
##  <a name="crebarctrl"></a>  CReBarCtrl::CReBarCtrl  
 Crée un objet `CReBarCtrl`.  
  
```  
CReBarCtrl();
```  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CReBarCtrl::Create](#create).  
  
##  <a name="deleteband"></a>  CReBarCtrl::DeleteBand  
 Implémente le comportement du message Win32 [RB_DELETEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774431), comme décrit dans le SDK Windows.  
  
```  
BOOL DeleteBand(UINT uBand);
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro de la bande doit être supprimé.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la bande a été supprimé avec succès ; Sinon, zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]  
  
##  <a name="dragmove"></a>  CReBarCtrl::DragMove  
 Implémente le comportement du message Win32 [RB_DRAGMOVE](https://msdn.microsoft.com/library/bb774433.aspx), comme décrit dans le SDK Windows.  
  
```  
void DragMove(DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwPos*  
 Une valeur DWORD qui contient les nouvelles coordonnées de la souris. La coordonnée horizontale est contenue dans le LOWORD et la coordonnée verticale est contenue dans le HIWORD. Si vous passez (DWORD) -1, le contrôle rebar utilise la position de la souris sur la dernière fois où le thread du contrôle appelé `GetMessage` ou `PeekMessage`.  
  
##  <a name="enddrag"></a>  CReBarCtrl::EndDrag  
 Implémente le comportement du message Win32 [RB_ENDDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774435), comme décrit dans le SDK Windows.  
  
```  
void EndDrag();
```  
  
##  <a name="getbandborders"></a>  CReBarCtrl::GetBandBorders  
 Implémente le comportement du message Win32 [RB_GETBANDBORDERS](http://msdn.microsoft.com/library/windows/desktop/bb774437), comme décrit dans le SDK Windows.  
  
```  
void GetBandBorders(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro de la bande pour laquelle les bordures sont récupérées.  
  
 *République populaire de Chine*  
 Un pointeur vers un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure qui recevra les bordures de bande. Si le contrôle rebar a le style RBS_BANDBORDERS, chaque membre de cette structure reçoit le nombre de pixels, dans la partie correspondante de la bande, qui constituent la bordure. Si le contrôle rebar n’a pas le style RBS_BANDBORDERS, seul le membre gauche de cette structure reçoit des informations valides. Pour obtenir une description des styles de contrôle rebar, consultez [Styles de contrôle Rebar](http://msdn.microsoft.com/library/windows/desktop/bb774377) dans le SDK Windows.  
  
##  <a name="getbandcount"></a>  CReBarCtrl::GetBandCount  
 Implémente le comportement du message Win32 [RB_GETBANDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774439), comme décrit dans le SDK Windows.  
  
```  
UINT GetBandCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de bandes assigné au contrôle.  
  
##  <a name="getbandinfo"></a>  CReBarCtrl::GetBandInfo  
 Implémente le comportement du message Win32 [RB_GETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774451) comme décrit dans le SDK Windows.  
  
```  
BOOL GetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro de la bande pour lequel les informations seront récupérées.  
  
 *prbbi*  
 Un pointeur vers un [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) structure qui doit recevoir les informations de la bande. Vous devez définir le `cbSize` membre de cette structure à `sizeof(REBARBANDINFO)` et définir le `fMask` membre pour les éléments que vous souhaitez récupérer avant d’envoyer ce message.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="getbandmargins"></a>  CReBarCtrl::GetBandMargins  
 Récupère les marges de la bande.  
  
```  
void GetBandMargins(PMARGINS pMargins);
```  
  
### <a name="parameters"></a>Paramètres  
 *pMargins*  
 Un pointeur vers un [marges](http://msdn.microsoft.com/library/windows/desktop/bb773244)structure qui recevra les informations.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre émule la fonctionnalité de la [RB_GETBANDMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb774453) du message, comme décrit dans le SDK Windows.  
  
##  <a name="getbarheight"></a>  CReBarCtrl::GetBarHeight  
 Récupère la hauteur de la barre de contrôle rebar.  
  
```  
UINT GetBarHeight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur qui représente la hauteur, en pixels, du contrôle.  
  
##  <a name="getbarinfo"></a>  CReBarCtrl::GetBarInfo  
 Implémente le comportement du message Win32 [RB_GETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774457), comme décrit dans le SDK Windows.  
  
```  
BOOL GetBarInfo(REBARINFO* prbi) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *prbi*  
 Un pointeur vers un [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) structure qui recevra les informations de contrôle rebar. Vous devez définir le *cbSize* membre de cette structure à `sizeof(REBARINFO)` avant d’envoyer ce message.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="getbkcolor"></a>  CReBarCtrl::GetBkColor  
 Implémente le comportement du message Win32 [RB_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774459), comme décrit dans le SDK Windows.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur COLORREF qui représentent la couleur d’arrière-plan par défaut actuelle.  
  
##  <a name="getcolorscheme"></a>  CReBarCtrl::GetColorScheme  
 Récupère le [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) structure pour le contrôle rebar.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Paramètres  
 *Procedure Calls, LPC*  
 Un pointeur vers un [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) structure, comme décrit dans le SDK Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Le `COLORSCHEME` structure inclut la couleur de surbrillance du bouton et la couleur de l’ombre.  
  
##  <a name="getdroptarget"></a>  CReBarCtrl::GetDropTarget  
 Implémente le comportement du message Win32 [RB_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb774463), comme décrit dans le SDK Windows.  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) interface.  
  
##  <a name="getextendedstyle"></a>  CReBarCtrl::GetExtendedStyle  
 Obtient les styles étendus du contrôle rebar actuel.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une combinaison (OR) au niveau du bit des indicateurs qui indiquent les styles étendus. Les indicateurs possibles sont RBS_EX_SPLITTER et RBS_EX_TRANSPARENT. Pour plus d’informations, consultez le *dwMask* paramètre de la [CReBarCtrl::SetExtendedStyle](#setextendedstyle) (méthode).  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [RB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774433) message, qui est décrite dans le SDK Windows.  
  
##  <a name="getimagelist"></a>  CReBarCtrl::GetImageList  
 Obtient le `CImageList` objet associé à un contrôle rebar.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet. Retourne NULL si aucune liste d’images n’est définie pour le contrôle.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre utilise la taille et masque les informations stockées dans le [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) structure, comme décrit dans le SDK Windows.  
  
##  <a name="getpalette"></a>  CReBarCtrl::GetPalette  
 Récupère la palette actuelle du contrôle rebar.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CPalette](../../mfc/reference/cpalette-class.md) objet qui spécifie la palette actuelle du contrôle rebar.  
  
### <a name="remarks"></a>Notes  
 Notez que cette fonction membre utilise un `CPalette` objet comme sa valeur de retour, plutôt qu’un HPALETTE.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]  
  
##  <a name="getrect"></a>  CReBarCtrl::GetRect  
 Implémente le comportement du message Win32 [RB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb774469), comme décrit dans le SDK Windows.  
  
```  
BOOL GetRect(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro d’une bande dans le contrôle rebar.  
  
 *République populaire de Chine*  
 Un pointeur vers un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure qui recevra les limites de la bande rebar.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]  
  
##  <a name="getrowcount"></a>  CReBarCtrl::GetRowCount  
 Implémente le comportement du message Win32 [RB_GETROWCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774471), comme décrit dans le SDK Windows.  
  
```  
UINT GetRowCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur UINT qui représente le nombre de lignes de bandes dans le contrôle.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]  
  
##  <a name="getrowheight"></a>  CReBarCtrl::GetRowHeight  
 Implémente le comportement du message Win32 [RB_GETROWHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb774473), comme décrit dans le SDK Windows.  
  
```  
UINT GetRowHeight(UINT uRow) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *uRow*  
 Index de base zéro de la bande qui aura sa hauteur récupérée.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur UINT qui représente la hauteur de ligne, en pixels.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]  
  
##  <a name="gettextcolor"></a>  CReBarCtrl::GetTextColor  
 Implémente le comportement du message Win32 [RB_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774475), comme décrit dans le SDK Windows.  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur COLORREF qui représentent la couleur de texte par défaut actuelle.  
  
##  <a name="gettooltips"></a>  CReBarCtrl::GetToolTips  
 Implémente le comportement du message Win32 [RB_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb774477), comme décrit dans le SDK Windows.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) objet.  
  
### <a name="remarks"></a>Notes  
 Notez que l’implémentation MFC de `GetToolTips` retourne un pointeur vers un `CToolTipCtrl`, au lieu d’un HWND.  
  
##  <a name="hittest"></a>  CReBarCtrl::HitTest  
 Implémente le comportement du message Win32 [RB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb774494), comme décrit dans le SDK Windows.  
  
```  
int HitTest(RBHITTESTINFO* prbht);
```  
  
### <a name="parameters"></a>Paramètres  
 *prbht*  
 Un pointeur vers un [RBHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb774391) structure. Avant d’envoyer le message, le `pt` membre de cette structure doit être initialisé sur le point qui va être testé dans les coordonnées clientes.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de la bande sur le point donné, ou -1 si aucune bande rebar a été au point.  
  
##  <a name="idtoindex"></a>  CReBarCtrl::IDToIndex  
 Implémente le comportement du message Win32 [RB_IDTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774496), comme décrit dans le SDK Windows.  
  
```  
int IDToIndex(UINT uBandID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *uBandID*  
 L’identificateur défini par l’application de la bande spécifiée, passée dans le `wID` membre de la [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) structure lors de la bande est insérée.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index de base zéro de bande en cas de réussite, ou sinon -1. Si l’index de la bande en double existe, la première est renvoyée.  
  
##  <a name="insertband"></a>  CReBarCtrl::InsertBand  
 Implémente le comportement du message Win32 [RB_INSERTBAND](http://msdn.microsoft.com/library/windows/desktop/bb774498), comme décrit dans le SDK Windows.  
  
```  
BOOL InsertBand(
    UINT uIndex,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Paramètres  
 *uIndex*  
 Index de base zéro de l’emplacement où la bande sera insérée. Si vous définissez ce paramètre sur -1, le contrôle ajoute au dernier emplacement de la nouvelle bande.  
  
 *prbbi*  
 Un pointeur vers un [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) structure qui définit la bande doit être inséré. Vous devez définir le *cbSize* membre de cette structure à `sizeof(REBARBANDINFO)` avant d’appeler cette fonction.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]  
  
##  <a name="maximizeband"></a>  CReBarCtrl::MaximizeBand  
 Redimensionne une bande dans un contrôle rebar à sa taille maximale.  
  
```  
void MaximizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro de la bande à être agrandi.  
  
### <a name="remarks"></a>Notes  
 Implémente le comportement du message Win32 [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) avec `fIdeal` définie sur 0, comme décrit dans le SDK Windows.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]  
  
##  <a name="minimizeband"></a>  CReBarCtrl::MinimizeBand  
 Redimensionne une bande dans un contrôle rebar à sa taille plus petite.  
  
```  
void MinimizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro de la bande soit réduite.  
  
### <a name="remarks"></a>Notes  
 Implémente le comportement du message Win32 [RB_MINIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774502), comme décrit dans le SDK Windows.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]  
  
##  <a name="moveband"></a>  CReBarCtrl::MoveBand  
 Implémente le comportement du message Win32 [RB_MOVEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774504), comme décrit dans le SDK Windows.  
  
```  
BOOL MoveBand(
    UINT uFrom,  
    UINT uTo);
```  
  
### <a name="parameters"></a>Paramètres  
 *uFrom*  
 Index de base zéro de la bande à déplacer.  
  
 *auto.*  
 Index de base zéro de la nouvelle position de la bande. Cette valeur de paramètre ne doit jamais être supérieure au nombre de bandes moins 1. Pour obtenir le nombre de bandes, appelez [GetBandCount](#getbandcount).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="pushchevron"></a>  CReBarCtrl::PushChevron  
 Implémente le comportement du message Win32 [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506), comme décrit dans le SDK Windows.  
  
```  
void PushChevron(
    UINT uBand,  
    LPARAM lAppValue);
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro de la bande dont chevron doit être envoyée.  
  
 *lAppValue*  
 Une application définie la valeur 32 bits. Consultez *lAppValue* dans [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506) dans le SDK Windows.  
  
##  <a name="restoreband"></a>  CReBarCtrl::RestoreBand  
 Redimensionne une bande dans un contrôle rebar à sa taille idéale.  
  
```  
void RestoreBand(UINT uBand);
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro de la bande à être agrandi.  
  
### <a name="remarks"></a>Notes  
 Implémente le comportement du message Win32 [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) avec `fIdeal` défini sur 1, comme décrit dans le SDK Windows.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]  
  
##  <a name="setbandinfo"></a>  CReBarCtrl::SetBandInfo  
 Implémente le comportement du message Win32 [RB_SETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774508), comme décrit dans le SDK Windows.  
  
```  
BOOL SetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro de la bande de recevoir les nouveaux paramètres.  
  
 *prbbi*  
 Pointeur vers un [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) structure qui définit la bande doit être inséré. Vous devez définir le `cbSize` membre de cette structure à `sizeof(REBARBANDINFO)` avant d’envoyer ce message.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]  
  
##  <a name="setbandwidth"></a>  CReBarCtrl::SetBandWidth  
 Définit la largeur de la bande spécifiée ancrée dans le contrôle rebar en cours.  
  
```  
BOOL SetBandWidth(
    UINT uBand,   
    int cxWidth);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] *uBand*|Index de base zéro d’une bande rebar.|  
|[in] *cxWidth*|Nouvelle largeur de la bande rebar, en pixels.|  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la méthode a réussi ; Sinon, FALSE.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [RB_SETBANDWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb774511) message, qui est décrite dans le SDK Windows.  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_rebar`, qui est utilisé pour accéder au contrôle rebar en cours. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit chaque bande rebar est la même largeur.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]  
  
##  <a name="setbarinfo"></a>  CReBarCtrl::SetBarInfo  
 Implémente le comportement du message Win32 [RB_SETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774513), comme décrit dans le SDK Windows.  
  
```  
BOOL SetBarInfo(REBARINFO* prbi);
```  
  
### <a name="parameters"></a>Paramètres  
 *prbi*  
 Un pointeur vers un [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) structure qui contient les informations à définir. Vous devez définir le `cbSize` membre de cette structure à `sizeof(REBARINFO)` avant d’envoyer ce message  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]  
  
##  <a name="setbkcolor"></a>  CReBarCtrl::SetBkColor  
 Implémente le comportement du message Win32 [RB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774515), comme décrit dans le SDK Windows.  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Paramètres  
 *CLR*  
 La valeur COLORREF qui représente la nouvelle couleur d’arrière-plan par défaut.  
  
### <a name="return-value"></a>Valeur de retour  
 Un [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur qui représente la couleur d’arrière-plan par défaut précédente.  
  
### <a name="remarks"></a>Notes  
 Consultez cette rubrique pour plus d’informations sur le moment définir la couleur d’arrière-plan et comment définir la valeur par défaut.  
  
##  <a name="setcolorscheme"></a>  CReBarCtrl::SetColorScheme  
 Définit le jeu de couleurs pour les boutons sur un contrôle rebar.  
  
```  
void SetColorScheme(const COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Paramètres  
 *Procedure Calls, LPC*  
 Un pointeur vers un [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) structure, comme décrit dans le SDK Windows.  
  
### <a name="remarks"></a>Notes  
 Le `COLORSCHEME` structure inclut la couleur de surbrillance du bouton et la couleur de l’ombre.  
  
##  <a name="setextendedstyle"></a>  CReBarCtrl::SetExtendedStyle  
 Définit les styles étendus pour le contrôle rebar actuel.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwMask,   
    DWORD dwStyleEx);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] *dwMask*|Une combinaison au niveau du bit (OR) d’indicateurs qui spécifient les indicateurs dans le *dwStyleEx* paramètre s’applique. Utiliser une ou plusieurs des valeurs suivantes :<br /><br /> RBS_EX_SPLITTER : Par défaut, afficher le séparateur en bas en mode horizontal et à droite en mode vertical.<br /><br /> RBS_EX_TRANSPARENT : Transférer le [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) message vers la fenêtre parente.|  
|[in] *dwStyleEx*|Une combinaison (OR) au niveau du bit des indicateurs qui spécifient les styles à appliquer. Pour définir un style, spécifiez le même indicateur est utilisé dans le *dwMask* paramètre. Pour réinitialiser un style, spécifiez zéro binaire.|  
  
### <a name="return-value"></a>Valeur de retour  
 Le style étendu précédent.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [RB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774519) message, qui est décrite dans le SDK Windows.  
  
##  <a name="setimagelist"></a>  CReBarCtrl::SetImageList  
 Affecte une liste d’images à un contrôle rebar.  
  
```  
BOOL SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Paramètres  
 *pImageList*  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet contenant la liste d’images pour être assigné au contrôle rebar.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="setowner"></a>  CReBarCtrl::SetOwner  
 Implémente le comportement du message Win32 [RB_SETPARENT](http://msdn.microsoft.com/library/windows/desktop/bb774522), comme décrit dans le SDK Windows.  
  
```  
CWnd* SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 *pWnd*  
 Un pointeur vers un `CWnd` objet à définir comme propriétaire du contrôle rebar.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CWnd](../../mfc/reference/cwnd-class.md) objet qui est le propriétaire actuel du contrôle rebar.  
  
### <a name="remarks"></a>Notes  
 Notez que cette fonction membre utilise des pointeurs vers `CWnd` objets pour le propriétaire actuel et sélectionné du contrôle rebar, plutôt que de handles à windows.  
  
> [!NOTE]
>  Cette fonction membre ne modifie pas le parent réels qui a été défini lorsque le contrôle a été créé ; au lieu de cela, il envoie les messages de notification à la fenêtre que vous spécifiez.  
  
##  <a name="setpalette"></a>  CReBarCtrl::SetPalette  
 Implémente le comportement du message Win32 [RB_SETPALETTE](http://msdn.microsoft.com/library/windows/desktop/bb774520), comme décrit dans le SDK Windows.  
  
```  
CPalette* SetPalette(HPALETTE hPal);
```  
  
### <a name="parameters"></a>Paramètres  
 *hPal*  
 HPALETTE qui spécifie la palette de nouveau le contrôle rebar utilisera.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CPalette](../../mfc/reference/cpalette-class.md) objet qui spécifie la palette précédente du contrôle rebar.  
  
### <a name="remarks"></a>Notes  
 Notez que cette fonction membre utilise un `CPalette` objet comme sa valeur de retour, plutôt qu’un HPALETTE.  
  
##  <a name="settextcolor"></a>  CReBarCtrl::SetTextColor  
 Implémente le comportement du message Win32 [RB_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774524), comme décrit dans le SDK Windows.  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Paramètres  
 *CLR*  
 Une valeur COLORREF qui représente le nouveau texte de couleur le `CReBarCtrl` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Le [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur représentant la couleur du texte précédent associé le `CReBarCtrl` objet.  
  
### <a name="remarks"></a>Notes  
 Il est fourni pour prendre en charge de la flexibilité de couleur de texte dans un contrôle rebar.  
  
##  <a name="settooltips"></a>  CReBarCtrl::SetToolTips  
 Associe un contrôle info-bulle à un contrôle rebar.  
  
```  
void SetToolTips(CToolTipCtrl* pToolTip);
```  
  
### <a name="parameters"></a>Paramètres  
 *pToolTip*  
 Un pointeur vers un [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) objet  
  
### <a name="remarks"></a>Notes  
 Vous devez détruire le `CToolTipCtrl` de l’objet lorsque vous avez terminé avec lui.  
  
##  <a name="setwindowtheme"></a>  CReBarCtrl::SetWindowTheme  
 Définit le style visuel du contrôle rebar.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Paramètres  
 *pszSubAppName*  
 Pointeur vers une chaîne Unicode qui contient le style visuel rebar à définir.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour n’est pas utilisée.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre émule la fonctionnalité de la [RB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb774530) du message, comme décrit dans le SDK Windows.  
  
##  <a name="showband"></a>  CReBarCtrl::ShowBand  
 Implémente le comportement du message Win32 [RB_SHOWBAND](http://msdn.microsoft.com/library/windows/desktop/bb774532), comme décrit dans le SDK Windows.  
  
```  
BOOL ShowBand(
    UINT uBand,  
    BOOL fShow = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 *uBand*  
 Index de base zéro d’une bande dans le contrôle rebar.  
  
 *fShow*  
 Indique si la bande doit être affichée ou masquée. Si cette valeur est TRUE, la bande s’affichera. Sinon, la bande sera masquée.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
##  <a name="sizetorect"></a>  CReBarCtrl::SizeToRect  
 Implémente le comportement du message Win32 [RB_SIZETORECT](http://msdn.microsoft.com/library/windows/desktop/bb774534), comme décrit dans le SDK Windows.  
  
```  
BOOL SizeToRect(CRect& rect);
```  
  
### <a name="parameters"></a>Paramètres  
 *Rect*  
 Une référence à un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui spécifie le rectangle du contrôle rebar doivent donc être dimensionné à.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Notez que cette fonction membre utilise un `CRect` objet en tant que paramètre, au lieu d’un `RECT` structure.  
  
## <a name="see-also"></a>Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)


