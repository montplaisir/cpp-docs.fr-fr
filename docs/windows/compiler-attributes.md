---
title: Attributs de compilateur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, attributes
- attributes [C++], compiler
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 02aa14eccddca4bc3631957d6aa3d3d1b2af6894
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463452"
---
# <a name="compiler-attributes"></a>Attributs de compilateur
Attributs de compilateur fournissent de nombreuses fonctionnalités.  
  
|Attribut|Description|  
|---------------|-----------------|  
|[emitidl](../windows/emitidl.md)|Détermine si tous les attributs IDL suivantes seront traitées et placés dans le fichier .idl généré.|  
|[event_receiver](../windows/event-receiver.md)|Crée un récepteur d’événements.|  
|[event_source](../windows/event-source.md)|Crée une source d'événement.|  
|[export](../windows/export.md)|Provoque une structure de données à placer dans le fichier .idl.|  
|[Implémente](../windows/implements-cpp.md)|Spécifie les interfaces de dispatch obligés d’être membres de la coclasse IDL.|  
|[importidl](../windows/importidl.md)|Insère le fichier .idl spécifié dans le fichier .idl généré.|  
|[importlib](../windows/importlib.md)|Rend disponibles les types qui ont déjà été compilés dans une autre bibliothèque de types pour la bibliothèque de types en cours de création.|  
|[includelib](../windows/includelib-cpp.md)|Génère un fichier .idl ou .h à inclure dans le fichier .idl généré.|  
|[library_block](../windows/library-block.md)|Place une construction à l’intérieur du bloc de bibliothèque du fichier .idl.|  
|[no_injected_text](../windows/no-injected-text.md)|Empêche le compilateur d’injecter du code à la suite d’utilisation de l’attribut.|  
|[satype](../windows/satype.md)|Spécifie le type de données de la `SAFEARRAY`.|  
|[version](../windows/version-cpp.md)|Identifie une version particulière entre plusieurs versions d’une interface ou une classe.|  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs par groupe](../windows/attributes-by-group.md)