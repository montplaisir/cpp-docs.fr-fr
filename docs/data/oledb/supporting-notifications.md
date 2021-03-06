---
title: Prise en charge des Notifications | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- events [C++], notifications in OLE DB
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB provider templates, notifications
- OLE DB providers, notifications
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9fea13ef4a89ee2a1105702db4fe692c12643d2
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337938"
---
# <a name="supporting-notifications"></a>Prise en charge des notifications

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>Implémentation d’Interfaces de Point de connexion sur le fournisseur et le consommateur  
 Pour implémenter des notifications, une classe de fournisseur doit hériter [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) et [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md).  
  
 `IRowsetNotifyCP` implémente le site du fournisseur pour l’interface de point de connexion [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx). `IRowsetNotifyCP` implémente des fonctions pour informer les écouteurs sur le point de connexion de diffusion `IID_IRowsetNotify` des modifications apportées au contenu de l’ensemble de lignes.  
  
 Notez que vous devez également implémenter et inscrire `IRowsetNotify` sur le consommateur (également appelé le récepteur) à l’aide de [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) afin que le consommateur peut gérer les notifications. Pour plus d’informations sur l’implémentation de l’interface de point de connexion sur le consommateur, consultez [réception des Notifications](../../data/oledb/receiving-notifications.md).  
  
 En outre, la classe doit également contenir un mappage qui définit l’entrée du point de connexion, comme suit :  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## <a name="adding-irowsetnotify"></a>Ajout de IRowsetNotify  
 Pour ajouter `IRowsetNotify`, vous devez ajouter `IConnectionPointContainerImpl<rowset-name>` et `IRowsetNotifyCP<rowset-name>` à votre chaîne d’héritage.  
  
 Par exemple, voici la chaîne d’héritage pour `RUpdateRowset` dans [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  L’exemple de code peut-être différer de ceux répertoriés ici ; Considérez l’exemple de code en tant que la version la plus récente.  
  
```cpp
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan>>, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll >>,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### <a name="setting-com-map-entries"></a>Définition des entrées de mappage COM  
 Vous devez également ajouter le code suivant au mappage COM dans votre ensemble de lignes :  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 Ces macros autoriser tout le monde appelant `QueryInterface` pour votre conteneur de point de connexion (la base de `IRowsetNotify`) pour trouver l’interface demandée sur votre fournisseur. Pour obtenir un exemple montrant comment utiliser les points de connexion, consultez l’exemple ATL POLYGON et le didacticiel.  
  
### <a name="setting-connection-point-map-entries"></a>Définition des entrées de mappage de Point de connexion  
 Vous devez également ajouter un mappage de point de connexion. Il doit ressembler à :  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 Ce mappage de point de connexion permet à un composant que vous recherchez le `IRowsetNotify` interface pour la rechercher dans votre fournisseur.  
  
### <a name="setting-properties"></a>Définition des propriétés  
 Vous devez également ajouter les propriétés suivantes à votre fournisseur. Vous devez uniquement ajouter des propriétés basées sur les interfaces que vous prenez en charge.  
  
|Propriété|Ajouter si vous prenez en charge|  
|--------------|------------------------|  
|`DBPROP_IConnectionPointContainer`|Toujours|  
|`DBPROP_NOTIFICATIONGRANULARITY`|Toujours|  
|`DBPROP_NOTIFICATIONPHASES`|Toujours|  
|`DBPROP_NOTIFYCOLUMNSET`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWDELETE`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWINSERT`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE`|Toujours|  
|`DBPROP_NOTIFYROWFIRSTCHANGE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWSETRELEASE`|Toujours|  
|`DBPROP_NOTIFYROWUNDOCHANGE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUNDODELETE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUNDOINSERT`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUPDATE`|`IRowsetUpdate`|  
  
 La majeure partie de l’implémentation pour les notifications sont déjà incorporées dans les modèles du fournisseur OLE DB. Si vous n’ajoutez pas `IRowsetNotifyCP` à votre chaîne d’héritage, le compilateur supprime tout ce code à partir de votre flux de compilation, ce qui rend la taille de votre code plus petits.  
  
## <a name="see-also"></a>Voir aussi  
 [Techniques avancées du fournisseur](../../data/oledb/advanced-provider-techniques.md)