---
title: _fwrite_nolock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fwrite_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fwrite_nolock
- fwrite_nolock
dev_langs:
- C++
helpviewer_keywords:
- fwrite_nolock function
- streams, writing data to
- _fwrite_nolock function
ms.assetid: 2b4ec6ce-742e-4615-8407-44a0a18ec1d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e22f2c281b076e64419686b9f7c058e284cc5532
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397920"
---
# <a name="fwritenolock"></a>_fwrite_nolock

Écrit des données dans un flux, sans verrouiller le thread.

## <a name="syntax"></a>Syntaxe

```C
size_t _fwrite_nolock(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Paramètres

*buffer*<br/>
Pointeur désignant les données à écrire.

*size*<br/>
Taille de l’élément en octets.

*count*<br/>
Nombre maximal d'éléments à écrire.

*Flux de données*<br/>
Pointeur désignant la structure **FILE**.

## <a name="return-value"></a>Valeur de retour

Identique à [fwrite](fwrite.md).

## <a name="remarks"></a>Notes

Cette fonction est une version sans verrouillage de **fwrite**. Il est identique à **fwrite** , sauf qu’il n’est pas protégé contre les interférences par d’autres threads. Elle peut être plus rapide, car elle n’entraîne pas la charge liée au verrouillage des autres threads. Utilisez cette fonction uniquement dans les contextes thread-safe, par exemple avec les applications monothread ou lorsque la portée appelante gère déjà l’isolation des threads.

## <a name="requirements"></a>Spécifications

|Fonction|En-tête requis|
|--------------|---------------------|
|**_fwrite_nolock**|\<stdio.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

Consultez l’exemple relatif à [fread](fread.md).

## <a name="see-also"></a>Voir aussi

[E/S de flux](../../c-runtime-library/stream-i-o.md)<br/>
[fread](fread.md)<br/>
[_write](write.md)<br/>
