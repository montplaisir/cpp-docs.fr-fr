---
title: _com_error::description | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 848709fa6cbbbfb4166750f86540de2433a73023
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404026"
---
# <a name="comerrordescription"></a>_com_error::Description
**Section spécifique à Microsoft**  
  
 Appels `IErrorInfo::GetDescription` (fonction).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_bstr_t Description( ) const;  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le résultat de `IErrorInfo::GetDescription` pour le `IErrorInfo` objet enregistré dans le `_com_error` objet. Le `BSTR` résultant est encapsulé dans un objet `_bstr_t`. Si aucun `IErrorInfo` est enregistrée, elle retourne un vide `_bstr_t`.  
  
## <a name="remarks"></a>Notes  
 Appelle le `IErrorInfo::GetDescription` fonction et récupère `IErrorInfo` stocké dans le `_com_error` objet. Tout échec lors de l’appel la `IErrorInfo::GetDescription` méthode est ignorée.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error, classe](../cpp/com-error-class.md)