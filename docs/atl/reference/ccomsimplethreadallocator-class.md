---
title: Ccomsimplethreadallocator, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2c571733aca48ddbfd881a294786d1de334c7c3
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884663"
---
# <a name="ccomsimplethreadallocator-class"></a>Ccomsimplethreadallocator, classe
Cette classe gère la sélection de thread pour la classe `CComAutoThreadModule`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComSimpleThreadAllocator
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComSimpleThreadAllocator::GetThread](#getthread)|Sélectionne un thread.|  
  
## <a name="remarks"></a>Notes  
 `CComSimpleThreadAllocator` gère la sélection de thread pour [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread` simplement parcourt chaque thread, puis retourne le suivant dans la séquence.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlbase.h  
  
##  <a name="getthread"></a>  CComSimpleThreadAllocator::GetThread  
 Sélectionne un thread en spécifiant le thread suivant dans la séquence.  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>Paramètres  
 *pApt*  
 Pas utilisé dans l’implémentation par défaut de d’ATL.  
  
 *nThreads*  
 Le nombre maximal de threads dans le module EXE.  
  
### <a name="return-value"></a>Valeur de retour  
 Un entier compris entre zéro et (*nThreads* - 1). Identifie un des threads dans le module EXE.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez remplacer `GetThread` pour fournir une autre méthode de sélection ou utiliser le *pApt* paramètre.  
  
 `GetThread` est appelée par [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).  
  
## <a name="see-also"></a>Voir aussi  
 [Ccomapartment, classe](../../atl/reference/ccomapartment-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
