---
title: Apparence, Assistant contrôle ATL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3dd95e3e25cd015fd326c236f15a965e3fb9e801
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39025878"
---
# <a name="appearance-atl-control-wizard"></a>Apparence, Assistant contrôle ATL
Insérer « Résultats de la recherche « résumé ici.  
  
 Utilisez cette page de l’Assistant pour identifier les options d’élément utilisateur supplémentaires pour le contrôle. Cette page est disponible pour les contrôles identifiés en tant que **contrôles Standard** sous **type de contrôle** sur le [Options, Assistant contrôle ATL](../../atl/reference/options-atl-control-wizard.md) page.  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
**Afficher l’état**  
Définit l’apparence du contrôle dans le conteneur.  
  
 -   **Opaque**: définit le bit VIEWSTATUS_OPAQUE dans le [double](http://msdn.microsoft.com/library/windows/desktop/ms687201) énumération et dessine le rectangle du contrôle entier passé à la [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) (méthode). Le contrôle apparaît complètement opaque et aucun du conteneur affiche au-delà des limites du contrôle.      
      
        Ce paramètre permet de dessiner le contrôle plus rapidement le conteneur. Si cette option n’est pas sélectionnée, le contrôle peut contenir des parties transparentes.  
      
        Seul un contrôle opaque peut avoir un arrière-plan uni.  
      
 -   Définit le bit VIEWSTATUS_SOLIDBKGND dans l’énumération double. L’arrière-plan du contrôle apparaît sous la forme d’une couleur unie sans motif.  
      
  Cette option est disponible uniquement si le **Opaque** option est également sélectionnée.  
  
**Ajouter un contrôle basé sur**  
Définit le contrôle doit être basé sur un type de contrôle Windows en ajoutant un [CContainedWindow](ccontainedwindowt-class.md) données membres à la classe qui implémente le contrôle. Il ajoute également une table des messages et des fonctions de gestionnaire de messages à traiter les messages Windows pour le contrôle. Dans la liste, choisissez le type de contrôle de Windows que vous souhaitez créer, le cas échéant.  

 -   `Button`  
      
 -   `ListBox`  
      
 -   `SysAnimate32`  
      
 -   `SysListView32`  
      
 -   `ComboBox`  
      
 -   `RichEdit`  
      
 -   `SysDateTimePick32`  
      
 -   `SysMonthCal32`  
      
 -   `ComboBoxEx32`  
      
 -   `ScrollBar`  
      
 -   `SysHeader32`  
      
 -   `SysTabControl32`  
      
 -   `Edit`  
      
 -   `Static`  
      
 -   `SysIPAddress32`  
      
 -   `SysTreeView32`  
  
**État divers**  
Définit des options d’apparence et le comportement supplémentaires pour le contrôle.  
  
 -   **Invisible au moment de l’exécution**: définit le contrôle est invisible au moment de l’exécution. Vous pouvez utiliser les contrôles invisibles pour effectuer des opérations en arrière-plan, telles que le déclenchement d’événements à intervalles réguliers.  
      
 -   **Agit comme un bouton**: définit le bit OLEMISC_ACTSLIKEBUTTON dans le [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) énumération pour permettre un contrôle d’agir comme un bouton. Si le conteneur a marqué le site du client du contrôle comme un bouton par défaut, cette option permet à votre contrôle de bouton à afficher comme un bouton par défaut en dessinant lui-même avec une image épaisse. Consultez [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) pour plus d’informations.  
      
  -   **Agit comme étiquette**: définit le bit OLEMISC_ACTSLIKELABEL dans l’énumération OLEMISC pour permettre un contrôle de remplacer l’étiquette native du conteneur. Le conteneur détermine que faire avec cet indicateur, voire rien.  
  
**Autre**  
Définit les options de comportement supplémentaires pour le contrôle.  
  
 -   **Normalisées DC**: définit le contrôle pour créer un contexte de périphérique normalisé lorsqu’elle est appelée pour dessiner lui-même. Cette action normalise l’apparence du contrôle, mais il rend le dessin moins efficace.  
      
 -   **Que la fenêtre**: Spécifie que votre contrôle ne peut pas être sans fenêtre. Si vous ne sélectionnez pas cette option, votre contrôle est automatiquement sans fenêtre dans des conteneurs qui prennent en charge les objets sans fenêtre, et il est automatiquement une fenêtre dans des conteneurs qui ne prennent pas en charge les objets sans fenêtre. Cette option force votre contrôle à utiliser une fenêtre, même dans des conteneurs qui prennent en charge les objets sans fenêtre.  
      
 -   **Insérable**: sélectionnez cette option pour que votre contrôle s’affichent dans le **insérer un objet** boîte de dialogue d’applications telles que Word et Excel. Votre contrôle peut ensuite être inséré par n’importe quelle application qui prend en charge les objets incorporés dans cette boîte de dialogue.  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant contrôle ATL](../../atl/reference/atl-control-wizard.md)   
 [SUBEDIT : Surclassement d’un contrôle Windows Standard](http://msdn.microsoft.com/30e46bdc-ed92-417c-b6b8-359017265a7b)

