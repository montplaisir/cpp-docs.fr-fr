---
title: timed_mutex, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::timed_mutex
- mutex/std::timed_mutex::timed_mutex
- mutex/std::timed_mutex::lock
- mutex/std::timed_mutex::try_lock
- mutex/std::timed_mutex::try_lock_for
- mutex/std::timed_mutex::try_lock_until
- mutex/std::timed_mutex::unlock
dev_langs:
- C++
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
caps.latest.revision: 9
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 40622e83235c4df32ec9afd25905ffdde2b97be7
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="timedmutex-class"></a>timed_mutex, classe
Représente un *type mutex limité dans le temps*. Les objets de ce type permettent d’appliquer une exclusion mutuelle (mutex) via un blocage limité dans le temps dans un programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class timed_mutex;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[timed_mutex](#timed_mutex)|Construit un objet `timed_mutex` qui n’est pas verrouillé.|  
|[timed_mutex::~timed_mutex, destructeur](#dtortimed_mutex_destructor)|Libère les ressources utilisées par l’objet `timed_mutex`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[lock](#lock)|Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.|  
|[try_lock](#try_lock)|Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.|  
|[try_lock_for](#try_lock_for)|Tente d’obtenir la propriété du `mutex` pour un intervalle de temps spécifié.|  
|[try_lock_until](#try_lock_until)|Tente d’obtenir la propriété du `mutex` jusqu’à une heure spécifiée.|  
|[unlock](#unlock)|Libère la propriété du `mutex`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<mutex >  
  
 **Espace de noms :** std  
  
##  <a name="lock"></a>timed_mutex::lock
 Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant possède déjà `mutex`, le comportement est indéfini.  
  
##  <a name="timed_mutex"></a>  timed_mutex::timed_mutex, constructeur  
 Construit un objet `timed_mutex` qui n’est pas verrouillé.  
  
```cpp  
timed_mutex();
```  
  
##  <a name="dtortimed_mutex_destructor"></a>  timed_mutex::~timed_mutex, destructeur  
 Libère les ressources utilisées par l’objet `mutex`.  
  
```cpp  
~timed_mutex();
```  
  
### <a name="remarks"></a>Notes  
 Si l'objet est verrouillé lorsque le destructeur s'exécute, le comportement est indéfini.  
  
##  <a name="try_lock"></a>timed_mutex::try_lock
 Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode obtient correctement la propriété du `mutex` ; sinon, `false`.  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant possède déjà `mutex`, le comportement est indéfini.  
  
##  <a name="try_lock_for"></a>timed_mutex::try_lock_for
 Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.  
  
```cpp  
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Paramètres  
 `Rel_time`  
 Objet [chrono::duration](../standard-library/duration-class.md) qui spécifie la durée maximale pendant laquelle la méthode essaie d’obtenir la propriété du `mutex`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode obtient correctement la propriété du `mutex` ; sinon, `false`.  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant possède déjà `mutex`, le comportement est indéfini.  
  
##  <a name="try_lock_until"></a>timed_mutex::try_lock_until
 Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.  
  
```cpp  
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```  
  
### <a name="parameters"></a>Paramètres  
 `Abs_time`  
 Point dans le temps qui spécifie le seuil au-delà duquel la méthode ne tente plus d'obtenir la propriété du `mutex`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode obtient correctement la propriété du `mutex` ; sinon, `false`.  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant possède déjà `mutex`, le comportement est indéfini.  
  
##  <a name="unlock"></a>timed_mutex::Unlock
 Libère la propriété du `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant ne possède pas `mutex`, le comportement est indéfini.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



