---
title: CMapStringToPtr, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMapStringToPtr
- AFXCOLL/CMapStringToPtr
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 1ac11143-eb0a-4511-a662-2df0d1d9005b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43053702b18355c0422a9fc87ac77e0a4ad75b82
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335540"
---
# <a name="cmapstringtoptr-class"></a>CMapStringToPtr, classe
Prend en charge les mappages de pointeurs void indexés par des objets `CString` .  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMapStringToPtr : public CObject  
```  
  
## <a name="members"></a>Membres  
 Les fonctions membres de `CMapStringToPtr` sont similaires aux fonctions membres de classe [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Ainsi, vous pouvez utiliser la documentation de référence de `CMapStringToOb` pour connaître les spécificités des fonctions membres. Partout où vous voyez un `CObject` pointeur en tant que paramètre de fonction ou valeur de retour, remplacez par un pointeur vers **void**.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 par exemple, se traduit par  
  
 `BOOL CMapStringToPtr::Lookup( LPCTSTR <key>, void*& <rValue> )`  
  
 `const;`  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Retourne le nombre d’éléments dans ce mappage.|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Détermine le nombre actuel d’éléments dans la table de hachage.|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Obtient l’élément suivant pour une itération.|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Retourne le nombre d’éléments dans ce mappage.|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Retourne la position du premier élément.|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Calcule la valeur de hachage d’une clé spécifiée.|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Initialise la table de hachage.|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Vérifie si la condition vide-map (pas d’éléments).|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Recherche un pointeur void selon la clé du pointeur void. La valeur de pointeur, pas l’entité qu’il pointe vers, est utilisée pour la comparaison de clés.|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Retourne une référence à la clé associée à la valeur de clé spécifiée.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Supprime tous les éléments de ce mappage.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Supprime un élément spécifié par une clé.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Insère un élément dans l’objet map. remplace un élément existant si une clé correspondante est trouvée.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMapStringToOb::operator [ ]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Insère un élément dans la classe map, substitution d’opérateur pour `SetAt`.|  
  
## <a name="remarks"></a>Notes  
 `CMapStringToPtr` incorpore la macro IMPLEMENT_DYNAMIC pour prendre en charge d’accès de type au moment de l’exécution et le vidage à un `CDumpContext` objet. Si vous avez besoin de vider des éléments cartographiques individuels, vous devez définir la profondeur du contexte de vidage à 1 ou supérieur.  
  
 Les mappages au pointeur de chaîne ne peuvent pas être sérialisés.  
  
 Quand un `CMapStringToPtr` objet est supprimé, ou lorsque ses éléments sont supprimés, le `CString` objets clés et les mots sont supprimés.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToPtr`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxcoll.h  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)



