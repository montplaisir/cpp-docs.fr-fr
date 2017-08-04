---
title: Classe unbounded_buffer | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unbounded_buffer
- AGENTS/concurrency::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::dequeue
- AGENTS/concurrency::unbounded_buffer::enqueue
- AGENTS/concurrency::unbounded_buffer::accept_message
- AGENTS/concurrency::unbounded_buffer::consume_message
- AGENTS/concurrency::unbounded_buffer::link_target_notification
- AGENTS/concurrency::unbounded_buffer::process_input_messages
- AGENTS/concurrency::unbounded_buffer::propagate_message
- AGENTS/concurrency::unbounded_buffer::propagate_output_messages
- AGENTS/concurrency::unbounded_buffer::release_message
- AGENTS/concurrency::unbounded_buffer::reserve_message
- AGENTS/concurrency::unbounded_buffer::resume_propagation
- AGENTS/concurrency::unbounded_buffer::send_message
- AGENTS/concurrency::unbounded_buffer::supports_anonymous_source
dev_langs:
- C++
ms.assetid: 6b1a939a-1819-4385-b1d8-708f83d4ec47
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 9a9c44985b1e9475b8760d835e2a8fd45361ea5a
ms.lasthandoff: 03/17/2017

---


Un bloc de messagerie `unbounded_buffer` est un `propagator_block` à cibles multiples, à sources multiples et ordonné, capable de stocker un nombre illimité de messages.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<  
   class             _Type  
>  
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Type`  
 Type de charge utile des messages stockés et propagés par la mémoire tampon.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[unbounded_buffer](#ctor)|Surchargé. Construit un `unbounded_buffer` bloc de messagerie.|  
|[~ unbounded_buffer, destructeur](#dtor)|Détruit le `unbounded_buffer` bloc de messagerie.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[la file d’attente](#dequeue)|Supprime un élément de la `unbounded_buffer` bloc de messagerie.|  
|[file d’attente](#enqueue)|Ajoute un élément à la `unbounded_buffer` bloc de messagerie.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[accept_message](#accept_message)|Accepte un message qui a été transmis par ce `unbounded_buffer` messagerie bloc, en transférant la propriété à l’appelant.|  
|[consume_message](#consume_message)|Consomme un message précédemment offert par le `unbounded_buffer` bloc de messagerie et réservé par la cible, en transférant la propriété à l’appelant.|  
|[link_target_notification](#link_target_notification)|Rappel qui notifie qu’une nouvelle cible a été liée à ce `unbounded_buffer` bloc de messagerie.|  
|[process_input_messages](#process_input_messages)|Place le `message``_PMessage` dans ce `unbounded_buffer` bloc de messagerie et essaie d’offrir à toutes les cibles liées.|  
|[propagate_message](#propagate_message)|Passe de façon asynchrone un message à partir d’un `ISource` à ce bloc `unbounded_buffer` bloc de messagerie. Il est appelé par le `propagate` la méthode appelée par un bloc source.|  
|[propagate_output_messages](#propagate_output_messages)|Place le `message``_PMessage` dans ce `unbounded_buffer` bloc de messagerie et essaie d’offrir à toutes les cibles liées. (Substitue [source_block::propagate_output_messages](source-block-class.md#propagate_output_messages).)|  
|[release_message](#release_message)|Libère une réservation de message précédente. (Substitue [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Réserve un message précédemment offert par ce `unbounded_buffer` bloc de messagerie. (Substitue [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Reprend la propagation après qu’une réservation a été libérée. (Substitue [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message](#send_message)|Passe de façon synchrone un message à partir d’un `ISource` à ce bloc `unbounded_buffer` bloc de messagerie. Il est appelé par le `send` la méthode appelée par un bloc source.|  
|[supports_anonymous_source](#supports_anonymous_source)|Remplace la `supports_anonymous_source` méthode pour indiquer que ce bloc peut accepter des messages offerts par une source qui n’est pas liée. (Substitue [ITarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  

 Pour plus d’informations, consultez [blocs de messages asynchrones](../asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `unbounded_buffer`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="accept_message"></a>accept_message 

 Accepte un message qui a été transmis par ce `unbounded_buffer` messagerie bloc, en transférant la propriété à l’appelant.  
  
```  
virtual message<_Type> * accept_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de l’offerte `message` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `message` que l’appelant est désormais propriétaire de l’objet.  
  
##  <a name="consume_message"></a>consume_message 

 Consomme un message précédemment offert par le `unbounded_buffer` bloc de messagerie et réservé par la cible, en transférant la propriété à l’appelant.  
  
```  
virtual message<_Type> * consume_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` de l’objet en cours de consommation.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `message` que l’appelant est désormais propriétaire de l’objet.  
  
### <a name="remarks"></a>Notes  
 Semblable à `accept`, mais est toujours précédé par un appel à `reserve`.  
  
##  <a name="dequeue"></a>la file d’attente 

 Supprime un élément de la `unbounded_buffer` bloc de messagerie.  
  
