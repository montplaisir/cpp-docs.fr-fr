---
title: Préparation d’un ordinateur de test pour lancer un exécutable de débogage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33683ebe349fbfdcb3fd51179ed6bc3140510c00
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33330295"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Préparation d'un ordinateur de test pour lancer un exécutable de débogage
Pour préparer un ordinateur à tester la version debug d'une application développée en Visual C++, vous devez déployer les versions debug des DLL de la bibliothèque Visual C++ dont l'application dépend. Pour identifier les DLL qui doivent être déployées, suivez les étapes dans [Fonctionnement des dépendances d’une application Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). En général, les versions debug des DLL de la bibliothèque Visual C++ ont un nom qui se termine par "d" ; par exemple, la version debug de msvcr100.dll se nomme msvcr100d.dll.  
  
> [!NOTE]
>  Les versions debug d'une application ne sont pas redistribuables, et les versions debug des DLL de la bibliothèque Visual C++ ne le sont pas non plus. Vous pouvez déployer les versions debug des applications et des DLL Visual C++ uniquement sur vos autres ordinateurs, dans le seul but de déboguer et de tester les applications sur un ordinateur où Visual Studio n'est pas installé. Pour plus d'informations, consultez [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md).  
  
 Il existe trois façons de déployer les versions debug des DLL de la bibliothèque Visual C++ ainsi que la version debug d'une application :  
  
-   Utilisez le déploiement central pour installer une version debug d’une DLL Visual C++ particulière dans le répertoire %windir%\system32\ en utilisant un projet d’installation qui inclut des modules de fusion pour la version et l’architecture de bibliothèque appropriées de votre application. Les modules de fusion se trouvent dans le répertoire Program Files ou Program Files (x86) sous \Common Files\Merge Modules\\. La version debug d’un module de fusion a un nom contenant le mot Debug, par exemple, Microsoft_VC110_DebugCRT_x86.msm. Un exemple de ce déploiement se trouve dans [Procédure pas à pas : déploiement d’une application Visual C++ à l’aide d’un projet d’installation](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
-   Utilisez le déploiement local pour installer une version debug d’une DLL Visual C++ particulière dans le répertoire d’installation de l’application en utilisant les fichiers fournis dans le répertoire Program Files ou Program Files (x86) sous \Microsoft Visual Studio \<version>\VC\redist\Debug_NonRedist\\.  
  
    > [!NOTE]
    >  Pour le débogage distant de votre application développée en Visual C++ 2005 ou Visual C++ 2008 sur un autre ordinateur, vous devez déployer les versions debug des DLL de la bibliothèque Visual C++ en tant qu'assemblys côte à côte partagés. Vous pouvez utiliser un projet d’installation ou Windows Installer pour installer les modules de fusion correspondants.  
  
-   Utilisez l’option _**Déployer** dans la boîte de dialogue **Gestionnaire de configurations** de Visual Studio pour copier la sortie du projet et d’autres fichiers sur l’ordinateur distant. 
  
 Après avoir installé les DLL Visual C++, vous pouvez exécuter un débogueur distant sur un partage réseau. Pour plus d’informations sur le débogage distant, consultez [Débogage distant](/visualstudio/debugger/remote-debugging.md).  
  
## <a name="see-also"></a>Voir aussi  
 
 [Déploiement dans Visual C++](../ide/deployment-in-visual-cpp.md)   
 [Options de ligne de commande de Windows Installer](http://msdn.microsoft.com/library/windows/desktop/aa367988.aspx)   
 [Exemples de déploiement](../ide/deployment-examples.md) [Débogage distant](/visualstudio/debugger/remote-debugging.md)