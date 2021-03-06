---
title: ComPtr::operator =, opérateur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fac3a845ea7c512f5a7ccffdabdf67ce26029ff8
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466161"
---
# <a name="comptroperator-operator"></a>ComPtr::operator=, opérateur
Assigne une valeur à actuel **ComPtr**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <typename U>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *U*  
 Une classe.  
  
 *other*  
 Un pointeur, une référence ou une référence rvalue à un type ou un autre **ComPtr**.  
  
## <a name="return-value"></a>Valeur de retour  
 Une référence à l’actuel **ComPtr**.  
  
## <a name="remarks"></a>Notes  
 La première version de cet opérateur assigne une valeur vide à actuel **ComPtr**.  
  
 Dans la deuxième version, si le pointeur d’interface affectation n’est pas le même que l’actuel **ComPtr** pointeur d’interface, le deuxième pointeur d’interface est affecté à l’actuel **ComPtr**.  
  
 Dans la troisième version, le pointeur d’interface affectation est affecté au actuel **ComPtr**.  
  
 Dans la quatrième version, si le pointeur d’interface de la valeur d’assignation n’est pas le même que l’actuel **ComPtr** pointeur d’interface, le deuxième pointeur d’interface est affecté à l’actuel **ComPtr**.  
  
 La cinquième version est un opérateur copie ; une référence à un **ComPtr** est affectée à l’actuel **ComPtr**.  
  
 La sixième version est un opérateur de copie qui utilise la sémantique ; de déplacement une référence rvalue à un **ComPtr** si n’importe quel type est statique, effectuer un cast, puis affecté au cours **ComPtr**.  
  
 La septième version est un opérateur de copie qui utilise la sémantique ; de déplacement une référence rvalue à un **ComPtr** de type *U* est statique converti puis et assignée à actuel **ComPtr**.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)