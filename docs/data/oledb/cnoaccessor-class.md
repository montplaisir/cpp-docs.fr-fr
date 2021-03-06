---
title: Cnoaccessor, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs:
- C++
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0527f4b154b4b5d0dc07b2b152a3975f49746abf
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336737"
---
# <a name="cnoaccessor-class"></a>CNoAccessor, classe
Peut être utilisé comme argument template (`TAccessor`) pour les classes de modèle, tel que `CCommand` et `CTable`, qui nécessitent un argument de classe d’accesseur.  
  
## <a name="syntax"></a>Syntaxe

```cpp
class CNoAccessor  
```  
  
## <a name="remarks"></a>Notes  
 Utilisez `CNoAccessor` comme argument de modèle lorsque vous ne souhaitez pas que la classe pour prendre en charge des paramètres ou des colonnes de sortie.  
  
 `CNoAccessor` implémente les méthodes stub suivantes, chacune d’elles correspondent à d’autres méthodes de classe d’accesseur :  
  
-   `BindColumns` -Lie les colonnes aux accesseurs.  
  
-   `BindParameters` -Lie les paramètres créés pour les colonnes.  
  
-   `Bind` -Crée des liaisons.  
  
-   `Close` -Ferme l’accesseur.  
  
-   `ReleaseAccessors` -Libère les accesseurs créés par la classe.  
  
-   `FreeRecordMemory` -Libère toutes les colonnes dans l’enregistrement actif qui doivent être libérées.  
  
-   `GetColumnInfo` -Obtient les informations de colonne à partir de l’ensemble de lignes ouvert.  
  
-   `GetNumAccessors` -Récupère le nombre d’accesseurs créé par la classe.  
  
-   `IsAutoAccessor` -Retourne la valeur true si les données sont récupérées automatiquement pour l’accesseur pendant une opération de déplacement.  
  
-   `GetHAccessor` -Récupère le handle d’accesseur d’un accesseur spécifié.  
  
-   `GetBuffer` -Récupère le pointeur vers la mémoire tampon de signet.  
  
-   `NoBindOnNullRowset` : Empêche la liaison de données sur des ensembles de lignes vide.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)