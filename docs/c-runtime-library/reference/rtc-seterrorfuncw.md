---
title: _RTC_SetErrorFuncW | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _RTC_SetErrorFuncW
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
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf610316c504e61d56556a20797f55d2906bca27
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32406912"
---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW

Désigne une fonction comme gestionnaire pour signaler les vérifications d’erreurs au moment de l’exécution (RTC).

## <a name="syntax"></a>Syntaxe

```C
_RTC_error_fnW _RTC_SetErrorFuncW(
   _RTC_error_fnW function
);
```

### <a name="parameters"></a>Paramètres

*function*<br/>
L’adresse de la fonction qui va gérer les vérifications d’erreurs au moment de l’exécution.

## <a name="return-value"></a>Valeur de retour

La fonction d’erreur définie précédemment ; ou **NULL** s’il n’existe aucune fonction définie précédemment.

## <a name="remarks"></a>Notes

Dans le nouveau code, utilisez uniquement **_RTC_SetErrorFuncW**. **_RTC_SetErrorFunc** est uniquement inclus dans la bibliothèque pour la compatibilité descendante.

Le **_RTC_SetErrorFuncW** rappel s’applique uniquement au composant auquel il a été lié, mais pas globalement.

Assurez-vous que l’adresse que vous passez à **_RTC_SetErrorFuncW** est celle d’une fonction de gestion d’erreur valide.

Si une erreur a été affectée un type de -1 à l’aide de [_RTC_SetErrorType](rtc-seterrortype.md), la fonction de gestion d’erreur n’est pas appelée.

Avant d’appeler cette fonction, vous devez d’abord appeler une des fonctions d’initialisation de vérification d’erreurs au moment de l’exécution. Pour plus d'informations, consultez [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).

**_RTC_error_fnW** est définie comme suit :

> **TypeDef int (__cdecl \*_RTC_error_fnW) (int** *errorType* **, wchar_t const \***  *nom de fichier* **, int***linenumber* **, wchar_t const \***  *moduleName* **, wchar_t const \***  *format* **,...) ;** 

où :

*errorType* le type d’erreur spécifié par [_RTC_SetErrorType](rtc-seterrortype.md).

*nom de fichier* le fichier source où la défaillance s’est produite, ou null si aucune information de débogage n’est disponible.

*LineNumber* la ligne *nom de fichier* où la défaillance s’est produite, ou 0 si aucune information de débogage n’est disponible.

*nom du module* la DLL ou le nom du fichier exécutable où la défaillance s’est produite.

*format* chaîne de style printf pour afficher un message d’erreur, en utilisant les paramètres restants. Le premier argument de VA_ARGLIST est le numéro de l’erreur RTC qui s’est produite.

Pour obtenir un exemple qui montre comment utiliser **_RTC_error_fnW**, consultez [Personnalisation des contrôles natifs à l’exécution](/visualstudio/debugger/native-run-time-checks-customization).

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapi.h>|

Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliothèques

Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Voir aussi

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Vérifications des erreurs au moment de l’exécution](../../c-runtime-library/run-time-error-checking.md)<br/>
