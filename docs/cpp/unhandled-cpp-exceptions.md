---
title: Les Exceptions C++ non gérées | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], unhandled exceptions
- catch keyword [C++], handler not found
- exceptions [C++], unhandled
- C++ exception handling, unhandled exceptions
- unhandled exceptions [C++]
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e2162034b3e9ff93ebccca0f7eb53299b19c648
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467977"
---
# <a name="unhandled-c-exceptions"></a>Exceptions C++ non gérées
Si un gestionnaire correspondant (ou points de suspension **catch** gestionnaire) est introuvable pour l’exception actuelle, le texte prédéfinie `terminate` fonction de l’exécution est appelée. (Vous pouvez également appeler explicitement `terminate` dans vos gestionnaires.) L'action par défaut de `terminate` est d'appeler `abort`. Si vous souhaitez `terminate` pour appeler une autre fonction dans votre programme avant de quitter l'application, appelez la fonction `set_terminate` avec le nom de la fonction à appeler comme unique argument. Vous pouvez appeler `set_terminate` à tout moment dans votre programme. Le `terminate` routine appelle toujours la dernière fonction donnée comme argument à `set_terminate`.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant lève une exception `char *`, mais ne contient pas de gestionnaire désigné pour intercepter des exceptions de type `char *`. L'appel à `set_terminate` indique à `terminate` d'appeler `term_func`.  
  
```cpp 
// exceptions_Unhandled_Exceptions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void term_func() {  
   cout << "term_func was called by terminate." << endl;  
   exit( -1 );  
}  
int main() {  
   try  
   {  
      set_terminate( term_func );  
      throw "Out of memory!"; // No catch handler for this exception  
   }  
   catch( int )  
   {  
      cout << "Integer exception raised." << endl;  
   }  
   return 0;  
}  
```  
  
## <a name="output"></a>Sortie  
  
```Output  
term_func was called by terminate.  
```  
  
 La fonction `term_func` doit terminer le programme ou le thread actuel, de préférence en appelant `exit`. Si elle ne fait pas cela et revient à la place à son appelant, la fonction `abort` est appelée.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion d’exceptions C++](../cpp/cpp-exception-handling.md)