---
title: Compilation d’un programme C++ qui cible le CLR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2a7bcb0eead62730f0b70b0b1df64e5ed08f1f0
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33336093"
---
# <a name="walkthrough-compiling-a-c-program-that-targets-the-clr-in-visual-studio"></a>Procédure pas à pas : compilation d'un programme C++ qui cible le CLR dans Visual Studio
Vous pouvez créer des programmes Visual C++ qui utilisent des classes .NET et les compiler à l’aide de l’environnement de développement Visual Studio.  
  
 Pour cette procédure, vous pouvez taper votre propre programme Visual C++ ou utiliser l’un des exemples de programmes. L’exemple de programme que nous utilisons dans cette procédure crée un fichier texte nommé textfile.txt et l’enregistre dans le répertoire du projet.  
  
## <a name="prerequisites"></a>Prérequis  
 Ces rubriques partent du principe que vous avez des notions de base du langage C++.  
  
### <a name="to-create-a-new-project-in-visual-studio-and-add-a-new-source-file"></a>Pour créer un projet dans Visual Studio et ajouter un nouveau fichier source  
  
1.  Créer un nouveau projet. Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet**.  
  
2.  Dans les types de projets Visual C++, cliquez sur **CLR**, puis sur **Projet vide CLR**.  
  
3.  Tapez un nom de projet.  
  
     Par défaut, la solution qui contient le projet porte le même nom que le nouveau projet, mais vous pouvez entrer un autre nom. Si vous le souhaitez, vous pouvez indiquer un emplacement différent pour le projet.  
  
     Cliquez sur **OK** pour créer le projet.  
  
4.  Si l’Explorateur de solutions n’est pas visible, cliquez sur **Explorateur de solutions** dans le menu **Affichage**.  
  
5.  Ajoutez un nouveau fichier source au projet :  
  
    -   Cliquez avec le bouton droit sur le dossier **Fichiers sources** dans l’Explorateur de solutions, pointez sur **Ajouter**, puis cliquez sur **Nouvel élément**.  
  
    -   Cliquez sur **Fichier C++ (.cpp)**, tapez un nom de fichier, puis cliquez **Ajouter**.  
  
     Le fichier **.cpp** apparaît dans le dossier **Fichiers sources** de l’Explorateur de solutions. Dans la fenêtre à onglets qui s’affiche, tapez le code souhaité dans ce fichier.  
  
6.  Cliquez dans l’onglet nouvellement créé dans Visual Studio et tapez un programme Visual C++ valide, ou copiez et collez l’un des exemples de programmes.  
  
     Vous pouvez par exemple utiliser l’exemple de programme [Guide pratique pour écrire un fichier texte (C++/CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md) (dans le nœud **Gestion de fichiers et E/S** du guide de programmation).  
  
     Si vous avez recours à l’exemple de programme, notez que vous devez utiliser le mot clé `gcnew` à la place de `new` pour créer un objet .NET, et que `gcnew` retourne un handle (`^`) au lieu d’un pointeur (`*`) :  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     Pour plus d’informations sur la nouvelle syntaxe Visual C++, consultez [Extensions de composant pour les plateformes Runtime](../windows/component-extensions-for-runtime-platforms.md).  
  
7.  Dans le menu **Générer** , cliquez sur **Générer la solution**.  
  
     La fenêtre **Sortie** affiche des informations sur la progression de la compilation, comme l’emplacement du journal de génération, et un message indiquant l’état de la build.  
  
     Si vous modifiez et exécutez le programme sans effectuer de génération, une boîte de dialogue peut indiquer que le projet est obsolète. Cochez la case dans cette boîte de dialogue avant de cliquer sur **OK** si vous souhaitez que Visual Studio utilise toujours les versions actuelles des fichiers au lieu de vous le demander chaque fois qu’il génère l’application.  
  
8.  Dans le menu **Déboguer**, cliquez sur **Démarrer sans débogage**.  
  
9. Quand vous exécutez l’exemple de programme, une fenêtre de commande s’affiche et indique que le fichier texte a été créé. Appuyez sur une touche pour fermer la fenêtre de commande.  
  
     Le fichier texte **textfile.txt** se trouve désormais dans votre répertoire de projet. Vous pouvez ouvrir ce fichier à l’aide du Bloc-notes.  
  
    > [!NOTE]
    >  Si vous choisissez le modèle Projet vide CLR, l’option de compilateur **/CLR** est définie automatiquement. Pour le vérifier, cliquez avec le bouton droit sur le projet dans **l’Explorateur de solutions**, cliquez sur **Propriétés**, puis examinez l’option **Prise en charge du Common Language Runtime** dans le nœud  **Général** de **Propriétés de configuration**.  
  
## <a name="whats-next"></a>Étapes suivantes  
 **Étape précédente :** [Procédure pas à pas : compilation d’un programme C++ natif sur la ligne de commande](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **Étape suivante :**[Procédure pas à pas : compilation d’un programme C sur la ligne de commande](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur le langage C++](../cpp/cpp-language-reference.md)   
 [Génération de programmes C/C++](../build/building-c-cpp-programs.md)