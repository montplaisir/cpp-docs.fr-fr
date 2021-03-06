---
title: iterator, struct | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a399fa8a9f8fc9a73d75605f31245e42a2154b7c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963626"
---
# <a name="iterator-struct"></a>iterator, struct

Struct de base vide permettant de garantir qu’une classe d’itérateur définie par l’utilisateur fonctionne correctement avec `iterator_trait`s.

## <a name="syntax"></a>Syntaxe

```cpp
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };
```

## <a name="remarks"></a>Notes

Le struct de modèle sert de type de base pour tous les itérateurs. Il définit les types de membres

- `iterator_category` (synonyme du paramètre du modèle `Category`).

- `value_type` (synonyme du paramètre du modèle `Type`).

- `difference_type` (synonyme du paramètre du modèle `Distance`).

- `distance_type` (synonyme du paramètre du modèle `Distance`)

- `pointer` (synonyme du paramètre du modèle `Pointer`).

- `reference` (synonyme du paramètre du modèle `Reference`).

Notez que `value_type` ne doit pas être une constante de type, même lorsque `pointer` pointe vers un objet de **const** `Type` et référence désigne un objet de **const** `Type`.

## <a name="example"></a>Exemple

Pour obtenir un exemple montrant comment déclarer et utiliser les types de la classe de base iterator, consultez [iterator_traits](../standard-library/iterator-traits-struct.md).

## <a name="requirements"></a>Configuration requise

**En-tête :** \<iterator>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[\<iterator>](../standard-library/iterator.md)<br/>
[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)<br/>
