---
title: "Erreur du compilateur C2482 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2482"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2482"
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2482
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : initialisation dynamique de données 'thread' non autorisée  
  
 Les variables déclarées avec l'attribut `thread` ne peuvent être initialisées avec une expression demandant une évaluation au moment de l'exécution.  Une expression statique est requise pour initialiser les données `thread`.  
  
 L'exemple suivant génère l'erreur C2482 :  
  
```  
// C2482.cpp  
// compile with: /c  
#define Thread __declspec( thread )  
Thread int tls_i = tls_i;   // C2482  
  
int j = j;   // OK in C++; C error  
Thread int tls_i = sizeof( tls_i );   // Okay in C and C++  
```