---
title: "Services CWinApp spéciaux | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
dev_langs: C++
helpviewer_keywords:
- files [MFC], most recently used
- DragAcceptFiles method [MFC]
- MRU lists
- GDI+, initializing for MFC
- GDI+, suppressing background thread [MFC]
- CWinApp class [MFC], shell registration
- application objects [MFC], services
- CWinApp class [MFC], initializing GDI+
- MFC, shell registration
- CWinApp class [MFC], File Manager drag and drop
- LoadStdProfileSettings method [MFC]
- MFC, most-recently-used file list
- RegisterShellFileTypes method [MFC]
- drag and drop [MFC], files
- registering file types
- Shell, registering file types
- services, provided by CWinApp
- CWinApp class [MFC], recently used documents
- CWinApp class [MFC], services
- files [MFC], drag and drop
- EnableShellOpen method [MFC]
- registry [MFC], most recently used files
- MFC, file operations
- registration [MFC], shell
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f8734bfd4e673e1298d6822bbd272e2d70ff7a81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="special-cwinapp-services"></a>Services CWinApp spéciaux
Outre la boucle de messages en cours d’exécution et de vous donner la possibilité d’initialiser l’application et nettoyer après cela, [CWinApp](../mfc/reference/cwinapp-class.md) fournit plusieurs autres services.  
  
##  <a name="_core_shell_registration"></a>Inscription du shell  
 Par défaut, l'Application MFC permet à l'utilisateur d'ouvrir les fichiers de données que votre application a créés en double-cliquant dessus dans l'Explorateur de fichiers ou le gestionnaire de fichiers. Si votre application est une application MDI et que vous spécifiez une extension pour les fichiers de votre application crée, l’Assistant Application MFC ajoute des appels à la [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) et [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)fonctions membres de [CWinApp](../mfc/reference/cwinapp-class.md) à la `InitInstance` remplacement qu’il écrit pour vous.  
  
 `RegisterShellFileTypes` stocke les types de documents de votre application avec l'Explorateur de fichiers ou le gestionnaire de fichiers. La fonction ajoute des entrées à la base de données d'inscription que Windows gère. Les entrées enregistrent chaque type de document, associent une extension au type de fichier, spécifient une ligne de commande pour ouvrir l’application, puis spécifient une commande d’échange dynamique de données (DDE) pour ouvrir un document de ce type.  
  
 `EnableShellOpen` termine le processus permettant à l'application de recevoir des commandes DDE à partir de l'Explorateur de fichiers ou du gestionnaire de fichiers pour ouvrir le fichier choisi par l'utilisateur.  
  
 Cette prise en charge d'inscription automatique dans `CWinApp` élimine le besoin de fournir un fichier .reg à votre application ou d'exécuter un travail d'installation particulier.  
  
 Si vous souhaitez initialiser GDI + pour votre application (en appelant [GdiplusStartup]--brokenlink--(_gdiplus_FUNC_GdiplusStartup_token_input_output_) dans votre [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) fonction), vous devez supprimer le thread d’arrière-plan GDI +.  
  
 Vous faire cela en définissant le **SuppressBackgroundThread** membre de la [structure GdiplusStartupInput]--brokenlink--(_gdiplus_STRUC_GdiplusStartupInput) **TRUE**. Lorsque la suppression GDI + arrière-plan thread, le **NotificationHook** et **NotificationUnhook** appels (voir [GdiplusStartupOutput]--brokenlink--(_gdiplus_STRUC_GdiplusStartupOutput)) doit être effectué juste avant d’entrer et de quitter la boucle de message de l’application. Par conséquent, un bon emplacement pour appeler **GdiplusStartup** et les fonctions de raccordement de notification dans une substitution de la fonction virtuelle [CWinApp::Run](../mfc/reference/cwinapp-class.md#run), comme indiqué ci-dessous :  
  
 [!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]  
  
 Si vous ne supprimez pas le thread GDI+ d'arrière-plan, les commandes DDE peuvent être publiées prématurément dans l'application avant que la fenêtre principale soit créée. Les commandes DDE publiées par le shell peuvent être suspendues prématurément, ce qui aboutit à des messages d'erreur.  
  
##  <a name="_core_file_manager_drag_and_drop"></a>Le Gestionnaire de fichiers glisser -déplacer  
 Les fichiers peuvent être glissés de la fenêtre d'affichage des fichiers dans le gestionnaire de fichiers ou l'Explorateur de fichiers vers une fenêtre de votre application. Vous pouvez, par exemple, activer un ou plusieurs fichiers à faire glisser vers la fenêtre principale d'une application MDI, où l'application peut extraire le nom et les fenêtres enfants MDI ouverts pour ces fichiers.  
  
 Pour activer la fonction glisser-déplacer dans votre application, l’Assistant Application MFC écrit un appel à la [CWnd](../mfc/reference/cwnd-class.md) fonction membre [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) pour votre fenêtre frame principale de votre `InitInstance`. Supprimez cet appel si vous ne souhaitez pas implémenter la fonctionnalité Glisser-déposer.  
  
> [!NOTE]
>  Vous pouvez également implémenter des fonctionnalités Glisser-déposer plus générales (comme faire glisser des données entre ou à l’intérieur de documents) avec OLE. Pour plus d’informations, consultez l’article [glisser-déplacer (OLE)](../mfc/drag-and-drop-ole.md).  
  
##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a>Le suivi de la plupart des Documents utilisés récemment  
 Lorsque l'utilisateur ouvre et ferme des fichiers, l'objet d'application gère les quatre fichiers récemment utilisés. Les noms de ces fichiers sont ajoutés au menu Fichier et mis à jour lorsqu'ils sont modifiés. Le framework stocke ces noms de fichiers dans le Registre ou dans le fichier .ini, avec le même nom que le projet et les lit à partir du fichier au démarrage de votre application. Le `InitInstance` remplacer que l’Assistant Application MFC crée pour vous inclut un appel à la [CWinApp](../mfc/reference/cwinapp-class.md) fonction membre [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings), ce qui charge à partir du Registre ou .ini fichier, y compris les derniers utilisé des noms de fichiers.  
  
 Ces entrées sont stockées comme suit :  
  
-   Dans Windows NT, Windows 2000 ou les versions ultérieures, la valeur est enregistrée dans une clé de Registre.  
  
-   Dans windows 3.x, la valeur est stockée dans le fichier WIN.INI.  
  
-   Dans Windows 95 et versions ultérieures, la valeur est stockée dans une version mise en cache du fichier WIN.INI.  
  
## <a name="see-also"></a>Voir aussi  
 [CWinApp : classe d’application](../mfc/cwinapp-the-application-class.md)