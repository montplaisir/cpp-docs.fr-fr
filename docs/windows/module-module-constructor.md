---
title: Module::module, constructeur | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Module
dev_langs:
- C++
helpviewer_keywords:
- Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b31e9f1e4536bc124bba359ece10217ef8b7f253
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875251"
---
# <a name="modulemodule-constructor"></a>Module::Module, constructeur
Initialise une nouvelle instance de la classe de Module.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Module();  
```  
  
## <a name="remarks"></a>Notes  
 Ce constructeur est protégé et ne peut pas être appelé avec le `new` (mot clé). Au lieu de cela, appelez [module::GetModule, méthode](../windows/module-getmodule-method.md) ou [module::Create, méthode](../windows/module-create-method.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module, classe](../windows/module-class.md)