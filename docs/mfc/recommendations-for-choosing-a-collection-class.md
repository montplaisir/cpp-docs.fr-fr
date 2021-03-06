---
title: Recommandations relatives au choix d’une classe de Collection | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- type safety of collection classes [MFC]
- collection classes [MFC], serialization
- collection classes [MFC], speed
- collection classes [MFC], type safety
- collection classes [MFC], choosing
- collection classes [MFC], functionality
- shapes, collection
- collection classes [MFC], template-based
- MFC collection classes [MFC], characteristics
- collection classes [MFC], about collection classes [MFC]
- serialization [MFC], collection classes
- collection classes [MFC], duplicates allowed
- collection classes [MFC], shapes
ms.assetid: a82188cd-443f-40d8-a244-edf292a53db4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28527f9668b9ca6a9ef00cf399a04ce9bad65716
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353130"
---
# <a name="recommendations-for-choosing-a-collection-class"></a>Recommandations relatives au choix d'une classe de collection
Cet article contient des informations détaillées visant à vous aider à choisir une classe de collection adaptée aux besoins de votre application.  
  
 Votre choix de classe de collection dépend de plusieurs facteurs, notamment :  
  
-   Les fonctionnalités de la forme de classe : ordre, indexation et performances, comme indiqué dans le tableau [Fonctionnalités des formes de collection](#_core_collection_shape_features) plus loin dans cette rubrique.  
  
-   Si la classe utilise des modèles C++  
  
-   Si les éléments stockés dans la collection peuvent être sérialisés  
  
-   Si les éléments stockés dans la collection peuvent faire l'objet d'un dump pour effectuer des diagnostics  
  
-   Si la collection est de type sécurisé  
  
 Le tableau suivant, [Fonctionnalités des formes de collection](#_core_collection_shape_features), résume les caractéristiques des formes de collection disponibles.  
  
-   Les colonnes 2 et 3 décrivent les caractéristiques d’accès et de classement de chaque forme. Dans le tableau, le terme « ordonné » signifie que l’ordre dans lequel les éléments sont insérés et supprimés détermine leur ordre dans la collection. Il ne signifie pas que les éléments sont triés en fonction de leur contenu. Le terme « indexé » signifie que les éléments de la collection peuvent être récupérés par un index entier, comme les éléments d’un tableau standard.  
  
-   Les colonnes 4 et 5 décrivent les performances de chaque forme. Dans les applications qui nécessitent de nombreuses insertions dans la collection, la vitesse d’insertion peut être particulièrement importante. Pour d’autres applications, la vitesse de recherche peut être plus importante.  
  
-   La colonne 6 indique si chaque forme autorise des éléments en double.  
  
### <a name="_core_collection_shape_features"></a>  Fonctionnalités des formes de collection  
  
|Forme|Ordered|Indexées|Insérer un élément|Rechercher un élément spécifié|Éléments en double|  
|-----------|--------------|--------------|-----------------------|----------------------------------|-------------------------|  
|Liste|Oui|Non|Rapide|Lente|Oui|  
|Tableau|Oui|Par entier|Lente|Lente|Oui|  
|Carte|Non|Par clé|Rapide|Rapide|Non (clés) Oui (valeurs)|  
  
 Le tableau suivant, [Caractéristiques des classes de collection MFC](#_core_characteristics_of_mfc_collection_classes), résume d’autres caractéristiques importantes de classes de collection MFC spécifiques afin de faciliter la sélection. Votre choix peut différer selon que la classe est basée sur des modèles C++, que ses éléments peuvent être sérialisés par le biais du mécanisme de [sérialisation](../mfc/serialization-in-mfc.md) du document MFC, que ses éléments peuvent être vidés par le biais du mécanisme de vidage de diagnostic du document MFC, ou que la classe est de type sécurisé (autrement dit, si vous pouvez garantir le type des éléments stockés dans une collection et récupérés à partir d’une collection d’après la classe).  
  
### <a name="_core_characteristics_of_mfc_collection_classes"></a>  Caractéristiques des classes de collection MFC  
  
|Classe|Utilise des modèles<br /><br /> C++|Peut être<br /><br /> sérialisée|Peut être<br /><br /> vidée|Est<br /><br /> de type sécurisé|  
|-----------|------------------------------|---------------------------|-----------------------|-----------------------|  
|`CArray`|Oui|Oui 1|Oui 1|Non|  
|`CByteArray`|Non|Oui|Oui|Oui 3|  
|`CDWordArray`|Non|Oui|Oui|Oui 3|  
|`CList`|Oui|Oui 1|Oui 1|Non|  
|`CMap`|Oui|Oui 1|Oui 1|Non|  
|`CMapPtrToPtr`|Non|Non|Oui|Non|  
|`CMapPtrToWord`|Non|Non|Oui|Non|  
|`CMapStringToOb`|Non|Oui|Oui|Non|  
|`CMapStringToPtr`|Non|Non|Oui|Non|  
|`CMapStringToString`|Non|Oui|Oui|Oui 3|  
|`CMapWordToOb`|Non|Oui|Oui|Non|  
|`CMapWordToPtr`|Non|Non|Oui|Non|  
|`CObArray`|Non|Oui|Oui|Non|  
|`CObList`|Non|Oui|Oui|Non|  
|`CPtrArray`|Non|Non|Oui|Non|  
|`CPtrList`|Non|Non|Oui|Non|  
|`CStringArray`|Non|Oui|Oui|Oui 3|  
|`CStringList`|Non|Oui|Oui|Oui 3|  
|`CTypedPtrArray`|Oui|Selon le cas 2|Oui|Oui|  
|`CTypedPtrList`|Oui|Selon le cas 2|Oui|Oui|  
|`CTypedPtrMap`|Oui|Selon le cas 2|Oui|Oui|  
|`CUIntArray`|Non|Non|Oui|Oui 3|  
|`CWordArray`|Non|Oui|Oui|Oui 3|  
  
 1. Pour sérialiser, vous devez appeler explicitement la collection d’objets `Serialize` fonction ; pour vider, vous devez appeler explicitement sa `Dump` (fonction). Vous ne pouvez pas utiliser la forme `ar << collObj` pour sérialiser ou la forme `dmp` `<< collObj` pour faire un dump.  
  
 2. La capacité à sérialiser varie en fonction du type de collection sous-jacent. Par exemple, si un tableau de pointeurs typés est basé sur `CObArray`, il est sérialisable. S’il est basé sur `CPtrArray`, il n’est pas sérialisable. En général, les classes « Ptr » ne peuvent pas être sérialisées.  
  
 3. Si Oui est indiqué dans cette colonne, une classe de collection qui n’est pas basée sur un modèle est de type sécurisé si vous l’utilisez comme prévu. Par exemple, si vous stockez des octets dans un `CByteArray`, le tableau est de type sécurisé. En revanche, si vous l’utilisez pour stocker des caractères, la sécurité de type est plus incertaine.  
  
## <a name="see-also"></a>Voir aussi  
 [Collections](../mfc/collections.md)   
 [Classes basées sur un modèle](../mfc/template-based-classes.md)   
 [Comment : définir une Collection de Type sécurisé](../mfc/how-to-make-a-type-safe-collection.md)   
 [Accès à tous les membres d’une collection](../mfc/accessing-all-members-of-a-collection.md)

