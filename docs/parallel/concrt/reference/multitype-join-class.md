---
title: multitype_join, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- multitype_join
- AGENTS/concurrency::multitype_join
- AGENTS/concurrency::multitype_join::multitype_join
- AGENTS/concurrency::multitype_join::accept
- AGENTS/concurrency::multitype_join::acquire_ref
- AGENTS/concurrency::multitype_join::consume
- AGENTS/concurrency::multitype_join::link_target
- AGENTS/concurrency::multitype_join::release
- AGENTS/concurrency::multitype_join::release_ref
- AGENTS/concurrency::multitype_join::reserve
- AGENTS/concurrency::multitype_join::unlink_target
- AGENTS/concurrency::multitype_join::unlink_targets
dev_langs:
- C++
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 03cb8520f9c4511aaff238f672f77b74b623b349
ms.contentlocale: fr-fr
ms.lasthandoff: 03/17/2017

---
# <a name="multitypejoin-class"></a>multitype_join, classe
Un bloc de messagerie `multitype_join` est un bloc de messagerie à sources multiples et à cible unique qui combine des messages de types différents en provenance de chacune de ses sources et qui offre un tuple des messages combinés à ses cibles.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<
    typename T,  
    join_type _Jtype = non_greedy  
>  
class multitype_join: public ISource<typename _Unwrap<T>::type>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le `tuple` type de charge utile des messages joints et propagés par le bloc.  
  
 `_Jtype`  
 Le genre de `join` bloc est `greedy` ou`non_greedy`  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`type`|Alias de type pour `T`.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[multitype_join](#ctor)|Surchargé. Construit un bloc de messagerie `multitype_join` .|  
|[~ multitype_join, destructeur](#dtor)|Détruit le `multitype_join` bloc de messagerie.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[accepter](#accept)|Accepte un message qui a été transmis par ce `multitype_join` bloc, en transférant la propriété à l’appelant.|  
|[acquire_ref](#acquire_ref)|Acquiert un décompte de références sur ce `multitype_join` bloc de messagerie, pour empêcher la suppression.|  
|[consommer](#consume)|Consomme un message précédemment offert par le `multitype_join` bloc de messagerie et réservé avec succès par la cible, en transférant la propriété à l’appelant.|  
|[link_target](#link_target)|Lie un bloc cible à ce `multitype_join` bloc de messagerie.|  
|[release](#release)|Libère une réservation de message réussie précédente.|  
|[release_ref](#release_ref)|Libère un décompte de références sur ce `multiple_join` bloc de messagerie.|  
|[reserve](#reserve)|Réserve un message précédemment offert par ce `multitype_join` bloc de messagerie.|  
|[unlink_target](#unlink_target)|Dissocie un bloc cible de ce `multitype_join` bloc de messagerie.|  
|[unlink_targets](#unlink_targets)|Dissocie toutes les cibles de ce `multitype_join` bloc de messagerie. (Substitue [ISource::unlink_targets](isource-class.md#unlink_targets).)|  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [ISource](isource-class.md)  
  
 `multitype_join`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="accept"></a>accepter 

 Accepte un message qui a été transmis par ce `multitype_join` bloc, en transférant la propriété à l’appelant.  
  
```  
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de l’offerte `message` objet.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `accept` méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le message dont l’appelant est désormais propriétaire.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 Acquiert un décompte de références sur ce `multitype_join` bloc de messagerie, pour empêcher la suppression.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers le bloc cible qui appelle cette méthode.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée par une `ITarget` objet lié à cette source pendant la `link_target` méthode.  
  
##  <a name="consume"></a>consommer 

 Consomme un message précédemment offert par le `multitype_join` bloc de messagerie et réservé avec succès par la cible, en transférant la propriété à l’appelant.  
  
```  
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de réservée `message` objet.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `consume` méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `message` que l’appelant est désormais propriétaire de l’objet.  
  
### <a name="remarks"></a>Remarques  
 Le `consume` méthode est similaire à `accept`, mais doit toujours être précédé par un appel à `reserve` qui a retourné `true`.  
  
##  <a name="link_target"></a>link_target 

 Lie un bloc cible à ce `multitype_join` bloc de messagerie.  
  
```  
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Un pointeur vers un `ITarget` à lier à ce bloc `multitype_join` bloc de messagerie.  
  
##  <a name="ctor"></a>multitype_join 

 Construit un bloc de messagerie `multitype_join` .  
  
```  
explicit multitype_join(
    T _Tuple);

 
multitype_join(
    Scheduler& _PScheduler,  
    T _Tuple);

 
multitype_join(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
multitype_join(
    multitype_join&& _Join);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Tuple`  
 `tuple` de sources pour ce bloc de messagerie `multitype_join` .  
  
 `_PScheduler`  
 Objet `Scheduler` dans lequel la tâche de propagation du bloc de messagerie `multitype_join` est planifiée.  
  
 `_PScheduleGroup`  
 Objet `ScheduleGroup` dans lequel la tâche de propagation du bloc de messagerie `multitype_join` est planifiée. L’objet `Scheduler` utilisé est suggéré par le groupe de planification.  
  
 `_Join`  
 Bloc de messagerie `multitype_join` à partir duquel la copie est effectuée. Notez que l’objet d'origine est orphelin, ce qui en fait un constructeur de déplacement.  
  
### <a name="remarks"></a>Remarques  
 Le runtime utilise le planificateur par défaut si vous ne spécifiez pas les paramètres `_PScheduler` ou `_PScheduleGroup` .  
  
 La construction du déplacement ne s’exécute pas en présence d’un verrou, ce qui signifie que c’est à l’utilisateur de s’assurer qu’il n’y a pas de tâches non activables en vol au moment du déplacement. Sinon, de nombreuses courses peuvent se produire, ce qui aboutit à des exceptions ou à un état incohérent.  
  
##  <a name="dtor"></a>~ multitype_join 

 Détruit le `multitype_join` bloc de messagerie.  
  
```  
~multitype_join();
```  
  
##  <a name="release"></a>version 

 Libère une réservation de message réussie précédente.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` libéré de l’objet.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `release` méthode.  
  
##  <a name="release_ref"></a>release_ref 

 Libère un décompte de références sur ce `multiple_join` bloc de messagerie.  
  
```  
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers le bloc cible qui appelle cette méthode.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée par un `ITarget` objet dissocié de cette source. Le bloc source est autorisé à libérer les ressources réservées pour le bloc cible.  
  
##  <a name="reserve"></a>réserve 

 Réserve un message précédemment offert par ce `multitype_join` bloc de messagerie.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` de l’objet en cours de réservation.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `reserve` méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le message a été réservé, `false` dans le cas contraire. Les réservations peuvent échouer pour de nombreuses raisons, notamment : le message a été déjà réservé ou accepté par une autre cible, la source pourrait refuser des réservations et ainsi de suite.  
  
### <a name="remarks"></a>Remarques  
 Après avoir appelé `reserve`, si elle réussit, vous devez appeler `consume` ou `release` pour accepter ou renoncer à la possession du message, respectivement.  
  
##  <a name="unlink_target"></a>unlink_target 

 Dissocie un bloc cible de ce `multitype_join` bloc de messagerie.  
  
```  
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Un pointeur vers un `ITarget` à dissocier de ce bloc `multitype_join` bloc de messagerie.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 Dissocie toutes les cibles de ce `multitype_join` bloc de messagerie.  
  
```  
virtual void unlink_targets();
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Classe Choice](choice-class.md)   
 [join, classe](join-class.md)
