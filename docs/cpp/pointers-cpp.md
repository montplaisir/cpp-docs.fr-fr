---
title: "Pointeurs | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "déclarations, pointeurs"
  - "déclarateurs, pointeurs"
  - "pointeurs"
  - "pointeurs, déclarations"
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Pointeurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les pointeurs sont déclarés à l'aide de la séquence ci\-dessous.  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator ;  
```  
  
 où tout déclarateur de pointeur valide peut être utilisé pour `declarator`.  La syntaxe d'un déclarateur de pointeur simple est la suivante :  
  
```  
* [cv-qualifiers] identifier [= expression]  
```  
  
 1.  Les spécificateurs de déclaration :  
  
-   Spécificateur de classe de stockage facultatif.  Pour plus d'informations, consultez [Spécificateurs](../cpp/specifiers.md).  
  
-   Mot clé `const` ou `volatile` facultatif appliqué au type de l'objet à pointer.  
  
-   Le spécificateur de type : le nom d'un type représentant le type de l'objet à pointer.  
  
 2.  Déclarateur :  
  
-   Modificateur spécifique Microsoft facultatif.  Pour plus d'informations, consultez [Modificateurs spécifiques Microsoft](../cpp/microsoft-specific-modifiers.md).  
  
-   Opérateur `*`.  
  
-   Mot clé `const` ou `volatile` facultatif appliqué au pointeur lui\-même.  
  
-   Identificateur.  
  
-   Initialiseur facultatif.  
  
 Le déclarateur d'un pointeur vers une fonction ressemble à ceci :  
  
```  
(* [cv-qualifiers] identifier )( argument-list ) [cv-qualifers]  
[exception specification] [= expression];  
```  
  
-   Pour un tableau de pointeurs, la syntaxe ressemble à ceci :  
  
```  
* identifier [ [ constant-expression ] ]  
```  
  
-   Toutefois, les déclarateurs de pointeur peuvent être plus complexes.  Pour plus d'informations, consultez [Déclarateurs](http://msdn.microsoft.com/fr-fr/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).  
  
-   Plusieurs déclarateurs et leurs initialiseurs peuvent apparaître simultanément dans une déclaration unique dans une liste séparée par des virgules suivant le spécificateur de déclaration.  
  
 Voici un exemple simple de déclaration de pointeur :  
  
```  
char *pch;  
```  
  
 La déclaration précédente spécifie que `pch` pointe vers un objet de type `char`.  
  
 Voici un exemple plus complexe  
  
```  
static unsigned int * const ptr;  
```  
  
 La déclaration précédente spécifie que `ptr` est un pointeur constant vers un objet de type `unsigned` `int` avec une durée de stockage statique.  
  
 L'exemple suivant montre comment plusieurs pointeurs sont déclarés et initialisés :  
  
```  
static int *p = &i, *q = &j;  
```  
  
 Dans l'exemple précédent, les pointeurs p et q pointent tous les deux vers des objets de type `int` et sont initialisés vers les adresses de i et de j respectivement.  Le spécificateur de classe de stockage `static` s'applique aux deux pointeurs.  
  
## Exemple  
  
```  
// pointer.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   int i = 1, j = 2; // local variables on the stack  
   int *p;  
  
   // a pointer may be assigned to "point to" the value of  
   // another variable using the & (address of) operator  
   p = & j;   
  
   // since j was on the stack, this address will be somewhere  
   // on the stack.  Pointers are printed in hex format using  
   // %p and conventionally marked with 0x.    
   printf_s("0x%p\n",  p);  
  
   // The * (indirection operator) can be read as "the value  
   // pointed to by".  
   // Since p is pointing to j, this should print "2"  
   printf_s("0x%p %d\n",  p, *p);  
  
   // changing j will change the result of the indirection  
   // operator on p.  
   j = 7;  
   printf_s("0x%p %d\n",  p, *p );  
  
   // The value of j can also be changed through the pointer  
   // by making an assignment to the dereferenced pointer  
   *p = 10;  
   printf_s("j is %d\n", j); // j is now 10  
  
   // allocate memory on the heap for an integer,  
   // initialize to 5  
   p = new int(5);  
  
   // print the pointer and the object pointed to  
   // the address will be somewhere on the heap  
   printf_s("0x%p %d\n",  p, *p);  
  
   // free the memory pointed to by p  
   delete p;  
  
   // At this point, dereferencing p with *p would trigger  
   // a runtime access violation.  
  
   // Pointer arithmetic may be done with an array declared  
   // on the stack or allocated on the heap with new.  
   // The increment operator takes into account the size   
   // of the objects pointed to.  
   p = new int[5];  
   for (i = 0; i < 5; i++, p++) {  
      *p = i * 10;  
      printf_s("0x%p %d\n", p, *p);  
   }  
  
   // A common expression seen is dereferencing in combination  
   // with increment or decrement operators, as shown here.  
   // The indirection operator * takes precedence over the   
   // increment operator ++.   
   // These are particularly useful in manipulating char arrays.  
   char s1[4] = "cat";  
   char s2[4] = "dog";  
   char* p1 = s1;  
   char* p2 = s2;  
  
   // the following is a string copy operation  
   while (*p1++ = *p2++);  
  
   // s2 was copied into s1, so now they are both equal to "dog"  
   printf_s("%s %s", s1, s2);  
}  
```  
  
  **0x0012FEC8**  
**0x0012FEC8 2**  
**0x0012FEC8 7**  
**j correspond à 10**  
**0x00320850 5**  
**0x00320850 0**  
**0x00320854 10**  
**0x00320858 20**  
**0x0032085C 30**  
**0x00320860 40**  
**dog dog**   
## Exemple  
 Un autre exemple illustre l'utilisation des pointeurs dans des structures de données. Dans ce cas, il s'agit d'une liste liée.  
  
```  
// pointer_linkedlist.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct NewNode {  
   NewNode() : node(0){}  
   int i;  
   NewNode * node;  
};  
  
