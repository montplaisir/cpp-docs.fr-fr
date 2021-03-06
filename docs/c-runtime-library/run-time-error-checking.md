---
title: Vérifications des erreurs d’exécution │ Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2468cd05efdf732fbf955b8532a61d24fa6c0ff4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409122"
---
# <a name="run-time-error-checking"></a>Vérifications des erreurs d’exécution

La bibliothèque Runtime C contient les fonctions qui prennent en charge les vérifications d’erreurs d’exécution (RTC). La vérification des erreurs d’exécution vous permet de générer votre programme afin que certains types d’erreurs d’exécution soient signalés. Vous spécifiez la façon dont les erreurs sont signalées et les types d’erreurs qui doivent l’être. Pour plus d’informations, consultez [Comment : utiliser les contrôles natifs à l'exécution](/visualstudio/debugger/how-to-use-native-run-time-checks).

 Utilisez les fonctions suivantes pour personnaliser la façon dont votre programme effectue la vérification des erreurs d’exécution.

## <a name="run-time-error-checking-functions"></a>Fonctions de vérification des erreurs d’exécution

|Fonction|Utilisez|
|--------------|---------|
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Retourne une brève description d’un type de vérification des erreurs d’exécution.|
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Retourne le nombre total d’erreurs pouvant être détectées par les vérifications d’erreurs d’exécution.|
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Désigne une fonction comme gestionnaire de rapport pour les vérifications d’erreurs d’exécution.|
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Associe une erreur détectée par les vérifications d’erreurs d’exécution à un type.|

## <a name="see-also"></a>Voir aussi

[Routines du runtime C universel par catégorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
 [/RTC (Vérifications des erreurs au moment de l’exécution)](../build/reference/rtc-run-time-error-checks.md)<br/>
 [runtime_checks](../preprocessor/runtime-checks.md)<br/>
 [Routines de débogage](../c-runtime-library/debug-routines.md)<br/>
