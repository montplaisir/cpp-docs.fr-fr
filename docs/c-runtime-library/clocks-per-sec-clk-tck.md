---
title: CLOCKS_PER_SEC, CLK_TCK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- CLOCKS_PER_SEC
- CLK_TCK
dev_langs:
- C++
helpviewer_keywords:
- CLOCKS_PER_SEC
- CLK_TCK constant
ms.assetid: bc285106-383d-44cb-91bf-276ad7de57bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbcc64419a34ff763f3e116474687fbadf055f42
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387399"
---
# <a name="clockspersec-clktck"></a>CLOCKS_PER_SEC, CLK_TCK
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <time.h>  
```  
  
## <a name="remarks"></a>Notes  
 La durée en secondes est la valeur retournée par la fonction `clock`, divisée par `CLOCKS_PER_SEC`. `CLK_TCK` est équivalent, mais considéré comme obsolète.  
  
## <a name="see-also"></a>Voir aussi  
 [clock](../c-runtime-library/reference/clock.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)