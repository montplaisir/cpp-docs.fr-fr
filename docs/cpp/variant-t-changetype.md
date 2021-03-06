---
title: _variant_t::ChangeType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f3790f4cb357ed830ba2c61b3c2906356dc64da
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465586"
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Section spécifique à Microsoft**  
  
 Change le type de la `_variant_t` objet au `VARTYPE`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *VarType*  
 Le `VARTYPE` pour ce `_variant_t` objet.  
  
 *pSrc*  
 Pointeur vers l'objet `_variant_t` à convertir. Si cette valeur est NULL, la conversion est effectuée en place.  
  
## <a name="remarks"></a>Notes  
 Cette fonction membre convertit un `_variant_t` objet dans le texte indiqué `VARTYPE`. Si *pSrc* est NULL, la conversion s’effectue sur place, sinon cela `_variant_t` objet est copié à partir de *pSrc* , puis sont converties.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_variant_t, classe](../cpp/variant-t-class.md)