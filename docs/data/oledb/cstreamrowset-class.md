---
title: CStreamRowset, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8b9f1c7aef4116ae057d771e66b5027c5783f64e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338010"
---
# <a name="cstreamrowset-class"></a>CStreamRowset, classe
Utilisé dans un `CCommand` ou `CTable` déclaration.  
  
## <a name="syntax"></a>Syntaxe

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
### <a name="parameters"></a>Paramètres  
 *TAccessor*  
 Classe d’accesseur.  

## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[CStreamRowset](#cstreamrowset)|Constructeur. Instancie et initialise le `CStreamRowset` objet.|  
|[Fermer](#close)|Versions le [ISequentialStream](https://msdn.microsoft.com/library/ms718035.aspx) pointeur d’interface dans la classe.|  
  
## <a name="remarks"></a>Notes  
 Utilisez `CStreamRowset` dans votre `CCommand` ou `CTable` déclaration, par exemple :  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]  
  
 ou  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` Retourne un `ISequentialStream` pointeur, qui est stocké dans `m_spStream`. Vous utilisez ensuite le `Read` méthode pour récupérer les données (chaîne Unicode) au format XML. Exemple :  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 effectue la mise en forme XML et retourne toutes les colonnes et toutes les lignes de l’ensemble de lignes sous forme de chaîne XML.  
  
> [!NOTE]
>  Cette fonctionnalité fonctionne uniquement avec SQL Server 2000.  
  
## <a name="cstreamrowset"></a> CStreamRowset::CStreamRowset
Instancie et initialise le `CStreamRowset` objet.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp
CStreamRowset();  
```  

## <a name="close"></a> CStreamRowset::Close
Versions le [ISequentialStream](https://msdn.microsoft.com/library/ms718035.aspx) pointeur d’interface dans la classe.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp
void Close();   
```  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)