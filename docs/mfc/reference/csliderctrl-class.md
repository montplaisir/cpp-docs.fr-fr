---
title: CSliderCtrl, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd58faa0cda2162f1abe906da8e38d4d62402db8
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850207"
---
# <a name="csliderctrl-class"></a>CSliderCtrl (classe)
Fournit les fonctionnalités du contrôle commun de curseur Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|Construit un objet `CSliderCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](#clearsel)|Efface la sélection actuelle d’un contrôle slider.|  
|[CSliderCtrl::ClearTics](#cleartics)|Supprime les marques de graduation actuelle à partir d’un contrôle slider.|  
|[CSliderCtrl::Create](#create)|Crée un contrôle slider et l’attache à un `CSliderCtrl` objet.|  
|[CSliderCtrl::CreateEx](#createex)|Crée un contrôle slider avec les styles étendus Windows spécifiés et l’attache à un `CSliderCtrl` objet.|  
|[CSliderCtrl::GetBuddy](#getbuddy)|Récupère le handle de fenêtre associée contrôle slider à un emplacement donné.|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|Récupère la taille de canal du contrôle de curseur.|  
|[CSliderCtrl::GetLineSize](#getlinesize)|Récupère la taille de ligne d’un contrôle slider.|  
|[CSliderCtrl::GetNumTics](#getnumtics)|Récupère le nombre de graduations dans un contrôle slider.|  
|[CSliderCtrl::GetPageSize](#getpagesize)|Récupère la taille de page d’un contrôle slider.|  
|[CSliderCtrl::GetPos](#getpos)|Récupère la position actuelle du curseur.|  
|[CSliderCtrl::GetRange](#getrange)|Récupère les positions minimales et maximales pour un curseur.|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|Récupère la position maximale pour un curseur.|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|Récupère la position minimale pour un curseur.|  
|[CSliderCtrl::GetSelection](#getselection)|Récupère la plage de la sélection actuelle.|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|Récupère la longueur du curseur dans le contrôle de barre de suivi actuel.|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|Récupère la taille du curseur de défilement du contrôle slider.|  
|[CSliderCtrl::GetTic](#gettic)|Récupère la position de la graduation spécifié.|  
|[CSliderCtrl::GetTicArray](#getticarray)|Récupère le tableau d’interrogation de positions de graduations pour un contrôle slider.|  
|[CSliderCtrl::GetTicPos](#getticpos)|Récupère la position de la graduation spécifié dans les coordonnées clientes.|  
|[CSliderCtrl::GetToolTips](#gettooltips)|Récupère le handle pour le contrôle d’info-bulle assigné au contrôle de curseur, le cas échéant.|  
|[CSliderCtrl::SetBuddy](#setbuddy)|Assigne une fenêtre en tant que la fenêtre associée pour un contrôle slider.|  
|[CSliderCtrl::SetLineSize](#setlinesize)|Définit la taille de ligne d’un contrôle slider.|  
|[CSliderCtrl::SetPageSize](#setpagesize)|Définit la taille de page d’un contrôle slider.|  
|[CSliderCtrl::SetPos](#setpos)|Définit la position actuelle du curseur.|  
|[CSliderCtrl::SetRange](#setrange)|Définit les positions minimales et maximales pour un curseur.|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|Définit la position maximale pour un curseur.|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|Définit la position minimale pour un curseur.|  
|[CSliderCtrl::SetSelection](#setselection)|Définit la durée de la sélection actuelle.|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|Définit la longueur du curseur dans le contrôle de barre de suivi actuel.|  
|[CSliderCtrl::SetTic](#settic)|Définit la position de la graduation spécifié.|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|Définit la fréquence des graduations marques par incrément de contrôle slider.|  
|[CSliderCtrl::SetTipSide](#settipside)|Positions un contrôle d’info-bulle utilisée par un contrôle de barre de suivi.|  
|[CSliderCtrl::SetToolTips](#settooltips)|Affecte un contrôle d’info-bulle à un contrôle slider.|  
  
## <a name="remarks"></a>Notes  
 Un « contrôle de curseur » (également appelé barre de suivi) est une fenêtre contenant un curseur et des coches facultatives. Lorsque l’utilisateur déplace le curseur, à l’aide de la souris ou les touches de direction, le contrôle envoie des messages de notification pour indiquer la modification.  
  
 Contrôles Slider sont utiles lorsque vous souhaitez que l’utilisateur de sélectionner une valeur discrète ou un ensemble de valeurs consécutives dans une plage. Par exemple, vous pouvez utiliser un contrôle slider pour autoriser l’utilisateur à définir la fréquence de répétition du clavier en déplaçant le curseur jusqu'à une graduation donnée.  
  
 Ce contrôle (et par conséquent la `CSliderCtrl` classe) est disponible uniquement pour les programmes s’exécutant sous Windows 95/98 et Windows NT version 3.51 et ultérieures.  
  
 Le curseur se déplace en incréments que vous spécifiez lors de sa création. Par exemple, si vous spécifiez que le curseur doit avoir une plage de cinq, le curseur ne peut occuper six positions : une position sur le côté gauche du contrôle slider et une position pour chaque incrément dans la plage. En règle générale, chacune de ces positions est identifiée par une graduation.  
  
 Vous créez un curseur à l’aide du constructeur et le `Create` fonction membre de `CSliderCtrl`. Une fois que vous avez créé un contrôle slider, vous pouvez utiliser les fonctions membres dans `CSliderCtrl` changer un grand nombre de ses propriétés. Les modifications que vous pouvez effectuer incluent définissant les positions minimales et maximales pour le curseur, le dessin des graduations, la définition d’une plage de sélection et le repositionnement du curseur.  
  
 Pour plus d’informations sur l’utilisation de `CSliderCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et [à l’aide de CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxcmn.h  
  
##  <a name="clearsel"></a>  CSliderCtrl::ClearSel  
 Efface la sélection actuelle d’un contrôle slider.  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 *bRedraw*  
 Indicateur de renouvellement. Si ce paramètre est TRUE, le curseur est redessiné après que la sélection est désactivée ; Sinon, le curseur n’est pas redessiné.  
  
##  <a name="cleartics"></a>  CSliderCtrl::ClearTics  
 Supprime les marques de graduation actuelle à partir d’un contrôle slider.  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 *bRedraw*  
 Indicateur de renouvellement. Si ce paramètre est TRUE, le curseur est redessiné après que les graduations sont désactivées ; Sinon, le curseur n’est pas redessiné.  
  
##  <a name="create"></a>  CSliderCtrl::Create  
 Crée un contrôle slider et l’attache à un `CSliderCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwStyle*  
 Spécifie le style du contrôle slider. Appliquer n’importe quelle combinaison de [styles de contrôle slider](http://msdn.microsoft.com/library/windows/desktop/bb760147), comme décrit dans le Kit de développement logiciel Windows, au contrôle.  
  
 *Rect*  
 Spécifie la taille et la position du curseur. Il peut s’agir un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure.  
  
 *pParentWnd*  
 Spécifie les fenêtre du parent du contrôle slider, généralement un `CDialog`. Il ne doit pas être NULL.  
  
 *nID*  
 Spécifie l’ID. du contrôle de curseur  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’initialisation a abouti ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Vous construisez un `CSliderCtrl` en deux étapes. Tout d’abord, appelez le constructeur, puis `Create`, ce qui crée le contrôle slider et l’attache à la `CSliderCtrl` objet.  
  
 Selon les valeurs définies pour *dwStyle*, le contrôle de curseur peut avoir une orientation verticale ou horizontale. Il peut avoir des graduations sur un côté, les deux côtés, ou aucune des deux. Il peut également être utilisé pour spécifier une plage de valeurs consécutives.  
  
 Pour appliquer des styles de fenêtre étendus au contrôle de curseur, appelez [CreateEx](#createex) au lieu de `Create`.  
  
##  <a name="createex"></a>  CSliderCtrl::CreateEx  
 Crée un contrôle (une fenêtre enfant) et l’associe le `CSliderCtrl` objet.  
  
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
 Spécifie le style du contrôle slider. Appliquer n’importe quelle combinaison de [styles de contrôle slider](http://msdn.microsoft.com/library/windows/desktop/bb760147), comme décrit dans le Kit de développement logiciel Windows, au contrôle.  
  
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
  
##  <a name="csliderctrl"></a>  CSliderCtrl::CSliderCtrl  
 Construit un objet `CSliderCtrl`.  
  
```  
CSliderCtrl();
```  
  
##  <a name="getbuddy"></a>  CSliderCtrl::GetBuddy  
 Récupère le handle de fenêtre associée contrôle slider à un emplacement donné.  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *fLocation*  
 Une valeur booléenne qui indique les deux handles de fenêtre associé à récupérer. Peut avoir l'une des valeurs suivantes :  
  
- TRUE récupère le handle pour l’ami à gauche du curseur. Si le contrôle de curseur utilise le style TBS_VERT, le message récupérera l’ami au-dessus du curseur.  
  
- FALSE récupère le handle pour l’ami à droite du curseur. Si le contrôle de curseur utilise le style TBS_VERT, le message récupérera l’ami sous le curseur.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CWnd](../../mfc/reference/cwnd-class.md) objet qui est la fenêtre associée à l’emplacement spécifié par *fLocation*, ou NULL si aucune fenêtre associée n’existe à cet emplacement.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TBM_GETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760178), comme décrit dans le SDK Windows. Pour obtenir une description des styles de contrôle de curseur, consultez [Styles du contrôle Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) dans le SDK Windows.  
  
##  <a name="getchannelrect"></a>  CSliderCtrl::GetChannelRect  
 Récupère la taille et la position du rectangle englobant pour les canaux d’un contrôle slider.  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *lprc*  
 Un pointeur vers un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui contient la taille et la position du canal de rectangle englobant de la fonction retourne.  
  
### <a name="remarks"></a>Notes  
 Le canal est la zone sur laquelle le curseur se déplace et qui contient la mise en surbrillance lorsqu’une plage est sélectionnée.  
  
##  <a name="getlinesize"></a>  CSliderCtrl::GetLineSize  
 Récupère la taille de la ligne pour un contrôle slider.  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille d’une ligne pour le contrôle slider.  
  
### <a name="remarks"></a>Notes  
 La taille de ligne affecte la quantité le curseur se déplace pour les notifications TB_LINEUP et quel. Le paramètre par défaut pour la taille de ligne est 1.  
  
##  <a name="getnumtics"></a>  CSliderCtrl::GetNumTics  
 Récupère le nombre de graduations dans un contrôle slider.  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de graduations dans le contrôle slider.  
  
##  <a name="getpagesize"></a>  CSliderCtrl::GetPageSize  
 Récupère la taille de la page pour un contrôle slider.  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille d’une page pour le contrôle slider.  
  
### <a name="remarks"></a>Notes  
 La taille de page affecte la quantité le curseur se déplace pour les notifications TB_PAGEUP et TB_PAGEDOWN.  
  
##  <a name="getpos"></a>  CSliderCtrl::GetPos  
 Récupère la position actuelle du curseur dans un contrôle slider.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Position actuelle.  
  
##  <a name="getrange"></a>  CSliderCtrl::GetRange  
 Récupère les positions minimales et maximales pour le curseur d’un contrôle slider.  
  
```  
void GetRange(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *nMin*  
 Référence à un entier qui reçoit la position minimale.  
  
 *nombre maximal*  
 Référence à un entier qui reçoit la position maximale.  
  
### <a name="remarks"></a>Notes  
 Cette fonction copie les valeurs dans les entiers référencés par *nMin* et *nMax*.  
  
##  <a name="getrangemax"></a>  CSliderCtrl::GetRangeMax  
 Récupère la position maximale pour le curseur d’un contrôle slider.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Position maximale du contrôle.  
  
##  <a name="getrangemin"></a>  CSliderCtrl::GetRangeMin  
 Récupère la position minimale pour le curseur d’un contrôle slider.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Position minimale du contrôle.  
  
##  <a name="getselection"></a>  CSliderCtrl::GetSelection  
 Récupère les positions de début et de fin de la sélection actuelle d’un contrôle slider.  
  
```  
void GetSelection(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *nMin*  
 Référence à un entier qui reçoit la position de départ de la sélection actuelle.  
  
 *nombre maximal*  
 Référence à un entier qui reçoit la position de fin de la sélection actuelle.  
  
##  <a name="getthumblength"></a>  CSliderCtrl::GetThumbLength  
 Récupère la longueur du curseur dans le contrôle de barre de suivi actuel.  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur du curseur, en pixels.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [TBM_GETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760201) message, qui est décrite dans le SDK Windows.  
  
##  <a name="getthumbrect"></a>  CSliderCtrl::GetThumbRect  
 Récupère la taille et la position du rectangle englobant pour le slider (curseur de défilement) d’un contrôle slider.  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *lprc*  
 Un pointeur vers un `CRect` objet qui contient le rectangle englobant pour le curseur lors de la fonction retourne.  
  
##  <a name="gettic"></a>  CSliderCtrl::GetTic  
 Récupère la position d’une graduation d’un contrôle slider.  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *nTic*  
 Index de base zéro identifiant une graduation.  
  
### <a name="return-value"></a>Valeur de retour  
 La position de la graduation spécifié ou - 1 si *nTic* ne spécifie pas un index valide.  
  
##  <a name="getticarray"></a>  CSliderCtrl::GetTicArray  
 Récupère l’adresse du tableau qui contient les positions des graduations pour un contrôle slider.  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’adresse du tableau qui contient les positions de marque de graduation pour le contrôle slider.  
  
##  <a name="getticpos"></a>  CSliderCtrl::GetTicPos  
 Récupère la position physique actuelle d’une graduation d’un contrôle slider.  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *nTic*  
 Index de base zéro identifiant une graduation.  
  
### <a name="return-value"></a>Valeur de retour  
 La position physique, en coordonnées clientes, de la graduation spécifié ou - 1 si *nTic* ne spécifie pas un index valide.  
  
##  <a name="gettooltips"></a>  CSliderCtrl::GetToolTips  
 Récupère le handle pour le contrôle d’info-bulle assigné au contrôle de curseur, le cas échéant.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) de l’objet, ou NULL si l’info-bulles ne sont pas en cours d’utilisation. Si le contrôle slider n’utilise pas le style TBS_TOOLTIPS, la valeur de retour est NULL.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TBM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760209), comme décrit dans le SDK Windows. Notez que cette fonction membre retourne un `CToolTipCtrl` objet au lieu d’un handle à un contrôle.  
  
 Pour obtenir une description des styles de contrôle de curseur, consultez [Styles du contrôle Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) dans le SDK Windows.  
  
##  <a name="setbuddy"></a>  CSliderCtrl::SetBuddy  
 Assigne une fenêtre en tant que la fenêtre associée pour un contrôle slider.  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 *pWndBuddy*  
 Un pointeur vers un `CWnd` objet qui sera définie en tant qu’ami du contrôle slider.  
  
 *fLocation*  
 Valeur qui spécifie l’emplacement d’affichage de la fenêtre associée. Cette valeur peut être une des opérations suivantes :  
  
- TRUE l’ami apparaît à gauche de la barre de suivi si le contrôle de barre de suivi utilise le style de styles TBS_HORZ. Si la barre de suivi utilise le style TBS_VERT, les contacts s’affiche au-dessus du contrôle de barre de suivi.  
  
- FALSE l’ami s’affiche à droite de la barre de suivi si le contrôle de barre de suivi utilise le style de styles TBS_HORZ. Si la barre de suivi utilise le style TBS_VERT, l’ami apparaît sous le contrôle de barre de suivi.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CWnd](../../mfc/reference/cwnd-class.md) objet qui a été précédemment affecté au contrôle de curseur à cet emplacement.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TBM_SETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760213), comme décrit dans le SDK Windows. Notez que cette fonction membre utilise des pointeurs vers `CWnd` objets, plutôt que des handles de fenêtre pour sa valeur de retour et le paramètre.  
  
 Pour obtenir une description des styles de contrôle de curseur, consultez [Styles du contrôle Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) dans le SDK Windows.  
  
##  <a name="setlinesize"></a>  CSliderCtrl::SetLineSize  
 Définit la taille de la ligne pour un contrôle slider.  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>Paramètres  
 *nSize*  
 La nouvelle taille de ligne du contrôle slider.  
  
### <a name="return-value"></a>Valeur de retour  
 La taille de la ligne précédente.  
  
### <a name="remarks"></a>Notes  
 La taille de ligne affecte la quantité le curseur se déplace pour les notifications TB_LINEUP et quel.  
  
##  <a name="setpagesize"></a>  CSliderCtrl::SetPageSize  
 Définit la taille de la page pour un contrôle slider.  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>Paramètres  
 *nSize*  
 La nouvelle taille de page du contrôle slider.  
  
### <a name="return-value"></a>Valeur de retour  
 La taille de page précédente.  
  
### <a name="remarks"></a>Notes  
 La taille de page affecte la quantité le curseur se déplace pour les notifications TB_PAGEUP et TB_PAGEDOWN.  
  
##  <a name="setpos"></a>  CSliderCtrl::SetPos  
 Définit la position actuelle du curseur dans un contrôle slider.  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>Paramètres  
 *nPos*  
 Spécifie la nouvelle position du curseur.  
  
##  <a name="setrange"></a>  CSliderCtrl::SetRange  
 Définit la durée (positions minimales et maximales) pour le curseur d’un contrôle slider.  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 *nMin*  
 Position minimale pour le curseur.  
  
 *nombre maximal*  
 Position maximale pour le curseur.  
  
 *bRedraw*  
 L’indicateur de renouvellement. Si ce paramètre est TRUE, le curseur est redessiné après que la plage est définie ; Sinon, le curseur n’est pas redessiné.  
  
##  <a name="setrangemax"></a>  CSliderCtrl::SetRangeMax  
 Définit la durée maximale pour le curseur d’un contrôle slider.  
  
```  
void SetRangeMax(
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 *nombre maximal*  
 Position maximale pour le curseur.  
  
 *bRedraw*  
 L’indicateur de renouvellement. Si ce paramètre est TRUE, le curseur est redessiné après que la plage est définie ; Sinon, le curseur n’est pas redessiné.  
  
##  <a name="setrangemin"></a>  CSliderCtrl::SetRangeMin  
 Définit la durée minimale pour le curseur d’un contrôle slider.  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 *nMin*  
 Position minimale pour le curseur.  
  
 *bRedraw*  
 L’indicateur de renouvellement. Si ce paramètre est TRUE, le curseur est redessiné après que la plage est définie ; Sinon, le curseur n’est pas redessiné.  
  
##  <a name="setselection"></a>  CSliderCtrl::SetSelection  
 Définit les positions de début et de fin pour la sélection actuelle d’un contrôle slider.  
  
```  
void SetSelection(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Paramètres  
 *nMin*  
 Position de départ pour le curseur.  
  
 *nombre maximal*  
 Position de fin pour le curseur.  
  
##  <a name="setthumblength"></a>  CSliderCtrl::SetThumbLength  
 Définit la longueur du curseur dans le contrôle de barre de suivi actuel.  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] *nLength*|Longueur du curseur, en pixels.|  
  
### <a name="remarks"></a>Notes  
 Cette méthode exige que le contrôle de barre de suivi [TBS_FIXEDLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760147) style.  
  
 Cette méthode envoie le [TBM_SETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760234) message, qui est décrite dans le SDK Windows.  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_sliderCtrl`, qui est utilisé pour accéder au contrôle de barre de suivi actuel. L’exemple définit également une variable, `thumbLength`, qui est utilisé pour stocker la longueur par défaut du composant de curseur de défilement du contrôle trackbar. Ces variables sont utilisées dans l’exemple suivant.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit le composant de curseur de défilement du contrôle trackbar à deux fois sa longueur par défaut.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="settic"></a>  CSliderCtrl::SetTic  
 Définit la position d’une graduation d’un contrôle slider.  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>Paramètres  
 *nTic*  
 Position de la graduation. Ce paramètre doit spécifier une valeur positive.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la graduation est définie ; sinon 0.  
  
##  <a name="setticfreq"></a>  CSliderCtrl::SetTicFreq  
 Définit la fréquence avec graduée marques sont affichés dans un contrôle slider.  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>Paramètres  
 *nFreq*  
 Fréquence des graduations.  
  
### <a name="remarks"></a>Notes  
 Par exemple, si la fréquence est définie sur 2, une graduation est affichée pour chaque incrément autres dans la plage du curseur. Le paramètre par défaut pour la fréquence est 1 (autrement dit, chaque incrément dans la plage est associé à une graduation).  
  
 Vous devez créer le contrôle avec le style TBS_AUTOTICKS pour utiliser cette fonction. Pour plus d’informations, consultez [CSliderCtrl::Create](#create).  
  
##  <a name="settipside"></a>  CSliderCtrl::SetTipSide  
 Positions un contrôle d’info-bulle utilisée par un contrôle de barre de suivi.  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>Paramètres  
 *%nemplacement*  
 Valeur représentant l’emplacement auquel afficher le contrôle d’info-bulle. Pour obtenir la liste des valeurs possibles, consultez le message Win32 [TBM_SETTIPSIDE](http://msdn.microsoft.com/library/windows/desktop/bb760240), comme décrit dans le SDK Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur qui représente l’emplacement précédent du contrôle d’info-bulle. La valeur de retour correspond à l’une des valeurs possibles pour *%nemplacement*.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 TBM_SETTIPSIDE, comme décrit dans le SDK Windows. Les contrôles de curseur qui utilisent le style TBS_TOOLTIPS affichent des info-bulles. Pour obtenir une description des styles de contrôle de curseur, consultez [Styles du contrôle Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) dans le SDK Windows.  
  
##  <a name="settooltips"></a>  CSliderCtrl::SetToolTips  
 Affecte un contrôle d’info-bulle à un contrôle slider.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Paramètres  
 *pWndTip*  
 Un pointeur vers un [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) objet contenant les info-bulles à utiliser avec le contrôle slider.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [TBM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760242), comme décrit dans le SDK Windows. Création d’un contrôle slider avec le style TBS_TOOLTIPS, il crée un contrôle d’info-bulle par défaut qui s’affiche à côté du curseur, en affichant la position actuelle du curseur. Pour obtenir une description des styles de contrôle de curseur, consultez [Styles du contrôle Trackbar](http://msdn.microsoft.com/library/windows/desktop/bb760147) dans le SDK Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [MFC exemple CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl, classe](../../mfc/reference/cprogressctrl-class.md)
