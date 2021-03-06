---
title: is_trivially_assignable, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47fabb7120cc13eeca38bc9d06428f686fc9f1b9
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955564"
---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable, classe

Teste si une valeur de type `From` peut être affectée de façon triviale au type `To`.

## <a name="syntax"></a>Syntaxe

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>Paramètres

Pour le type de l’objet qui reçoit l’assignation.

À partir du type de l’objet qui fournit la valeur.

## <a name="remarks"></a>Notes

L’expression `declval<To>() = declval<From>()` doit être bien formée et le compilateur doit savoir qu’elle ne nécessite aucune opération non triviale. Les deux `From` et `To` doivent être des types complets, **void**, ou des tableaux de limite inconnue.

## <a name="requirements"></a>Configuration requise

**En-tête :** \<type_traits>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[<type_traits>](../standard-library/type-traits.md)<br/>
