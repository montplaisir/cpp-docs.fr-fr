---
title: Ajout d’un événement (didacticiel ATL, partie 5) | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c08bd2ca05b0bb73b85572ab86222c2d1210115c
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848630"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Ajout d'un événement (Didacticiel ATL, Partie 5)
Dans cette étape, vous allez ajouter un `ClickIn` et un `ClickOut` événement à votre contrôle ATL. Vous activeront le `ClickIn` événement si l’utilisateur clique dans le polygone et incendie `ClickOut` si l’utilisateur clique en dehors. Les tâches pour ajouter un événement sont les suivantes :  
  
-   Ajout de la `ClickIn` et `ClickOut` méthodes  
  
-   Génération de la bibliothèque de types  
  
-   Implémentation des Interfaces de Point de connexion  
  
## <a name="adding-the-clickin-and-clickout-methods"></a>Ajouter les méthodes ClickIn et ClickOut  
 Lorsque vous avez créé le contrôle ATL à l’étape 2, vous avez sélectionné le **points de connexion** case à cocher. Cela a créé le `_IPolyCtlEvents` interface dans le fichier Polygon.idl. Notez que le nom d’interface commence par un trait de soulignement. Il s’agit d’une convention pour indiquer que l’interface est une interface interne. Par conséquent, les programmes qui vous permettent de parcourir les objets COM peuvent choisir de ne l’interface à l’utilisateur. Notez également que la sélection **points de connexion** ajouté la ligne suivante dans le fichier Polygon.idl pour indiquer que `_IPolyCtlEvents` est l’interface source par défaut :  
  
 `[default, source] dispinterface _IPolyCtlEvents;`  
  
 L’attribut source indique que le contrôle est la source des notifications, donc il appellera cette interface sur le conteneur.  
  
 Ajoutez maintenant le `ClickIn` et `ClickOut` méthodes pour le `_IPolyCtlEvents` interface.  
  
#### <a name="to-add-the-clickin-and-clickout-methods"></a>Pour ajouter les méthodes ClickIn et ClickOut  
  
1.  Dans l’affichage de classes, développez Polygon et PolygonLib pour afficher _IPolyCtlEvents.  
  
2.  Avec le bouton droit _IPolyCtlEvents. Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une méthode**.  
  
3.  Sélectionnez un **Type de retour** de `void`.  
  
4.  Entrez *ClickIn* dans le **nom de la méthode** boîte.  
  
5.  Sous **les attributs de paramètre**, sélectionnez le **dans** boîte.  
  
6.  Sélectionnez un **type de paramètre** de `LONG`.  
  
7.  Type *x* en tant que le **nom du paramètre**, puis cliquez sur **ajouter**.  
  
8.  Répétez les étapes 5 à 7, cette fois pour un **nom du paramètre** de *y*.  
  
9. Cliquez sur **Suivant**.  
  
10. Type `method ClickIn` en tant que le **helpstring**.  
  
11. Cliquez sur **Terminer**.  
  
