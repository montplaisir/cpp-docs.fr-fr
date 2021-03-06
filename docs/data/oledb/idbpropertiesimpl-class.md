---
title: Idbpropertiesimpl, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- GetProperties
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
- IDBPropertiesImpl.SetProperties
- SetProperties
- IDBPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- IDBPropertiesImpl class
- GetProperties method
- GetPropertyInfo method
- SetProperties method
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 51593d14967e2814d69cb0a912d937b689dc3632
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337113"
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl, classe
Fournit une implémentation pour le `IDBProperties` interface.  
  
## <a name="syntax"></a>Syntaxe

```cpp
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
### <a name="parameters"></a>Paramètres  
 *T*  
 Votre classe, dérivée de `IDBPropertiesImpl`.  

## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="members"></a>Membres  
  
### <a name="interface-methods"></a>Méthodes d’interface  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|Retourne les valeurs des propriétés dans les groupes de propriétés de Source de données, sources de données et d’initialisation qui sont actuellement définies sur l’objet de source de données ou les valeurs des propriétés dans le groupe de propriétés d’initialisation qui sont actuellement définies sur le énumérateur.|  
|[GetPropertyInfo](#getpropertyinfo)|Retourne des informations sur toutes les propriétés prises en charge par le fournisseur.|  
|[SetProperties](#setproperties)|Définit les propriétés dans les groupes de propriétés de Source de données et d’initialisation, pour les objets de source de données, ou le groupe de propriétés d’initialisation pour les énumérateurs.|  
  
## <a name="remarks"></a>Notes  
 [IDBProperties](https://msdn.microsoft.com/library/ms719607.aspx) est une interface obligatoire pour les objets de source de données et une interface facultative pour les énumérateurs. Toutefois, si un énumérateur expose [IDBInitialize](https://msdn.microsoft.com/library/ms713706.aspx), elle doit exposer `IDBProperties`. `IDBPropertiesImpl` implémente `IDBProperties` à l’aide d’une fonction statique définie par [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

## <a name="getproperties"></a> IDBPropertiesImpl::GetProperties
Retourne les valeurs des propriétés dans les groupes de propriétés de Source de données, sources de données et d’initialisation qui sont actuellement définies sur l’objet de source de données ou les valeurs des propriétés dans le groupe de propriétés d’initialisation qui sont actuellement définies sur le énumérateur.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp
STDMETHOD(GetProperties)(ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IDBProperties::GetProperties](https://msdn.microsoft.com/library/ms714344.aspx) dans le *de référence du programmeur OLE DB*.  
  
 Certains paramètres correspondent aux *de référence du programmeur OLE DB* des noms différents, qui sont décrites dans les paramètres `IDBProperties::GetProperties`:  
  
|Paramètres de modèle OLE DB|*Référence du programmeur OLE DB* paramètres|  
|--------------------------------|------------------------------------------------|  
|*cPropertySets*|*cPropertyIDSets*|  
|*rgPropertySets*|*rgPropertyIDSets*|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
### <a name="remarks"></a>Notes  
 Si le fournisseur est initialisé, cette méthode retourne les valeurs des propriétés dans le DBPROPSET_DATASOURCE, DBPROPSET_DATASOURCEINFO, les groupes de propriétés DBPROPSET_DBINIT qui sont actuellement définies sur l’objet de source de données. Si le fournisseur n’est pas initialisé, elle retourne uniquement les propriétés de groupe DBPROPSET_DBINIT. 
  
## <a name="getpropertyinfo"></a> IDBPropertiesImpl::GetPropertyInfo
Retourne des informations de propriété pris en charge par la source de données.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp
STDMETHOD(GetPropertyInfo)(ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcPropertyInfoSets,   
   DBPROPINFOSET ** prgPropertyInfoSets,   
   OLECHAR ** ppDescBuffer);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IDBProperties::GetPropertyInfo](https://msdn.microsoft.com/library/ms718175.aspx) dans le *de référence du programmeur OLE DB*.  
  
 Certains paramètres correspondent aux *de référence du programmeur OLE DB* des noms différents, qui sont décrites dans les paramètres `IDBProperties::GetPropertyInfo`:  
  
|Paramètres de modèle OLE DB|*Référence du programmeur OLE DB* paramètres|  
|--------------------------------|------------------------------------------------|  
|*cPropertySets*|*cPropertyIDSets*|  
|*rgPropertySets*|*rgPropertyIDSets*|  
  
### <a name="remarks"></a>Notes  
 Utilise [IDBInitializeImpl::m_pCUtlPropInfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) pour implémenter cette fonctionnalité. 

## <a name="setproperties"></a> IDBPropertiesImpl::SetProperties
Définit les propriétés dans les groupes de propriétés de Source de données et d’initialisation, pour les objets de source de données, ou le groupe de propriétés d’initialisation pour les énumérateurs.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IDBProperties::SetProperties](https://msdn.microsoft.com/library/ms723049.aspx) dans le *de référence du programmeur OLE DB*.  
  
### <a name="remarks"></a>Notes  
 Si le fournisseur est initialisé, cette méthode définit les valeurs des propriétés dans le DBPROPSET_DATASOURCE, DBPROPSET_DATASOURCEINFO, groupes de propriétés DBPROPSET_DBINIT pour l’objet de source de données. Si le fournisseur n’est pas initialisé, elle définit uniquement les propriétés de groupe DBPROPSET_DBINIT.  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)