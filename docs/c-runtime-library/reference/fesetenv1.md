---
title: fesetenv | Documents Microsoft
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
- fesetenv
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
- fesetenv
- fenv/fesetenv
dev_langs:
- C++
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: 6
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
ms.openlocfilehash: 96453fb182aa3c14bec8a296899cfcd15d39222c
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="fesetenv"></a>fesetenv
Définit l’environnement à virgule flottante actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `penv`  
 Pointeur désignant un objet `fenv_t` qui contient un environnement à virgule flottante tel que défini par un appel à [fegetenv](fegetenv1.md) ou [feholdexcept](feholdexcept2.md). Vous pouvez également spécifier l’environnement à virgule flottante de démarrage par défaut à l’aide de la macro FE_DFL_ENV.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne 0 si l’environnement a été correctement défini. Sinon, retourne une valeur différente de zéro.  
  
## <a name="remarks"></a>Notes  
 La fonction `fesetenv` définit l’environnement à virgule flottante actuel à partir de la valeur stockée dans l’objet `fenv_t` désigné par `penv`. L’environnement à virgule flottante rassemble les indicateurs d’état et les modes de contrôle qui affectent les calculs à virgule flottante. Cela inclut le mode d’arrondi et les indicateurs d’état pour les exceptions de virgule flottante.  Si `penv` n’est pas FE_DFL_ENV ou ne désigne pas un objet `fenv_t` valide, le comportement suivant n’est pas défini.  
  
 Un appel à cette fonction définit les indicateurs d’état d’exception qui se trouvent dans l’objet `penv`, mais ne déclenche pas les exceptions correspondantes.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la directive `#pragma fenv_access(on)` avant l’appel. Pour plus d’informations, consultez [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête C|En-tête C++|  
|--------------|--------------|------------------|  
|`fesetenv`|\<fenv.h>|\<cfenv>|  
  
 Pour plus d’informations sur la compatibilité, voir consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)