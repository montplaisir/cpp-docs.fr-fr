---
title: "deque::empty (STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::empty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre empty [STL/CLR]"
ms.assetid: 6ff3dd07-ebdf-47f9-b0d2-8a3229390d3b
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::empty (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vérifie l'absence d'éléments.  
  
## Syntaxe  
  
```  
bool empty();  
```  
  
## Notes  
 La fonction membre retourne vrai pour une séquence contrôlée vide.  Équivaut à [deque::size](../dotnet/deque-size-stl-clr.md)`() == 0`.  Vous l'utilisez pour tester si le deque est vide.  
  
## Exemple  
  
```  
// cliext_deque_empty.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**size\(\) \= 3**  
**vide\(\) \= faux**  
**size\(\) \= 0**  
**vide\(\) \= Vrai**   
## Configuration requise  
 **En\-tête :** \<cliext\/deque\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::size](../dotnet/deque-size-stl-clr.md)