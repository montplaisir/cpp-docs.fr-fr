---
title: event_receiver | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_receiver
dev_langs:
- C++
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0b13acb5d637b4a733f2a2b9c66c8ded977c7847
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569932"
---
# <a name="eventreceiver"></a>event_receiver
Crée un récepteur d'événements (récepteur).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 *type*  
 Une énumération de l’une des valeurs suivantes :  
  
-   `native` pour le code C/C++ non managé (valeur par défaut pour les classes natives).  
  
-   `com` pour le code COM. Cette valeur nécessite que vous incluiez les fichiers d’en-tête suivants :  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **layout_dependent**  
 Spécifiez *layout_dependent* uniquement si `type` = **com**. *layout_dependent* est une valeur booléenne :  
  
-   **true** signifie que la signature des délégués dans le récepteur doit correspondre exactement à ceux auxquels ils sont raccordés des source de l’événement des événements. Les noms de gestionnaire d’événements récepteur doivent correspondre aux noms spécifiés dans l’interface de source d’événement pertinent. Vous devez utiliser `coclass` lorsque *layout_dependent* est **true**. Il est légèrement plus efficace de spécifier **true**.  
  
-   **false** (valeur par défaut) signifie que la classe de stockage et de la convention d’appel (virtuelle, statique, etc.) n’ont pas à correspondre à la méthode d’événement et les gestionnaires ; ni les noms des gestionnaires doivent-ils correspondre aux noms de méthode source interface d’événements.  
  
## <a name="remarks"></a>Notes  
 Le **event_receiver** attribut C++ indique que la classe ou structure à laquelle il est appliqué est un récepteur d’événements, l’utilisation du modèle d’événement unifié de Visual C++.  
  
 **event_receiver** est utilisé avec le [event_source](../windows/event-source.md) attribut et la [__hook](../cpp/hook.md) et [__unhook](../cpp/unhook.md) mots clés. Utilisez `event_source` pour créer des sources d’événements. Utilisez **__hook** dans les méthodes d’un récepteur d’événements à associer (« raccordement ») des méthodes de récepteur d’événements pour les événements de source d’événements. Utilisez **__unhook** pour dissocier les.  
  
 *layout_dependent* est spécifié uniquement pour les récepteurs d’événements COM (`type`=**com**). La valeur par défaut pour *layout_dependent* est **false**.  
  
> [!NOTE]
>  Une classe ou structure modélisée ne peut pas contenir d'événements.  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, **struct**|  
|**Renouvelable**|Non|  
|**Attributs requis**|**coclasse** lorsque *layout_dependent*=**true**|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs de compilateur](../windows/compiler-attributes.md)   
 [event_source](../windows/event-source.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [Attributs de classe](../windows/class-attributes.md)   