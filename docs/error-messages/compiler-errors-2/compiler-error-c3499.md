---
title: Erreur du compilateur C3499 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3499
dev_langs:
- C++
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: a0e4f471b75c39a11ac5684c7c1826321629befe
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3499"></a>Erreur du compilateur C3499
une expression lambda dont le type de retour spécifié est void ne peut pas retourner de valeur  
  
 Le compilateur génère cette erreur quand une expression lambda qui spécifie `void` comme type de retour retourne une valeur, ou quand une expression lambda contient plusieurs instructions et retourne une valeur, mais ne spécifie pas son type de retour.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Ne retournez pas une valeur à partir de l’expression lambda ; ou  
  
-   Fournissez le type de retour de l’expression lambda ; ou  
  
-   Combinez les instructions qui composent le corps de l’expression lambda dans une instruction unique.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3499, car le corps d’une expression lambda contient plusieurs instructions et retourne une valeur, mais l’expression lambda ne spécifie pas le type de retour :  
  
```  
// C3499a.cpp  
  
int main()  
{  
   [](int x) { int n = x * 2; return n; } (5); // C3499  
}  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre deux résolutions possibles pour l’erreur C3499. La première résolution fournit le type de retour de l’expression lambda. La seconde résolution combine les instructions qui composent le corps de l’expression lambda dans une instruction unique.  
  
```  
// C3499b.cpp  
  
int main()  
{  
   // Possible resolution 1:   
   // Provide the return type of the lambda expression.  
   [](int x) -> int { int n = x * 2; return n; } (5);  
  
   // Possible resolution 2:   
   // Combine the statements that make up the body of   
   // the lambda expression into a single statement.  
   [](int x) { return x * 2; } (5);  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)