---
title: XForm, Structure | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6084882bed6690269fbb926f394159491d22978a
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885882"
---
# <a name="xform-structure"></a>XFORM, structure
Le `XFORM` structure a la forme suivante :  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## <a name="remarks"></a>Notes  
 Le `XFORM` structure spécifie un espace universel pour la transformation de l’espace de page. Le `eDx` et `eDy` membres spécifient les composants de la translation horizontale et verticale, respectivement. Le tableau suivant montre comment les autres membres sont utilisés, en fonction de l’opération :  
  
|Opération|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|Cosinus de l’angle de rotation|Sinus de l’angle de rotation|Sinus négatif d’angle de rotation|Cosinus de l’angle de rotation|  
|`Scaling`|Composant de mise à l’échelle horizontale|Nothing|Nothing|Composant de mise à l’échelle verticale|  
|`Shear`|Nothing|Constante de proportionnalité horizontal|Constante de proportionnalité verticale|Nothing|  
|`Reflection`|Composant de réflexion horizontal|Nothing|Nothing|Composant de réflexion verticale|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

