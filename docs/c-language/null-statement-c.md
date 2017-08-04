---
title: "null, instruction (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "expressions (C++), null"
  - "instruction null"
  - "valeurs null, expressions"
  - "point-virgule, instruction null C"
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# null, instruction (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une « instruction null » est une instruction contenant uniquement un point\-virgule ; elle peut figurer partout où une instruction est attendue.  Rien ne se produit lorsqu'une instruction null est exécutée.  La façon correcte de coder une instruction null est :  
  
## Syntaxe  
  
```  
  
;  
  
```  
  
## Notes  
 Les instructions telles que **do**, **for**, **if** et `while` requièrent qu'une instruction exécutable apparaissent comme corps d'instruction.  L'instruction null répond à la syntaxe requise dans les situations qui ne nécessitent pas de corps d'instruction substantiel.  
  
 Comme pour toute autre instruction C, vous pouvez inclure une étiquette avant une instruction null.  Pour étiqueter un élément qui n'est pas une instruction, telle que l'accolade fermante d'une instruction composée, vous pouvez étiqueter une instruction null et l'insérer immédiatement avant l'élément pour obtenir le même effet.  
  
 L'exemple suivant illustre l'instruction null :  
  
```  
for ( i = 0; i < 10; line[i++] = 0 )  
     ;  
```  
  
 Dans cet exemple, l'expression de boucle de l'instruction **for** `line[i++] = 0` for initialise les 10 premiers éléments de `line` à 0.  Le corps d'instruction est une instruction null, car aucune autre instruction n'est nécessaire.  
  
## Voir aussi  
 [Instructions](../c-language/statements-c.md)