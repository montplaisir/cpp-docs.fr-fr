---
title: Erreur du compilateur C3179 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3179
dev_langs:
- C++
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6234eceb35bda37a3616113d3010fe09cb669c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246028"
---
# <a name="compiler-error-c3179"></a>Erreur du compilateur C3179
type managé ou WinRT sans nom interdit  
  
Tous les structs et toutes les classes CLR et WinRT doivent avoir des noms.  
  
L'exemple suivant génère l'erreur C3179 et montre comment la corriger :  
  
```  
// C3179a.cpp  
// compile with: /clr /c  
typedef value struct { // C3179  
// try the following line instead  
// typedef value struct MyStruct {  
   int i;  
} V;  
```  
