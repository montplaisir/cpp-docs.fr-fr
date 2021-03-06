---
title: '&lt;map&gt;, fonctions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: 3c6cb7d0308e4bafc531fe0baf0c5d666228c3ec
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966366"
---
# <a name="ltmapgt-functions"></a>&lt;map&gt;, fonctions

|||
|-|-|
|[swap (map)](#swap)|[swap (multimap)](#swap_multimap)|

## <a name="swap_multimap"></a>  swap  (map)

Échange les éléments de deux classes map.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    map<Key, Traits, Compare, Alloctor>& left,
    map<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Paramètres

*droit* la carte qui fournit les éléments à échanger ou mappage dont les éléments doivent être échangés avec ceux du mappage *gauche*.

*gauche* la carte dont les éléments doivent être échangés avec ceux du mappage *droit*.

### <a name="remarks"></a>Notes

La fonction de modèle est un algorithme spécialisé sur la classe de conteneur map pour exécuter la fonction membre `left`.[ échange](../standard-library/map-class.md#swap)( `right`). Il s’agit d’une instance du classement partiel des modèles de fonction par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle, **template** \< **class T**> **void swap**( **T&**, **T&**), dans la classe d’algorithme fonctionne par assignation et est une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide, car elle peut fonctionner avec la représentation interne de la classe de conteneur.

### <a name="example"></a>Exemple

Pour obtenir un exemple qui utilise la version de modèle de `swap`, consultez l’exemple de code de la fonction membre [map::swap](../standard-library/map-class.md#swap).

## <a name="swap"></a>  swap  (multimap)

Échange les éléments de deux multimaps.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Paramètres

*droit* multimap qui fournit les éléments à échanger ou multimap dont les éléments doivent être échangés avec ceux du multimap *gauche*.

*gauche* multimap dont les éléments doivent être échangés avec ceux du multimap *droit*.

### <a name="remarks"></a>Notes

La fonction de modèle est un algorithme spécialisé sur la carte de classe de conteneur à exécuter sur la classe conteneur multimap pour exécuter la fonction membre `left`.[ échange](../standard-library/multimap-class.md#swap) (`right`). Il s’agit d’une instance du classement partiel des modèles de fonction par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle, **template** \< **class T**> **void swap**( **T&**, **T&**), dans la classe d’algorithme fonctionne par assignation et est une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide, car elle peut fonctionner avec la représentation interne de la classe de conteneur.

### <a name="example"></a>Exemple

Pour obtenir un exemple qui utilise la version de modèle de `swap`, consultez l’exemple de code de la fonction membre [multimap::swap](../standard-library/multimap-class.md#swap).

## <a name="see-also"></a>Voir aussi

[\<map>](../standard-library/map.md)<br/>
