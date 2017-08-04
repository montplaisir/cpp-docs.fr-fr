---
title: '&lt;set&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
caps.latest.revision: 7
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 6c26128064b2f20a55ab1b9d1c013829e72523e0
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="ltsetgt-functions"></a>&lt;set&gt;, fonctions
|||  
|-|-|  
|[swap (map)](#swap)|[swap (multiset)](#swap_multiset)|  
  
##  <a name="swap"></a>  swap  (map)
 Échange les éléments de deux classes set.  
  
```
template <class Key, class Traits, class Allocator>  
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 set qui fournit les éléments à échanger ou set dont les éléments doivent être échangés avec ceux du set `left`.  
  
 `left`  
 set dont les éléments doivent être échangés avec ceux du set `right`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle est un algorithme spécialisé sur la classe de conteneur set pour exécuter la fonction membre `left``.`[swap](../standard-library/set-class.md#swap)( `right`). Il s’agit d’une instance du classement partiel des modèles de fonction par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle  
  
 `template` \< **classT**> **void swap**( **T&**, **T&**)  
  
 dans la classe d’algorithme fonctionne par assignation. C’est une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide, car elle peut fonctionner avec la représentation interne de la classe conteneur.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple d’utilisation de la version de modèle de `swap`, consultez l’exemple de code pour la classe membre [set::swap](../standard-library/set-class.md#swap).  
  
##  <a name="swap_multiset"></a>  swap  (multiset)
 Échange les éléments de deux classes multiset.  
  
```
template <class Key, class Traits, class Allocator>  
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 multiset qui fournit les éléments à échanger ou multiset dont les éléments doivent être échangés avec ceux du multiset `left`.  
  
 `left`  
 multiset dont les éléments doivent être échangés avec ceux du multiset `right`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle est un algorithme spécialisé sur la classe de conteneur multiset pour exécuter la fonction membre `left``.`[swap](../standard-library/multiset-class.md#swap)( `right`). Il s’agit d’une instance du classement partiel des modèles de fonction par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle  
  
 `template` \< **classT**> **void swap**( **T&**, **T&**)  
  
 dans la classe d’algorithme fonctionne par assignation. C’est une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide, car elle peut fonctionner avec la représentation interne de la classe conteneur.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple d’utilisation de la version de modèle de `swap`, consultez l’exemple de code pour la classe membre [multiset::swap](../standard-library/multiset-class.md#swap).  
  
## <a name="see-also"></a>Voir aussi  
 [\<set>](../standard-library/set.md)



