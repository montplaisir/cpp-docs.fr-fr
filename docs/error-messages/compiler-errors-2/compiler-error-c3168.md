---
title: Erreur du compilateur C3168 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3168
dev_langs:
- C++
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: da24e70142fa8b54b88e1d721cad01865f306202
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3168"></a>Erreur du compilateur C3168
'type' : type d’enum sous-jacent non conforme  
  
Le type sous-jacent spécifié pour le `enum` type n’était pas valide. Le type sous-jacent doit être un type C++ intégral ou un type CLR correspondant.  
  
L’exemple suivant génère l’erreur C3168 :  
  
```  
// C3168.cpp  
// compile with: /clr /c  
ref class G{};  
  
enum class E : G { e };   // C3168  
enum class F { f };   // OK  
```  
