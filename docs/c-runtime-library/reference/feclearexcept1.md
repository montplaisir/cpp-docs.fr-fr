---
title: feclearexcept1 | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- feclearexcept
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- feclearexcept
- fenv/feclearexcept
dev_langs:
- C++
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: face2637f308a56d95baa7563a6409dd38870d73
ms.sourcegitcommit: 2f571220e16f6c20e1fdb005f6cbc9e7ef5608f5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37070075"
---
# <a name="feclearexcept"></a>feclearexcept

Tente d’effacer les indicateurs d’exception de virgule flottante spécifiés par l’argument.

## <a name="syntax"></a>Syntaxe

```C
int feclearexcept(
   int excepts
);
```

### <a name="parameters"></a>Paramètres

*sauf*<br/>
Indicateurs d’état d’exception à effacer.

## <a name="return-value"></a>Valeur de retour

Retourne zéro si *, sauf* est égal à zéro, ou si toutes les exceptions spécifiées ont été effacées avec succès. Sinon, retourne une valeur différente de zéro.

## <a name="remarks"></a>Notes

Le **feclearexcept** fonction tente d’effacer flottante point d’indicateurs d’état exception spécifiées par *, sauf*. La fonction prend en charge les macros d’exception suivantes, définies dans fenv.h :

|Macros d’exception|Description|
|---------------------|-----------------|
|FE_DIVBYZERO|Une erreur de singularité ou de pôle s’est produite dans une opération à virgule flottante précédente ; une valeur infinie a été créée.|
|FE_INEXACT|La fonction a été forcée d’arrondir le résultat stocké d’une opération à virgule flottante précédente.|
|FE_INVALID|Une erreur de domaine s’est produite pendant une opération à virgule flottante précédente.|
|FE_OVERFLOW|Une erreur de plage s’est produite ; le résultat d’une opération à virgule flottante précédente était trop grand pour être représenté.|
|FE_UNDERFLOW|Le résultat d’une opération à virgule flottante précédente était trop petit pour être représenté avec une précision complète ; une valeur dénormalisée a été créée.|
|FE_ALL_EXCEPT|Opération OR au niveau du bit de toutes les exceptions de virgule flottante prises en charge.|

Le *, sauf* argument peut être zéro ou l’OR au niveau du bit d’un ou plusieurs des macros d’exception prise en charge. Le résultat de toute autre valeur d’argument est indéfini.

## <a name="requirements"></a>Configuration requise

|Fonction|En-tête C|En-tête C++|
|--------------|--------------|------------------|
|**feclearexcept**|\<fenv.h>|\<cfenv>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Voir aussi

[Référence alphabétique des fonctions](crt-alphabetical-function-reference.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
