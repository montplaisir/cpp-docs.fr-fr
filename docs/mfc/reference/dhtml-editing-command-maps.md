---
title: Mappages de commande d’édition DHTML | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d040f3cb4c9bf8e1f3afc0e8213cd4513fc8571
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123368"
---
# <a name="dhtml-editing-command-maps"></a>Mappages de commande d'édition DHTML
Les macros suivantes peuvent être utilisés pour mapper les commandes d’édition DHTML [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-classes dérivées. Pour obtenir un exemple de leur utilisation, consultez [exemple HTMLEdit](../../visual-cpp-samples.md).  
  
### <a name="dhtml-editing-command-map-macros"></a>Macros de table de commande édition DHTML  
  
|||  
|-|-|  
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Déclare un mappage de commande édition DHTML dans une classe.|  
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Démarre la définition d’une table de commande édition DHTML au sein d’une classe.|  
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|Marque la fin d’un mappage de commande édition DHTML.|  
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Mappe un ID de commande à une commande d’édition HTML.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Mappe un ID de commande à une commande d’édition HTML et le Gestionnaire de messages.|  
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Mappe un ID de commande à une commande d’édition HTML et d’un élément d’interface utilisateur.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Mappe un ID de commande à un éditeur de commande, le Gestionnaire de messages et élément d’interface utilisateur HTML.|  
  
##  <a name="declare_dhtmlediting_cmdmap"></a>  DECLARE_DHTMLEDITING_CMDMAP  
 Déclare un mappage de commande édition DHTML dans une classe.  
  
```  
DECLARE_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Paramètres  
 *nom de classe*  
 Nom de la classe.  
  
### <a name="remarks"></a>Notes  
 Cette macro doit être utilisée dans la définition de [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-classes dérivées.  
  
 Utilisez [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) pour implémenter le mappage.  
  
### <a name="example"></a>Exemple  
 Consultez [exemple HTMLEdit](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Configuration requise  
  **En-tête** afxhtml.h  
  
##  <a name="begin_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP  
 Démarre la définition d’une table de commande édition DHTML au sein d’une classe.  
  
```  
BEGIN_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Paramètres  
 *nom de classe*  
 Le nom de la classe contenant le mappage de commande édition DHTML. Cette classe doit dériver directement ou indirectement [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) et inclure le [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) macro dans sa définition de classe.  
  
### <a name="remarks"></a>Notes  
 Ajoutez un mappage de commande édition DHTML à votre classe pour mapper les commandes de l’interface utilisateur pour les commandes d’édition HTML.  
  
 Placez la macro BEGIN_DHTMLEDITING_CMDMAP dans le fichier d’implémentation (.cpp) de la classe suivi [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) macros pour les commandes de la classe consiste à mapper (par exemple, à partir de ID_EDIT_CUT à IDM_CUT). Utilisez le [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap) macro pour marquer la fin de la table d’événements.  
  
### <a name="requirements"></a>Configuration requise  
  **En-tête** afxhtml.h  
  
##  <a name="end_dhtmlediting_cmdmap"></a>  END_DHTMLEDITING_CMDMAP  
 Marque la fin d’un mappage de commande édition DHTML.  
  
```  
END_DHTMLEDITING_CMDMAP()   
```  
  
### <a name="remarks"></a>Notes  
 Utilisez conjointement avec [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap).  
  
### <a name="example"></a>Exemple  
 Consultez [exemple HTMLEdit](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Configuration requise  
  **En-tête** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry"></a>  DHTMLEDITING_CMD_ENTRY  
 Mappe un ID de commande à une commande d’édition HTML.  
  
```  
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)   
```  
  
### <a name="parameters"></a>Paramètres  
 *cmdID*  
 L’ID de commande (par exemple, ID_EDIT_COPY).  
  
 *dhtmlcmdID*  
 Le code HTML modification commande auquel *cmdID* mappe (par exemple, IDM_COPY).  
  
### <a name="example"></a>Exemple  
 Consultez [exemple HTMLEdit](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Configuration requise  
  **En-tête** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func"></a>  DHTMLEDITING_CMD_ENTRY_FUNC  
 Mappe un ID de commande à une commande d’édition HTML et le Gestionnaire de messages.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)   
```  
  
### <a name="parameters"></a>Paramètres  
 *cmdID*  
 L’ID de commande (par exemple, ID_EDIT_COPY).  
  
 *dhtmlcmdID*  
 Le code HTML modification commande auquel *cmdID* mappe (par exemple, IDM_COPY).  
  
 *member_func_name*  
 Le nom de la fonction de gestionnaire de messages à laquelle la commande est mappée.  
  
### <a name="example"></a>Exemple  
 Consultez [exemple HTMLEdit](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Configuration requise  
  **En-tête** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_type"></a>  DHTMLEDITING_CMD_ENTRY_TYPE  
 Mappe un ID de commande à une commande d’édition HTML et d’un élément d’interface utilisateur.  
  
```  
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)  
```  
  
### <a name="parameters"></a>Paramètres  
 *cmdID*  
 L’ID de commande (par exemple, ID_EDIT_COPY).  
  
 *dhtmlcmdID*  
 Le code HTML modification commande auquel *cmdID* mappe (par exemple, IDM_COPY).  
  
 *elemType*  
 Le type élément d’interface utilisateur ; une des AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX ou AFX_UI_ELEMTYPE_RADIO.  
  
### <a name="example"></a>Exemple  
 Consultez [exemple HTMLEdit](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Configuration requise  
  **En-tête** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func_type"></a>  DHTMLEDITING_CMD_ENTRY_FUNC_TYPE  
 Mappe un ID de commande à un éditeur de commande, le Gestionnaire de messages et élément d’interface utilisateur HTML.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)   
```  
  
### <a name="parameters"></a>Paramètres  
 *cmdID*  
 L’ID de commande (par exemple, ID_EDIT_COPY).  
  
 *dhtmlcmdID*  
 Le code HTML modification commande auquel *cmdID* mappe (par exemple, IDM_COPY).  
  
 *member_func_name*  
 Le nom de la fonction de gestionnaire de messages à laquelle la commande est mappée.  
  
 *elemType*  
 Le type élément d’interface utilisateur ; une des AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX ou AFX_UI_ELEMTYPE_RADIO.  
  
### <a name="example"></a>Exemple  
 Consultez [exemple HTMLEdit](../../visual-cpp-samples.md).  

### <a name="requirements"></a>Configuration requise  
  **En-tête** afxhtml.h  
    
## <a name="see-also"></a>Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
