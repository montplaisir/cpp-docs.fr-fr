---
title: '&lt;hash_set&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_set>
- std::<hash_set>
dev_langs: C++
helpviewer_keywords: hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d19b48ef1ccf9e611d40781015c5e40ed3c3eb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;
> [!NOTE]
>  Cet en-tête est obsolète. L’alternative est [<unordered_set>](../standard-library/unordered-set.md).  
  
 Définit les classes de modèle de conteneur hash_set et hash_multiset et leurs modèles de prise en charge.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <hash_set>  
  
```  
  
## <a name="remarks"></a>Notes  
  
### <a name="operators"></a>Opérateurs  
  
|Version de hash_set|Version de hash_multiset|Description|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[operator!= (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|Teste si l’objet hash_set ou hash_multiset situé à gauche de l’opérateur n’est pas égal à l’objet hash_set ou hash_multiset situé à droite.|  
|[operator== (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[operator== (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|Teste si l’objet hash_set ou hash_multiset situé à gauche de l’opérateur est égal à l’objet hash_set ou hash_multiset situé à droite.|  
  
### <a name="specialized-template-functions"></a>Fonctions avec modèle spécialisé  
  
|Version de hash_set|Version de hash_multiset|Description|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_set)](../standard-library/hash-set-functions.md#swap)|[swap (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|Échange les éléments de deux objets hash_set ou hash_multiset.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[hash_compare, classe](../standard-library/hash-compare-class.md)|Décrit un objet qui peut être utilisé par les conteneurs associatifs de hachage, hash_map, hash_multimap, hash_set ou hash_multiset, comme objet de paramètre **Traits** par défaut pour ordonner et hacher les éléments qu’ils contiennent.|  
|[hash_set, classe](../standard-library/hash-set-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle les valeurs des éléments contenus sont uniques et servent de valeurs de clés.|  
|[hash_multiset, classe](../standard-library/hash-multiset-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle les valeurs des éléments contenus sont uniques et servent de valeurs de clés.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)


