---
title: CWinTraits, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1e400352a6eca09fd26ea1a1e2ba5cff60888bc
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026099"
---
# <a name="cwintraits-class"></a>CWinTraits, classe
Cette classe fournit une méthode pour standardiser les styles utilisés lors de la création d’un objet de fenêtre.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisés dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```  
  
#### <a name="parameters"></a>Paramètres  
 *t_dwStyle*  
 Styles de fenêtre standard par défaut.  
  
 *t_dwExStyle*  
 Par défaut des styles de fenêtre étendus.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(Statique) Récupère les styles étendus pour le `CWinTraits` objet.|  
|[CWinTraits::GetWndStyle](#getwndstyle)|(Statique) Récupère les styles standards pour le `CWinTraits` objet.|  
  
## <a name="remarks"></a>Notes  
 Cela [caractéristiques de fenêtre](../../atl/understanding-window-traits.md) classe fournit une méthode simple pour standardiser les styles utilisés pour la création d’un objet de fenêtre ATL. Utiliser une spécialisation de cette classe comme un paramètre de modèle à [CWindowImpl](../../atl/reference/cwindowimpl-class.md) ou l’autre des classes de fenêtre ATL pour spécifier les styles standard et étendu par défaut utilisés pour les instances de cette classe de fenêtre.  
  
 Utilisez ce modèle lorsque vous souhaitez fournir par défaut des styles de fenêtre qui seront utilisées uniquement quand aucun autre style n’est spécifiés dans l’appel à [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 ATL fournit trois spécialisations prédéfinies de ce modèle pour des combinaisons de styles de fenêtre couramment utilisés :  
  
 `CControlWinTraits`  
 Conçu pour une fenêtre de contrôle standard. Les styles standards suivants sont utilisés : WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN et WS_CLIPSIBLINGS. Il n’existe aucun des styles étendus.  
  
 `CFrameWinTraits`  
 Conçu pour une fenêtre frame standard. Incluent les styles standards utilisées : WS_OVERLAPPEDWINDOW, WS_CLIPCHILDREN et WS_CLIPSIBLINGS. Incluent les styles étendus utilisés : WS_EX_APPWINDOW et WS_EX_WINDOWEDGE.  
  
 `CMDIChildWinTraits`  
 Conçu pour une fenêtre enfant MDI standard. Incluent les styles standards utilisées : WS_OVERLAPPEDWINDOW WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN et WS_CLIPSIBLINGS. Incluent les styles étendus utilisés : WS_EX_MDICHILD.  
  
 Si vous souhaitez vous assurer que certains styles sont définis pour toutes les instances de la classe de fenêtre tout en autorisant d’autres styles à définir sur une base par instance, utilisez [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) à la place.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlwin.h  
  
##  <a name="getwndstyle"></a>  CWinTraits::GetWndStyle  
 Appelez cette fonction pour récupérer les styles standards de la `CWinTraits` objet.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwStyle*  
 Styles utilisés pour la création d’une fenêtre standards. Si *dwStyle* est 0, les valeurs de style de modèle (`t_dwStyle`) sont retournés. Si *dwStyle* est différent de zéro, *dwStyle* est retourné.  
  
### <a name="return-value"></a>Valeur de retour  
 Les styles de fenêtre standard de l’objet.  
  
##  <a name="getwndexstyle"></a>  CWinTraits::GetWndExStyle  
 Appelez cette fonction pour récupérer les styles étendus de la `CWinTraits` objet.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwExStyle*  
 Styles étendus utilisés pour la création d’une fenêtre. Si *dwExStyle* est 0, les valeurs de style de modèle (`t_dwExStyle`) sont retournés. Si *dwExStyle* est différent de zéro, *dwExStyle* est retourné.  
  
### <a name="return-value"></a>Valeur de retour  
 Styles de fenêtre étendus de l’objet.  
  
## <a name="see-also"></a>Voir aussi  
 [Membres de classe](http://msdn.microsoft.com/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Présentation des caractéristiques de fenêtre](../../atl/understanding-window-traits.md)
