---
title: Affichage et ajout de contrôles ActiveX à une boîte de dialogue | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.controls.activex
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], adding ActiveX controls
- Insert ActiveX Control command
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 61448cba890c03feaf2d9fcbda5cdb93478f4c04
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891164"
---
# <a name="viewing-and-adding-activex-controls-to-a-dialog-box"></a>Affichage et ajout de contrôles ActiveX dans une boîte de dialogue
Avec Visual Studio, vous pouvez insérer des contrôles ActiveX dans votre boîte de dialogue.  
  
### <a name="to-see-the-activex-controls-you-have-available"></a>Pour afficher les contrôles ActiveX disponibles  
  
1.  Ouvrez une boîte de dialogue dans l’Éditeur de boîtes de dialogue.  
  
2.  Cliquez avec le bouton droit n’importe où dans le corps de la boîte de dialogue.  
  
3.  Dans le menu contextuel, cliquez sur **Insérer un contrôle ActiveX**.  
  
     La boîte de dialogue [Insérer un contrôle ActiveX](../windows/insert-activex-control-dialog-box.md) apparaît et affiche tous les contrôles ActiveX disponibles sur votre système. En bas de la boîte de dialogue figure le chemin d’accès au fichier de contrôle ActiveX.  
  
### <a name="to-add-an-activex-control-to-a-dialog-box"></a>Pour ajouter un contrôle ActiveX à une boîte de dialogue  
  
1.  Dans la boîte de dialogue [Insérer un contrôle ActiveX](../windows/insert-activex-control-dialog-box.md), sélectionnez le contrôle que vous souhaitez ajouter à votre boîte de dialogue, puis cliquez sur **OK**.  
  
     Le contrôle apparaît dans la boîte de dialogue, où vous pouvez le modifier ou créer des gestionnaires comme vous le feriez pour n’importe quel autre contrôle.  
  
    > [!NOTE]
    >  Vous pouvez ajouter des contrôles ActiveX à la fenêtre [Boîte à outils](/visualstudio/ide/reference/toolbox). Pour plus d’informations, consultez [Gestion des éléments et des onglets de la boîte à outils](http://msdn.microsoft.com/en-us/21285050-cadd-455a-b1f5-a2289a89c4db).  
  
    > [!CAUTION]
    >  Il se peut que la distribution de tous les contrôles ActiveX sur votre système ne soit pas autorisée juridiquement. Reportez-vous au contrat de licence du logiciel qui a installé les contrôles ou contactez l’éditeur du logiciel.  
  
     Vous pouvez placer des contrôles dans la fenêtre Boîte à outils pour en faciliter l’accès. Pour plus d’informations, consultez [Personnaliser la boîte de dialogue Boîte à outils](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb).  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 **Spécifications**  
  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles dans les boîtes de dialogue](../windows/controls-in-dialog-boxes.md)   
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Conteneurs de contrôles ActiveX](../mfc/activex-control-containers.md)

