---
title: "Avertissement du compilateur (niveau 3) C4390 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4390"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4390"
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau 3) C4390
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

';' : une instruction contrôlée a été trouvée vide ; est\-ce ce que vous souhaitiez ?  
  
 Un point\-virgule a été trouvé après une expression de contrôle qui ne contient aucune instruction.  
  
 Si vous obtenez C4390 à cause d'une macro, vous devriez utiliser le pragma [warning](../../preprocessor/warning.md) pour désactiver C4390 dans le module qui contient la macro.  
  
 L'exemple suivant génère l'erreur C4390 :  
  
```  
// C4390.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
   if (i);   // C4390  
      i++;  
}  
```