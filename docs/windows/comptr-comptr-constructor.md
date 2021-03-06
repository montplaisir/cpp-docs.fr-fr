---
title: Comptr::comptr, constructeur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr, constructor
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d08eb264ff3b4fc2f0170d6aee742ff29611613e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465368"
---
# <a name="comptrcomptr-constructor"></a>ComPtr::ComPtr, constructeur
Initialise une nouvelle instance de la **ComPtr** classe. Les surcharges fournissent des constructeurs par défaut, de copie, de déplacement et de conversion.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<class U>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<class U>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<class U>  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr<U>&& other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *U*  
 Le type de la *autres* paramètre.  
  
 *other*  
 Un objet de type *U*.  
  
## <a name="return-value"></a>Valeur de retour  
  
## <a name="remarks"></a>Notes  
 Le premier constructeur est le constructeur par défaut, l’implicitement crée un objet vide. Le deuxième constructeur spécifie [__nullptr](../windows/nullptr-cpp-component-extensions.md), ce qui crée explicitement un objet vide.  
  
 Le troisième constructeur crée un objet à partir de l’objet spécifié par un pointeur.  
  
 Les quatrième et cinquième constructeurs sont des constructeurs de copie. Le cinquième constructeur copie un objet s’il est converti vers le type actuel.  
  
 Les sixième et septième constructeurs sont des constructeurs de déplacement. Le septième constructeur déplace un objet s’il est converti vers le type actuel.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)