---
title: strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
dev_langs:
- C++
helpviewer_keywords:
- fstrpbrk function
- _ftcspbrk function
- _mbspbrk_l function
- strpbrk function
- _fstrpbrk function
- mbspbrk function
- characters [C++], scanning strings
- _tcspbrk function
- wcspbrk function
- ftcspbrk function
- character sets [C++], scanning strings for characters
- strings [C++], scanning
- tcspbrk function
- _mbspbrk function
- mbspbrk_l function
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db26c60badceab6c1422146a32de3d6dd2ecb8bd
ms.sourcegitcommit: 04d327940787df1297b72d534f388a035d472af0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39181131"
---
# <a name="strpbrk-wcspbrk-mbspbrk-mbspbrkl"></a>strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l

Analyse des chaînes à la recherche de caractères présents dans les jeux de caractères spécifiés.

> [!IMPORTANT]
> `_mbspbrk` et `_mbspbrk_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge dans les applications de la plateforme Windows universelle](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntaxe

```C
char *strpbrk(
   const char *str,
   const char *strCharSet
); // C only
char *strpbrk(
   char *str,
   const char *strCharSet
); // C++ only
const char *strpbrk(
   const char *str,
   const char *strCharSet
); // C++ only
wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C only
wchar_t *wcspbrk(
   wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
const wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C only
unsigned char *_mbspbrk(
   unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
const unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C only
unsigned char *_mbspbrk_l(
   unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C++ only
const unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char* strCharSet,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Paramètres

*str*<br/>
Chaîne se terminant par un caractère Null faisant l’objet de la recherche.

*strCharSet*<br/>
Jeu de caractères se terminant par null.

*locale*<br/>
Paramètres régionaux à utiliser.

## <a name="return-value"></a>Valeur de retour

Retourne un pointeur désignant la première occurrence de n’importe quel caractère à partir de *strCharSet* dans *str*, ou un pointeur NULL si les deux arguments de chaîne n’ont aucun caractère en commun.

## <a name="remarks"></a>Notes

Le `strpbrk` fonction retourne un pointeur désignant la première occurrence d’un caractère dans *str* qui appartient au jeu de caractères dans *strCharSet*. La recherche n’inclut pas le caractère Null de fin.

`wcspbrk` et `_mbspbrk` sont des versions à caractères larges et à caractères multioctets de `strpbrk`. Les arguments et la valeur de retour de `wcspbrk` sont des chaînes de caractères larges ; ceux de `_mbspbrk` sont des chaînes de caractères multioctets.

`_mbspbrk` valide ses paramètres. Si *str* ou *strCharSet* est NULL, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `_mbspbrk` renvoie la valeur NULL et définit `errno` à EINVAL. `strpbrk` et `wcspbrk` ne vérifient pas leurs paramètres. Ces trois fonctions se comportent sinon de façon identique.

`_mbspbrk` est similaire à `_mbscspn`, sauf que `_mbspbrk` retourne un pointeur et non une valeur de type [size_t](../../c-runtime-library/standard-types.md).

En C, ces fonctions prennent une **const** pointeur pour le premier argument. En C++, deux surcharges sont disponibles. La surcharge acceptant un pointeur vers **const** retourne un pointeur vers **const**; la version qui accepte un pointeur vers non -**const** retourne un pointeur vers non -**const** . La macro _CRT_CONST_CORRECT_OVERLOADS est défini si les deux le **const** et non-**const** versions de ces fonctions sont disponibles. Si vous avez besoin non -**const** comportement pour les deux surcharges C++, définissez le symbole _CONST_RETURN.

La valeur de sortie est affectée par la valeur du paramètre de catégorie LC_CTYPE des paramètres régionaux ; Pour plus d’informations, consultez [setlocale](setlocale-wsetlocale.md). Les versions de ces fonctions sans le **_l** utilisez suffixe les paramètres régionaux actuels pour ce comportement dépendant des paramètres régionaux ; la version avec le **_l** suffixe est identique, sauf qu’elle utilise les paramètres régionaux passé à la place. Pour plus d’informations, consultez [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique

|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|
|**n/a**|**n/a**|`_mbspbrk_l`|**n/a**|

## <a name="requirements"></a>Configuration requise

|Routine|En-tête requis|
|-------------|---------------------|
|`strpbrk`|\<string.h>|
|`wcspbrk`|\<string.h> ou \<wchar.h>|
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h>|

Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

```C
// crt_strpbrk.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";
   char *result = NULL;

   // Return pointer to first digit in "string".
   printf( "1: %s\n", string );
   result = strpbrk( string, "0123456789" );
   printf( "2: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "3: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "4: %s\n", result );
}
```

```Output
1: The 3 men and 2 boys ate 5 pigs

2: 3 men and 2 boys ate 5 pigs

3: 2 boys ate 5 pigs

4: 5 pigs
```

## <a name="see-also"></a>Voir aussi

[Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Paramètres régionaux](../../c-runtime-library/locale.md)<br/>
[Interprétation des séquences de caractères multi-octets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
