---
title: "or_eq | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "std::or_eq"
  - "or_eq"
  - "std.or_eq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "or_eq (fonction)"
ms.assetid: 1eb92464-ed58-40d8-a30e-f0a6aa2f4318
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# or_eq
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une alternative à l'opérateur &#124;\=.  
  
## Syntaxe  
  
```  
  
#define or_eq |=  
  
```  
  
## Notes  
 La macro génère l'opérateur &#124;\=.  
  
## Exemple  
  
```  
// iso646_oreq.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 3, b = 2, result;  
  
   result= a |= b;  
   cout << result << endl;  
  
   result= a or_eq b;  
   cout << result << endl;  
}  
```  
  
  **3**  
**3**   
## Configuration requise  
 **En\-tête :** \<iso646.h\>