---
title: "R&#233;sum&#233; des instructions | Microsoft Docs"
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
ms.assetid: ce45d2fe-ec0e-459f-afb1-80ab6a7f0239
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# R&#233;sum&#233; des instructions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*statement* :  
 *labeled\-statement*  
  
 *compound\-statement*  
  
 *expression\-statement*  
  
 *selection\-statement*  
  
 *iteration\-statement*  
  
 *jump\-statement*  
  
 *try\-except\-statement* \/\* Spécifique de Microsoft \*\/  
  
 *try\-finally\-statement* \/\* Spécifique de Microsoft \*\/  
  
 *jump\-statement* :  
 **goto**  *identifier*  **;**  
  
 **continue ;**  
  
 **break ;**  
  
 **return**  *expression* opt **;**  
  
 *compound\-statement* :  
 **{**  *declaration\-list* opt *statement\-list* opt **}**  
  
 *declaration\-list* :  
 *declaration*  
  
 *declaration\-list declaration*  
  
 *statement\-list* :  
 *instruction*  
  
 *statement\-list statement*  
  
 *expression\-statement* :  
 *expression* opt **;**  
  
 *iteration\-statement* :  
 **while \(**  *expression*  **\)**  *statement*  
  
 **do**  *statement*  **while \(**  *expression*  **\) ;**  
  
 **for \(**  *expression* opt **;** *expression* opt **;** *expression* opt **\)** *statement*  
  
 *selection\-statement* :  
 **if \(**  *expression*  **\)**  *statement*  
  
 **if \(**  *expression*  **\)**  *statement*  **else**  *statement*  
  
 **switch \(**  *expression*  **\)**  *statement*  
  
 *labeled\-statement* :  
 *identifier*  **:**  *statement*  
  
 **case**  *constant\-expression*  **:**  *statement*  
  
 **default :**  *statement*  
  
 *try\-except\-statement*:   \/\* Spécifique de Microsoft \*\/  
 **\_\_try**  *compound\-statement*  
  
 **\_\_except \(**  *expression*  **\)**  *compound\-statement*  
  
 *try\-finally\-statement*:   \/\* Spécifique de Microsoft \*\/  
 **\_\_try**  *compound\-statement*  
  
 **\_\_finally**  *compound\-statement*  
  
## Voir aussi  
 [Grammaire de la structure de la phrase](../c-language/phrase-structure-grammar.md)