12. Répétez les étapes ci-dessus pour définir un `ClickOut` méthode avec le même `LONG` paramètres *x* et *y*, le même **les attributs de paramètre** et les mêmes `void` type de retour.  
  
 Vérifiez le fichier Polygon.idl que le code a été ajouté à la `_IPolyCtlEvents` dispinterface.  
  
 Le `_IPolyCtlEvents` dispinterface dans votre fichier Polygon.idl doit maintenant ressembler à ceci :  
  
 [!code-cpp[NVC_ATL_Windowing#56](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_1.idl)]  
  
 Le `ClickIn` et `ClickOut` take méthodes x et les coordonnées y de l’utilisateur a cliqué dessu point en tant que paramètres.  
  
## <a name="generating-the-type-library"></a>Génération de la bibliothèque de types  
 Générer la bibliothèque de types à ce stade, car l’Assistant de Point de connexion l’utilisera pour obtenir les informations nécessaires construire une interface de point de connexion et une interface de conteneur de point de connexion pour votre contrôle.  
  
#### <a name="to-generate-the-type-library"></a>Pour générer la bibliothèque de types  
  
1.  Régénérez votre projet.  
  
     - ou -  
  
2.  Cliquez sur le fichier Polygon.idl dans l’Explorateur de solutions et cliquez sur **compiler** dans le menu contextuel.  
  
 Cela créera le fichier Polygon.tlb, qui est votre bibliothèque de types. Le fichier Polygon.tlb n’est pas visible à partir de l’Explorateur de solutions, car il est un fichier binaire et ne peut pas être affiché ou modifié directement.  
  
## <a name="implementing-the-connection-point-interfaces"></a>Implémentation des Interfaces de Point de connexion  
 Implémenter une interface de point de connexion et une interface de conteneur de point de connexion pour votre contrôle. Dans COM, les événements sont implémentés via le mécanisme de points de connexion. Pour recevoir des événements à partir d’un objet COM, un conteneur établit une connexion au point de connexion qui implémente l’objet COM de notifications. Comme un objet COM peut avoir plusieurs points de connexion, l’objet COM implémente également une interface de conteneur de point de connexion. Via cette interface, le conteneur peut déterminer les points de connexion sont prises en charge.  
  
 L’interface qui implémente un point de connexion est appelée `IConnectionPoint`, et l’interface qui implémente un conteneur de point de connexion est appelée `IConnectionPointContainer`.  
  
 Pour aider à implémenter `IConnectionPoint`, vous allez utiliser l’Assistant Implémentation d’un Point de connexion. Cet Assistant génère le `IConnectionPoint` interface en lisant votre bibliothèque de types et en implémentant une fonction pour chaque événement qui peut être déclenché.  
  
#### <a name="to-use-the-implement-connection-point-wizard"></a>Pour utiliser l’Assistant Implémentation d’un Point de connexion  
  
1.  Dans l’affichage de classes, classe d’implémentation de votre contrôle avec le bouton droit `CPolyCtl`.  
  
2.  Dans le menu contextuel, cliquez sur **ajouter**, puis cliquez sur **ajouter un Point de connexion**.  
  
3.  Sélectionnez `_IPolyCtlEvents` à partir de la **Interfaces sources** liste et double-cliquez dessus pour l’ajouter à la **implémenter les points de connexion** colonne. Cliquez sur **Terminer**. Une classe proxy du point de connexion doit être générée, dans ce cas, `CProxy_IPolyCtlEvents`.  
  
 Si vous examinez le fichier _IPolyCtlEvents_CP.h généré dans l’Explorateur de solutions, vous verrez qu’il a une classe appelée `CProxy_IPolyCtlEvents` qui dérive de `IConnectionPointImpl`. _IPolyCtlEvents_CP.h définit également les deux méthodes `Fire_ClickIn` et `Fire_ClickOut`, qui accepte les deux paramètres des coordonnées. Vous appelez ces méthodes lorsque vous souhaitez déclencher un événement à partir de votre contrôle.  
  
 L’Assistant a également ajouté `CProxy_PolyEvents` et `IConnectionPointContainerImpl` à la liste d’héritage multiple de votre contrôle. L’Assistant bombardé `IConnectionPointContainer` pour vous en ajoutant les entrées appropriées au mappage COM.  
  
 Vous avez terminé l’implémentation du code pour prendre en charge des événements. Maintenant, ajoutez du code pour déclencher les événements au moment approprié. N’oubliez pas, vous vous apprêtez à déclencher un `ClickIn` ou `ClickOut` événement lorsque l’utilisateur clique sur le bouton gauche de la souris dans le contrôle. Pour déterminer à quel moment l’utilisateur clique sur le bouton, ajoutez un gestionnaire pour le `WM_LBUTTONDOWN` message.  
  
#### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>Pour ajouter un gestionnaire pour le message WM_LBUTTONDOWN  
  
1.  Dans l’affichage de classes, avec le bouton droit de la classe CPolyCtl, puis cliquez sur **propriétés** dans le menu contextuel.  
  
2.  Dans le **propriétés** fenêtre, cliquez sur le **Messages** icône, puis cliquez sur `WM_LBUTTONDOWN` dans la liste sur la gauche.  
  
3.  Dans la liste déroulante qui s’affiche, cliquez sur  **\<Ajouter > OnLButtonDown**. Le `OnLButtonDown` déclaration du gestionnaire sera ajoutée à PolyCtl.h, et l’implémentation du gestionnaire sera ajoutée à PolyCtl.cpp.  
  
 Ensuite, modifiez le gestionnaire.  
  
#### <a name="to-modify-the-onlbuttondown-method"></a>Pour modifier la méthode OnLButtonDown  
  
1.  Modifier le code qui comprend le `OnLButtonDown` méthode dans PolyCtl.cpp (en supprimant tout code placé par l’Assistant) afin qu’il ressemble à ceci :  
  
     [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]  
  
 Cela rend de code utilise les points calculés dans le `OnDraw` (fonction) pour créer une région qui détecte les clics de la souris de l’utilisateur avec l’appel à `PtInRegion`.  
  
 Le *uMsg* paramètre est l’ID du message Windows en cours de traitement. Cela vous permet d’avoir une fonction qui gère une série de messages. Le *wParam* et *lParam* paramètres sont les valeurs standard pour le message en cours de traitement. Le paramètre bHandled vous permet de spécifier si la fonction a traité le message ou non. Par défaut, la valeur est définie sur TRUE pour indiquer que la fonction a traité le message, mais vous pouvez le définir sur FALSE. Cela entraîne ATL continuer la recherche d’une autre fonction de gestionnaire de messages à envoyer le message.  
  
## <a name="building-and-testing-the-control"></a>Création et test du contrôle  
 Essayer maintenant vos événements. Générer le contrôle et recommencer l’ActiveX Control Test Container. Cette fois-ci, affichez la fenêtre de journal des événements. Pour acheminer des événements dans la fenêtre Sortie, cliquez sur **journalisation** à partir de la **Options** menu et sélectionnez **journal dans la fenêtre sortie**. Insérez le contrôle et essayez de cliquer dans la fenêtre. Notez que `ClickIn` est déclenché si vous cliquez à l’intérieur du polygone plein, et `ClickOut` est déclenché lorsque vous cliquez en dehors de celle-ci.  
  
 Ensuite, vous allez ajouter une page de propriétés.  
  
 [À l’étape 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [à l’étape 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Didacticiel](../atl/active-template-library-atl-tutorial.md)

