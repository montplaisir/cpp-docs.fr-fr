---
title: _ismbbkalnum, _ismbbkalnum_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbbkalnum
- _ismbbkalnum_l
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
apitype: DLLExport
f1_keywords:
- _ismbbkalnum
- ismbbkalnum
- ismbbkalnum_l
- _ismbbkalnum_l
dev_langs:
- C++
helpviewer_keywords:
- _ismbbkalnum_l function
- ismbbkalnum_l function
- _ismbbkalnum function
- ismbbkalnum function
ms.assetid: e1d70e7b-29d0-469c-9d93-442b99de22ac
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 0c3e3333fd5cfc0445a4ee95a2cd16f8913b25e1
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="ismbbkalnum-ismbbkalnuml"></a>_ismbbkalnum, _ismbbkalnum_l
Détermine si un caractère multioctet particulier est un symbole de texte non ASCII.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _ismbbkalnum(  
   unsigned int c   
);  
int _ismbbkalnum_l(  
   unsigned int c,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Entier à tester.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 `_ismbbkalnum` retourne une valeur différente de zéro si l'entier `c` correspond à un symbole de texte autre qu'un signe de ponctuation ou 0 dans le cas contraire. `_ismbbkalnum` utilise les paramètres régionaux actifs pour les informations sur les caractères dépendants des paramètres régionaux. `_ismbbkalnum_l` est identique à `_ismbbkalnum` , à ceci près qu’elle prend les paramètres régionaux en tant que paramètre. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_ismbbkalnum`|\<mbctype.h>|  
|`_ismbbkalnum_l`|\<mbctype.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Classification d’octet](../../c-runtime-library/byte-classification.md)   
 [_ismbb, routines](../../c-runtime-library/ismbb-routines.md)