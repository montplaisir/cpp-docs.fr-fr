---
title: Erreur du compilateur C2575 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2575
dev_langs:
- C++
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 739f6195d1f9203b1313815b3f4ee839374b1ad3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229798"
---
# <a name="compiler-error-c2575"></a>Erreur du compilateur C2575
'identificateur' : seules les fonctions membres et les bases peuvent être virtuelles  
  
 Une fonction globale ou la classe est déclarée `virtual`. Cette opération n’est pas autorisée.  
  
 L’exemple suivant génère l’erreur C2575 :  
  
```  
// C2575.cpp  
// compile with: /c  
virtual void func() {}   // C2575  
  
void func2() {}  
struct A {  
   virtual void func2(){}  
};  
```