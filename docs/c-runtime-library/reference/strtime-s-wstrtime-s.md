---
title: _strtime_s, _wstrtime_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wstrtime_s
- _strtime_s
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wstrtime_s
- strtime_s
- wstrtime_s
- _strtime_s
dev_langs:
- C++
helpviewer_keywords:
- wstrtime_s function
- copying time to buffers
- strtime_s function
- _wstrtime_s function
- time, copying
- _strtime_s function
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7f9814bb783c763eef6d94e9d1372316a2393a6
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451245"
---
# <a name="strtimes-wstrtimes"></a>_strtime_s, _wstrtime_s

Copient l’heure actuelle dans une mémoire tampon. Ces versions de [_strtime, _wstrtime](strtime-wstrtime.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Syntaxe

```C
errno_t _strtime_s(
   char *buffer,
   size_t numberOfElements
);
errno_t _wstrtime_s(
   wchar_t *buffer,
   size_t numberOfElements
);
template <size_t size>
errno_t _strtime_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrtime_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>Paramètres

*buffer*<br/>
Mémoire tampon, d’une longueur d’au moins 10 octets, dans laquelle l’heure doit être écrite.

*numberOfElements*<br/>
Taille de la mémoire tampon.

## <a name="return-value"></a>Valeur de retour

Zéro si l’opération aboutit.

Si une condition d’erreur se présente, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). En cas d’échec, la valeur de retour est un code d’erreur. Les codes d’erreur sont définis dans ERRNO.H. Consultez le tableau suivant pour en savoir plus sur les erreurs générées exactement par cette fonction. Pour plus d’informations sur les codes d’erreur, consultez [errno, constantes](../../c-runtime-library/errno-constants.md).

### <a name="error-conditions"></a>Conditions d’erreur

|*buffer*|*numberOfElements*|Retourner|Contenu de *tampon*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(indifférent)|**EINVAL**|Non modifiée|
|Pas **NULL** (pointant vers la mémoire tampon valide)|0|**EINVAL**|Non modifiée|
|Pas **NULL** (pointant vers la mémoire tampon valide)|0 < taille < 9|**EINVAL**|Chaîne vide|
|Pas **NULL** (pointant vers la mémoire tampon valide)|Taille > 9|0|Heure actuelle au format spécifié dans la section Notes|

## <a name="security-issues"></a>Problèmes de sécurité

En passant un non valide non -**NULL** valeur pour la mémoire tampon entraîne une violation d’accès si le *numberOfElements* paramètre est supérieur à 9.

Passage d’une valeur *numberOfElements* qui est supérieure à la taille réelle de la mémoire tampon entraîne le dépassement de mémoire tampon.

## <a name="remarks"></a>Notes

Ces fonctions fournissent des versions plus sécurisées de [_strtime](strtime-wstrtime.md) et [_wstrtime](strtime-wstrtime.md). Le **_strtime_s** fonction copie l’heure locale actuelle dans la mémoire tampon vers laquelle pointée *timestr*. L’heure sous la forme **hh : mm :** où **hh** comprend deux chiffres représentant l’heure dans la notation de 24 heures, **mm** comprend deux chiffres représentant les minutes après l’heure et **ss** comprend deux chiffres représentant les secondes. Par exemple, la chaîne **18:23:44** représente 23 minutes et 44 secondes après 6 heures La mémoire tampon doit avoir une longueur au moins égale à 9 octets. La taille réelle est spécifiée par le deuxième paramètre.

**_wstrtime** est une version à caractères larges de **_strtime**; la valeur des arguments et de retour de **_wstrtime** sont des chaînes à caractères larges. Ces fonctions se comportent sinon de façon identique.

En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument taille) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d'informations, consultez [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mapping"></a>Mappage de routines de texte générique :

|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime_s**|**_strtime_s**|**_strtime_s**|**_wstrtime_s**|

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**_strtime_s**|\<time.h>|
|**_wstrtime_s**|\<time.h> ou \<wchar.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

```C
// strtime_s.c

#include <time.h>
#include <stdio.h>

int main()
{
    char tmpbuf[9];
    errno_t err;

    // Set time zone from TZ environment variable. If TZ is not set,
    // the operating system is queried to obtain the default value
    // for the variable.
    //
    _tzset();

    // Display operating system-style date and time.
    err = _strtime_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
      exit(1);
    }
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );
    err = _strdate_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
       exit(1);
    }
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );

}
```

```Output
OS time:            14:37:49
OS date:            04/25/03
```

## <a name="see-also"></a>Voir aussi

[Gestion du temps](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
