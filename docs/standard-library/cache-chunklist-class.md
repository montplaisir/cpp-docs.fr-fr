---
title: cache_chunklist, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_chunklist
- stdext::cache_chunklist
- cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- cache_chunklist class
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 283186349d84225fdf9d1d52ec04817a12f3d27f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="cachechunklist-class"></a>cache_chunklist, classe
Définit un [allocateur de blocs](../standard-library/allocators-header.md) qui alloue et désalloue des blocs de mémoire de taille unique.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <std::size_t Sz, std::size_t Nelts = 20>  
class cache_chunklist
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Sz`|Nombre d’éléments du tableau à allouer.|  
  
## <a name="remarks"></a>Notes  
 Cette classe de modèle utilise `operator new` pour allouer des segments de mémoire brute et sous-alloue des blocs pour allouer du stockage à un bloc de mémoire si nécessaire ; elle stocke des blocs de mémoire désalloués dans une liste de libération séparée pour chaque segment et utilise `operator delete` pour désallouer un segment quand aucun de ses blocs de mémoire n’est utilisé.  
  
 Chaque bloc de mémoire contient `Sz` octets de mémoire utilisable et un pointeur vers le segment auquel il appartient. Chaque segment contient `Nelts` blocs de mémoire, trois pointeurs, un entier et les données dont `operator new` et `operator delete` ont besoin.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[cache_chunklist](#cache_chunklist)|Construit un objet de type `cache_chunklist`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[allocate](#allocate)|Alloue un bloc de mémoire.|  
|[deallocate](#deallocate)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="allocate"></a>  cache_chunklist::allocate  
 Alloue un bloc de mémoire.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`count`|Nombre d’éléments du tableau à allouer.|  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’objet alloué.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="cache_chunklist"></a>  cache_chunklist::cache_chunklist  
 Construit un objet de type `cache_chunklist`.  
  
```
cache_chunklist();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="deallocate"></a>  cache_chunklist::deallocate  
 Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`ptr`|Pointeur vers le premier objet à désallouer dans le stockage.|  
|`count`|Nombre d’objets à désallouer dans le stockage.|  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)