void WalkList(NewNode * ptr) {  
   if (ptr != 0) {  
      int i = 1;  
      while (ptr->node != 0 ) {  
         cout << "node " << i++ << " = " << ptr->i << endl;  
         ptr = ptr->node;  
      }  
      cout << "node " << i++ << " = " << ptr->i << endl;  
   }  
}  
  
void AddNode(NewNode ** ptr) {  
   NewNode * walker = 0;  
   NewNode * MyNewNode = new NewNode;  
   cout << "enter a number: " << endl;  
   cin >> MyNewNode->i;  
  
   if (*ptr == 0)  
      *ptr = MyNewNode;  
   else  {  
      walker = *ptr;  
      while (walker->node != 0)  
         walker = walker->node;  
  
      walker->node = MyNewNode;  
   }  
}  
  
int main() {  
   char ans = ' ';  
   NewNode * ptr = 0;  
   do {  
      cout << "a (add node)  d (display list)  q (quit)" << endl;  
      cin >> ans;  
      switch (ans) {  
      case 'a':  
         AddNode(&ptr);  
         break;  
      case 'd':  
         WalkList(ptr);  
         break;  
      }  
   } while (ans != 'q');  
}  
```  
  
  **`a 45 d a 789 d q`a \(ajouter le nœud\) d \(liste d'affichage\) q \(quitter\)**  
**entrez un nombre :**   
**a \(ajouter le nœud\) d \(liste d'affichage\) q \(quitter\)**  
**nœud 1 \= 45**  
**a \(ajouter le nœud\) d \(liste d'affichage\) q \(quitter\)**  
**entrez un nombre :**   
**a \(ajouter le nœud\) d \(liste d'affichage\) q \(quitter\)**  
**nœud 1 \= 45**  
**node 2 \= 789**  
**a \(ajouter le nœud\) d \(liste d'affichage\) q \(quitter\)**   
## Voir aussi  
 [C\+\+ Abstract Declarators](http://msdn.microsoft.com/fr-fr/e7e18c18-0cad-4450-942b-d27e1d4dd088)   
 [Addition de types pointeur](../misc/addition-of-pointer-types.md)   
 [Opérateur d'indirection : \*](../cpp/indirection-operator-star.md)   
 [Opérateur address\-of : &](../cpp/address-of-operator-amp.md)