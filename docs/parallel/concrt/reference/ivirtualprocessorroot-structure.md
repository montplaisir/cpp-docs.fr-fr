---
title: IVirtualProcessorRoot, Structure | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Activate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Deactivate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::EnsureAllTasksVisible
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::GetId
dev_langs:
- C++
helpviewer_keywords:
- IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9620ee391b525356bfdb50b00d7e76c03b480815
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692424"
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot, structure
Abstraction d'un thread matériel sur laquelle un proxy de thread peut s'exécuter.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct IVirtualProcessorRoot : public IExecutionResource;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IVirtualProcessorRoot::Activate](#activate)|Provoque le proxy de thread associé à l’interface du contexte d’exécution `pContext` pour lancer l’exécution sur cette racine de processeur virtuel.|  
|[IVirtualProcessorRoot::Deactivate](#deactivate)|Provoque le proxy de thread en cours d’exécution sur cette racine de processeur virtuel arrête de distribuer le contexte d’exécution. Le proxy de thread reprendra l’exécution sur un appel à la `Activate` (méthode).|  
|[IVirtualProcessorRoot::EnsureAllTasksVisible](#ensurealltasksvisible)|Provoque des données stockées dans la hiérarchie de la mémoire de processeurs individuels visibles à tous les processeurs sur le système. Elle garantit qu’une barrière de mémoire a été exécutée sur tous les processeurs avant le retour de la méthode.|  
|[IVirtualProcessorRoot::GetId](#getid)|Retourne un identificateur unique pour la racine de processeur virtuel.|  
  
## <a name="remarks"></a>Notes  
 Chaque racine de processeur virtuel a une ressource d’exécution associés. Le `IVirtualProcessorRoot` interface hérite de la [IExecutionResource](iexecutionresource-structure.md) interface. Plusieurs racines de processeur virtuel peuvent correspondre au même thread matériel sous-jacent.  
  
 Le Gestionnaire des ressources accorde des racines de processeur virtuel aux planificateurs en réponse aux demandes de ressources. Un planificateur peut utiliser une racine de processeur virtuel pour effectuer le travail en l’activant avec un contexte d’exécution.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [IExecutionResource](iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="activate"></a>  IVirtualProcessorRoot::Activate, méthode  
 Provoque le proxy de thread associé à l’interface du contexte d’exécution `pContext` pour lancer l’exécution sur cette racine de processeur virtuel.  
  
```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `pContext`  
 Une interface pour le contexte d’exécution qui sera distribué sur cette racine de processeur virtuel.  
  
### <a name="remarks"></a>Notes  
 Le Gestionnaire des ressources fournira un proxy de thread si ce n’est associé à l’interface du contexte d’exécution `pContext`  
  
 Le `Activate` méthode peut être utilisée pour lancer l’exécution du travail sur une racine de processeur virtuel retournée par le Gestionnaire de ressources ou pour reprendre le proxy de thread sur une racine de processeur virtuel désactivé ou est sur le point de désactiver. Consultez [IVirtualProcessorRoot::Deactivate](#deactivate) pour plus d’informations sur la désactivation. Lorsque vous reprenez une racine de processeur virtuel désactivée, le paramètre `pContext` doit être le même que le paramètre utilisé pour désactiver la racine de processeur virtuel.  
  
 Une fois qu’une racine de processeur virtuel a été activée pour la première fois, les paires suivantes d’appels à `Deactivate` et `Activate` peuvent être en concurrence avec eux. Cela signifie que le Gestionnaire des ressources pour recevoir un appel à `Activate` avant de recevoir le `Deactivate` appel prévu.  
  
 Lorsque vous activez une racine de processeur virtuel, vous indiquent au Gestionnaire de ressources que cette racine de processeur virtuel est actuellement occupée. Si votre planificateur ne peut pas trouver de travail à exécuter sur cette racine, il doit appeler la `Deactivate` méthode pour informer le Gestionnaire de ressources que la racine de processeur virtuel est inactive. Le Gestionnaire de ressources utilise ces données pour le système d’équilibrer la charge.  
  
 `invalid_argument` est levée si l’argument `pContext` a la valeur `NULL`.  
  
 `invalid_operation` est levée si l’argument `pContext` ne représente pas le contexte d’exécution qui a été distribué le plus récemment par cette racine de processeur virtuel.  
  
 Le fait de l’activation d’une racine de processeur virtuel augmente le niveau d’abonnement du thread matériel sous-jacent d’une unité. Pour plus d’informations sur les niveaux d’abonnement, consultez [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="deactivate"></a>  IVirtualProcessorRoot::Deactivate, méthode  
 Provoque le proxy de thread en cours d’exécution sur cette racine de processeur virtuel arrête de distribuer le contexte d’exécution. Le proxy de thread reprendra l’exécution sur un appel à la `Activate` (méthode).  
  
```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `pContext`  
 Contexte actuellement distribué par cette racine.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne. La valeur `true` indique que le proxy de thread retourné à partir de la `Deactivate` méthode en réponse à un appel à la `Activate` (méthode). La valeur `false` indique que le proxy de thread retourné par la méthode en réponse à un événement de notification dans le Gestionnaire de ressources. Sur un planificateur de threads (UMS) en mode utilisateur planifiable, cela indique que les éléments apparaissent dans la liste de saisie semi-automatique du planificateur et le planificateur est requis pour les gérer.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour arrêter temporairement l’exécution d’une racine de processeur virtuel lorsque vous ne peut pas trouver de travail dans votre planificateur. Un appel à la `Deactivate` méthode doit provenir de la `Dispatch` méthode du contexte d’exécution de la dernière activation de la racine de processeur virtuel avec. En d’autres termes, le proxy de thread appelant le `Deactivate` méthode doit être celui qui est en cours d’exécution sur la racine de processeur virtuel. Appel de la méthode sur une racine de processeur virtuel que vous n’exécutez pas sur peut entraîner un comportement non défini.  
  
 Une racine de processeur virtuel désactivée peut être réveillée par un appel à la `Activate` (méthode), avec le même argument qui a été transmis à la `Deactivate` (méthode). Le planificateur est chargé de s’assurer que les appels à la `Activate` et `Deactivate` méthodes sont associés, mais ils ne sont pas obligatoirement être reçus dans un ordre spécifique. Le Gestionnaire de ressources peut gérer la réception d’un appel à la `Activate` méthode avant de recevoir un appel à la `Deactivate` méthode prévu.  
  
 Si une racine de processeur virtuel déclenche et la valeur de retour à partir de la `Deactivate` méthode est la valeur `false`, le planificateur doit interroger la liste de saisie semi-automatique UMS via la `IUMSCompletionList::GetUnblockNotifications` méthode, agir sur ces informations, puis appeler la `Deactivate`(méthode) à nouveau. Cela doit être répété jusqu'à ce que le `Deactivate` méthode retourne la valeur `true`.  
  
 `invalid_argument` est levée si l’argument `pContext` a la valeur `NULL`.  
  
 `invalid_operation` est levée si la racine de processeur virtuel n’a jamais été activée, ou l’argument `pContext` ne représente pas le contexte d’exécution qui a été distribué le plus récemment par cette racine de processeur virtuel.  
  
 Le fait de la désactivation d’une racine de processeur virtuel diminue le niveau d’abonnement du thread matériel sous-jacent de 1. Pour plus d’informations sur les niveaux d’abonnement, consultez [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="ensurealltasksvisible"></a>  IVirtualProcessorRoot::EnsureAllTasksVisible, méthode  
 Provoque des données stockées dans la hiérarchie de la mémoire de processeurs individuels visibles à tous les processeurs sur le système. Elle garantit qu’une barrière de mémoire a été exécutée sur tous les processeurs avant le retour de la méthode.  
  
```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `pContext`  
 Contexte actuellement distribué par cette racine de processeur virtuel.  
  
### <a name="remarks"></a>Notes  
 Vous trouverez cette méthode utiles lorsque vous souhaitez synchroniser la désactivation d’une racine de processeur virtuel avec l’ajout de nouvelles tâches dans le planificateur. Pour des raisons de performances, vous pouvez décider ajouter des éléments de travail à votre planificateur sans exécuter une barrière de mémoire, ce qui signifie que les éléments de travail ajoutés par un thread d’exécution sur un seul processeur ne sont pas immédiatement visibles pour tous les autres processeurs. À l’aide de cette méthode conjointement avec la `Deactivate` racines de méthode, vous pouvez vous assurer que votre planificateur ne désactive pas toutes ses processeur virtuel lorsqu’il existent des éléments de travail dans les collections de votre planificateur.  
  
 Un appel à la `EnsureAllTasksVisibleThe` méthode doit provenir de la `Dispatch` méthode du contexte d’exécution de la dernière activation de la racine de processeur virtuel avec. En d’autres termes, le proxy de thread appelant le `EnsureAllTasksVisible` méthode doit être celui qui est en cours d’exécution sur la racine de processeur virtuel. Appel de la méthode sur une racine de processeur virtuel que vous n’exécutez pas sur peut entraîner un comportement non défini.  
  
 `invalid_argument` est levée si l’argument `pContext` a la valeur `NULL`.  
  
 `invalid_operation` est levée si la racine de processeur virtuel n’a jamais été activée, ou l’argument `pContext` ne représente pas le contexte d’exécution qui a été distribué le plus récemment par cette racine de processeur virtuel.  
  
##  <a name="getid"></a>  IVirtualProcessorRoot::GetId, méthode  
 Retourne un identificateur unique pour la racine de processeur virtuel.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Identificateur entier.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)
