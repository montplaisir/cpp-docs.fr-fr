---
title: Erreur du compilateur C3611 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3611
dev_langs:
- C++
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdd09d86eac5e6182adb9f012c0e450b92d410b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252010"
---
# <a name="compiler-error-c3611"></a>Erreur du compilateur C3611
'fonction' : une fonction sealed ne peut pas avoir de spécificateur pure  
  
 Une fonction sealed a été déclarée de manière incorrecte.  Pour plus d’informations, consultez [sealed](../../windows/sealed-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3611.  
  
```  
// C3611.cpp  
// compile with: /clr /c  
  
ref struct V {  
   virtual void Test() sealed = 0;   // C3611  
   virtual void Test2() sealed;   // OK  
   virtual void Test3() = 0;   // OK  
};  
```