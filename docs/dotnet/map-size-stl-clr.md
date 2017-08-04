---
title: "map::size (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre size [STL/CLR]"
ms.assetid: e28e5ab6-9d3f-4aab-8bb4-c90520776239
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# map::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Compte le nombre d'éléments.  
  
## Syntaxe  
  
```  
size_type size();  
```  
  
## Notes  
 La méthode retourne la longueur de la séquence contrôlée.  Vous l'utilisez pour déterminer le nombre d'éléments figurant actuellement dans la séquence contrôlée.  Si tout ce dont vous vous souciez est si la séquence a une taille différente de zéro, consultez [map::empty](../dotnet/map-empty-stl-clr.md)`()`.  
  
## Exemple  
  
```  
// cliext_map_size.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.insert(Mymap::make_value(L'd', 4));   
    c1.insert(Mymap::make_value(L'e', 5));   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**size\(\) \= 0 après avoir libéré**  
**size\(\) \= 2 après avoir ajouté 2**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)   
 [map::empty](../dotnet/map-empty-stl-clr.md)