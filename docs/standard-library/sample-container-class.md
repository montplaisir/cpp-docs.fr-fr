---
title: sample container, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- container classes
f1_keywords: []
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
caps.latest.revision: 10
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 0f45ecbb6746c8d660e699ac0f7c08ecfb5dbb68
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="sample-container-class"></a>sample container, classe
> [!NOTE]
>  Cette rubrique fait partie de la documentation Visual C++. Elle fournit un exemple non opérationnel de conteneurs utilisés dans la bibliothèque standard C++. Pour plus d’informations, consultez [Conteneurs disponibles dans la bibliothèque standard C++](../standard-library/stl-containers.md).  
  
 Décrit un objet qui contrôle une séquence de longueur variable constituée d’éléments ayant généralement le type **Ty**. La séquence est stockée de différentes manières en fonction du conteneur utilisé.  
  
 Un constructeur conteneur ou une fonction membre peut trouver l’occasion d’appeler le constructeur **Ty**(**const Ty&**) ou la fonction **Ty::operator=**(**const Ty&**). Si cet appel lève une exception, l’objet conteneur est tenu de maintenir son intégrité et de lever toute autre exception interceptée. Vous pouvez en toute sécurité échanger, assigner, effacer ou détruire un objet conteneur qui a levé l’une de ces exceptions. En général, vous ne pouvez toutefois pas prédire l’état de la séquence contrôlée par l’objet conteneur.  
  
 Voici quelques avertissements supplémentaires :  
  
-   Si l’expression **~Ty** lève une exception, l’état résultant de l’objet conteneur n’est pas défini.  
  
-   Si le conteneur stocke un objet allocateur *al* et que l’objet *al* lève une exception qui n’est pas le résultat d’un appel à *al***.allocate**, l’état résultant de l’objet conteneur n’est pas défini.  
  
-   Si le conteneur stocke un objet fonction *comp* pour déterminer comment ordonner la séquence contrôlée et que l’objet *comp* lève une exception quelconque, l’état résultant de l’objet conteneur n’est pas défini.  
  
 Les classes de conteneur définies dans la bibliothèque standard C++ satisfont plusieurs conditions supplémentaires, comme cela est décrit dans les paragraphes suivants.  
  
 La classe de modèle de conteneur [list](../standard-library/list-class.md) fournit un comportement déterministe et utile, même en présence des exceptions décrites ci-dessus. Par exemple, si une exception est levée au moment de l’insertion d’un ou de plusieurs éléments, le conteneur n’est pas modifié et l’exception est levée une nouvelle fois.  
  
 Pour *toutes* les classes de conteneur définies dans la bibliothèque standard C++, si une exception est levée pendant les appels aux fonctions membres ci-dessous, le comportement est le suivant :  
  
```  
<A NAME="vclrfcontainerinsert"></A>insert // single element inserted  
<A NAME="vclrfcontainerpushback"></A>push_back  
<A NAME="vclrfcontainerpushfront"></A>push_front  
```  
  
 Le conteneur n’est pas modifié et l’exception est levée une nouvelle fois.  
  
 Pour *toutes* les classes de conteneur définies dans la bibliothèque standard C++, aucune exception n’est levée pendant les appels aux fonctions membres ci-dessous :  
  
```  
<A NAME="vclrfcontainerpopback"></A>pop_back  
<A NAME="vclrfcontainerpopfront"></A>pop_front  
```  
  
 La fonction membre [erase](../standard-library/container-class-erase.md) lève une exception uniquement si une opération de copie (construction assignment ou copy) lève une exception.  
  
 En outre, aucune exception n’est levée pendant la copie d’un itérateur retourné par une fonction membre.  
  
 La fonction membre [swap](../standard-library/container-class-swap.md) ajoute des promesses pour *toutes* les classes de conteneur définies dans la bibliothèque standard C++  :  
  
-   La fonction membre lève une exception uniquement si le conteneur stocke un objet allocateur al, et `al` lève une exception à la fin de la copie.  
  
-   Les références, pointeurs et itérateurs qui désignent les éléments des séquences contrôlées permutées restent valides.  
  
 Un objet d’une classe de conteneur définie dans la bibliothèque standard C++ alloue et libère du stockage pour la séquence qu’il contrôle via un objet stocké de type `Alloc` (en règle générale, un paramètre de modèle). Cet objet allocateur doit avoir la même interface externe qu’un objet de classe **allocator\<Ty>**. En particulier, `Alloc` doit avoir un type identique à **Alloc::rebind<value_type>::other**  
  
 Pour *toutes* les classes de conteneur définies dans la bibliothèque standard C++, la fonction membre **Alloc get_allocator const;** retourne une copie de l’objet allocateur stocké. Notez que l’objet allocateur stocké n’est *pas* copié quand l’objet conteneur est assigné. Tous les constructeurs initialisent la valeur stockée dans **allocateur** à `Alloc` si le constructeur ne contient aucun paramètre d’allocateur.  
  
 Selon la norme C++, une classe de conteneur définie dans la bibliothèque standard C++ effectue les suppositions suivantes :  
  
-   Tous les objets de la classe `Alloc` sont comparés sur une base égale.  
  
-   Le type **Alloc::const_pointer** est identique à **const Ty \***.  
  
-   Le type **Alloc::const_reference** est identique à **const Ty&**.  
  
-   Le type **Alloc::pointer** est identique à **Ty \***.  
  
-   Le type **Alloc::reference** est identique à **Ty&**.  
  
 Dans cette implémentation, cependant, les conteneurs ne font pas de telles suppositions de simplification. Par conséquent, ils fonctionnent correctement avec des objets allocateurs plus complexes :  
  
-   Tous les objets de la classe `Alloc` ne sont pas forcément comparés sur une base égale. (Vous pouvez conserver plusieurs pools de stockage.)  
  
-   Le type **Alloc::const_pointer** n’est pas forcément identique à **const Ty \***. (Un pointeur const peut être une classe.)  
  
-   Le type **Alloc::pointer** n’est pas forcément identique à **Ty \***. (Un pointeur peut être une classe.)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête** : \<sample container>  
  
## <a name="see-also"></a>Voir aussi  
 [\<sample container>](../standard-library/sample-container.md)

