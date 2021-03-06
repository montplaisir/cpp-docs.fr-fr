---
title: Asyncbase::Start, méthode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ab47405f81cf6fb92af215f1868d8ad7c42bffa7
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463728"
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start, méthode
Démarre l’opération asynchrone.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération démarre ou est déjà démarré ; Sinon, E_ILLEGAL_STATE_CHANGE.  
  
## <a name="remarks"></a>Notes  
 **Start()** est une implémentation par défaut de `IAsyncInfo::Start`, et n’effectue aucun travail réel. Pour lancer une opération asynchrone, remplacer le `OnStart()` méthode virtuelle pure.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** async.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)