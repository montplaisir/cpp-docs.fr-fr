---
title: Erreur du compilateur C3075 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3075
dev_langs:
- C++
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
caps.latest.revision: 5
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
ms.openlocfilehash: b94da321ec35c840d929fe3b17ebb63885d86994
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3075"></a>Erreur du compilateur C3075
'instance' : vous ne pouvez pas incorporer une instance d’un type référence, 'type', dans un type valeur  
  
 Un type valeur ne peut pas contenir une instance d’un type référence.  
  
 Pour plus d’informations, consultez [la sémantique de pile C++ pour les Types référence](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3075.  
  
```  
// C3075.cpp  
// compile with: /clr /c  
ref struct U {};  
value struct X {  
   U y;   // C3075  
};  
  
ref struct Y {  
   U y;   // OK  
};  
```