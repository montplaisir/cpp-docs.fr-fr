---
title: Compilateur avertissement (niveau 4) C4680 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4680
dev_langs:
- C++
helpviewer_keywords:
- C4680
ms.assetid: 6e043f4c-c601-4b77-8130-920cff1d912e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 64c43a1d099d47cbf9b3705bb57c783780aa00aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300132"
---
# <a name="compiler-warning-level-4-c4680"></a>Avertissement du compilateur (niveau 4) C4680
'classe' : coclasse ne spécifie pas une interface par défaut  
  
 A [par défaut](../../windows/default-cpp.md) interface n’a pas été spécifié pour une classe qui a été marquée avec la [coclasse](../../windows/coclass.md) attribut. Dans l’ordre pour un objet soit utile, il doit implémenter une interface.  
  
 L’exemple suivant génère l’erreur C4680 :  
  
```  
// C4680.cpp  
// compile with: /W4  
#include <windows.h>  
[module(name="MyModule")];  
  
[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface1  
{  
   HRESULT f1();  
};  
  
[ object, uuid(37331a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface2  
{  
   HRESULT f1();  
};  
  
// to resolve C4680, specify a source interface also  
// for example, default(IMyIface1, IMyface2)  
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f), default(IMyIface1), source(IMyIface1) ]  
class CMyClass : public IMyIface1  
{   // C4680  
};  
  
int main()  
{  
}  
```