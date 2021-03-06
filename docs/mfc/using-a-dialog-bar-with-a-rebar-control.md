---
title: Utilisation d’une barre de boîte de dialogue avec un contrôle Rebar | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WM_EX_TRANSPARENT
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa2628df5f446105e6b7881709a0c72c19fe230e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950488"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Utilisation d'une barre de boîte de dialogue avec un contrôle rebar
Comme mentionné dans [contrôles Rebar et bandes](../mfc/rebar-controls-and-bands.md), chaque bande peut contenir qu’une seule fenêtre enfant (ou contrôle). Cela peut être une limitation si vous souhaitez avoir plus d’une fenêtre enfant par bande. Une solution pratique consiste à créer une ressource de barre de boîte de dialogue avec plusieurs contrôles et d’ajouter une bande (contenant la barre de boîte de dialogue) au contrôle rebar.  
  
 Normalement, si vous voulez que la bande de barre de boîte de dialogue transparente, vous devez définir le style étendu WS_EX_TRANSPARENT pour l’objet de barre de boîte de dialogue. Toutefois, WS_EX_TRANSPARENT ayant des problèmes de peindre correctement l’arrière-plan d’une barre de boîte de dialogue, vous devez effectuer un travail supplémentaire pour obtenir l’effet souhaité.  
  
 La procédure suivante décrit les étapes nécessaires pour obtenir la transparence sans utiliser le WS_EX_TRANSPARENT de style étendu.  
  
### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Pour implémenter une barre de boîte de dialogue transparent dans une bande rebar  
  
1.  À l’aide de la [boîte de dialogue Ajouter une classe](../mfc/reference/adding-an-mfc-class.md), ajoutez une nouvelle classe (par exemple, `CMyDlgBar`) qui implémente votre objet de barre de boîte de dialogue.  
  
2.  Ajoutez un gestionnaire pour le message WM_ERASEBKGND.  
  
3.  Dans le nouveau gestionnaire, modifiez le code existant pour correspondre à l’exemple suivant :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  Ajoutez un gestionnaire pour le message WM_MOVE.  
  
5.  Dans le nouveau gestionnaire, modifiez le code existant pour correspondre à l’exemple suivant :  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 Les nouveaux gestionnaires simulent la transparence de la barre de boîte de dialogue en transmettant le message WM_ERASEBKGND à la fenêtre parente et en forçant la mise à jour chaque fois que l’objet de barre de boîte de dialogue est déplacé.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

