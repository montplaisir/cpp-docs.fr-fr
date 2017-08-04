---
title: Erreur du compilateur C2099 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2099
dev_langs:
- C++
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
caps.latest.revision: 11
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
ms.openlocfilehash: 74fdc75470600c29029c52e38ab2073e484dbde6
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2099"></a>Erreur du compilateur C2099
l'initialiseur n'est pas une constante  
  
 Cette erreur est émise uniquement par le compilateur C et ne se produit que pour les variables non automatiques.  Le compilateur initialise des variables non automatiques au début du programme et les valeurs avec lesquelles elles sont initialisées doivent être des constantes.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2099.  
  
```  
// C2099.c  
int j;  
int *p;  
j = *p;   // C2099 *p is not a constant  
```  
  
## <a name="example"></a>Exemple  
 Erreur C2099 peut également se produire, car le compilateur n’est pas en mesure d’effectuer un repli constant sur une expression sous **/fp : strict** , car les paramètres d’environnement de précision en virgule flottante (consultez [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md) pour plus d’informations) peuvent différer de la compilation et au moment de l’exécution.  
  
 En cas d’échec du repli de constante, le compilateur appelle l’initialisation dynamique, ce qui n’est pas autorisé en C.  
  
 Pour résoudre cette erreur, compilez le module en tant que fichier .cpp ou simplifiez l’expression.  
  
 Pour plus d’informations, consultez l’article [/fp (Spécifier le comportement de virgule flottante)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
 L’exemple suivant génère l’erreur C2099.  
  
```  
// C2099_2.c  
// compile with: /fp:strict /c  
float X = 2.0 - 1.0;   // C2099  
float X2 = 1.0;   // OK  
```