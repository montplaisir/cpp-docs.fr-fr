---
title: CLinkCtrl, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
dev_langs:
- C++
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a384f79944ace90fcb289511e18297de7a7da233
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208008"
---
# <a name="clinkctrl-class"></a>CLinkCtrl, classe
Fournit les fonctionnalités du contrôle commun SysLink Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|Construit un objet `CLinkCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CLinkCtrl::Create](#create)|Crée un contrôle de lien et l’attache à un `CLinkCtrl` objet.|  
|[CLinkCtrl::CreateEx](#createex)|Crée un contrôle de lien avec des styles étendus et l’attache à un `CLinkCtrl` objet.|  
|[CLinkCtrl::GetIdealHeight](#getidealheight)|Récupère la hauteur idéale du contrôle de lien.|  
|[CLinkCtrl::GetIdealSize](#getidealsize)|Calcule la hauteur préférée du texte du lien pour le contrôle de lien actuel, en fonction de la largeur de la liaison spécifiée.|  
|[CLinkCtrl::GetItem](#getitem)|Récupère les États et les attributs d’un élément de contrôle de lien.|  
|[CLinkCtrl::GetItemID](#getitemid)|Récupère l’ID d’un élément de contrôle de lien.|  
|[CLinkCtrl::GetItemState](#getitemstate)|Récupère l’état de l’élément de contrôle de lien.|  
|[CLinkCtrl::GetItemUrl](#getitemurl)|Récupère l’URL représenté par l’élément de contrôle de lien.|  
|[CLinkCtrl::HitTest](#hittest)|Détermine si l’utilisateur a cliqué sur le lien spécifié.|  
|[CLinkCtrl::SetItem](#setitem)|Définit les États et les attributs d’un élément de contrôle de lien.|  
|[CLinkCtrl::SetItemID](#setitemid)|Définit l’ID d’un élément de contrôle de lien.|  
|[CLinkCtrl::SetItemState](#setitemstate)|Définit l’état de l’élément de contrôle de lien.|  
|[CLinkCtrl::SetItemUrl](#setitemurl)|Définit l’URL représenté par l’élément de contrôle de lien.|  
  
## <a name="remarks"></a>Notes  
 Un « lier le contrôle » fournit un moyen pratique d’intégrer des liens hypertexte dans une fenêtre. Le contrôle réel est une fenêtre qui restitue le texte marqué et lance des applications appropriées lorsque l’utilisateur clique sur un lien incorporé. Plusieurs liens sont pris en charge au sein d’un contrôle et est accessible par un index de base zéro.  
  
 Ce contrôle (et par conséquent la `CLinkCtrl` classe) est disponible uniquement pour les programmes s’exécutant sous Windows XP et versions ultérieures.  
  
 Pour plus d’informations, consultez [contrôle SysLink](http://msdn.microsoft.com/library/windows/desktop/bb760706) dans le SDK Windows.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxcmn.h  
  
##  <a name="clinkctrl"></a>  CLinkCtrl::CLinkCtrl  
 Construit un objet `CLinkCtrl`.  
  
```  
CLinkCtrl();
```  
  
##  <a name="create"></a>  CLinkCtrl::Create  
 Crée un contrôle de lien et l’attache à un `CLinkCtrl` objet.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszLinkMarkup*  
 Pointeur vers une chaîne se terminant par zéro contenant le texte marqué le texte à afficher. Pour plus d’informations, consultez la section « Balisage et lien accès » dans la rubrique [vue d’ensemble des contrôles SysLink](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 *dwStyle*  
 Spécifie le style du contrôle de lien. Appliquer n’importe quelle combinaison de styles de contrôle. Consultez [des Styles de contrôle courants](http://msdn.microsoft.com/library/windows/desktop/bb775498) dans le `Windows SDK` pour plus d’informations.  
  
 *Rect*  
 Spécifie la taille et la position du contrôle de lien. Il peut s’agir un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [RECT](../../mfc/reference/rect-structure1.md) structure.  
  
 *pParentWnd*  
 Spécifie la fenêtre parente du contrôle de lien. Il ne doit pas être NULL.  
  
 *nID*  
 Spécifie l’ID. du contrôle de lien  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si l’initialisation a abouti ; Sinon, FALSE.  
  
### <a name="remarks"></a>Notes  
 Vous construisez un `CLinkCtrl` objet en deux étapes. Tout d’abord, appelez le constructeur, puis `Create`, ce qui crée le contrôle de lien et l’attache à la `CLinkCtrl` objet. Si vous souhaitez utiliser des styles étendus windows avec votre contrôle, appelez [CLinkCtrl::CreateEx](#createex) au lieu de `Create`.  
  
 La deuxième forme de la `Create` méthode est déconseillée. Utiliser la première forme qui spécifie le *lpszLinkMarkup* paramètre.  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit deux variables, nommées `m_Link1` et `m_Link2`, qui sont utilisés pour accéder à deux contrôles de lien.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant crée un contrôle de lien basé sur l’emplacement d’un autre contrôle de lien. Le chargeur de ressources crée le premier contrôle de lien au démarrage de votre application. Lorsque votre application passe à la méthode OnInitDialog, vous créez le deuxième contrôle de lien par rapport à la position du premier contrôle de lien. Puis vous redimensionnez le deuxième contrôle de lien pour s’adapter au texte qu’il affiche.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]  
  
##  <a name="createex"></a>  CLinkCtrl::CreateEx  
 Crée un contrôle de lien avec des styles étendus et l’attache à un `CLinkCtrl` objet.  
  
```  
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwExStyle,  
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszLinkMarkup*  
 Pointeur vers une chaîne se terminant par zéro contenant le texte marqué le texte à afficher. Pour plus d’informations, consultez la section « Balisage et lien accès » dans la rubrique [vue d’ensemble des contrôles SysLink](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 *dwExStyle*  
 Spécifie le style étendu du contrôle de lien. Pour obtenir la liste des styles étendus de Windows, consultez le *dwExStyle* paramètre pour [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) dans le SDK Windows.  
  
 *dwStyle*  
 Spécifie le style du contrôle de lien. Appliquer n’importe quelle combinaison de styles de contrôle. Pour plus d’informations, consultez [des Styles de contrôle courants](http://msdn.microsoft.com/library/windows/desktop/bb775498) dans le SDK Windows.  
  
 *Rect*  
 Spécifie la taille et la position du contrôle de lien. Il peut s’agir un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [RECT](../../mfc/reference/rect-structure1.md) structure.  
  
 *pParentWnd*  
 Spécifie la fenêtre parente du contrôle de lien. Il ne doit pas être NULL.  
  
 *nID*  
 Spécifie l’ID. du contrôle de lien  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si l’initialisation a abouti ; Sinon, FALSE.  
  
### <a name="remarks"></a>Notes  
 Utilisez `CreateEx` au lieu de [créer](#create) pour appliquer les constantes de style Windows étendus.  
  
 La deuxième forme de la `CreateEx` méthode est déconseillée. Utiliser la première forme qui spécifie le *lpszLinkMarkup* paramètre.  
  
##  <a name="getidealheight"></a>  CLinkCtrl::GetIdealHeight  
 Récupère la hauteur idéale du contrôle de lien.  
  
```  
int GetIdealHeight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La hauteur idéale de contrôle, en pixels.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [LM_GETIDEALHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb760716), comme décrit dans le SDK Windows.  
  
##  <a name="getidealsize"></a>  CLinkCtrl::GetIdealSize  
 Calcule la hauteur préférée du texte du lien pour le contrôle de lien actuel, en fonction de la largeur de la liaison spécifiée.  
  
```  
int GetIdealSize(
    int cxMaxWidth,   
    SIZE* pSize) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] *cxMaxWidth*|La largeur maximale de la liaison, en pixels.|  
|[out] \* *pSize*|Un pointeur vers un Windows [taille](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure. Lorsque cette méthode est retournée, le *cy* membre de la `SIZE` structure contient la hauteur du texte de lien idéal pour la largeur de texte de lien spécifié par *cxMaxWidth*. Le *cx* membre de la structure contient la largeur de texte de lien qui est réellement nécessaire.|  
  
### <a name="return-value"></a>Valeur de retour  
 La hauteur préférée du texte du lien, en pixels. La valeur de retour est identique à la valeur de la *cy* membre de la `SIZE` structure.  
  
### <a name="remarks"></a>Notes  
 Pour obtenir un exemple de la `GetIdealSize` (méthode), consultez l’exemple dans [CLinkCtrl::Create](#create).  
  
 Cette méthode envoie le [LM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760718) message, qui est décrite dans le SDK Windows.  
  
##  <a name="getitem"></a>  CLinkCtrl::GetItem  
 Récupère les États et les attributs d’un élément de contrôle de lien.  
  
```  
BOOL GetItem(PLITEM pItem) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *pItem*  
 Un pointeur vers un [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) structure pour recevoir des informations sur les éléments.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720), comme décrit dans le SDK Windows.  
  
##  <a name="getitemid"></a>  CLinkCtrl::GetItemID  
 Récupère l’ID d’un élément de contrôle de lien.  
  
```  
BOOL GetItemID(
    int iLink,  
    CString& strID) const;  
  
BOOL GetItemID(
    int iLink,  
    LPWSTR szID,  
    UINT cchID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *iLink*  
 L’index d’un élément de contrôle de lien.  
  
 *strID*  
 Un [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) objet contenant l’ID de l’élément spécifié.  
  
 *szID*  
 Chaîne se terminant par null qui contient l’ID de l’élément spécifié.  
  
 *cchID*  
 La taille en caractères de la *szID* mémoire tampon.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
> [!NOTE]
>  Cette fonction retourne également FALSE si la mémoire tampon de *szID ou strID* est inférieure à MAX_LINKID_TEXT.  
  
### <a name="remarks"></a>Notes  
 Récupère l’ID d’un élément de contrôle de liaison spécifique. Pour plus d’informations, consultez le message Win32 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) dans le SDK Windows.  
  
##  <a name="getitemstate"></a>  CLinkCtrl::GetItemState  
 Récupère l’état de l’élément de contrôle de lien.  
  
```  
BOOL GetItemState(
    int iLink,  
    UINT* pnState,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *iLink*  
 L’index d’un élément de contrôle de lien.  
  
 *pnState*  
 La valeur de l’élément d’état spécifié.  
  
 *stateMask*  
 Combinaison d’indicateurs qui décrit quel élément d’état à obtenir. Pour obtenir la liste de valeurs, consultez la description de la `state` membre dans le [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) structure. Éléments autorisées sont identiques à celles autorisées dans `state`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Récupère la valeur de l’élément d’état spécifié d’un élément de contrôle de liaison spécifique. Pour plus d’informations, consultez le message Win32 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) dans le SDK Windows.  
  
##  <a name="getitemurl"></a>  CLinkCtrl::GetItemUrl  
 Récupère l’URL représenté par l’élément de contrôle de lien.  
  
```  
BOOL GetItemUrl(
    int iLink,  
    CString& strUrl) const;  
  
BOOL GetItemUrl(
    int iLink,  
    LPWSTR szUrl,  
    UINT cchUrl) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *iLink*  
 L’index d’un élément de contrôle de lien.  
  
 *strUrl*  
 Un [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) objet contenant l’URL représenté par l’élément spécifié  
  
 *szUrl*  
 Une chaîne se terminant par null qui contient l’URL représenté par l’élément spécifié  
  
 *cchUrl*  
 La taille en caractères de la *szURL* mémoire tampon.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
> [!NOTE]
>  Cette fonction retourne également FALSE si la mémoire tampon de *szUrl ou strUrl* est inférieure à MAX_LINKID_TEXT.  
  
### <a name="remarks"></a>Notes  
 Récupère l’URL représenté par l’élément de contrôle de lien spécifié. Pour plus d’informations, consultez le message Win32 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) dans le SDK Windows.  
  
##  <a name="hittest"></a>  CLinkCtrl::HitTest  
 Détermine si l’utilisateur a cliqué sur le lien spécifié.  
  
```  
BOOL HitTest(PLHITTESTINFO phti) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *phti*  
 Pointeur vers un `LHITTESTINFO` structure contenant des informations sur le lien, l’utilisateur a cliqué.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [LM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb760722), comme décrit dans le SDK Windows.  
  
##  <a name="setitem"></a>  CLinkCtrl::SetItem  
 Définit les États et les attributs d’un élément de contrôle de lien.  
  
```  
BOOL SetItem(PLITEM pItem);
```  
  
### <a name="parameters"></a>Paramètres  
 *pItem*  
 Un pointeur vers un [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) structure contenant les informations à définir.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724), comme décrit dans le SDK Windows.  
  
##  <a name="setitemid"></a>  CLinkCtrl::SetItemID  
 Récupère l’ID d’un élément de contrôle de lien.  
  
```  
BOOL SetItemID(
    int iLink,  
    LPCWSTR szID);
```  
  
### <a name="parameters"></a>Paramètres  
 *iLink*  
 L’index d’un élément de contrôle de lien.  
  
 *szID*  
 Chaîne se terminant par null qui contient l’ID de l’élément spécifié.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Définit l’ID d’un élément de contrôle de liaison spécifique. Pour plus d’informations, consultez le message Win32 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) dans le SDK Windows.  
  
##  <a name="setitemstate"></a>  CLinkCtrl::SetItemState  
 Récupère l’état de l’élément de contrôle de lien.  
  
```  
BOOL SetItemState(
    int iLink,  
    UINT state,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```  
  
### <a name="parameters"></a>Paramètres  
 *iLink*  
 L’index d’un élément de contrôle de lien.  
  
 *pnState*  
 La valeur de l’état spécifié de l’article en cours.  
  
 *stateMask*  
 Combinaison d’indicateurs décrivant l’état de l’article en cours. Pour obtenir la liste de valeurs, consultez la description de la `state` membre dans le [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) structure. Éléments autorisées sont identiques à celles autorisées dans `state`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Définit la valeur de l’élément d’état spécifié d’un élément de contrôle de liaison spécifique. Pour plus d’informations, consultez le message Win32 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) dans le SDK Windows.  
  
##  <a name="setitemurl"></a>  CLinkCtrl::SetItemUrl  
 Définit l’URL représenté par l’élément de contrôle de lien.  
  
```  
BOOL SetItemUrl(
    int iLink,  
    LPCWSTR szUrl);
```  
  
### <a name="parameters"></a>Paramètres  
 *iLink*  
 L’index d’un élément de contrôle de lien.  
  
 *szUrl*  
 Une chaîne se terminant par null qui contient l’URL représenté par l’élément spécifié  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Définit l’URL représenté par l’élément de contrôle de lien spécifié. Pour plus d’informations, consultez le message Win32 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) dans le SDK Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)
