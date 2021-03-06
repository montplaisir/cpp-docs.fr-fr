---
title: Cmapstringtostring, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
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
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CMapStringToString [MFC], CPair
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
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 613e49478349779709571927ee38b0903f141730
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336236"
---
# <a name="cmapstringtostring-class"></a>Cmapstringtostring, classe
Prend en charge les mappages d'objets `CString` indexés par des objets `CString` .  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMapStringToString : public CObject  
```  
  
## <a name="members"></a>Membres  
 Les fonctions membres de `CMapStringToString` sont similaires aux fonctions membres de classe [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Ainsi, vous pouvez utiliser la documentation de référence de `CMapStringToOb` pour connaître les spécificités des fonctions membres. Partout où vous voyez un `CObject` pointeur comme paramètre, de fonction de valeur de retour ou « output » remplacer par un pointeur vers **char**. Partout où vous voyez un `CObject` pointeur comme un paramètre de fonction de « entrée », remplacez par un pointeur vers **char**.  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 par exemple, se traduit par  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### <a name="public-structures"></a>Structures publiques  
  
|Name|Description|  
|----------|-----------------|  
|[CMapStringToString::CPair](#cpair)|Une structure imbriquée contenant une valeur de clé et la valeur de l’objet de chaîne associée.|  
  
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
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|Obtient un pointeur vers le premier `CString` dans le mappage.|  
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|Obtient un pointeur vers la prochaine `CString` pour une itération.|  
|[CMapStringToString::PLookup](#plookup)|Retourne un pointeur vers un `CString` dont la valeur correspond à la valeur spécifiée.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Supprime tous les éléments de ce mappage.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Supprime un élément spécifié par une clé.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Insère un élément dans l’objet map. remplace un élément existant si une clé correspondante est trouvée.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMapStringToOb::operator [ ]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Insère un élément dans la classe map, substitution d’opérateur pour `SetAt`.|  
  
## <a name="remarks"></a>Notes  
 `CMapStringToString` incorpore la macro `IMPLEMENT_SERIAL` pour prendre en charge la sérialisation et le vidage de ses éléments. Chaque élément est sérialisé à son tour, si un mappage est stocké dans une archive, soit avec l’insertion surchargée ( **<<**) opérateur ou avec le `Serialize` fonction membre.  
  
 Si vous avez besoin d’un dump de l’individu `CString` -  `CString` éléments, vous devez définir la profondeur du contexte de vidage à 1 ou supérieur.  
  
 Quand un `CMapStringToString` objet est supprimé, ou lorsque ses éléments sont supprimés, le `CString` les objets sont supprimés si nécessaire.  
  
 Pour plus d’informations sur `CMapStringToString`, consultez l’article [Collections](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToString`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxcoll.h  
  
##  <a name="cpair"></a>  CMapStringToString::CPair  
 Contient une valeur de clé et la valeur de l’objet de chaîne associée.  
  
### <a name="remarks"></a>Notes  
 Il s’agit d’une structure imbriquée au sein de la classe [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md).  
  
 La structure se compose de deux champs :  
  
- `key` La valeur réelle du type de clé.  
  
- `value` La valeur de l’objet associé.  
  
 Il est utilisé pour stocker les valeurs de retour à partir de [CMapStringToString::PLookup](#plookup), [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc), et [CMapStringToString::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple d’utilisation, consultez l’exemple de [CMapStringToString::PLookup](#plookup).  
  
##  <a name="pgetfirstassoc"></a>  CMapStringToString::PGetFirstAssoc  
 Retourne la première entrée de l’objet map.  
  
```  
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la première entrée dans le mappage ; consultez [CMapStringToString::CPair](#cpair). Si le mappage est vide, la valeur est NULL.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction pour retourner un pointeur du premier élément dans l’objet map.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]  
  
##  <a name="pgetnextassoc"></a>  CMapStringToString::PGetNextAssoc  
 Récupère l’élément de mappage vers lequel pointé *pAssocRec*.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssoc) const;  
  
CPair *PGetNextAssoc(const CPair* pAssoc);
```  
  
### <a name="parameters"></a>Paramètres  
 *pAssoc*  
 Pointe vers une entrée de mappage retournée par une précédente [PGetNextAssoc](#pgetnextassoc) ou [PGetFirstAssoc](#pgetfirstassoc) appeler.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’entrée suivante dans le mappage ; consultez [CMapStringToString::CPair](#cpair). Si l’élément est le dernier dans le mappage, la valeur est NULL.  
  
### <a name="remarks"></a>Notes  
 Appelez cette méthode pour effectuer une itération dans tous les éléments dans le mappage. Récupérer le premier élément avec un appel à `PGetFirstAssoc` , puis itérer la carte avec des appels successifs à `PGetNextAssoc`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="plookup"></a>  CMapStringToString::PLookup  
 Recherche la valeur mappée à une clé donnée.  
  
```  
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```  
  
### <a name="parameters"></a>Paramètres  
 *key*  
 Pointeur vers la clé de l’élément à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la clé spécifiée.  
  
### <a name="remarks"></a>Notes  
 Appelez cette méthode pour rechercher un élément de carte avec une clé qui correspond exactement à la clé donnée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC COLLECT](../../visual-cpp-samples.md)   
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)



