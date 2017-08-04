---
title: "Avertissement du compilateur (niveau 1) C4319 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4319"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4319"
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4319
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : zéro étendant 'type' vers 'type' d'une taille supérieure  
  
 Le résultat de l'opérateur ~ \(complément au niveau du bit\) est non signé, puis étendu par zéro quand il est converti en un type plus grand.  
  
 Dans l'exemple suivant, ~\(a \- 1\) est évalué comme une expression de type long non signée 32 bits, qui est ensuite convertie au format 64 bits par extension avec des zéros.  Cela peut entraîner des résultats d'opération inattendus.  
  
```  
// C4319.cpp  
// compile with: cl /W4 C4319.cpp  
int main() {  
   unsigned long a = 0;  
   unsigned long long q = 42;  
   q = q & ~(a - 1);    // C4319 expected  
}  
```