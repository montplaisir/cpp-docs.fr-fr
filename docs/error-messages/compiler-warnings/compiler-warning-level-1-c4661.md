---
title: Compilateur avertissement (niveau 1) C4661 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4661
dev_langs:
- C++
helpviewer_keywords:
- C4661
ms.assetid: 603bb8b7-356d-4eef-924b-64d769bac5bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce88913a29dd9ec3f9d5d2e78c3e52ad3ead54fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280947"
---
# <a name="compiler-warning-level-1-c4661"></a>Avertissement du compilateur (niveau 1) C4661
'identificateur' : aucune définition appropriée pour la demande d’instanciation explicite du modèle  
  
 Un membre de la classe de modèle n’est pas défini.  
  
## <a name="example"></a>Exemple  
  
```  
// C4661.cpp  
// compile with: /W1 /LD  
template<class T> class MyClass {  
public:  
   void i();   // declaration but not definition  
};  
template MyClass< int >;  // C4661  
```