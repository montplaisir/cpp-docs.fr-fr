---
title: Idbcreatesessionimpl, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 756cc7ba203a1655bf5112d9c03e84707644f1e5
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337568"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl, classe
Fournit une implémentation pour le [IDBCreateSession](https://msdn.microsoft.com/library/ms724076.aspx) interface.  
  
## <a name="syntax"></a>Syntaxe

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
### <a name="parameters"></a>Paramètres  
 *T*  
 VOTRE CLASSE DÉRIVÉE  
  
 *SessionClass*  
 L’objet de session.  

## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h 
  
## <a name="members"></a>Membres  
  
### <a name="interface-methods"></a>Méthodes d’interface  
  
|||  
|-|-|  
|[CreateSession](#createsession)|Crée une nouvelle session de l’objet de source de données et retourne l’interface demandée sur la session nouvellement créée.|  
  
## <a name="remarks"></a>Notes  
 Une interface obligatoire sur les objets de source de données.  

## <a name="createsession"></a> IDBCreateSessionImpl::CreateSession
Crée une nouvelle session de l’objet de source de données et retourne l’interface demandée sur la session nouvellement créée.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppDBSession);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IDBCreateSession::CreateSession](https://msdn.microsoft.com/library/ms714942.aspx) dans le *de référence du programmeur OLE DB*.   
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)