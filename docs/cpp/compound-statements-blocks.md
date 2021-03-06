---
title: Instructions composées (blocs) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs:
- C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c85de0f147d0cfed873a091d17c46e56bf5758a9
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408794"
---
# <a name="compound-statements-blocks"></a>Instructions composées (blocs)
Une instruction composée se compose de zéro ou plusieurs instructions entre accolades (**{}**). Une instruction composée peut être utilisée partout où une instruction est attendue. Les instructions composées sont généralement appelées « blocs ».  
  
## <a name="syntax"></a>Syntaxe  
  
```  
{ [ statement-list ] }  
```  
  
## <a name="remarks"></a>Notes  
 L’exemple suivant utilise une instruction composée comme le *instruction* dans le cadre de la **si** instruction (consultez [if instruction](../cpp/if-else-statement-cpp.md) pour plus d’informations sur la syntaxe) :  
  
```cpp 
if( Amount > 100 )  
{  
    cout << "Amount was too large to handle\n";  
    Alert();  
}  
else  
{
    Balance -= Amount;  
}
```  
  
> [!NOTE]
>  Comme une déclaration est une instruction, une déclaration peut prendre l’une des instructions dans le *liste d’instructions*. Par conséquent, les noms déclarés au sein d'une instruction composée, mais pas explicitement déclarés comme statiques, ont une portée locale et (pour les objets) une durée de vie locale. Consultez [étendue](../cpp/scope-visual-cpp.md) pour plus d’informations sur le traitement des noms avec une portée locale.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble des instructions C++](../cpp/overview-of-cpp-statements.md)