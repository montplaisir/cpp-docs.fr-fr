---
title: Erreur du compilateur C2004 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2004
dev_langs:
- C++
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
caps.latest.revision: 10
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
ms.openlocfilehash: 81b2693ba3a1132738b5a1ff0e830fc4cef36e13
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2004"></a>Erreur du compilateur C2004
attendu 'defined(id)'  
  
 Un identificateur doit apparaître entre les parenthèses qui suivent le mot clé du préprocesseur.  
  
 Cette erreur peut également être générée en raison de la mise en conformité du compilateur pour Visual Studio .NET 2003 : parenthèses absentes dans la directive de préprocesseur. Si la parenthèse fermante est absente dans une directive de préprocesseur, le compilateur génère une erreur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2004 :  
  
```  
// C2004.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG   // C2004  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```  
  
## <a name="example"></a>Exemple  
 Résolution possible :  
  
```  
// C2004b.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG)  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```