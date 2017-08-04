---
title: "_pgmptr, _wpgmptr | Microsoft Docs"
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
  - "pgmptr"
  - "_pgmptr"
  - "wpgmptr"
  - "_wpgmptr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_pgmptr (fonction)"
  - "_wpgmptr (fonction)"
  - "pgmptr (fonction)"
  - "wpgmptr (fonction)"
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _pgmptr, _wpgmptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chemin d'accès du fichier exécutable \(exe\).  Déconseillé ; utiliser [\_get\_pgmptr](../c-runtime-library/reference/get-pgmptr.md) et [\_get\_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md).  
  
## Syntaxe  
  
```  
extern char *_pgmptr;  
extern wchar_t *_wpgmptr;  
```  
  
## Notes  
 Lorsqu'un programme lancement de l'interpréteur de commandes \(Cmd.exe\), `_pgmptr` est initialisé automatiquement vers le chemin d'accès complet du fichier exécutable.  Par exemple, si Hello.exe dans C:\\BIN et C:\\BIN est dans le chemin d'accès, `_pgmptr` a la valeur C:\\BIN\\Hello.exe lorsque vous exécutez :  
  
```  
C> hello   
```  
  
 Lorsqu'un programme n'est pas exécuté à partir de la ligne de commande, `_pgmptr` peut être initialisé en tant que nom du programme \(le nom du fichier sans extension de nom de fichier\) ou nom de fichier,chemin d'accès relativf, ou chemin d'accès complet.  
  
 `_wpgmptr` est le miroir en caractères larges de `_pgmptr` pour une utilisation avec les programmes qui utilisent `wmain`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## Configuration requise  
  
|Variable|En\-tête requis|  
|--------------|---------------------|  
|`_pgmptr`, `_wpgmptr`|\<stdlib.h\>|  
  
## Exemple  
 L'exemple suivant illustre l'utilisation du mot clé `_pgmptr` :  
  
```  
// crt_pgmptr.c  
// compile with: /W3  
// The following program demonstrates the use of _pgmptr.  
//  
#include <stdio.h>  
#include <stdlib.h>  
int main( void )  
{  
   printf("The full path of the executing program is : %Fs\n",   
     _pgmptr); // C4996  
   // Note: _pgmptr is deprecated; use _get_pgmptr instead  
}  
```  
  
 Vous pouvez utiliser `_wpgmptr` en modifiant `%Fs` à `%S` et `main` à `wmain`.  
  
## Voir aussi  
 [Variables globales](../c-runtime-library/global-variables.md)