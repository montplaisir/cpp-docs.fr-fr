---
title: fprintf, _fprintf_l, fwprintf, _fwprintf_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fwprintf
- fprintf
- _fprintf_l
- _fwprintf_l
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
apitype: DLLExport
f1_keywords:
- fprintf
- fwprintf
- _ftprintf
dev_langs:
- C++
helpviewer_keywords:
- _fwprintf_l function
- fprintf function
- fprintf_l function
- _fprintf_l function
- _ftprintf function
- fwprintf function
- ftprintf_l function
- ftprintf function
- _ftprintf_l function
- print formatted data to streams
- fwprintf_l function
ms.assetid: 34a87e1c-6e4d-4d48-a611-58314dd4dc4b
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: d0f921aa46915220bb92f8ed1834f4c0e28ed57d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="fprintf-fprintfl-fwprintf-fwprintfl"></a>fprintf, _fprintf_l, fwprintf, _fwprintf_l
Envoient les données mises en forme vers un flux. Il existe des versions plus sécurisées de ces fonctions. Consultez [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fprintf(   
   FILE *stream,  
   const char *format [,  
   argument ]...  
);  
int _fprintf_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...  
);  
int fwprintf(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...  
);  
int _fwprintf_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]...  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
 `format`  
 Chaîne de contrôle de format.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 `fprintf` retourne le nombre d’octets écrits. `fwprintf` retourne le nombre de caractères larges écrits. Chacune de ces fonctions retourne une valeur négative à la place en cas d’erreur de sortie. Si `stream` ou `format` a la valeur `NULL`, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions retournent -1 et définissent `errno` avec la valeur `EINVAL`. La chaîne de format ne fait pas l’objet d’une vérification des caractères de mise en forme, comme c’est le cas avec `fprintf_s` ou `fwprintf_s`.  
  
 Consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d’informations sur ces éléments et autres codes d’erreur.  
  
## <a name="remarks"></a>Remarques  
 `fprintf` met en forme et envoie une série de caractères et de valeurs vers la sortie `stream`. Chaque fonction `argument` (le cas échéant) est convertie et sortie selon la spécification de format correspondante dans `format`. Pour `fprintf`, l’argument `format` a les mêmes syntaxe et utilisation que dans `printf`.  
  
 `fwprintf` est une version à caractères larges de `fprintf` ; dans `fwprintf`, `format` est une chaîne à caractères larges. Ces fonctions se comportent de la même façon si le flux est ouvert en mode ANSI. `fprintf` ne prend actuellement pas en charge la sortie vers un flux UNICODE.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
> [!IMPORTANT]
>  Assurez-vous que `format` n'est pas une chaîne définie par l'utilisateur.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ftprintf`|`fprintf`|`fprintf`|`fwprintf`|  
|`_ftprintf_l`|`_fprintf_l`|`_fprintf_l`|`_fwprintf_l`|  
  
 Pour plus d’informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fprintf`, `_fprintf_l`|\<stdio.h>|  
|`fwprintf`, `_fwprintf_l`|\<stdio.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_fprintf.c  
/* This program uses fprintf to format various  
 * data and print it to the file named FPRINTF.OUT. It  
 * then displays FPRINTF.OUT on the screen using the system  
 * function to invoke the operating-system TYPE command.  
 */  
  
#include <stdio.h>  
#include <process.h>  
  
FILE *stream;  
  
int main( void )  
{  
   int    i = 10;  
   double fp = 1.5;  
   char   s[] = "this is a string";  
   char   c = '\n';  
  
   fopen_s( &stream, "fprintf.out", "w" );  
   fprintf( stream, "%s%c", s, c );  
   fprintf( stream, "%d\n", i );  
   fprintf( stream, "%f\n", fp );  
   fclose( stream );  
   system( "type fprintf.out" );  
}  
```  
  
```Output  
this is a string  
10  
1.500000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [Syntaxe de spécification de format : fonctions printf et wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)