---
title: "Erreur du compilateur C2761 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2761"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2761"
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2761
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : redéclaration de la fonction membre non autorisée  
  
 Vous ne pouvez pas redéclarer une fonction membre.  Vous pouvez la définir, mais pas la redéclarer.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2761 :  
  
```  
// C2761.cpp  
class a {  
   int t;  
   void test();  
};  
  
void a::a;     // C2761  
void a::test;  // C2761  
  
```  
  
## Exemple  
 Il n'est pas possible de définir les membres non statiques d'une classe ou d'une structure.  L'exemple suivant génère l'erreur C2761 :  
  
```  
// C2761_b.cpp  
// compile with: /c  
struct C {  
   int s;  
   static int t;  
};  
  
int C::s;   // C2761  
int C::t;   // OK  
```