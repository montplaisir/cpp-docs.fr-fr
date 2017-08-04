---
title: "Addition (+) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pointeurs, ajouter des entiers"
ms.assetid: b9014fee-825d-46ef-91db-5d46807081fc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Addition (+)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'opérateur d'addition \(**\+**\) génère l'addition de ses deux opérandes.  Les deux opérandes peuvent être des types intégraux ou flottants, ou un opérande peut être un pointeur et l'autre un entier.  
  
 Lorsqu'un entier est ajouté à un pointeur, la valeur entière \(*i*\) est convertie en la multipliant par la taille de la valeur que le pointeur adresse.  Après la conversion, la valeur entière représente les emplacements de mémoire *\- i*, où chaque position a une longueur spécifiée par le type pointeur.  Lorsque la valeur entière convertie est ajoutée à la valeur du pointeur, il en résulte une nouvelle valeur de pointeur représentant les positions de l'adresse *i* par rapport à l'adresse d'origine.  La nouvelle valeur de pointeur adresse une valeur du même type que la valeur de pointeur d'origine. Par conséquent, elle est identique à l'indexation de tableau \(consultez [Tableaux unidimensionnels](../c-language/one-dimensional-arrays.md) et [Tableaux multidimensionnels](../c-language/multidimensional-arrays-c.md)\).  Si le pointeur de somme passe hors du tableau, sauf au premier emplacement après l'extrémité supérieure, le résultat n'est pas défini.  Pour plus d'informations, consultez [Opérations arithmétiques sur les pointeurs](../c-language/pointer-arithmetic.md).  
  
## Voir aussi  
 [Opérateurs additifs C](../c-language/c-additive-operators.md)