```  
_Type dequeue();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La charge utile du message supprimé de la `unbounded_buffer`.  
  
##  <a name="enqueue"></a>file d’attente 

 Ajoute un élément à la `unbounded_buffer` bloc de messagerie.  
  
```  
bool enqueue(  
   _Type const&                 _Item  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Item`  
 Élément à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si l’élément a été accepté, `false` dans le cas contraire.  
  
##  <a name="link_target_notification"></a>link_target_notification 

 Rappel qui notifie qu’une nouvelle cible a été liée à ce `unbounded_buffer` bloc de messagerie.  
  
```  
virtual void link_target_notification(  
   _Inout_ ITarget<_Type> *                 _PTarget  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers la cible récemment liée.  
  
##  <a name="propagate_message"></a>propagate_message 

 Passe de façon asynchrone un message à partir d’un `ISource` à ce bloc `unbounded_buffer` bloc de messagerie. Il est appelé par le `propagate` la méthode appelée par un bloc source.  
  
```  
virtual message_status propagate_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers l'objet `message`.  
  
 `_PSource`  
 Pointeur vers le bloc source qui transmet le message.  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md#message_status) indication de ce que la cible a décidé de faire avec ce message.  
  
##  <a name="propagate_output_messages"></a>propagate_output_messages 

 Place le `message``_PMessage` dans ce `unbounded_buffer` bloc de messagerie et essaie d’offrir à toutes les cibles liées.  
  
```  
virtual void propagate_output_messages();  
```  
  
### <a name="remarks"></a>Notes  
 Si un autre message est déjà à celle-ci dans le `unbounded_buffer`, la propagation aux cibles liées ne se produit pas jusqu'à ce que les premiers messages ont été acceptés ou consommés. La première cible liée qui a été `accept` ou `consume` le message prend la propriété, et aucune autre cible ne peut ensuite obtenir le message.  
  
##  <a name="process_input_messages"></a>process_input_messages 

 Place le `message``_PMessage` dans ce `unbounded_buffer` bloc de messagerie et essaie d’offrir à toutes les cibles liées.  
  
```  
virtual void process_input_messages(  
   _Inout_ message<_Type> *                 _PMessage  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
  
##  <a name="release_message"></a>release_message 

 Libère une réservation de message précédente.  
  
```  
virtual void release_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` libéré de l’objet.  
  
##  <a name="reserve_message"></a>reserve_message 

 Réserve un message précédemment offert par ce `unbounded_buffer` bloc de messagerie.  
  
```  
virtual bool reserve_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` de l’objet en cours de réservation.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le message a été réservé, `false` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Après avoir `reserve` est appelée, si elle retourne `true`, `consume` ou `release` doit être appelé pour accepter ou libérer la propriété du message.  
  
##  <a name="resume_propagation"></a>resume_propagation 

 Reprend la propagation après qu’une réservation a été libérée.  
  
```  
virtual void resume_propagation();  
```  
  
##  <a name="send_message"></a>send_message 

 Passe de façon synchrone un message à partir d’un `ISource` à ce bloc `unbounded_buffer` bloc de messagerie. Il est appelé par le `send` la méthode appelée par un bloc source.  
  
```  
virtual message_status send_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers l'objet `message`.  
  
 `_PSource`  
 Pointeur vers le bloc source qui transmet le message.  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md#message_status) indication de ce que la cible a décidé de faire avec ce message.  
  
##  <a name="supports_anonymous_source"></a>supports_anonymous_source 

 Remplace la `supports_anonymous_source` méthode pour indiquer que ce bloc peut accepter des messages offerts par une source qui n’est pas liée.  
  
```  
virtual bool supports_anonymous_source();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Étant donné que le bloc ne pas reporter des messages transmis.  
  
##  <a name="ctor"></a>unbounded_buffer 

 Construit un `unbounded_buffer` bloc de messagerie.  
  
```  
unbounded_buffer();  
  
unbounded_buffer(  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler,  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup,  
   filter_method const&                 _Filter  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Filter`  
 Fonction de filtre qui détermine si les messages transmis doivent être acceptés.  
  
 `_PScheduler`  
 Le `Scheduler` objet dans lequel la tâche de propagation pour le `unbounded_buffer` bloc de messagerie est planifiée.  
  
 `_PScheduleGroup`  
 Le `ScheduleGroup` objet dans lequel la tâche de propagation pour le `unbounded_buffer` bloc de messagerie est planifiée. L’objet `Scheduler` utilisé est suggéré par le groupe de planification.  
  
### <a name="remarks"></a>Notes  
 Le runtime utilise le planificateur par défaut si vous ne spécifiez pas les paramètres `_PScheduler` ou `_PScheduleGroup` .  
  
 Le type `filter_method` est un functor avec la signature `bool (_Type const &)` qui est appelé par ce `unbounded_buffer` bloc de messagerie afin de déterminer si elle doit accepter un message proposé.  
  
##  <a name="dtor"></a>~ unbounded_buffer 

 Détruit le `unbounded_buffer` bloc de messagerie.  
  
```  
~unbounded_buffer();  
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Classe overwrite_buffer](overwrite-buffer-class.md)   
 [single_assignment, classe](single-assignment-class.md)


