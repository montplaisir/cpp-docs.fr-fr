---
title: Sampler, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sampler
- AMP_GRAPHICS/sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::get_address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::get_border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::get_filter_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::filter_mode
dev_langs:
- C++
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
caps.latest.revision: 7
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
ms.openlocfilehash: f81208e40cb2a211b714af1efe801e81cd567374
ms.contentlocale: fr-fr
ms.lasthandoff: 03/17/2017

---
# <a name="sampler-class"></a>sampler, classe
La classe échantillonneur rassemble les informations de configuration d’échantillonnage à utiliser pour l’échantillonnage de texture.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class sampler;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[échantillon de constructeur](#ctor)|Surchargé. Construit une instance de l’échantillon.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get_address_mode](#get_address_mode)|Retourne le `address_mode` qui est associé à l’objet de l’échantillon.|  
|[get_border_color](#get_border_color)|Retourne la couleur de bordure qui est associé à l’objet de l’échantillon.|  
|[get_filter_mode](#get_filter_mode)|Retourne le `filter_mode` qui est associé à l’objet de l’échantillon.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[operator=](#operator_eq)|Surchargé. Opérateur d'assignation.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[address_mode](#address_mode)|Obtient le mode d’adresse de le `sampler` objet.|  
|[border_color](#border_color)|Obtient la couleur de bordure du `sampler` objet.|  
|[filter_mode](#filter_mode)|Obtient le mode de filtre de le `sampler` objet.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `sampler`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_graphics.h  
  
 **Namespace :** concurrency::graphics  
  
##  <a name="ctor"></a>échantillon 

 Construit une instance de la [sampler, classe](sampler-class.md).  
  
```  
sampler() restrict(cpu);

 *// [1] default constructor  
 
sampler(// [2] constructor  
    filter_mode _Filter_mode) restrict(cpu);

 
sampler(// [3] constructor  
    address_mode _Address_mode,  
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

 
sampler(// [4] constructor  
    filter_mode _Filter_mode,  
    address_mode _Address_mode,  
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

 
sampler(// [5] copy constructor  
    const sampler& _Other) restrict(amp,
    cpu);

 
sampler(// [6] move constructor  
    sampler&& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Filter_mode`  
 Le mode de filtre à utiliser pour l’échantillonnage.  
  
 `_Address_mode`  
 Le mode d’adressage à utiliser pour l’échantillonnage de toutes les dimensions.  
  
 `_Border_color`  
 La couleur de bordure à utiliser si le mode d’adresse est address_border. La valeur par défaut est `float_4(0.0f, 0.0f, 0.0f, 0.0f)`.  
  
 `_Other`  
 [5] constructeur de copie  
 Le `sampler` à copier dans le nouvel objet `sampler` instance.  
  
 [6] constructeur de déplacement  
 Le `sampler` déplacer dans le nouvel objet `sampler` instance.  
  
##  <a name="address_mode"></a>address_mode 

 Obtient le mode d’adresse de le `sampler` objet.  
  
```  
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;  
```  
  
##  <a name="border_color"></a>border_color 

 Obtient la couleur de bordure du `sampler` objet.  
  
```  
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;  
```  
  
##  <a name="filter_mode"></a>filter_mode 

 Obtient le mode de filtre de le `sampler` objet.  
  
```  
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;  
```  
  
##  <a name="get_address_mode"></a>get_address_mode 

 Renvoie le mode de filtre qui est configuré pour ce `sampler`.  
  
```  
Concurrency::graphics::address_mode get_address_mode() const __GPU;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le mode d’adresse qui est configuré pour l’échantillonnage.  
  
##  <a name="get_border_color"></a>get_border_color 

 Retourne la couleur de bordure qui est configurée pour ce `sampler`.  
  
```  
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Float_4 qui contient la couleur de bordure.  
  
##  <a name="get_filter_mode"></a>get_filter_mode 

 Renvoie le mode de filtre qui est configuré pour ce `sampler`.  
  
```  
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le mode de filtre qui est configuré pour l’échantillonnage.  
  
##  <a name="operator_eq"></a>opérateur = 

 Affecte la valeur d’un autre objet échantillonneur à un échantillon existant.  
  
```  
sampler& operator= (// [1] copy assignment operator const sampler& _Other) restrict(amp,
    cpu);

 
sampler& operator= (// [2] move assingment operator sampler&& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 [1] opérateur d’assignation de copie  
 Le `sampler` objet à copier dans la collection `sampler`.  
  
 [2] opérateur d’assignation de déplacement  
 Le `sampler` déplacer dans cet objet `sampler`.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à cette instance de l’échantillon.  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::graphics, espace de noms](concurrency-graphics-namespace.md)
