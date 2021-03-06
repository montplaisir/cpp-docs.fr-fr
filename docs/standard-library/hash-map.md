---
title: '&lt;hash_map&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caae1a52c36c5d21e55e90a821b280f2face7ede
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959772"
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Cet en-tête est obsolète. L’alternative est [ \<unordered_map >](unordered-map.md).

Définit les classes de modèle de conteneur hash_map et hash_multimap et leurs modèles de prise en charge.

## <a name="syntax"></a>Syntaxe

> #<a name="include-hashmap"></a>inclure < hash_map >

### <a name="operators"></a>Opérateurs

|Version de hash_map|Version de hash_multimap|Description|
|-----------------------|----------------------------|-----------------|
|[operator!= (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|Teste si l’objet hash_map ou hash_multimap situé à gauche de l’opérateur n’est pas égal à l’objet hash_map ou hash_multimap situé à droite.|
|[operator== (hash_map)](hash-map-operators.md#op_eq_eq)|[operator== (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|Teste si l’objet hash_map ou hash_multimap situé à gauche de l’opérateur est égal à l’objet hash_map ou hash_multimap situé à droite.|

### <a name="specialized-template-functions"></a>Fonctions avec modèle spécialisé

|Version de hash_map|Version de hash_multimap|Description|
|-----------------------|----------------------------|-----------------|
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|Échange les éléments de deux objets hash_maps ou hash_multimaps.|

### <a name="classes"></a>Classes

|Classe|Description|
|-|-|
|[hash_compare, classe](hash-compare-class.md)|Décrit un objet qui peut être utilisé par les conteneurs associatifs de hachage de, hash_map, hash_multimap, hash_set ou hash_multiset, comme une valeur par défaut `Traits` objet de paramètre pour ordonner et hacher les éléments qu’ils contiennent.|
|[value_compare, classe](value-compare-class.md)|Fournit un objet de fonction qui peut comparer les éléments d’un hash_map en comparant les valeurs de leurs clés pour déterminer leur ordre relatif dans le hash_map.|
|[hash_map, classe](hash-map-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle chaque élément est une paire qui a une clé de tri dont la valeur est unique et une valeur de données associée.|
|[hash_multimap, classe](hash-multimap-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle chaque élément est une paire qui a une clé de tri dont la valeur ne doit pas nécessairement être unique et une valeur de données associée.|

## <a name="requirements"></a>Configuration requise

**En-tête :** \<hash_map>

**Espace de noms :** stdext

## <a name="see-also"></a>Voir aussi

[Fichiers d’en-tête référence](cpp-standard-library-header-files.md)
[sécurité des threads dans la bibliothèque Standard C++](thread-safety-in-the-cpp-standard-library.md)
[référence de la bibliothèque C++ Standard](cpp-standard-library-reference.md)
