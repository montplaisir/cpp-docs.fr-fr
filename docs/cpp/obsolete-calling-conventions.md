---
title: Conventions d’appel obsolètes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs:
- C++
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 922103e808541e2829350749a04d6004ba36577f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403418"
---
# <a name="obsolete-calling-conventions"></a>Conventions d’appel obsolètes
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Le **__pascal**, **__fortran**, et **__syscall** conventions d’appel ne sont plus prises en charge. Vous pouvez émuler leurs fonctionnalités en utilisant l’une des conventions d’appel prises en charge et les options appropriées de l’Éditeur de liens.  
  
 \<Windows.h > prend désormais en charge la macro WINAPI, qui se traduit par la convention d’appel appropriée pour la cible. Utilisez WINAPI où vous avez utilisé précédemment PASCAL ou **__far \__pascal**.  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Passage des arguments et conventions de dénomination](../cpp/argument-passing-and-naming-conventions.md)