---
title: "Erreur du compilateur C2754 | Microsoft Docs"
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
  - "C2754"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2754"
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2754
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'spécialisation' : une spécialisation partielle ne peut pas avoir un paramètre de modèle sans type dépendant  
  
 Vous avez tenté de partiellement spécialiser une classe de modèle ayant un paramètre de modèle sans type dépendant.  Cela n'est pas autorisé.  
  
 L'exemple suivant génère l'erreur C2754 :  
  
```  
// C2754.cpp  
// compile with: /c  
  
template<class T, T t>  
struct A {};  
  
template<class T, int N>  
struct B {};  
  
template<class T> struct A<T,5> {};   // C2754  
template<> struct A<int,5> {};   // OK  
template<class T> struct B<T,5> {};   // OK  
```