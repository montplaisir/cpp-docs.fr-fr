---
title: Compilateur avertissement (niveaux 1 et 4) C4112 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43718511af0d85f0c9026fe70b4749c4e3d4b1e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299277"
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Avertissement du compilateur (niveaux 1 et 4) C4112
\#ligne nécessite un entier compris entre 1 et nombre  
  
 La directive [#line](../../preprocessor/hash-line-directive-c-cpp.md) spécifie un paramètre entier qui se trouve en dehors de la plage autorisée.  
  
 Si le paramètre spécifié est inférieur à 1, le compteur de lignes est réinitialisé à 1. Si le paramètre spécifié est supérieur à *nombre*, qui est la limite définie par le compilateur, le compteur de lignes est inchangé. Il s’agit d'un avertissement de niveau 1 sous compatibilité ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) et un avertissement de niveau 4 avec les extensions Microsoft ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 L’exemple suivant génère l’avertissement C4112 :  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```