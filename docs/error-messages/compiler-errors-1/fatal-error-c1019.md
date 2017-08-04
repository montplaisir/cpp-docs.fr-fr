---
title: "Erreur irrécupérable C1019 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1019
dev_langs:
- C++
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b980d08adc2d941d817735dc92df55de5c8be686
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1019"></a>Erreur irrécupérable C1019
#else inattendu  
  
 La directive `#else` se trouve à l’extérieur d’une construction `#if`, `#ifdef`ou `#ifndef` . Utilisez `#else` uniquement dans l’une de ces constructions.  
  
 L’exemple suivant génère l’erreur C1019 :  
  
```  
// C1019.cpp  
#else   // C1019  
#endif  
  
int main() {}  
```  
  
 Résolution possible :  
  
```  
// C1019b.cpp  
#if 1  
#else  
#endif  
  
int main() {}  
```