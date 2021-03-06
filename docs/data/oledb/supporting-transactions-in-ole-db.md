---
title: Prise en charge des Transactions dans OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 932185002032ab86ca80b2b3384bfe6cbb69f8b1
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338708"
---
# <a name="supporting-transactions-in-ole-db"></a>Prise en charge des transactions dans OLE DB
Un [transaction](../../data/transactions-mfc-data-access.md) consiste à regrouper ou du lot, une série de mises à jour à une source de données afin que toutes réussissent et sont validées en même temps ou (si l’une d’elles échoue), aucun n’est validée et toute la transaction est restaurée. Ce processus garantit l’intégrité du résultat sur la source de données.  
  
 OLE DB prend en charge les transactions avec les trois méthodes suivantes :  
  
-   [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/library/ms709786.aspx)  
  
-   [ITransaction::Commit](https://msdn.microsoft.com/library/ms713008.aspx)  
  
-   [ITransaction::Abort](https://msdn.microsoft.com/library/ms709833.aspx)  
  
## <a name="relationship-of-sessions-and-transactions"></a>Relations des Sessions et Transactions  
 Un objet de source de données unique peut créer un ou plusieurs objets de session, chacun d’eux peut être à l’intérieur ou en dehors de l’étendue d’une transaction à un moment donné.  
  
 Quand une session n’entre pas une transaction, tout le travail effectué au sein de cette session sur le magasin de données est immédiatement validé sur chaque appel de méthode. (Cela est parfois appelé mode de validation automatique ou implicite.)  
  
 Lorsqu’une session entre une transaction, les tout le travail effectué au sein de cette session sur le magasin de données fait partie de cette transaction et soit validé ou abandonné comme une seule unité. (Cela est parfois appelé mode de validation manuelle.)  
  
 Prise en charge de la transaction est spécifique au fournisseur. Si le fournisseur que vous utilisez prend en charge les transactions, un objet de session qui prend en charge `ITransaction` et `ITransactionLocal` pouvez entrer une simple (c'est-à-dire, non imbriquée) transaction. La classe de modèles OLE DB [CSession](../../data/oledb/csession-class.md) prend en charge ces interfaces et est la méthode recommandée pour implémenter la prise en charge des transactions dans Visual C++.  
  
## <a name="starting-and-ending-the-transaction"></a>Début et fin de la Transaction  
 Vous appelez le `StartTransaction`, `Commit`, et `Abort` méthodes dans l’objet d’ensemble de lignes dans le consommateur.  
  
 Appel `ITransactionLocal::StartTransaction` démarre une nouvelle transaction locale. Lorsque vous démarrez la transaction, les modifications éventuellement mandatées par les opérations suivantes ne sont pas réellement appliquées au magasin de données jusqu'à ce que vous validez la transaction.  
  
 Appel `ITransaction::Commit` ou `ITransaction::Abort` met fin à la transaction. `Commit` toutes les modifications dans l’étendue de la transaction à appliquer au magasin de données. `Abort` causes de toutes les modifications dans l’étendue de la transaction doit être annulée et le magasin de données est laissé dans un état, il avaient avant le démarrage de la transaction.  
  
## <a name="nested-transactions"></a>Transactions imbriquées  
 Un [imbriqués transaction](https://msdn.microsoft.com/library/ms716985.aspx) se produit lorsque vous démarrez une nouvelle transaction locale lorsqu’une transaction active existe déjà sur la session. La nouvelle transaction est démarrée en tant que transaction imbriquée sous la transaction en cours. Si le fournisseur ne prend pas en charge les transactions imbriquées, l’appel `StartTransaction` lorsqu’il existe déjà une transaction active dans la session renvoie XACT_E_XTIONEXISTS.  
  
## <a name="distributed-transactions"></a>Transactions distribuées  
 Une transaction distribuée est une transaction qui met à jour des données distribuées ; Autrement dit, les données sur plusieurs systèmes informatiques en réseau. Si vous souhaitez prendre en charge des transactions sur un système distribué, vous devez utiliser le .NET Framework plutôt que la prise en charge des transactions OLE DB.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)