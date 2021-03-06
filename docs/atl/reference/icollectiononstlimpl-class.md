---
title: ICollectionOnSTLImpl, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl::get__NewEnum
- ATLCOM/ATL::ICollectionOnSTLImpl::getcount
- ATLCOM/ATL::ICollectionOnSTLImpl::get_Item
- ATLCOM/ATL::ICollectionOnSTLImpl::m_coll
dev_langs:
- C++
helpviewer_keywords:
- ICollectionOnSTLImpl class
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 812deba7cb33a713d8b1a55eaa4c375092168dce
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881670"
---
# <a name="icollectiononstlimpl-class"></a>ICollectionOnSTLImpl, classe
Cette classe fournit des méthodes utilisées par une classe de collection.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>  
class ICollectionOnSTLImpl : public T
```  
  
#### <a name="parameters"></a>Paramètres  
 *T*  
 Une interface COM de la collection.  
  
 *CollType*  
 Une classe de conteneur de bibliothèque C++ Standard.  
  
 *ItemType*  
 Le type d’élément exposé par l’interface du conteneur.  
  
 *CopyItem*  
 Un [copier la classe de stratégie](../../atl/atl-copy-policy-classes.md).  
  
 *EnumType*  
 Un [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)-classe d’énumérateur compatible.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[ICollectionOnSTLImpl::get__NewEnum](#newenum)|Retourne un objet énumérateur pour la collection.|  
|[ICollectionOnSTLImpl::getcount](#get_count)|Retourne le nombre d’éléments dans la collection.|  
|[ICollectionOnSTLImpl::get_Item](#get_item)|Retourne l’élément demandé à partir de la collection.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[ICollectionOnSTLImpl::m_coll](#m_coll)|Collection.|  
  
## <a name="remarks"></a>Notes  
 Cette classe fournit l’implémentation pour les trois méthodes d’une interface de collection : [getcount](#get_count), [get_Item](#get_item), et [get__NewEnum](#newenum).  
  
 Pour utiliser cette classe :  
  
-   Définir ou empruntez une interface de collection que vous souhaitez implémenter.  
  
-   Dérivez votre classe à partir d’une spécialisation de `ICollectionOnSTLImpl` basées sur cette interface de collection.  
  
-   Utiliser votre classe dérivée pour implémenter toutes les méthodes à partir de l’interface de collection ne pas gérés par `ICollectionOnSTLImpl`.  
  
> [!NOTE]
>  Si l’interface de collection est une interface double, dérivez votre classe de [IDispatchImpl](../../atl/reference/idispatchimpl-class.md), en passant le `ICollectionOnSTLImpl` spécialisation comme premier paramètre de modèle si vous souhaitez ATL pour fournir l’implémentation de la `IDispatch` méthodes.  
  
-   Ajouter des éléments à la [m_coll](#m_coll) membre pour remplir la collection.  
  
 Pour plus d’informations et des exemples, consultez [Collections et énumérateurs ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `T`  
  
 `ICollectionOnSTLImpl`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlcom.h  
  
##  <a name="get_count"></a>  ICollectionOnSTLImpl::getcount  
 Cette méthode retourne le nombre d’éléments dans la collection.  
  
```
STDMETHOD(getcount)(long* pcount);
```  
  
### <a name="parameters"></a>Paramètres  
 *pcount*  
 [out] Le nombre d’éléments dans la collection.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
##  <a name="get_item"></a>  ICollectionOnSTLImpl::get_Item  
 Cette méthode retourne l’élément spécifié à partir de la collection.  
  
```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```  
  
### <a name="parameters"></a>Paramètres  
 *Index*  
 [in] L’index de base 1, d’un élément dans la collection.  
  
 *pVar*  
 [out] L’élément correspondant *Index*.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
### <a name="remarks"></a>Notes  
 L’élément est obtenu en copiant les données à la position spécifiée dans [m_coll](#m_coll) à l’aide de la méthode de copie de la [copier la classe de stratégie](../../atl/atl-copy-policy-classes.md) passé comme argument de modèle dans le `ICollectionOnSTLImpl` spécialisation.  
  
##  <a name="newenum"></a>  ICollectionOnSTLImpl::get__NewEnum  
 Retourne un objet énumérateur pour la collection.  
  
```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```  
  
### <a name="parameters"></a>Paramètres  
 *ppUnk*  
 [out] Le **IUnknown** pointeur d’un objet énumérateur créé récemment.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
### <a name="remarks"></a>Notes  
 L’énumérateur créé récemment conserve un itérateur de la collection d’origine, `m_coll`(donc aucune copie n’est effectuée) et maintient une référence COM sur l’objet de collection pour vous assurer que la collection reste active alors qu’il existe des énumérateurs en suspens.  
  
##  <a name="m_coll"></a>  ICollectionOnSTLImpl::m_coll  
 Ce membre contient les éléments représentés par la collection.  
  
```
CollType m_coll;
```  
  
## <a name="see-also"></a>Voir aussi  
 [ATLCollections, exemple](../../visual-cpp-samples.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
