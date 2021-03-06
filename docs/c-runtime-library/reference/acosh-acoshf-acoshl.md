---
title: acosh, acoshf, acoshl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- acoshf
- acosh
- acoshl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- acosh
- acoshf
- acoshl
- math/acosh
- math/acoshf
- math/acoshl
dev_langs:
- C++
helpviewer_keywords:
- acoshf function
- acosh function
- acoshl function
ms.assetid: 6985c4d7-9e2a-44ce-9a9b-5a43015f15f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 546006fcf1c559317b4afff424976db8109442e7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404750"
---
# <a name="acosh-acoshf-acoshl"></a>acosh, acoshf, acoshl

Calcule le cosinus hyperbolique inverse.

## <a name="syntax"></a>Syntaxe

```C
double acosh( double x );
float acoshf( float x );
long double acoshl( long double x );
```

```cpp
float acosh( float x );  // C++ only
long double acosh( long double x );  // C++ only
```

### <a name="parameters"></a>Paramètres

*x*  
Valeur à virgule flottante.

## <a name="return-value"></a>Valeur de retour

Le **acosh** fonctions retournent le cosinus hyperbolique inverse (arc le cosinus hyperbolique) de *x*. Ces fonctions sont valides sur le domaine *x* ≥ 1. Si *x* est inférieur à 1, `errno` a la valeur `EDOM` et le résultat est une valeur NaN silencieuse. Si *x* est une valeur NaN silencieuse, indéfini, ou l’infini, la même valeur est retournée.

|Entrée|Exception SEH|`_matherr` |
|-----------|-------------------|--------------------------|
|± QNAN, IND, INF|aucun|none|
|*x* < 1|none|none|

## <a name="remarks"></a>Notes

Lorsque vous utilisez C++, vous pouvez appeler des surcharges de **acosh** qui acceptent et retournent **float** ou **long** **double** valeurs. Dans un programme C, **acosh** accepte et retourne toujours **double**.

## <a name="requirements"></a>Configuration requise

|Fonction|En-tête C|En-tête C++|
|--------------|--------------|------------------|
|**ACOSH**, **acoshf**, **acoshl**|\<math.h>|\<cmath>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

```C
// crt_acosh.c
// Compile by using: cl /W4 crt_acosh.c
// This program displays the hyperbolic cosine of pi / 4
// and the arc hyperbolic cosine of the result.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = cosh( pi / 4 );
   y = acosh( x );
   printf( "cosh( %f ) = %f\n", pi/4, x );
   printf( "acosh( %f ) = %f\n", x, y );
}
```

```Output
cosh( 0.785398 ) = 1.324609
acosh( 1.324609 ) = 0.785398
```

## <a name="see-also"></a>Voir aussi

[Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)  
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)  
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)  
[cos, cosf, cosl](cosh-coshf-coshl.md)  
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)  
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)  