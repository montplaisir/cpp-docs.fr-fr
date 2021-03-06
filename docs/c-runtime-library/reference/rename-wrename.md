---
title: rename, _wrename | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- rename
- _wrename
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wrename
- _trename
- Rename
dev_langs:
- C++
helpviewer_keywords:
- trename function
- directories [C++], renaming
- renaming directories
- names [C++], changing file
- _trename function
- rename function
- wrename function
- files [C++], renaming
- _wrename function
- names [C++], changing directory
- renaming files
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f02829b394649b86dfda9baad7c5792853fce746
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407471"
---
# <a name="rename-wrename"></a>rename, _wrename

Suppriment un fichier ou un répertoire.

## <a name="syntax"></a>Syntaxe

```C
int rename(
   const char *oldname,
   const char *newname
);
int _wrename(
   const wchar_t *oldname,
   const wchar_t *newname
);
```

### <a name="parameters"></a>Paramètres

*oldname*<br/>
Pointeur désignant l’ancien nom.

*newname*<br/>
Pointeur désignant le nouveau nom.

## <a name="return-value"></a>Valeur de retour

Chacune de ces fonctions retourne 0 en cas de réussite. En cas d’erreur, la fonction retourne une valeur différente de zéro et définit **errno** à une des valeurs suivantes :

|Valeur de la variable errno|Condition|
|-|-|
**EACCES**|Le fichier ou le répertoire spécifié par *newname* existe déjà ou n’a pas pu être créé (chemin non valide) ; ou *oldname* est un répertoire et *newname* spécifie un autre chemin.
**ENOENT**|Le fichier ou le chemin spécifié par *oldname* est introuvable.
**EINVAL**|Le nom contient des caractères non valides.

Pour connaître les autres valeurs de retour possibles, consultez [_doserrno, _errno, syserrlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Notes

La fonction **rename** renomme le fichier ou le répertoire spécifié par *oldname* avec le nom fourni par *newname*. L’ancien nom doit être le chemin d’un fichier ou répertoire existant. Le nouveau nom doit être le nom d’un fichier ou répertoire existant. Vous pouvez utiliser **rename** pour déplacer un fichier d’un répertoire ou appareil vers un autre en indiquant un autre chemin dans l’argument *newname*. Cependant, vous ne pouvez pas utiliser **rename** pour déplacer un répertoire. Les répertoires peuvent être renommés, mais pas déplacés.

**_wrename** est une version à caractères larges de **affiche_r**; les arguments de **_wrename** sont des chaînes à caractères larges. **_wrename** et **affiche_r** comportent de façon identique.

### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique

|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_trename**|**rename**|**rename**|**_wrename**|

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**rename**|\<io.h> ou \<stdio.h>|
|**_wrename**|\<stdio.h> ou \<wchar.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliothèques

Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Exemple

```C
// crt_renamer.c
/* This program attempts to rename a file named
* CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation
* to succeed, a file named CRT_RENAMER.OBJ must exist and
* a file named CRT_RENAMER.JBO must not exist.
*/

#include <stdio.h>

int main( void )
{
   int  result;
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";

   /* Attempt to rename file: */
   result = rename( old, new );
   if( result != 0 )
      printf( "Could not rename '%s'\n", old );
   else
      printf( "File '%s' renamed to '%s'\n", old, new );
}
```

### <a name="output"></a>Sortie

```Output
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'
```

## <a name="see-also"></a>Voir aussi

[Gestion de fichiers](../../c-runtime-library/file-handling.md)<br/>
