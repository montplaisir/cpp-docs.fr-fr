---
title: "Erreur du compilateur C2081 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2081"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2081"
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2081
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : nom incorrect dans la liste de paramètres formels  
  
 L'identificateur a causé une erreur de syntaxe.  
  
 Cette erreur peut être générée en cas d'utilisation du style ancien pour la liste de paramètres formels.  Vous devez spécifier le type des paramètres dans la liste de paramètres formels.  
  
 L'exemple suivant génère l'erreur C2081 :  
  
```  
// C2081.c  
void func( int i, j ) {}  // C2081, no type specified for j  
```  
  
 Résolution possible :  
  
```  
// C2081b.c  
// compile with: /c  
void func( int i, int j ) {}  
```