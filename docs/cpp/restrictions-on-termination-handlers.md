---
title: Restrictions sur les gestionnaires de terminaisons | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ae16363956afc7cca853307ef2888846a02864d
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461768"
---
# <a name="restrictions-on-termination-handlers"></a>Restrictions sur les gestionnaires de terminaison
Vous ne pouvez pas utiliser un **goto** pour sauter dans une **__try** bloc d’instructions ou un **__finally** bloc d’instructions. À la place, vous devez entrer dans le bloc d'instruction via le flux de contrôle normal. (Vous pouvez, toutefois, sauter hors d’un **__try** bloc d’instructions.) En outre, vous ne pouvez pas imbriquer un gestionnaire d’exceptions ou un gestionnaire de terminaisons dans un **__finally** bloc.  
  
 Certains types de code autorisés dans un gestionnaire de terminaisons produisent des résultats incertains. Si vous en utilisez, faites-le avec précaution. Un est un **goto** instruction qui saute hors d’un **__finally** bloc d’instructions. Si le bloc s'exécute dans le cadre de l'arrêt normal, rien d'inhabituel ne se produit. Mais si le système est en train de dérouler la pile, ce déroulement s'arrête, et la fonction actuelle prend le contrôle comme s'il n'y avait pas eu d'arrêt anormal.  
  
 Un **retourner** instruction à l’intérieur d’un **__finally** bloc d’instructions présente à peu près la même situation. Le contrôle retourne à l'appelant immédiat de la fonction contenant le gestionnaire de terminaisons. Si le système était en train de dérouler la pile, ce processus est désactivé, et le programme continue comme si aucune exception n'était levée.  
  
## <a name="see-also"></a>Voir aussi  
 [Écriture d’un gestionnaire de terminaisons](../cpp/writing-a-termination-handler.md)   
 [Gestion structurée des exceptions (C/C++)](../cpp/structured-exception-handling-c-cpp.md)