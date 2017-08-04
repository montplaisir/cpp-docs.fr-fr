---
title: "IDBSchemaRowsetImpl::CreateSchemaRowset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBSchemaRowsetImpl::CreateSchemaRowset"
  - "ATL::IDBSchemaRowsetImpl::CreateSchemaRowset"
  - "CreateSchemaRowset"
  - "IDBSchemaRowsetImpl.CreateSchemaRowset"
  - "ATL.IDBSchemaRowsetImpl.CreateSchemaRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSchemaRowset (méthode)"
ms.assetid: ad3e3e4d-45b9-461c-b7b8-3af6843631b1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IDBSchemaRowsetImpl::CreateSchemaRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente une fonction de création d’objet COM pour l’objet spécifié par le paramètre de modèle.  
  
## Syntaxe  
  
```  
  
template < class   
SchemaRowsetClass  
 >  
HRESULT CreateSchemaRowset(  
   IUnknown *  
pUnkOuter  
,  
   ULONG   
cRestrictions  
,  
   const VARIANT   
rgRestrictions  
[],  
   REFIID   
riid  
,  
   ULONG   
cPropertySets  
,  
   DBPROPSET   
rgPropertySets  
[],  
   IUnknown**   
ppRowset  
,  
   SchemaRowsetClass*&   
pSchemaRowset  
);  
  
```  
  
#### Paramètres  
 `pUnkOuter`  
 \[in\] [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) externe pendant l’agrégation ; sinon, **NULL**.  
  
 `cRestrictions`  
 \[in\] Nombre de restrictions appliquées à l’ensemble de lignes du schéma.  
  
 `rgRestrictions`  
 \[in\] Tableau de **VARIANT**s de `cRestrictions` à appliquer à l’ensemble de lignes.  
  
 `riid`  
 \[in\] Interface [QueryInterface](../../atl/queryinterface.md) pour le **IUnknown** de sortie.  
  
 `cPropertySets`  
 \[in\] Nombre de sets de propriétés à définir.  
  
 `rgPropertySets`  
 \[in\] Tableau de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) qui spécifient les propriétés définies.  
  
 `ppRowset`  
 \[out\] **IUnknown** sortant demandé par `riid`. Ce **IUnknown** est une interface sur l’objet d’ensemble de lignes du schéma.  
  
 `pSchemaRowset`  
 \[out\] Pointeur vers une instance de la classe d’ensemble de lignes du schéma. Ce paramètre n’est généralement pas utilisé, mais il peut l’être si vous devez effectuer des tâches supplémentaires sur l’ensemble de lignes du schéma avant de le passer à un objet COM. La durée de vie de `pSchemaRowset` est limitée par `ppRowset`.  
  
## Valeur de retour  
 Valeur `HRESULT` standard.  
  
## Notes  
 Cette fonction implémente un créateur générique pour tous les types d’ensembles de lignes du schéma. En règle générale, l’utilisateur n’appelle pas cette fonction. Elle est appelée par l’implémentation du mappage de schéma.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IDBSchemaRowsetImpl, classe](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/fr-fr/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)   
 [Classes de jeu de lignes du schéma et classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)