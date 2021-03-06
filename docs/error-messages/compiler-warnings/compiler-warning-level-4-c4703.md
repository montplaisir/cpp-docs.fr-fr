---
title: Compilateur avertissement (niveau 4) C4703 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4703
dev_langs:
- C++
helpviewer_keywords:
- C4703
ms.assetid: 5dad454e-69e3-4931-9168-050a861c05f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d47cc6eb5692e39bfaa810bc15862bffb30083f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296105"
---
# <a name="compiler-warning-level-4-c4703"></a>Avertissement du compilateur (niveau 4) C4703
Potentiellement non initialisée variable de pointeur locale 'name' utilisé  
  
 La variable de pointeur locale *nom* a peut-être été utilisé sans assignée une valeur. Cela peut entraîner des résultats imprévisibles.  
  
## <a name="example"></a>Exemple  
 Le code suivant génère C4701 et C4703.  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr) // C4701 and C4703  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
```Output  
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used  
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used  
  
```  
  
 Pour corriger cet avertissement, initialisez la variable comme indiqué dans cet exemple :  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p = nullptr;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr)  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Compilateur avertissement (niveau 4) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)   
 [Avertissements, /sdl et amélioration de la détection des variable non initialisées](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)