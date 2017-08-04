---
title: "R&#233;solution de surcharge des appels de mod&#232;les de fonctions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "résolution de surcharge des modèles de fonctions"
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# R&#233;solution de surcharge des appels de mod&#232;les de fonctions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un modèle de fonction peut surcharger des fonctions non basées sur un modèle du même nom.  Dans ce scénario, les appels de fonction sont résolus d'abord en utilisant la déduction de l'argument template pour instancier le modèle de fonction avec une seule spécialisation.  Si la déduction d'argument template échoue, les autres surcharges de fonction sont prises en compte pour résoudre l'appel.  Ces autres surcharges, également connues comme étant l'ensemble de candidats, incluent des fonctions non basées sur un modèle et d'autres modèles de fonctions instanciés.  Si la déduction d'arguments template réussit, la fonction générée est comparée aux autres fonctions pour déterminer la meilleure correspondance, d'après les règles relative à la résolution de la surcharge.  Pour plus d'informations, consultez [Surcharge](../misc/overloading-cpp.md) et [Correspondance d'argument](../misc/argument-matching.md).  
  
## Exemple  
 Si une fonction non basée sur un modèle est une correspondance également correcte par rapport à une fonction de modèle, c'est elle qui est choisie \(sauf si les arguments template ont été explicitement spécifiés\), comme dans l'appel `f(1, 1)` illustré dans l'exemple suivant.  
  
```  
// template_name_resolution9.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
void f(char, char) { cout << "f(char, char)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   f(1, 1);   // Equally good match; choose the nontemplate function.  
   f('a', 1); // Chooses the template function.  
   f<int, int>(2, 2);  // Template arguments explicitly specified.  
}  
```  
  
  **f\(int, int\)**  
**void f\(T1, T2\)**  
**void f\(T1, T2\)**   
## Exemple  
 L'exemple suivant montre que la fonction de modèle à correspondance exacte est privilégiée si la fonction non basée sur un modèle requiert une conversion.  
  
```  
// template_name_resolution10.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   long l = 0;  
   int i = 0;  
   // Call the template function f(long, int) because f(int, int)  
   // would require a conversion from long to int.  
   f(l, i);  
}  
```  
  
  **void f\(T1, T2\)**   
## Voir aussi  
 [Résolution de noms](../cpp/templates-and-name-resolution.md)   
 [typename](../cpp/typename.md)   
 [Déduction d'arguments de modèle](../Topic/Template%20Argument%20Deduction.md)