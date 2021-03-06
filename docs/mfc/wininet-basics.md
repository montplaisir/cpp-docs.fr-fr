---
title: Fondamentaux relatifs à WinInet | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7061c3203436197eb1bd03ae56058e0bd0f26f9d
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955581"
---
# <a name="wininet-basics"></a>Éléments fondamentaux relatifs à WinInet
Vous pouvez utiliser WinInet pour ajouter la prise en charge FTP pour télécharger des fichiers à partir de votre application. Vous pouvez substituer [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) et utiliser le *dwContext* paramètre pour fournir des informations de progression pour les utilisateurs que vous recherchez et téléchargez des fichiers.  
  
 Cet article contient les rubriques suivantes :  
  
-   [Créer un navigateur très Simple](#_core_create_a_very_simple_browser)  
  
-   [Une Page Web de téléchargement](#_core_download_a_web_page)  
  
-   [FTP d’un fichier](#_core_ftp_a_file)  
  
-   [Récupérer un répertoire Gopher](#_core_retrieve_a_gopher_directory)  
  
-   [Afficher les informations de progression pendant le transfert de fichiers](#_core_display_progress_information_while_transferring_files)  
  
 Les extraits de code ci-dessous montrent comment créer un navigateur simple, télécharger une page Web, FTP, un fichier et rechercher un fichier gopher. Ils ne sont pas destinés à titre d’exemple complète et pas tous contenir la gestion des exceptions.  
  
 Pour plus d’informations sur WinInet, consultez [extension Internet Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md).  
  
##  <a name="_core_create_a_very_simple_browser"></a> Créer un navigateur très Simple  
 [!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]  
  
##  <a name="_core_download_a_web_page"></a> Une Page Web de téléchargement  
 [!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]  
  
##  <a name="_core_ftp_a_file"></a> FTP d’un fichier  
 [!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a> Récupérer un répertoire Gopher  
 [!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]  
  
## <a name="use-onstatuscallback"></a>Utilisation de OnStatusCallback  
 Lorsque vous utilisez les classes WinInet, vous pouvez utiliser la [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) membre de votre application [CInternetSession](../mfc/reference/cinternetsession-class.md) objet à récupérer les informations d’état. Si vous dérivez votre propre `CInternetSession` de l’objet, substituez `OnStatusCallback`et activer les rappels d’état, MFC appelle votre `OnStatusCallback` fonction avec des informations de progression sur toutes les activités de la session Internet.  
  
 Car une session unique peut prendre en charge plusieurs connexions (qui, pendant leur durée de vie, peuvent effectuer diverses opérations distinctes), `OnStatusCallback` a besoin d’un mécanisme pour identifier chaque changement d’état avec une connexion particulière ou une transaction. Ce mécanisme est fourni par le paramètre d’ID de contexte fourni à de nombreuses fonctions membres dans les classes de prise en charge WinInet. Ce paramètre est toujours de type **DWORD** et est toujours nommé *dwContext*.  
  
 Le contexte affecté à un objet Internet particulier est utilisé uniquement pour identifier l’activité de l’objet provoque dans le `OnStatusCallback` membre de la `CInternetSession` objet. L’appel à `OnStatusCallback` reçoit plusieurs paramètres ; ces paramètres fonctionnent ensemble pour indiquer quel cours a été effectuée pour les transactions et la connexion à votre application.  
  
 Lorsque vous créez un `CInternetSession` objet, vous pouvez spécifier un *dwContext* paramètre au constructeur. `CInternetSession` lui-même n’utilise pas l’ID de contexte ; au lieu de cela, il passe l’ID de contexte sur les **InternetConnection**-les objets qui ne reçoivent pas explicitement un ID de contexte de leurs propres dérivés. Ensuite, ceux `CInternetConnection` objets passera à l’identificateur de contexte pour `CInternetFile` objets qu’ils créent si vous ne spécifiez pas explicitement un ID de contexte différent. Si, en revanche, vous spécifiez un ID de contexte spécifiques de votre choix, l’objet et tout travail qu’elle fournit à associer à cet ID de contexte. Vous pouvez utiliser l’ID de contexte pour identifier les informations d’état sont fournies dans votre `OnStatusCallback` (fonction).  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a> Afficher les informations de progression pendant le transfert de fichiers  
 Par exemple, si vous écrivez une application qui crée une connexion avec un serveur FTP pour lire un fichier et se connecte également à un serveur HTTP à une page Web, vous devez avoir un `CInternetSession` (objet), deux `CInternetConnection` objets (un doit être un `CFtpSession` et l’autre un `CHttpSession`) et deux `CInternetFile` objets (un pour chaque connexion). Si vous avez utilisé les valeurs par défaut pour le *dwContext* paramètres, vous ne serez pas en mesure de faire la distinction entre les `OnStatusCallback` appels qui indiquent la progression de la connexion FTP et les appels qui indiquent la progression de la Connexion HTTP. Si vous spécifiez un *dwContext* ID, vous pouvez ultérieurement à un test dans `OnStatusCallback`, vous saurez que l’opération ayant généré le rappel.  
  
## <a name="see-also"></a>Voir aussi  
 [Base de programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)   
 [Extension Internet Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)

