---
title: "Erreur irr&#233;cup&#233;rable C1060 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1060"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1060"
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur irr&#233;cup&#233;rable C1060
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

espace du tas insuffisant pour le compilateur  
  
 Le système d'exploitation ou la bibliothèque Runtime ne peut pas répondre à une demande de mémoire.  
  
### Pour corriger cette erreur, essayez les solutions possibles suivantes  
  
1.  Si le compilateur émet aussi les erreurs [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) et [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md), utilisez l'option de compilateur [\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) pour abaisser la limite d'allocation de mémoire.  Si vous réduisez l'allocation de mémoire restante, l'espace du tas dont dispose votre application est plus important.  
  
     Si l'option [\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) est déjà définie, essayez de la supprimer.  Il se peut que l'espace du tas soit épuisé, car la limite d'allocation de mémoire spécifiée dans l'option est trop élevée.  Si vous supprimez l'option [\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md), le compilateur utilise une limite par défaut.  
  
2.  Si vous compilez sur une plateforme 64 bits, utilisez l'ensemble d'outils de compilateur 64 bits.  Pour plus d'informations, consultez [Comment : activer un ensemble d'outils du compilateur Visual C\+\+ 64 bits sur la ligne de commande](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  Sous Windows 32 bits, essayez d'utiliser le commutateur boot.ini [\/3GB](http://go.microsoft.com/fwlink/?LinkId=177831).  
  
4.  Augmentez la taille du fichier d'échange Windows.  
  
5.  Fermez les autres programmes en cours d'exécution.  
  
6.  Éliminez les fichiers include superflus.  
  
7.  Éliminez les variables globales inutiles, par exemple, en allouant la mémoire de façon dynamique au lieu de déclarer un grand tableau.  
  
8.  Éliminez les déclarations non utilisées.  
  
9. Fractionnez le fichier en cours en fichiers moins volumineux.