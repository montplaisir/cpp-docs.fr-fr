---
title: Erreur du compilateur C2231 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2231
dev_langs:
- C++
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 223af570c50bd4918e9b136c30e9e97971739752
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-error-c2231"></a>Erreur du compilateur C2231
'.' : opérande gauche pointe vers 'clé-classe', utilisez '->'  
  
 L’opérande à gauche de l’opération de sélection de membres (.) est un pointeur au lieu d’une classe, structure ou union.  
  
 L’exemple suivant génère l’erreur C2231 :  
  
```  
// C2231.c  
struct S {  
   int member;  
} s, *ps = &s;  
int main() {  
   ps.member = 0;   // C2231  
  
   // OK  
   ps->member = 0;   // crash  
   s.member = 0;  
}  
```