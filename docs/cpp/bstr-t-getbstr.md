---
title: _bstr_t::GetBSTR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetBSTR
dev_langs:
- C++
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8863f3a6c37693ec28f931c2af4cb0d299788daa
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402661"
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR
**Section spécifique à Microsoft**  
  
 Pointe sur le début du `BSTR` encapsulé par l'objet `_bstr_t`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
BSTR& GetBSTR( );  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Début du `BSTR` encapsulé par l'objet `_bstr_t`.  
  
## <a name="remarks"></a>Notes  
 **GetBSTR** affecte tous les `_bstr_t` objets qui partagent un `BSTR`. Plusieurs `_bstr_t` peuvent partager un `BSTR` en utilisant le constructeur de copie et et **opérateur =**.  
  
## <a name="example"></a>Exemple  
 Consultez [_bstr_t::Assign](../cpp/bstr-t-assign.md) pour obtenir un exemple utilisant **GetBSTR**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_bstr_t, classe](../cpp/bstr-t-class.md)