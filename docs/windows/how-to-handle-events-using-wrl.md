---
title: 'Comment : gérer les événements à l’aide de WRL | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 287fe57868f1550e2f778bd9122d0d350011084e
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570631"
---
# <a name="how-to-handle-events-using-wrl"></a>Comment : gérer les événements à l'aide de WRL
Ce document montre comment utiliser la bibliothèque de modèles C++ (WRL) de Windows Runtime pour s’abonner à et gérer les événements d’un objet Windows Runtime.  
  
 Pour obtenir un exemple plus simple qui crée une instance de ce composant et récupère une valeur de propriété, consultez [Comment : activer et utiliser un composant d’exécution Windows](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
## <a name="subscribing-to-and-handling-events"></a>Abonnement à et gestion des événements  
 Les étapes suivantes démarrer un `ABI::Windows::System::Threading::IDeviceWatcher` de l’objet et utiliser des gestionnaires d’événements pour surveiller la progression. Le `IDeviceWatcher` interface vous permet d’énumérer les appareils de façon asynchrone, ou en arrière-plan, et recevoir une notification lorsque les appareils sont ajoutées, supprimées ou modifiées. Le [rappel](../windows/callback-function-windows-runtime-cpp-template-library.md) fonction est une partie importante de cet exemple, car il lui permet de spécifier des gestionnaires d’événements qui traitent les résultats de l’opération d’arrière-plan. L’exemple complet suit.  
  
> [!WARNING]
>  Bien que vous utilisez généralement la bibliothèque de modèles Windows Runtime C++ dans une application de plateforme Windows universelle, cet exemple utilise une application console à titre d’illustration. Les fonctions telles que `wprintf_s` ne sont pas disponibles à partir d’une application de plateforme Windows universelle. Pour plus d’informations sur les types et les fonctions que vous pouvez utiliser dans une application de plateforme Windows universelle, consultez [fonctions CRT non prises en charge dans les applications de plateforme Windows universelle](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) et [Win32 et COM pour les applications UWP](/uwp/win32-and-com/win32-and-com-for-uwp-apps).  
  
1.  Inclure (`#include`) toute requise Windows Runtime, bibliothèque de modèles C++ Windows Runtime ou les en-têtes de bibliothèque C++ Standard.  
  
     [!code-cpp[wrl-consume-event#2](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]  
  
     Windows.Devices.Enumeration.h déclare les types qui sont requis pour énumérer les appareils.  
  
     Nous vous recommandons d'utiliser la directive `using namespace` dans votre fichier .cpp pour rendre le code plus lisible.  
  
2.  Déclarez les variables locales pour l’application. Cet exemple conserve le nombre de périphériques énumérés et jetons d’inscription qui lui permettent de se désabonner plus tard d’événements.  
  
     [!code-cpp[wrl-consume-event#7](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]  
  
3.  Initialiser le Runtime de Windows.  
  
     [!code-cpp[wrl-consume-event#3](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]  
  
4.  Créer un [événement](../windows/event-class-windows-runtime-cpp-template-library.md) objet qui synchronise l’achèvement du processus d’énumération à l’application principale.  
  
     [!code-cpp[wrl-consume-event#4](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  Cet événement est de démonstration uniquement dans le cadre d’une application console. Cet exemple utilise l’événement pour vous assurer qu’une opération asynchrone se termine avant l’application se ferme. Dans la plupart des applications, vous en général, n’attendez pas les opérations asynchrones se terminent.  
  
5.  Créer une fabrique d’activation pour le `IDeviceWatcher` interface.  
  
     [!code-cpp[wrl-consume-event#5](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]  
  
     Le Runtime Windows utilise des noms qualifiés complets pour identifier les types. Le `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` paramètre est une chaîne qui est fournie par le Runtime Windows et contient le nom de classe runtime requis.  
  
6.  Créer le `IDeviceWatcher` objet.  
  
     [!code-cpp[wrl-consume-event#6](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]  
  
7.  Utilisez le `Callback` (fonction) pour vous abonner à la `Added`, `EnumerationCompleted`, et `Stopped` événements.  
  
     [!code-cpp[wrl-consume-event#8](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]  
  
     Le `Added` Gestionnaire d’événements incrémente le nombre de périphériques énumérés. Il arrête le processus d’énumération après que dix périphériques sont détectés.  
  
     Le `Stopped` supprime les gestionnaires d’événements de gestionnaire d’événements et définit l’événement d’achèvement.  
  
     Le `EnumerationCompleted` Gestionnaire d’événements arrête le processus de l’énumération. Nous gérons cet événement dans le cas où il existe moins de dix périphériques.  
  
    > [!TIP]
    >  Cet exemple utilise une expression lambda pour définir les rappels. Vous pouvez également utiliser des objets de fonction (functors), des pointeurs de fonction, ou [std::function](../standard-library/function-class.md) objets. Pour plus d’informations sur les expressions lambda, consultez [Expressions Lambda](../cpp/lambda-expressions-in-cpp.md).  
  
8.  Démarrer le processus d’énumération.  
  
     [!code-cpp[wrl-consume-event#9](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]  
  
9. Attendez que le processus d’énumération terminer, puis imprimer un message. Tous les objets `ComPtr` et RAII quittent la portée et sont libérés automatiquement.  
  
     [!code-cpp[wrl-consume-event#10](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]  
  
 Voici un exemple complet :  
  
 [!code-cpp[wrl-consume-event#1](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Pour compiler le code, copiez-le et collez-le dans un projet Visual Studio ou collez-le dans un fichier nommé `wrl-consume-events.cpp` , puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 `cl.exe wrl-consume-events.cpp runtimeobject.lib`  
  
## <a name="see-also"></a>Voir aussi  
 [Bibliothèque de modèles Windows Runtime C++ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)