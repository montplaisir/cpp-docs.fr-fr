---
title: "Erreur irrécupérable C1103 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1103
dev_langs:
- C++
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
caps.latest.revision: 6
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
ms.openlocfilehash: e750c21ab6f9d3882413a83731c0fa2787f8fe47
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1103"></a>Erreur irrécupérable C1103
erreur irrécupérable lors de l’importation de progid : 'message'  
  
 Le compilateur a détecté un problème d’importation d’une bibliothèque de types.  Par exemple, vous ne pouvez pas spécifier une bibliothèque de types avec progid et spécifier également `no_registry`.  
  
 Pour plus d’informations, consultez [Directive #import](../../preprocessor/hash-import-directive-cpp.md).  
  
 L’exemple suivant génère l’erreur C1103 :  
  
```  
// C1103.cpp  
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103  
```