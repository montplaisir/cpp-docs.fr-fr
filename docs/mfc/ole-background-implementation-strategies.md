---
title: 'Arrière-plan OLE : Stratégies d’implémentation | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe15690b50c9398d660ca53effbec23cc35f49e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350495"
---
# <a name="ole-background-implementation-strategies"></a>Arrière-plan OLE : stratégies d'implémentation
Selon votre application, il existe quatre méthodes d'implémentation possibles pour ajouter la prise en charge OLE :  
  
-   Vous écrivez une nouvelle application.  
  
     Ce cas de figure est généralement celui qui demande le moins le travail. Lancez l’Assistant Application MFC et sélectionnez Fonctionnalités avancées ou Prise en charge des documents composés pour créer un squelette d’application. Pour plus d’informations sur ces options et ce qu’elles font, consultez l’article [création d’un programme EXE MFC](../mfc/reference/mfc-application-wizard.md).  
  
-   Vous avez un programme écrit avec la version 2.0 de la bibliothèque MFC ou une version ultérieure qui ne prend pas en charge OLE.  
  
     Créez une application avec l'Assistant d'application MFC comme indiqué précédemment, puis copiez et collez le code de l'application dans votre application existante. Cela fonctionne pour les serveurs, conteneurs et les applications automatisées. Consultez la bibliothèque MFC [SCRIBBLE](../visual-cpp-samples.md) sample pour obtenir un exemple de cette stratégie.  
  
-   Vous avez un programme de bibliothèque MFC qui implémente la prise en charge de la version 1.0 d'OLE.  
  
     Consultez [Note technique 41 MFC](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) pour cette stratégie de conversion.  
  
-   Vous possédez une application qui n'a pas été écrite à l'aide de Microsoft Foundation Classes et qui peut avoir ou non implémenté la prise en charge OLE.  
  
     Ce cas de figure est celui qui exige le plus de travail. Une approche consiste à créer une application, comme dans la première stratégie, puis à copier et coller le code existant dans celle-ci. Si votre code existant est écrit en C, vous devrez peut-être le changer afin qu'il puisse être compilé en tant que code C++. Si votre code C appelle l'API Windows, vous ne devez pas le modifier pour utiliser les classes Microsoft Foundation. Cette approche demandera probablement une certaine restructuration de votre programme pour prendre en charge l'architecture Document/Vue utilisée par les versions 2.0 et supérieures de Microsoft Foundation Classes. Pour plus d’informations sur cette architecture, consultez [Note technique 25](../mfc/tn025-document-view-and-frame-creation.md).  
  
 Une fois que vous avez décidé d’une stratégie, vous devez lire le [conteneurs](../mfc/containers.md) ou [serveurs](../mfc/servers.md) articles (selon le type d’application que vous écrivez) ou examiner les exemples de programmes, ou les deux. Les exemples OLE MFC [OCLIENT](../visual-cpp-samples.md) et [HIERSVR](../visual-cpp-samples.md) montrent comment implémenter les différents aspects des conteneurs et des serveurs, respectivement. À divers moments tout au long de ces articles, vous serez renvoyé à certaines fonctions des exemples de techniques présentées ici.  
  
## <a name="see-also"></a>Voir aussi  
 [Arrière-plan OLE](../mfc/ole-background.md)   
 [Conteneurs : Implémentation d’un conteneur](../mfc/containers-implementing-a-container.md)   
 [Serveurs : Implémentation d’un serveur](../mfc/servers-implementing-a-server.md)   
 [Assistant Application MFC](../mfc/reference/mfc-application-wizard.md)

