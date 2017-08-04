---
title: feholdexcept2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- feholdexcept
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
- feholdexcept
- fenv/feholdexcept
dev_langs:
- C++
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: 5
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
ms.openlocfilehash: 210a0a2b353d691916c8f091205518bb67e375df
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="feholdexcept"></a>feholdexcept
Enregistre l’environnement à virgule flottante actuel dans l’objet spécifié, supprime les indicateurs d’état à virgule flottante et, si possible, place l’environnement à virgule flottante en mode sans interruption.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int feholdexcept(  
   fenv_t *penv  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `penv`  
 Pointeur désignant un objet `fenv_t` destiné à contenir une copie de l’environnement à virgule flottante.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne zéro si et seulement si la fonction est correctement activer la gestion des exceptions de virgule flottante sans interruption.  
  
## <a name="remarks"></a>Remarques  
 La fonction `feholdexcept` est utilisée pour stocker l’état de l’environnement à virgule flottante actuel dans l’objet `fenv_t` désigné par `penv` et pour définir l’environnement de façon à ce qu’il n’interrompe pas l’exécution sur les exceptions de virgule flottante. Il s’agit du mode sans interruption.  Ce mode reste actif jusqu’à ce que l’environnement soit restauré à l’aide de [fesetenv](fesetenv1.md) ou [feupdateenv](../../c-runtime-library/reference/feupdateenv.md).  
  
 Vous pouvez utiliser cette fonction au début d’une sous-routine qui a besoin de masquer une ou plusieurs exceptions de virgule flottante à l’appelant. Pour signaler une exception, vous pouvez simplement désactiver les exceptions indésirables à l’aide de [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md), puis mettre fin au mode sans interruption avec un appel à `feupdateenv`.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la directive `#pragma fenv_access(on)` avant l’appel. Pour plus d’informations, consultez [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`feholdexcept`|\<fenv.h>|\<cfenv>|  
  
 Pour plus d’informations sur la compatibilité, voir consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [fesetenv](fesetenv1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)