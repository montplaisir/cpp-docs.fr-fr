---
title: Problèmes de conception architecturale OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, application design considerations
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5b080945309732bec06c63eb665bbf6dd5f4acb5
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340561"
---
# <a name="ole-db-architectural-design-issues"></a>Questions relatives à la conception architecturale d'OLE DB
Vous devez envisager les problèmes suivants avant de commencer votre application OLE DB :  
  
 **Quelle implémentation de programmation utiliserez-vous pour écrire votre application OLE DB ?**  
 Microsoft offre plusieurs bibliothèques pour ce faire : une bibliothèque de modèles OLE DB, des attributs OLE DB et les interfaces OLE DB brutes dans le SDK OLE DB. En outre, il existe les Assistants vous aident à écrire votre programme. Ces implémentations sont décrites dans [modèles OLE DB, attributs et autres implémentations](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md).  
  
 **Vous devez écrire votre propre fournisseur ?**  
 La plupart des développeurs n’avez pas besoin d’écrire leur propre fournisseur. Microsoft propose plusieurs fournisseurs. Chaque fois que vous créez une connexion de données (par exemple, lorsque vous ajoutez un consommateur à votre projet à l’aide de l’Assistant Consommateur OLE DB ATL), le **propriétés des liaisons de données** boîte de dialogue répertorie tous les fournisseurs disponibles inscrits sur votre système. Si un de ces fournisseurs est approprié pour votre propre application d’accès données stocker et les données, le plus simple consiste à faire est utiliser un de ces. Toutefois, si votre banque de données ne tient pas dans une de ces catégories, vous devez créer votre propre fournisseur. Pour plus d’informations sur la création de fournisseurs, consultez [les modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
 **Quel est le niveau de prise en charge avez-vous besoin pour votre consommateur ?**  
 Certains consommateurs peuvent être très simple ; tandis que d’autres peuvent être très complexes. La fonctionnalité des objets OLE DB est spécifiée par les propriétés. Lorsque vous utilisez l’Assistant Consommateur OLE DB ATL pour créer un consommateur ou l’Assistant fournisseur de base de données pour créer un fournisseur, il définit les propriétés d’objet approprié pour vous permettre de vous fournir un jeu standard de fonctionnalités. Toutefois, si les classes générées par l’Assistant consommateur ou fournisseur ne prennent pas en charge tout ce dont vous avez besoin pour effectuer, vous devez faire référence aux interfaces de ces classes dans le [bibliothèque de modèles OLE DB](../../data/oledb/ole-db-templates.md). Ces interfaces englobent les interfaces OLE DB brutes, offrant une implémentation supplémentaire afin de faciliter leur utilisation.  
  
 Par exemple, si vous souhaitez mettre à jour des données dans un ensemble de lignes, mais vous avez oublié de le spécifier lorsque vous avez créé le consommateur avec l’Assistant, vous pouvez spécifier les fonctionnalités après le fait en définissant le `DBPROP_IRowsetChange` et `DBPROP_UPDATABILITY` propriétés sur l’objet command. Ensuite, quand l’ensemble de lignes est créé, il a le `IRowsetChange` interface.  
  
 **Avez-vous un code plus ancien à l’aide d’une autre technologie d’accès aux données (ADO, ODBC ou DAO) ?**  
 Étant donné les combinaisons possibles des technologies (par exemple, à l’aide de composants d’ADO avec des composants OLE DB et la migration de code ODBC vers OLE DB), couvrant toutes les situations n’entre pas dans la portée de la documentation de Visual C++. Toutefois, de nombreux articles couvrant différents scénarios sont disponibles sur les sites Web de Microsoft à l’adresse suivante :  
  
-   [Aide et support Microsoft](http://go.microsoft.com/fwlink/p/?linkid=148218)  
  
-   [Vue d’ensemble des articles techniques sur Microsoft Data Access](http://go.microsoft.com/fwlink/p/?linkid=148217)  
  
-   [Centre de solutions de Visual Studio](http://go.microsoft.com/fwlink/p/?linkid=148215)  
  
-   [Rechercher dans Microsoft.com](http://search.microsoft.com/)  
  
 Lorsque vous effectuez une recherche, entrez une combinaison de mots clés qui convient le mieux à votre scénario. par exemple : Si vous utilisiez des objets ADO avec un fournisseur OLE DB, essayez une recherche booléenne avec **ADO et « OLE DB »**. Si vous voulez migrer un code DAO plus ancien vers ODBC, sélectionnez « tous les mots » et spécifiez des chaînes telles que **DAO migration**.  
  
## <a name="see-also"></a>Voir aussi  
 [Programmation OLE DB](../../data/oledb/ole-db-programming.md)   
 [Vue d’ensemble de la programmation OLE DB](../../data/oledb/ole-db-programming-overview.md)