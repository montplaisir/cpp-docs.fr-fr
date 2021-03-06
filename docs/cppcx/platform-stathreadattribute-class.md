---
title: Platform::STAThreadAttribute (classe) | Documents Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab58409bf86af77c9b1f751b9978b5e7103bd043
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089351"
---
# <a name="platformstathreadattribute-class"></a>Platform::STAThreadAttribute (classe)
Indique que le modèle de thread d'une application est un modèle STA (Single-Threaded Apartment).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
public ref class STAThreadAttribute sealed : Attribute  
```  
  
### <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[STAThreadAttribute, constructeur 1](#ctor)|Initialise une nouvelle instance de la classe.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
 L’attribut STAThreadAttribute hérite [Platform::Object, classe](../cppcx/platform-object-class.md). STAThreadAttribute surcharge ou possède également les membres suivants :  
  
|Name|Description|  
|----------|-----------------|  
|[STAThreadAttribute::Equals](#equals)|Détermine si l'objet spécifié est identique à l'objet actuel.|  
|[STAThreadAttribute::GetHashCode](#gethashcode)|Retourne le code de hachage de cette instance.|  
|[STAThreadAttribute::ToString](#tostring)|Retourne une chaîne qui représente l'objet actuel.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `Platform`  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** collection.h  
  
 **Espace de noms :** Platform  



## <a name="ctor"></a> STAThreadAttribute constructor
Initialise une nouvelle instance de la classe STAThreadAttribute.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
public:STAThreadAttribute()  
```  
  


## <a name="equals"></a> STAThreadAttribute::Equals
Détermine si l'objet spécifié est identique à l'objet actuel.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
public:virtual override bool Equals(  Object^ obj)  
```  
  
### <a name="parameters"></a>Paramètres  
 obj  
 Objet à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si les objets sont égaux ; sinon `false`.  
  


## <a name="gethashcode"></a> STAThreadAttribute::GetHashCode
Retourne le code de hachage de cette instance.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Code de hachage de cette instance.  
  


## <a name="tostring"></a> STAThreadAttribute::ToString
Retourne une chaîne qui représente l'objet actuel.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
public:String^ ToString()  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Chaîne qui représente l'objet actuel.  
  

  
## <a name="see-also"></a>Voir aussi  
 [Plateforme Namespace](platform-namespace-c-cx.md)