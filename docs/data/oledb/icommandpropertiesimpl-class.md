---
title: Icommandpropertiesimpl, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
- SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b360b56066ecbb5cc605012b234c0ac11afb2a11
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339410"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl, classe
Fournit une implémentation de la [ICommandProperties](https://msdn.microsoft.com/library/ms723044.aspx) interface.  
  
## <a name="syntax"></a>Syntaxe

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>Paramètres  
 *T*  
 Votre classe dérivée  
  
 *PropClass*  
 Votre classe de propriétés.  

## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="members"></a>Membres  
  
### <a name="interface-methods"></a>Méthodes d’interface  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|Retourne la liste des propriétés dans le groupe de propriétés d’ensemble de lignes qui sont actuellement demandées pour l’ensemble de lignes.|  
|[SetProperties](#setproperties)|Définit les propriétés dans le groupe de propriétés d’ensemble de lignes.|  
  
## <a name="remarks"></a>Notes  
 Ce champ est obligatoire sur les commandes. L’implémentation est fournie par une fonction statique définie par le [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) macro.  

## <a name="getproperties"></a> ICommandPropertiesImpl::GetProperties
Retourne tous les jeux de propriété demandée à l’aide du mappage des propriétés de la commande.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [ICommandProperties::GetProperties](https://msdn.microsoft.com/library/ms723119.aspx) dans le *de référence du programmeur OLE DB*.  
  
### <a name="remarks"></a>Notes  
 Voir [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="setproperties"></a> ICommandPropertiesImpl::SetProperties
Définit les propriétés de l’objet de commande.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [ICommandProperties::SetProperties](https://msdn.microsoft.com/library/ms711497.aspx) dans le *de référence du programmeur OLE DB*.  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)