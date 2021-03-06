---
title: _com_error::WCode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCode
dev_langs:
- C++
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c9ad0cbfa614c132a75e25f46b34e37ec3a5fc64
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407002"
---
# <a name="comerrorwcode"></a>_com_error::WCode
**Section spécifique à Microsoft**  
  
 Récupère le code d’erreur 16 bits mappé dans la valeur HRESULT encapsulé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WORD WCode ( ) const throw( );  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Si la valeur HRESULT est dans la plage 0 x 80040200 à 0x8004FFFF, la `WCode` méthode retourne le HRESULT moins 0 x 80040200 ; sinon, elle retourne zéro.  
  
## <a name="remarks"></a>Notes  
 Le `WCode` méthode est utilisée pour annuler un mappage qui se produit dans le code de prise en charge COM. Le wrapper pour un `dispinterface` propriété ou méthode appelle une routine d’assistance qui empaquette les arguments et les appels `IDispatch::Invoke`. Au retour, si un HRESULT d’échec de `DISP_E_EXCEPTION` est retourné, les informations d’erreur sont récupérées à partir de la `EXCEPINFO` structure passée au `IDispatch::Invoke`. Le code d’erreur peut être une valeur 16 bits stockée dans le `wCode` membre de la `EXCEPINFO` structure ou une valeur de 32 bits dans le `scode` membre de la `EXCEPINFO` structure. Si une application 16 bits `wCode` est retournée, elle doit tout d’abord être mappé à un HRESULT d’échec 32 bits.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error, classe](../cpp/com-error-class.md)