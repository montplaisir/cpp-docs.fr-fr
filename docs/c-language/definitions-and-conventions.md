---
title: "D&#233;finitions et conventions | Microsoft Docs"
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
  - "définition des éléments non terminaux"
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finitions et conventions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les terminaux sont des points de terminaison dans une définition de syntaxe.  Aucune autre résolution n'est possible.  Les terminaux incluent l'ensemble des mots réservés et des identificateurs définis par l'utilisateur.  
  
 Les non terminaux sont des espaces réservés dans la syntaxe qui sont définis ailleurs dans ce résumé de syntaxe.  Les définitions peuvent être récursives.  
  
 Un composant facultatif est indiqué par l'élément opt indicé.  Par exemple :  
  
```  
  
{ expression <SUB>opt</SUB> }  
```  
  
 indique une expression facultative entre accolades.  
  
 Les conventions syntaxiques utilisent différents attributs de police pour différents composants de la syntaxe.  Les symboles et les polices sont comme suit :  
  
|Attribut|Description|  
|--------------|-----------------|  
|*nonterminal*|Le type italique indique des symboles non terminaux.|  
|**const**|Les symboles terminaux en gras sont des mots réservés littéraux et des symboles littéraux qui doivent être écrits comme indiqué.  Les caractères situés dans ce contexte respectent toujours la casse.|  
|option|Les symboles non terminaux suivis de l'indication « option » sont toujours facultatifs.|  
|police par défaut|Les caractères dans le jeu décrit ou répertorié dans cette police peuvent être utilisés comme terminaux dans les instructions C.|  
  
 Un signe deux\-points \(**:**\) qui suit un symbole non terminal introduit sa définition.  Les définitions alternatives figurent sur des lignes distinctes, sauf lorsqu'elles sont précédées des mots « one of ».  
  
## Voir aussi  
 [Résumé de la syntaxe du langage C](../c-language/c-language-syntax-summary.md)