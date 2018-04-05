---
title: _ltoa, _ltow | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _ltoa
- _ltow
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
- ltow
- _ltot
- _ltoa
- _ltow
dev_langs:
- C++
helpviewer_keywords:
- converting integers
- _ltoa function
- _ltow function
- ltow function
- ltoa function
- long integer conversion to string
- converting numbers, to strings
ms.assetid: 14036104-2c25-4759-87c0-918ed8521e47
caps.latest.revision: ''
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25dc7c06f2e5eadacb568a096fda30f81a16570b
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2018
---
# <a name="ltoa-ltow"></a>_ltoa, _ltow
Convertit un entier long en chaîne. Des versions plus sécurisées de ces fonctions sont disponibles. Consultez [_ltoa_s, _ltow_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *_ltoa(  
   long value,  
   char *str,  
   int radix   
);  
wchar_t *_ltow(  
   long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ltoa(  
   long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ltow(  
   long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 `value`  
 Nombre à convertir.  
  
 `str`  
 Chaîne de résultat.  
  
 `radix`  
 Base de `value`.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces fonctions retourne un pointeur désignant `str`. Aucun retour d'erreur.  
  
## <a name="remarks"></a>Notes  
 La fonction `_ltoa` convertit les chiffres de `value` en chaîne de caractères se terminant par un caractère Null et stocke le résultat (jusqu’à 33 octets) dans `str`. Le `radix` argument spécifie la base de `value`, qui doit être comprise entre 2-36. Si `radix` est égal à 10 et `value` est négatif, le premier caractère de la chaîne stockée est le signe moins (-). `_ltow` est une version à caractères larges de `_ltoa` ; le second argument et la valeur de retour de `_ltow` sont des chaînes à caractères larges. Chacune de ces fonctions est fournie par Microsoft.  
  
> [!IMPORTANT]
>  Pour éviter les dépassements de mémoire tampon, vérifiez que la capacité de la mémoire tampon `str` est suffisante pour accueillir les chiffres convertis plus le caractère Null de fin et un caractère de signe.  
  
 En C++, ces fonctions ont des surcharges de modèle. Pour plus d'informations, consultez [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_ltoa`|\<stdlib.h>|  
|`_ltow`|\<stdlib.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md)