---
title: 2.6.1 maître construction | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a60a8df380fdcc0052d8fe2d070c8d926bcb28f8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689553"
---
# <a name="261-master-construct"></a>2.6.1 Construction master
Le **master** directive identifie une construction qui spécifie un bloc structuré qui est exécuté par le thread principal de l’équipe. La syntaxe de la **master** la directive est la suivante :  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 D’autres threads dans l’équipe n’exécutent pas le bloc structuré associé. Il n’existe aucune barrière implicite sur l’entrée ou sortie de la construction de référence.