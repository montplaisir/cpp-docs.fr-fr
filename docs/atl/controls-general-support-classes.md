---
title: 'Contrôles ATL : Classes de prise en charge général | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.controls
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6674bbdc29a6945cb26ea6b2caa03cc8c72be230
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958515"
---
# <a name="controls-general-support-classes"></a>Contrôles : Classes de prise en charge général
Les classes suivantes fournissent la prise en charge générale pour les contrôles ATL :  
  
-   [CComControl](../atl/reference/ccomcontrol-class.md) se compose de membres de données et des fonctions d’assistance qui sont essentielles à des contrôles ATL.  
  
-   [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) fournit les méthodes nécessaires pour les contrôles.  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) fournit les méthodes principales par le biais duquel un conteneur communique avec un contrôle. Gère l’activation et la désactivation des contrôles de la place.  
  
-   [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) combine l’initialisation dans un seul appel pour éviter les retards lors du chargement des contrôles conteneurs.  
  
-   [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) fournit une interaction minimale de la souris pour un contrôle inactif dans le cas contraire.  
  
## <a name="sample-program"></a>Exemple de programme  
 [ATLFire](../visual-cpp-samples.md)  
  
## <a name="related-articles"></a>Articles connexes  
 [Didacticiel ATL](../atl/active-template-library-atl-tutorial.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../atl/atl-class-overview.md)

