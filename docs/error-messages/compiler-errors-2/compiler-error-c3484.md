---
title: Erreur du compilateur C3484 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3484
dev_langs:
- C++
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5de302987e4ea56e9ee6f29bed1b5842579a8f5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251954"
---
# <a name="compiler-error-c3484"></a>Erreur du compilateur C3484
'->' attendu avant le type de retour  
  
 Vous devez indiquer `->` avant le type de retour d’une expression lambda.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Indiquez `->` avant le type de retour.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3484 :  
  
```  
// C3484a.cpp  
  
int main()  
{  
   return []() . int { return 42; }(); // C3484  
}  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant résout l’erreur C3484 en fournissant `->` avant le type de retour de l’expression lambda :  
  
```  
// C3484b.cpp  
  
int main()  
{  
   return []() -> int { return 42; }();  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)