---
title: Le cloud et Web de programmation dans Visual C++ | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-azure
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 360404530df8d07a3cd8fc35654c0c9563ae29fe
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412398"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Cloud et programmation Web dans Visual C++

En C++, vous disposez de plusieurs options de connexion web et cloud.

## <a name="cloud-programming-options"></a>Options de programmation de cloud computing

- [Microsoft Azure Mobile Services](http://www.windowsazure.com/develop/mobile/)

   Fournit des API natives que vous pouvez utiliser dans les applications de plateforme Windows universelle (UWP) ou des applications de bureau Windows pour se connecter à Windows Azure Mobile Services. Bien que la plupart des exemples présentés sur le site web soient en C#, vous pouvez aussi utiliser C++. Pour plus d’informations, consultez [Démarrage rapide : ajout d’un service mobile en C++](http://msdn.microsoft.com/library/windows/apps/dn263181.aspx).

- [Bibliothèque cliente de stockage Microsoft Azure pour C++](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)

   La bibliothèque cliente de stockage Azure pour C++ fournit une API complète pour travailler avec le stockage Azure, y compris de manière non limitative, les capacités suivantes :

  - Créer, lire, supprimer et répertorier des conteneurs d’objets blob, les tables et les files d’attente.
  - Créer, lire, supprimer, liste et copie les objets BLOB plus lire et écrire des plages d’objets blob.
  - INSERT, delete, replace, merge et interroger des entités dans une table Azure.
  - File d’attente et de retrait des messages dans une file d’attente Azure.
  - Liste tardivement des conteneurs, objets BLOB, tables et files d’attente et tardivement interroger des entités

- [OneDrive API](https://dev.onedrive.com/README.htm)

   L’API OneDrive fournit un ensemble de services HTTP pour connecter votre application aux fichiers et dossiers dans Office 365 et SharePoint Server 2016.

- [SDK C++ REST (nom de code Casablanca)](https://github.com/Microsoft/cpprestsdk)

   Fournit une API de moderne, multiplateforme et asynchrone pour interagir avec les services REST.

  - Effectuer des appels REST sur n’importe quel serveur HTTP, avec prise en charge intégrée pour la sérialisation et de l’analyse de documents JSON
  - Prend en charge OAuth 1 et 2, y compris un écouteur local de redirection
  - Établir des connexions WebSocket auprès des services à distance
  - Une tâche asynchrone complet API basée sur la bibliothèque de modèles parallèles, y compris un pool de threads intégré

   Prend en charge le bureau de Windows (7 +), Windows Server (2012 +), plateforme universelle Windows, Linux, OS x, Android et iOS. 

- [Windows::Web::Http::HttpClient](https://msdn.microsoft.com/en-us/library/windows/apps/windows.web.http.httpclient.aspx)

   Classe de client HTTP Windows Runtime modélisée sur la classe .NET Framework du même nom dans l'espace de noms System.Web. `HttpClient` prend entièrement en charge le chargement et le téléchargement asynchrones via HTTP, ainsi que les filtres de pipeline qui permettent l'insertion de gestionnaires HTTP personnalisés dans le pipeline. Le Kit de développement logiciel (SDK) Windows inclut des exemples de filtres pour les connexions réseau limitées, l'authentification OAuth et bien plus encore. Pour les applications qui ciblent uniquement les plateforme Windows universelle, nous vous recommandons d’utiliser la `Windows::Web:HttpClient` classe. 

- [Interface IXMLHTTPRequest2](http://msdn.microsoft.com/library/windows/apps/hh831151.aspx)

   Fournit une interface COM native que vous pouvez utiliser dans les applications Windows Runtime ou des applications de bureau Windows pour se connecter à Internet via HTTP et émettre GET, PUT et d’autres commandes HTTP. Pour plus d’informations, consultez [procédure pas à pas : connexion à l’aide de tâches et les requêtes HTTP XML](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).

- [Windows Internet (WinInet)](http://msdn.microsoft.com/library/windows/desktop/aa385331\(v=vs.85\).aspx)

   API Windows que vous pouvez utiliser dans les applications de bureau Windows pour vous connecter à Internet.

## <a name="see-also"></a>Voir aussi

[Visual C++](../visual-cpp-in-visual-studio.md) <br/>
[Les réseaux et les services web](/windows/uwp/networking/)
