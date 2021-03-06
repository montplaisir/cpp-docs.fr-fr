---
title: Csimplemapequalhelperfalse, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 70cea341e7f78032cdaca260e3c891f4c762e0b6
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882622"
---
# <a name="csimplemapequalhelperfalse-class"></a>Csimplemapequalhelperfalse, classe
Cette classe est une application d’assistance pour la [CSimpleMap](../../atl/reference/csimplemap-class.md) classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Statique) Teste l’égalité de deux clés.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Statique) Retourne la valeur false.|  
  
## <a name="remarks"></a>Notes  
 Cette classe de traits constitue un supplément pour le `CSimpleMap` classe. Il fournit une méthode permettant de comparer deux éléments contenus dans le `CSimpleMap` objet, en particulier deux éléments de valeur ou les deux éléments clés.  
  
 La comparaison de valeur retournera toujours la valeur false et en outre, appelez `ATLASSERT` avec un argument False s’il est déjà référencé. Dans les situations où le test d’égalité n’est pas suffisamment défini, cette classe permet à une carte contenant des paires clé/valeur pour fonctionner correctement pour la plupart des méthodes, mais échouer de manière bien définie pour les méthodes qui dépendent des comparaisons telles que [CSimpleMap :: FindVal](../../atl/reference/csimplemap-class.md#findval).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>  CSimpleMapEqualHelperFalse::IsEqualKey  
 Teste l’égalité de deux clés.  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>Paramètres  
 *K1*  
 La première clé.  
  
 *K2*  
 La deuxième clé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si les clés sont égales, sinon false.  
  
### <a name="remarks"></a>Notes  
 Cette méthode appelle [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).  
  
##  <a name="isequalvalue"></a>  CSimpleMapEqualHelperFalse::IsEqualValue  
 Retourne false.  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne false.  
  
### <a name="remarks"></a>Notes  
 Cette méthode retourne toujours false et appellera `ATLASSERT` avec un argument False s’il est déjà référencé. L’objectif de `CSimpleMapEqualHelperFalse::IsEqualValue` consiste à forcer les méthodes à l’aide de comparaisons à échouer de manière bien définie lors de tests d’égalité n’ont pas été correctement définies.  
  
## <a name="see-also"></a>Voir aussi  
 [Csimplemapequalhelper, classe](../../atl/reference/csimplemapequalhelper-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
