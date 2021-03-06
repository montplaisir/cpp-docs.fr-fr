---
title: Tâches légères | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d602f83cfe2da6bc1506e07720d3ef021ebce04a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687411"
---
# <a name="lightweight-tasks"></a>Tâches légères
Ce document décrit le rôle des tâches légères dans le Runtime d’accès concurrentiel. A *tâche légère* est une tâche que vous planifiez directement à partir d’un `concurrency::Scheduler` ou `concurrency::ScheduleGroup` objet. Une tâche légère ressemble à la fonction que vous fournissez à l’API Windows [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) (fonction). Par conséquent, les tâches légères sont utiles lorsque vous adaptez du code existant pour utiliser les fonctionnalités de planification du Runtime d’accès concurrentiel. Le Runtime d’accès concurrentiel lui-même utilise des tâches légères pour planifier des agents asynchrones et envoyer des messages entre les blocs de messages asynchrones.  
  
> [!TIP]
>  Le runtime d'accès concurrentiel fournit un planificateur par défaut, et vous n'êtes donc pas obligé d'en créer un dans votre application. Étant donné que le Planificateur de tâches vous aide à optimiser les performances de vos applications, nous vous recommandons de commencer avec la [bibliothèque de modèles parallèles (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) ou [bibliothèque d’Agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) si vous êtes nouveau pour le Runtime d’accès concurrentiel.  
  
 Tâches légères présentent moins de traitement que les agents asynchrones et les groupes de tâches. Par exemple, le runtime ne pas vous informe lorsqu’une tâche légère se termine. En outre, le runtime ne pas intercepter ou de gérer les exceptions levées à partir d’une tâche légère. Pour plus d’informations sur la gestion des exceptions et les tâches légères, consultez [la gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Pour la plupart des tâches, nous vous recommandons d’utiliser des fonctionnalités plus fiables telles que les groupes de tâches et les algorithmes parallèles, car elles vous permettent de facilement diviser des tâches complexes en plus simples. Pour plus d’informations sur les groupes de tâches, consultez [parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Pour plus d’informations sur les algorithmes parallèles, consultez [des algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
 Pour créer une tâche légère, appelez le [Concurrency::ScheduleGroup :: ScheduleTask](reference/schedulegroup-class.md#scheduletask), [Concurrency::CurrentScheduler :: ScheduleTask](reference/currentscheduler-class.md#scheduletask), ou [Concurrency::Scheduler :: ScheduleTask ](reference/scheduler-class.md#scheduletask) (méthode). Pour attendre qu’une tâche légère se termine, attendez que le planificateur parent arrête ou utilisez un mécanisme de synchronisation tel qu’un [concurrency::event](../../parallel/concrt/reference/event-class.md) objet.  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple qui montre comment adapter du code existant pour utiliser une tâche légère, consultez [procédure pas à pas : adaptation d’un Code existant pour utiliser des tâches légères](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Procédure pas à pas : adaptation d’un code existant pour l’utilisation de tâches légères](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)

