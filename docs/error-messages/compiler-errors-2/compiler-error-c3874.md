---
title: Erreur du compilateur C3874 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3874
dev_langs:
- C++
helpviewer_keywords:
- C3874
ms.assetid: fd55fc05-69a7-4237-b3b7-dca1d5400b4f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb1224b1e5b14c0f34e10b7eff972d4014cccdff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268253"
---
# <a name="compiler-error-c3874"></a>Erreur du compilateur C3874
type de retour de 'function' doit être 'int' au lieu de 'type'  
  
 Une fonction n’a pas le type de retour attendu par le compilateur.  
  
 L’exemple suivant génère l’erreur C3874 :  
  
```  
// C3874b.cpp  
double main()  
{   // C3874  
}  
```