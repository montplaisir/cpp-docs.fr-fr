---
title: operator&lt;= (&lt;sample container&gt;) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<=
- std.operator<=
- operator<=
- std.<=
- std::operator<=
- <=
dev_langs:
- C++
helpviewer_keywords:
- operator<=
- operator <=
- <= operator, with specific objects
- <= operator
ms.assetid: 338577dd-dc88-4a2b-9e12-0379c54fc8a2
caps.latest.revision: 9
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 3267090567017a0aba7100d464a628bd0a0bcbea
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="operatorlt-ltsample-containergt"></a>operator&lt;= (&lt;sample container&gt;)
> [!NOTE]
>  Cette rubrique fait partie de la documentation Visual C++. Elle fournit un exemple non opérationnel de conteneurs utilisés dans la bibliothèque standard C++. Pour plus d’informations, consultez [Conteneurs disponibles dans la bibliothèque standard C++](../standard-library/stl-containers.md).  
  
 Surcharge **operator<=** pour comparer deux objets de la classe de modèle [Container](../standard-library/sample-container-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Ty>  
bool operator<=(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne `!(right < left)`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<sample container>](../standard-library/sample-container.md)

