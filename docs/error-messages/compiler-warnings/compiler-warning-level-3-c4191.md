---
title: Compilateur avertissement (niveau 3) C4191 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4191
dev_langs:
- C++
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
caps.latest.revision: 11
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
ms.openlocfilehash: 5cdd66e6318867a7f4df8ff70b6440ae6e7bfa3a
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4191"></a>Avertissement du compilateur (niveau 3) C4191
'operator/operation' : conversion risquée de 'type of expression' en 'type required'  
  
 Plusieurs opérations faisant appel à des pointeurs fonction sont considérées comme non sécurisées :  
  
-   Types de fonction avec conventions d’appel différentes.  
  
-   Types de fonction avec conventions de retour différentes.  
  
-   Types d’argument ou de retour de différentes tailles, catégories de types ou classifications.  
  
-   Longueurs des listes d’arguments différentes (sur `__cdecl`, le cast de type n’est effectué que de la liste la plus longue vers la liste la plus courte, même si la plus courte est déclarée varargs).  
  
-   Pointeur vers des données (autre que **void\***) utilisé comme alias d’un pointeur vers une fonction.  
  
-   Toute autre différence de type pouvant conduire à une erreur ou un avertissement sur un `reinterpret_cast`.  
  
 L’appel de cette fonction par le pointeur résultat peut bloquer votre programme.  
  
 Cet avertissement est désactivé par défaut. Consultez [avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d’informations.  
  
 L’exemple suivant génère l’avertissement C4191.  
  
```  
// C4191.cpp  
// compile with: /W3 /clr  
#pragma warning(default: 4191)  
  
void __clrcall f1() { }  
void __cdecl   f2() { }  
  
typedef void (__clrcall * fnptr1)();  
typedef void (__cdecl   * fnptr2)();  
  
int main() {  
   fnptr1 fp1 = static_cast<fnptr1>(&f1);  
   fnptr2 fp2 = (fnptr2) &f2;  
  
   fnptr1 fp3 = (fnptr1) &f2;   // C4191  
   fnptr2 fp4 = (fnptr2) &f1;   // C4191  
};  
```