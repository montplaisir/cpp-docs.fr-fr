---
title: '&lt;tuple&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <tuple>
dev_langs:
- C++
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ba25328b86a51e34cba60bd55b63ce2eab696d6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864582"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

Définit un modèle `tuple` dont les instances détiennent des objets de types variables.

## <a name="syntax"></a>Syntaxe

```cpp
#include <tuple>
```

### <a name="classes"></a>Classes

|Classe|Description|
|-|-|
|[tuple](../standard-library/tuple-class.md)|Encapsule une séquence d’éléments de longueur fixe.|
|[tuple_element, classe](../standard-library/tuple-element-class-tuple.md)|Encapsule le type d'un élément `tuple`.|
|[tuple_size, classe](../standard-library/tuple-size-class-tuple.md)|Encapsule le nombre d'éléments `tuple`.|

### <a name="operators"></a>Opérateurs

|Opérateur|Description|
|-|-|
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|Comparaison d’objets `tuple`, égal|
|[operator!=](../standard-library/tuple-operators.md#op_neq)|Comparaison d’objets `tuple`, non égal|
|[operator<](../standard-library/tuple-operators.md#op_lt)|Comparaison d’objets `tuple`, inférieur à|
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|Comparaison d’objets `tuple`, inférieur ou égal à|
|[operator>](../standard-library/tuple-operators.md#op_gt)|Comparaison d’objets `tuple`, supérieur à|
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|Comparaison d’objets `tuple`, supérieur ou égal à|

### <a name="functions"></a>Fonctions

|Fonction|Description|
|-|-|
|[get](../standard-library/tuple-functions.md#get)|Obtient un élément auprès d'un objet `tuple`.|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Crée un `tuple` à partir des valeurs de l’élément.|
|[tie](../standard-library/tuple-functions.md#tie)|Crée un `tuple` à partir des références d’élément.|

## <a name="see-also"></a>Voir aussi

[\<array>](../standard-library/array.md)<br/>
