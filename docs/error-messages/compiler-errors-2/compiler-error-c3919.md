---
title: "Erreur du compilateur C3919 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3919"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3919"
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3919
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'méthode\_événement' : la fonction doit avoir le type 'type'  
  
 Une méthode d'accesseur d'événement n'a pas été déclarée correctement.  
  
 Pour plus d'informations sur les événements, consultez [event](../../windows/event-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3919 :  
  
```  
// C3919.cpp  
// compile with: /clr /c  
using namespace System;  
delegate void D(String^);  
ref class R {  
   event D^ e {  
      int add(int);   // C3919  
      int remove(int);   // C3919  
  
      void add(D^);   // OK  
      void remove(D^);   // OK  
   }  
};  
```