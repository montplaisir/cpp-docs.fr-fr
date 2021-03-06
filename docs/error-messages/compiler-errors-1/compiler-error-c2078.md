---
title: Erreur du compilateur C2078 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2078
dev_langs:
- C++
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab44fd94f34f80623b58dea01eee4e0143b6dbc4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167068"
---
# <a name="compiler-error-c2078"></a>Erreur du compilateur C2078
initialiseurs trop nombreux  
  
 Le nombre d'initialiseurs dépasse le nombre d'objets à initialiser.  
  
 Le compilateur peut déduire l'affectation correcte des initialiseurs à des objets et à des objets internes quand les accolades internes sont omises de la liste des initialiseurs. L'utilisation d'accolades complètes élimine également toute ambiguïté et entraîne une attribution correcte. L'utilisation d'accolades partielles peut provoquer l'erreur C2078 en raison d'une ambiguïté dans l'attribution d'initialiseurs aux objets.  
  
 L'exemple suivant génère l'erreur C2078 et montre comment la corriger :  
  
```  
// C2078.cpp  
// Compile by using: cl /c /W4 C2078.cpp  
struct S {  
   struct {  
      int x, y;  
   } z[2];  
};  
  
int main() {  
   int d[2] = {1, 2, 3};   // C2078  
   int e[2] = {1, 2};      // OK  
  
   char a[] = {"a", "b"};  // C2078  
   char *b[] = {"a", "b"}; // OK  
   char c[] = {'a', 'b'};  // OK  
  
   S s1{1, 2, 3, 4};       // OK  
   S s2{{1, 2}, {3, 4}};   // C2078  
   S s3{{1, 2, 3, 4}};     // OK  
   S s4{{{1, 2}, {3, 4}}}; // OK  
}  
  
```