---
title: "hash_set::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre erase [STL/CLR]"
ms.assetid: 620998a0-00c9-4be6-899b-2d71661375b6
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime les éléments placés aux positions spécifiées.  
  
## Syntaxe  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### Paramètres  
 premièrement  
 Début de la plage à effacer.  
  
 key  
 Valeur de clé à supprimer.  
  
 last  
 Fin de la plage à effacer.  
  
 where  
 Élément à effacer.  
  
## Notes  
 La première fonction membre supprime l'élément de la séquence contrôlée vers laquelle pointe `where`, et retourne un itérateur qui indique le premier élément restant au delà de l'élément supprimé, ou [hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`()` si aucun tel élément n'existe.  Vous l'utilisez pour retirer un élément.  
  
 La deuxième méthode supprime les éléments de la séquence contrôlée dans la plage `[``first``,` `last``)`, et retourne un itérateur qui désigne le premier élément restant au delà de tous les éléments supprimés, ou `end()` si aucun tel élément n'existe.  Vous l'utilisez pour supprimer zéro ou plusieurs éléments contigus.  
  
 La troisième méthode supprime tout élément de la séquence contrôlée dont la clé est de tri équivalent à `key`, puis retourne le nombre d'éléments supprimés.  Vous l'utilisez pour supprimer et compter les éléments qui correspondent à la clé spécifiée.  
  
 Chaque suppression d'élément prend un temps proportionnel au logarithme du nombre d'éléments dans la séquence contrôlée.  
  
## Exemple  
  
```  
// cliext_hash_set_erase.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.insert(L'd');   
    c1.insert(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    Myhash_set::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**erase\(begin\(\)\) \= b**  
 **b c d e**  
**erase\(begin\(\), end\(\)\-1\) \= e**  
**size\(\) \= 1**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::clear](../dotnet/hash-set-clear-stl-clr.md)