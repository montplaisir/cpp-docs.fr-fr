---
title: '&lt;unordered_map&gt;, fonctions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- unordered_map/std::swap
- unordered_map/std::swap (unordered_map)
- unordered_map/std::swap (unordered_multimap)
dev_langs:
- C++
ms.assetid: cf2e4115-f205-4a0e-90be-a143ffcc1f44
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::swap (unordered_map/multimap)
ms.workload:
- cplusplus
ms.openlocfilehash: 76210e9ae860f8a7de0f22db2b7108e90e09e5be
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965550"
---
# <a name="ltunorderedmapgt-functions"></a>&lt;unordered_map&gt;, fonctions

|||
|-|-|
|[swap (unordered_map)](#swap)|[swap (unordered_multimap)](#swap_function_multimap)|

## <a name="swap"></a>  swap (unordered_map)

Échange le contenu de deux conteneurs.

```cpp
template <class Key, class Ty, class Hash, class Pred, class Alloc>
void swap(
    unordered_map <Key, Ty, Hash, Pred, Alloc>& left,
    unordered_map <Key, Ty, Hash, Pred, Alloc>& right);
```

### <a name="parameters"></a>Paramètres

*Key*  
 Type de clé.

*Ty*  
 Type mappé.

*hachage*  
 Type d'objet de la fonction de hachage.

*Pred*  
 Type d’objet de fonction de comparaison d’égalité.

*Alloc*  
 Classe allocator.

*left*  
 Premier conteneur à échanger.

*right*  
 Second conteneur à échanger.

### <a name="remarks"></a>Notes

La fonction de modèle exécute `left.`[unordered_map::swap](../standard-library/unordered-map-class.md#swap)`(right)`.

### <a name="example"></a>Exemple

```cpp
// std__unordered_map__u_m_swap.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_map<char, int> Mymap;
int main()
    {
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    Mymap c2;

    c2.insert(Mymap::value_type('d', 4));
    c2.insert(Mymap::value_type('e', 5));
    c2.insert(Mymap::value_type('f', 6));

    c1.swap(c2);

// display contents " [f 6] [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    swap(c1, c2);

// display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
    }

```

```Output
[c, 3] [b, 2] [a, 1]
[f, 6] [e, 5] [d, 4]
[c, 3] [b, 2] [a, 1]
```

## <a name="swap_function_multimap"></a>  swap (unordered_multimap)

Échange le contenu de deux conteneurs.

```cpp
template <class Key, class Ty, class Hash, class Pred, class Alloc>
void swap(
    unordered_multimap <Key, Ty, Hash, Pred, Alloc>& left,
    unordered_multimap <Key, Ty, Hash, Pred, Alloc>& right);
```

### <a name="parameters"></a>Paramètres

*Key*  
 Type de clé.

*Ty*  
 Type mappé.

*hachage*  
 Type d'objet de la fonction de hachage.

*Pred*  
 Type d’objet de fonction de comparaison d’égalité.

*Alloc*  
 Classe allocator.

*left*  
 Premier conteneur à échanger.

*right*  
 Second conteneur à échanger.

### <a name="remarks"></a>Notes

La fonction de modèle exécute `left.`[unordered_multimap::swap](../standard-library/unordered-multimap-class.md#swap)`(right)`.

### <a name="example"></a>Exemple

```cpp
// std__unordered_map__u_mm_swap.cpp
// compile with: /EHsc
#include <unordered_map>
#include <iostream>

typedef std::unordered_multimap<char, int> Mymap;
int main()
{
    Mymap c1;

    c1.insert(Mymap::value_type('a', 1));
    c1.insert(Mymap::value_type('b', 2));
    c1.insert(Mymap::value_type('c', 3));

    // display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    Mymap c2;

    c2.insert(Mymap::value_type('d', 4));
    c2.insert(Mymap::value_type('e', 5));
    c2.insert(Mymap::value_type('f', 6));

    c1.swap(c2);

    // display contents " [f 6] [e 5] [d 4]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents " [c 3] [b 2] [a 1]"
    for (Mymap::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << it->first << ", " << it->second << "]";
    std::cout << std::endl;

    return (0);
}

```

```Output
[c, 3] [b, 2] [a, 1]
[f, 6] [e, 5] [d, 4]
[c, 3] [b, 2] [a, 1]
```

## <a name="see-also"></a>Voir aussi

[<unordered_map>](../standard-library/unordered-map.md)<br/>
