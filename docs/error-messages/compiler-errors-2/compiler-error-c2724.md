---
title: Erreur du compilateur C2724 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2724
dev_langs:
- C++
helpviewer_keywords:
- C2724
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0bf22539a53a0eee78a7d0be110d7459cf5d4f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234890"
---
# <a name="compiler-error-c2724"></a>Erreur du compilateur C2724
'identificateur' : 'static' ne doit pas être utilisé sur les fonctions membres définies au niveau de la portée du fichier  
  
 Les fonctions membres statiques doivent être déclarées avec une liaison externe.  
  
 L’exemple suivant génère l’erreur C2724 :  
  
```  
// C2724.cpp  
class C {  
   static void func();  
};  
  
static void C::func(){};   // C2724  
// try the following line instead  
// void C::func(){};  
```