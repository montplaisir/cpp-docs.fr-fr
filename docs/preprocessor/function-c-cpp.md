---
title: "function (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "function_CPP"
  - "vc-pragma.function"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "function (pragma)"
  - "pragmas, function (fonction)"
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
caps.latest.revision: 10
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# function (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie que les appels aux fonctions spécifiées dans la liste d'arguments du pragma sont générés.  
  
## Syntaxe  
  
```  
  
#pragma function( function1 [, function2, ...] )  
```  
  
## Notes  
 Si vous utilisez le pragma **intrinsic** \(ou \/Oi\) pour demander au compilateur de générer des fonctions intrinsèques \(les fonctions intrinsèques sont générées sous la forme de code inline, et non en tant qu'appels de fonction\), vous pouvez utiliser le pragma **function** pour forcer explicitement un appel de fonction.  Lorsqu'un pragma function est détecté, il prend effet à la première définition de fonction contenant une fonction intrinsèque spécifiée.  L'effet se poursuit jusqu'à la fin du fichier source ou la détection d'un pragma **intrinsic** spécifiant la même fonction intrinsic.  Le pragma **function** peut être utilisé uniquement en dehors d'une fonction, au niveau global.  
  
 Pour obtenir les listes des fonctions qui comportent des formes intrinsèques, consultez [\#pragma intrinsic](../preprocessor/intrinsic.md).  
  
## Exemple  
  
```  
// pragma_directive_function.cpp  
#include <ctype.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
  
// use intrinsic forms of memset and strlen  
#pragma intrinsic(memset, strlen)  
  
// Find first word break in string, and set remaining  
// chars in string to specified char value.  
char *set_str_after_word(char *string, char ch) {  
   int i;  
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */  
  
   for(i = 0; i < len; i++) {  
      if (isspace(*(string + i)))   
         break;  
   }  
  
   for(; i < len; i++)   
      *(string + i) = ch;  
  
   return string;  
}  
  
// do not use strlen intrinsic  
#pragma function(strlen)  
  
// Set all chars in string to specified char value.  
char *set_str(char *string, char ch) {  
   // Uses intrinsic for memset, but calls strlen library function  
   return (char *) memset(string, ch, strlen(string));  
}  
  
int main() {  
   char *str = (char *) malloc(20 * sizeof(char));  
  
   strcpy_s(str, sizeof("Now is the time"), "Now is the time");  
   printf("str is '%s'\n", set_str_after_word(str, '*'));  
   printf("str is '%s'\n", set_str(str, '!'));  
}  
```  
  
  **str is 'Now\*\*\*\*\*\*\*\*\*\*\*\*'**  
**str is '\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!'**   
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)