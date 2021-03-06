---
title: Codbcfieldinfo, Structure | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CODBCFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1723e93320129fae232bb850caa123d1638a37b
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853080"
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo, structure
Le `CODBCFieldInfo` structure contient des informations sur les champs dans une source de données ODBC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CODBCFieldInfo  
{  
    CString m_strName;  
    SWORD m_nSQLType;  
    UDWORD m_nPrecision;  
    SWORD m_nScale;  
    SWORD m_nNullability;  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 *m_strName*  
 Nom du champ.  
  
 *m_nSQLType*  
 Le type de données SQL du champ. Cela peut être un type de données ODBC SQL ou un type de données spécifiques au pilote SQL. Pour obtenir la liste des types de données ODBC SQL valides, consultez « Types de données SQL » dans le SDK Windows. Pour plus d’informations sur les types de données spécifiques au pilote SQL, consultez la documentation du pilote.  
  
 *m_nPrecision*  
 La précision maximale du champ. Pour plus d’informations, consultez « Précision, échelle, longueur et taille d’affichage » dans le SDK Windows.  
  
 *m_nScale*  
 La mise à l’échelle du champ. Pour plus d’informations, consultez « Précision, échelle, longueur et taille d’affichage » dans le SDK Windows.  
  
 *m_nNullability*  
 Indique si le champ accepte une valeur Null. Cela peut prendre l’une des deux valeurs : SQL_NULLABLE si le champ accepte les valeurs Null ou SQL_NO_NULLS si le champ n’accepte pas les valeurs Null.  
  
## <a name="remarks"></a>Notes  
 Pour récupérer ces informations, appelez [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxdb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)


