---
title: "multiset::generic_value (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::generic_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_value (membre) (STL/CLR)"
ms.assetid: 4b77b5f8-1e69-48b3-b523-c92ab538a29f
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::generic_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type d'un élément à utiliser avec l'interface générique pour le conteneur.  
  
## Syntaxe  
  
```  
typedef GValue generic_value;  
```  
  
## Notes  
 Le type décrit un objet de type `GValue` qui décrit la valeur de l'élément stockée pour une utilisation avec l'interface générique pour ce modèle de classe de conteneur.  
  
## Exemple  
  
```  
// cliext_multiset_generic_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymultiset::generic_iterator gcit = gc1->begin();   
    Mymultiset::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**  
 **a**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::generic\_container](../dotnet/multiset-generic-container-stl-clr.md)   
 [multiset::generic\_iterator](../dotnet/multiset-generic-iterator-stl-clr.md)   
 [multiset::generic\_reverse\_iterator](../dotnet/multiset-generic-reverse-iterator-stl-clr.md)