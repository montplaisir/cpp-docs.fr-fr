---
title: include_alias | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, include_alias
- include_alias pragma
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84e09b51d6f234bdc17353c358e378f18e153567
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33838928"
---
# <a name="includealias"></a>include_alias

Spécifie que *short_filename* doit être utilisé en tant qu’alias pour *nom_fichier_long*.

## <a name="syntax"></a>Syntaxe

> #<a name="pragma-includealiaslongfilename-shortfilename"></a>pragma include_alias («*nom_fichier_long*«, »*short_filename*»)  
> #<a name="pragma-includealiaslongfilename-shortfilename"></a>pragma include_alias (*nom_fichier_long*, *short_filename*)

## <a name="remarks"></a>Notes

Certains systèmes de fichiers autorisent l'utilisation de noms de fichiers d'en-tête plus longs que la limite 8.3 du système de fichiers FAT. Le compilateur ne peut pas simplement tronquer les noms plus longs à 8.3, car les huit premiers caractères des noms de fichiers d'en-tête plus longs peuvent ne pas être uniques. Chaque fois que le compilateur rencontre le *nom_fichier_long* chaîne, il remplace *short_filename*et recherche le fichier d’en-tête *short_filename* à la place. Ce pragma doit figurer avant les directives `#include` correspondantes. Par exemple :

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

L'alias recherché doit correspondre exactement à la spécification, aussi bien pour ce qui est de la casse, de l'orthographe, que de l'utilisation des guillemets doubles et des crochets pointus. Le **include_alias** pragma effectue une correspondance sur les noms de fichiers de chaîne simple ; aucune autre validation de nom de fichier n’est effectuée. Par exemple, avec les directives suivantes,

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

aucune attribution d'alias (substitution) n'est effectuée, puisque les chaînes de fichier d'en-tête ne correspondent pas exactement. En outre, les noms de fichiers en-tête utilisés comme arguments pour les options /Yu et /Yc du compilateur, ou le **hdrstop** pragma, ne sont pas substitués. Par exemple, si votre fichier source contient la directive suivante,
  
```cpp
#include <AppleSystemHeaderStop.h>
```

l'option correspondante du compilateur doit être

> /YcAppleSystemHeaderStop.h

Vous pouvez utiliser la **include_alias** pragma pour mapper un nom de fichier d’en-tête à un autre. Par exemple :

```cpp
#pragma include_alias( "api.h", "c:\version1.0\api.h" )
#pragma include_alias( <stdio.h>, <newstdio.h> )
#include "api.h"
#include <stdio.h>
```

Ne combinez pas les noms de fichiers placés entre guillemets doubles avec des noms de fichiers placés entre crochets pointus. Par exemple, prenons deux ci-dessus **#pragma include_alias** directives, le compilateur n’exécute aucune substitution sur les serveurs suivants `#include` directives :

```cpp
#include <api.h>
#include "stdio.h"
```

En outre, la directive suivante génère une erreur :

```cpp
#pragma include_alias(<header.h>, "header.h")  // Error
```

Notez que le nom de fichier indiquée dans les messages d’erreur, ou en tant que la valeur de la **&#95; &#95;fichier&#95; &#95;** (macro), est le nom du fichier après la substitution a été effectuée. Par exemple, consultez la sortie après les directives suivantes :

```cpp
#pragma include_alias( "VeryLongFileName.H", "myfile.h" )
#include "VeryLongFileName.H"
```

Une erreur dans VERYLONGFILENAME. H génère le message d’erreur suivant :

```Output
myfile.h(15) : error C2059 : syntax error
```

Notez également que la transitivité n'est pas prise en charge. Avec les directives suivantes,

```cpp
#pragma include_alias( "one.h", "two.h" )
#pragma include_alias( "two.h", "three.h" )
#include "one.h"
```

le compilateur recherche le fichier TWO.H à la place de THREE.H.  

## <a name="see-also"></a>Voir aussi

[Directives pragma et mot clé _Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)