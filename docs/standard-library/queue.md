---
title: '&lt;queue&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<queue>
- std.<queue>
- <queue>
dev_langs:
- C++
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
caps.latest.revision: 20
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
ms.openlocfilehash: 8c2f3d928d305baa4fce49eb55ee8c6a65cd794b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="ltqueuegt"></a>&lt;queue&gt;
Définit les classes de modèle priority_queue et queue et plusieurs modèles de prise en charge.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <queue>  
  
```  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator!=](../standard-library/queue-operators.md#op_neq)|Teste si l'objet de file d'attente situé à gauche de l'opérateur n'est pas égal à l'objet de file d'attente situé à droite.|  
|[operator<](../standard-library/queue-operators.md#op_lt)|Teste si l'objet de file d'attente situé à gauche de l'opérateur est inférieur à l'objet de file d'attente situé à droite.|  
|[operator\<=](../standard-library/queue-operators.md#op_gt_eq)|Teste si l'objet de file d'attente situé à gauche de l'opérateur est inférieur ou égal à l'objet de file d'attente situé à droite.|  
|[operator==](../standard-library/queue-operators.md#op_eq_eq)|Teste si l'objet de file d'attente situé à gauche de l'opérateur est égal à l'objet de file d'attente situé à droite.|  
|[operator>](../standard-library/queue-operators.md#op_gt)|Teste si l'objet de file d'attente situé à gauche de l'opérateur est supérieur à l'objet de file d'attente situé à droite.|  
|[operator>=](../standard-library/queue-operators.md#op_gt_eq)|Teste si l'objet de file d'attente situé à gauche de l'opérateur est supérieur ou égal à l'objet de file d'attente situé à droite.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[queue, classe](../standard-library/queue-class.md)|Classe d'adaptateur de conteneur de modèle qui fournit une restriction de fonctionnalité limitant l'accès aux premier et dernier éléments d'un certain type de conteneur sous-jacent.|  
|[priority_queue, classe](../standard-library/priority-queue-class.md)|Classe d'adaptateur de conteneur de modèle qui fournit une restriction de fonctionnalité limitant l'accès à l'élément supérieur d'un certain type de conteneur sous-jacent, qui est toujours le plus grand.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)

