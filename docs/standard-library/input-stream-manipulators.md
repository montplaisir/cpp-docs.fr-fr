---
title: "Manipulateurs de flux d’entrée | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 3b5f43364e0cfb286ead62f1c38d4d30aec707fc
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="input-stream-manipulators"></a>Manipulateurs de flux d'entrée
De nombreux manipulateurs, tels que [setprecision]--brokenlink--(../Topic/not%20found:3ddde610-70cc-4cfa-8a89-3e83d1d356a8.md#setprecision), sont définis pour la classe `ios` et s’appliquent donc aux flux d’entrée. Quelques manipulateurs affectent néanmoins les objets de flux d’entrée proprement dits. Parmi eux, les plus importants sont les manipulateurs de base, `dec`, `oct` et `hex`, qui déterminent la base de conversion utilisée avec les nombres du flux d’entrée.  
  
 Lors de l’extraction, le manipulateur `hex` autorise le traitement de divers formats d’entrée. Par exemple, c, C, 0xc, 0xC, 0Xc et 0XC sont tous interprétés comme l’entier décimal 12. Tout caractère autre que ceux de 0 à 9, de A à F, de a à f, x et X mettent fin à la conversion numérique. Ainsi, la séquence `"124n5"` est convertie en nombre 124 avec le bit [basic_ios::fail](../standard-library/basic-ios-class.md#fail) défini.  
  
## <a name="see-also"></a>Voir aussi  
 [Flux d’entrée](../standard-library/input-streams.md)

