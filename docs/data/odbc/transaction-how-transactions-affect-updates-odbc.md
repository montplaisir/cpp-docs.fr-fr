---
title: 'Transaction : Répercussions des Transactions sur les mises à jour (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e540b68b820234ee6d30295b40c7e0f4cb7c806d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338588"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>Transaction : répercussions des transactions sur les mises à jour (ODBC)
Met à jour vers la [source de données](../../data/odbc/data-source-odbc.md) sont gérés lors de transactions via l’utilisation d’une mémoire tampon d’édition (la même méthode utilisée en dehors des transactions). Les membres de données de champ d’un recordset servent collectivement un mémoire tampon d’édition qui contient l’enregistrement actuel, le jeu d’enregistrements sauvegardé temporairement pendant un `AddNew` ou `Edit`. Pendant une `Delete` opération, l’enregistrement en cours n’est pas sauvegardée dans une transaction. Pour plus d’informations sur la mémoire tampon d’édition et comment les mises à jour stockent l’enregistrement en cours, consultez [Recordset : mise à jour des enregistrements par les Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
> [!NOTE]
>  Si vous avez implémenté l’extraction de lignes en bloc, vous ne pouvez pas appeler `AddNew`, `Edit`, ou `Delete`. Vous devez plutôt écrire vos propres fonctions pour effectuer des mises à jour de la source de données. Pour plus d’informations sur l’extraction de lignes en bloc, consultez [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Pendant les transactions, `AddNew`, `Edit`, et `Delete` opérations peuvent être validées ou restaurées. Les effets de `CommitTrans` et `Rollback` peut entraîner l’enregistrement actif ne pas être restaurée à la mémoire tampon d’édition. Pour vous assurer que l’enregistrement actif est correctement restauré, il est important de comprendre comment la `CommitTrans` et `Rollback` fonctions membres de `CDatabase` fonctionnent avec les fonctions de mise à jour de `CRecordset`.  
  
##  <a name="_core_how_committrans_affects_updates"></a> Comment CommitTrans sur les mises à jour  
 Le tableau suivant décrit les effets de `CommitTrans` sur les transactions.  
  
### <a name="how-committrans-affects-updates"></a>Comment CommitTrans sur les mises à jour  
  
|Opération|État de la source de données|  
|---------------|---------------------------|  
|`AddNew` et `Update`, puis `CommitTrans`|Nouvel enregistrement sont ajoutés à la source de données.|  
|`AddNew` (sans `Update`), puis `CommitTrans`|Nouvel enregistrement est perdu. Enregistrement ne pas ajouté à la source de données.|  
|`Edit` et `Update`, puis `CommitTrans`|Modifications validées dans la source de données.|  
|`Edit` (sans `Update`), puis `CommitTrans`|Modifications de l’enregistrement sont perdues. Enregistrement reste inchangé dans la source de données.|  
|`Delete` Puis `CommitTrans`|Enregistrements supprimés de la source de données.|  
  
##  <a name="_core_how_rollback_affects_updates"></a> Impact de la restauration des Transactions  
 Le tableau suivant décrit les effets de `Rollback` sur les transactions.  
  
### <a name="how-rollback-affects-transactions"></a>Impact de la restauration des Transactions  
  
|Opération|État de l’enregistrement en cours|Vous devez également|État de la source de données|  
|---------------|------------------------------|-------------------|---------------------------|  
|`AddNew` et `Update`, puis `Rollback`|Contenu de l’enregistrement actif est stocké temporairement pour libérer de l’espace pour le nouvel enregistrement. Nouvel enregistrement est entré dans la mémoire tampon d’édition. Après avoir `Update` est appelée, actuel enregistrement est rétabli dans la mémoire tampon d’édition.||Ajout à la source de données effectuée par `Update` est inversé.|  
|`AddNew` (sans `Update`), puis `Rollback`|Contenu de l’enregistrement actif est stocké temporairement pour libérer de l’espace pour le nouvel enregistrement. Modifier mémoire tampon contient le nouvel enregistrement.|Appeler `AddNew` afin de rétablir la mémoire tampon d’édition pour un nouvel enregistrement vide. Ou appelez `Move`(0) pour restaurer les anciennes valeurs à la mémoire tampon d’édition.|Étant donné que `Update` n’était pas appelée, aucune modification apportée à la source de données.|  
|`Edit` et `Update`, puis `Rollback`|Une version non modifiée de l’enregistrement actif est stockée temporairement. Des modifications sont apportées au contenu de la mémoire tampon d’édition. Après avoir `Update` est appelée, la version non modifiée version de l’enregistrement est toujours temporairement stockée.|*Feuille de réponse dynamique*: l’enregistrement en cours, puis y revenir pour rétablir la version non modifiée de l’enregistrement dans la mémoire tampon d’édition.<br /><br /> *Instantané*: appelez `Requery` pour actualiser le jeu d’enregistrements à partir de la source de données.|Modifications apportées à la source de données effectuée par `Update` sont inversés.|  
|`Edit` (sans `Update`), puis `Rollback`|Une version non modifiée de l’enregistrement actif est stockée temporairement. Des modifications sont apportées au contenu de la mémoire tampon d’édition.|Appeler `Edit` afin de rétablir la version non modifiée de l’enregistrement à la mémoire tampon d’édition.|Étant donné que `Update` n’était pas appelée, aucune modification apportée à la source de données.|  
|`Delete` Puis `Rollback`|Le contenu de l’enregistrement en cours est supprimé.|Appelez `Requery` pour restaurer le contenu de l’enregistrement actuel à partir de la source de données.|Suppression des données à partir de la source de données est inversée.|  
  
## <a name="see-also"></a>Voir aussi  
 [Transaction (ODBC)](../../data/odbc/transaction-odbc.md)   
 [Transaction (ODBC)](../../data/odbc/transaction-odbc.md)   
 [Transaction : Exécution d’une Transaction dans un Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)   
 [CDatabase, classe](../../mfc/reference/cdatabase-class.md)   
 [CRecordset, classe](../../mfc/reference/crecordset-class.md)