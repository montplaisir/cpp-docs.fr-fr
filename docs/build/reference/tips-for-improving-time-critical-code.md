---
title: "Conseils pour l&#39;am&#233;lioration du code &#224; dur&#233;e critique | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_lfind (fonction)"
  - "_lsearch (fonction)"
  - "tâches en arrière-plan"
  - "meilleures pratiques, code à durée critique"
  - "bsearch (fonction)"
  - "cache (C++), accès et défaut de résultat"
  - "pertes de cycle d'horloge"
  - "code, à durée critique"
  - "exécution, améliorations de la vitesse"
  - "allocation des tas, performances du code à durée critique"
  - "performances de la recherche linéaire"
  - "listes, trier"
  - "performances du tas local"
  - "mémoire (C++), surveiller l'utilisation"
  - "MFC (C++), performances"
  - "optimisation (C++), code à durée critique"
  - "erreurs de page"
  - "performances (C++), code à durée critique"
  - "programmes (C++), performances"
  - "qsort (fonction)"
  - "rechercher (C++), améliorer les performances"
  - "routines de tri"
  - "trier les données, améliorer les performances"
  - "routines de tri standard"
  - "threads (C++), tâches en arrière-plan"
  - "threads (C++), meilleures pratiques"
  - "threads (C++), performances"
ms.assetid: 3e95a8cc-6239-48d1-9d6d-feb701eccb54
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Conseils pour l&#39;am&#233;lioration du code &#224; dur&#233;e critique
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'écriture d'un code rapide demande de comprendre tous les aspects de votre application, ainsi que la manière dont elle interagit avec le système.  Cette rubrique suggère des alternatives à certaines techniques de codage évidentes pour vous aider à garantir que les parties critiques en termes de temps de votre code fonctionnent correctement.  
  
 Pour résumer, l'amélioration de code critique en terme de temps exige que vous :  
  
-   connaissiez les parties de votre programme qui doivent être rapides ;  
  
-   connaissiez la taille et la vitesse de votre code ;  
  
-   connaissiez le coût des nouvelles fonctionnalités ;  
  
-   connaissiez le travail minimal requis pour accomplir la tâche.  
  
 Pour rassembler des informations sur les performances de votre code, vous pouvez utiliser l'Analyseur de performances \(perfmon.exe\).  
  
## Sections de cet article  
  
-   [Échecs dans le cache et défauts de page](#_core_cache_hits_and_page_faults)  
  
-   [Tri et recherche](#_core_sorting_and_searching)  
  
-   [MFC et bibliothèques de classes](#_core_mfc_and_class_libraries)  
  
-   [Bibliothèques partagées](#vcovrsharedlibraries)  
  
-   [Tas](#_core_heaps)  
  
-   [Threads](#_core_threads)  
  
-   [Petite plage de travail](#_core_small_working_set)  
  
##  <a name="_core_cache_hits_and_page_faults"></a> Échecs dans le cache et défauts de page  
 Les correspondances manquées dans le cache, à la fois dans le cache interne et le cache externe, ainsi que les défauts de page \(accès à la mémoire auxiliaire pour les données et les instructions du programme\) ralentissent les performances d'un programme.  
  
 Une correspondance dans le cache d'UC peut coûter à votre programme entre 10 et 20 cycles d'horloge.  Une correspondance dans le cache externe peut coûter entre 20 et 40 cycles d'horloge.  Un défaut de page peut coûter un million de cycles d'horloge \(dans l'hypothèse d'un processeur traitant 500 millions d'instructions par seconde et d'une durée de 2 millisecondes pour un défaut de page\).  Par conséquent, il est dans l'intérêt de l'exécution du programme d'écrire du code permettant de réduire le nombre de correspondances manquées dans le cache et de défauts de page.  
  
 Une des raisons de la lenteur de certains programmes peut être qu'ils acceptent plus de défauts de page ou manquent le cache plus souvent que nécessaire.  Pour éviter cela, il est important d'utiliser des structures de données dotées d'une bonne localité de référence, c'est\-à\-dire qui maintient ensemble les éléments associés.  Parfois, une structure de données qui semble appropriée s'avère désastreuse en raison d'une médiocre localité de référence, et l'inverse est parfois vrai.  Voici deux exemples :  
  
-   Des listes liées allouées dynamiquement peuvent réduire les performances d'un programme, car quand vous recherchez un élément ou quand vous parcourez une liste jusqu'à la fin, chaque lien ignoré peut manquer le cache ou générer un défaut de page.  Une implémentation de liste basée sur des tableaux simples peut en fait être nettement plus rapide en raison d'une meilleure mise en cache et d'un nombre réduit de défauts de page. Compte tenu du fait qu'il serait plus difficile d'accroître le tableau, cette solution pourrait encore être plus rapide.  
  
-   Les tables de hachage qui utilisent des listes liées allouées dynamiquement peuvent dégrader les performances.  Par extension, les tables de hachage qui utilisent des listes liées allouées dynamiquement pour stocker leur contenu peuvent fonctionner nettement moins bien.  En fait, dans l'analyse finale, une recherche linéaire simple dans un tableau peut effectivement être plus rapide \(selon les circonstances\).  Les tables de hachage basées sur tableau \(on parle de « hachage fermé »\) constituent une implémentation souvent négligée qui affiche fréquemment des performances supérieures.  
  
##  <a name="_core_sorting_and_searching"></a> Tri et recherche  
 Le tri est intrinsèquement un processus long par rapport à de nombreuses opérations standard.  La meilleure façon d'éviter un ralentissement inutile consiste à éviter d'effectuer des tris aux moments critiques.  Vous pouvez éventuellement :  
  
-   différer un tri jusqu'à un moment non critique pour les performances ;  
  
-   trier les données plus tôt, à un moment non critique pour les performances ;  
  
-   trier uniquement la partie des données qui a réellement besoin d'être triée.  
  
 Parfois, vous pouvez établir la liste dans l'ordre de tri.  Soyez prudent, car si vous avez besoin d'insérer des données dans l'ordre de tri, vous avez peut\-être besoin d'une structure de données plus compliquée avec une médiocre qualité de référence, entraînant des échecs dans le cache et des défauts de page.  Il n'existe pas d'approche qui fonctionne dans tous les cas.  Essayez plusieurs approches et mesurez les différences.  
  
 Voici quelques conseils généraux en matière de tri :  
  
-   Utilisez un tri de stock pour réduire au maximum les bogues.  
  
-   Tout travail que vous pouvez effectuer au préalable pour réduire la complexité du tri est utile.  Si un passage unique sur vos données simplifie les comparaisons et réduit le tri de O\(n log n\) à O\(n\), vous en serez quasiment certainement gagnant.  
  
-   Pensez à la localité de référence de l'algorithme de tri et aux données sur lesquelles vous prévoyez qu'il s'exécutera.  
  
 Il existe moins d'alternatives pour les recherches que pour le tri.  Si la recherche dépend de façon critique du temps, une recherche binaire ou une recherche dans une table de hachage est quasiment toujours la meilleure solution, mais pour ce qui est du tri, vous devez garder à l'esprit la localité.  Une recherche linéaire dans un petit tableau peut être plus rapide qu'une recherche binaire dans une structure de données avec de nombreux pointeurs qui génère des défauts de page ou des échecs dans le cache.  
  
##  <a name="_core_mfc_and_class_libraries"></a> MFC et bibliothèques de classes  
 La bibliothèque MFC \(Microsoft Foundation Classes\) peut grandement simplifier l'écriture de code.  Lorsque vous écrivez du code fortement dépendant du temps, vous devez être conscient de la surcharge inhérente à certaines classes.  Examinez le code MFC qu'utilise votre code fortement dépendant du temps pour voir s'il satisfait à vos exigences en matière de performances.  La liste suivante identifie les fonctions et classes MFC dont vous devez être conscient :  
  
-   `CString` La bibliothèque MFC appelle la bibliothèque Runtime C pour allouer dynamiquement de la mémoire pour un objet[CString](../../atl-mfc-shared/reference/cstringt-class.md).  Dans l'ensemble, `CString` est aussi efficace que toute autre chaîne allouée dynamiquement.  Comme pour toute chaîne allouée dynamiquement, il a la surcharge de l'allocation et de la libération dynamiques.  Souvent, un tableau `char` simple sur la pile peut servir le même objectif et être plus rapide.  N'utilisez pas `CString` pour stocker une chaîne constante.  Utilisez plutôt `const char *`.  Toute opération que vous effectuez avec un objet `CString` présente une certaine surcharge.  L'utilisation des [fonctions de chaîne](../../c-runtime-library/string-manipulation-crt.md) de la bibliothèque runtime peut être plus rapide.  
  
-   `CArray` Un objet [CArray](../../mfc/reference/carray-class.md) fournit une flexibilité qu'un tableau standard ne fournit pas, mais votre programme n'en a peut\-être pas besoin.  Si vous connaissez les limites spécifiques du tableau, vous pouvez utiliser un tableau fixe global à la place.  Si vous utilisez `CArray`, utilisez `CArray::SetSize` pour établir sa taille et spécifiez le nombre d'éléments dont il croîtra quand une réallocation sera nécessaire.  Dans le cas contraire, l'ajout d'éléments peut entraîner la réallocation et la copie fréquentes de votre tableau, ce qui est inefficace et peut fragmenter la mémoire.  De plus, sachez que si vous insérez un élément dans un tableau, l'objet `CArray` déplace les éléments suivants dans la mémoire et peut être amené à augmenter la taille du tableau.  Ces actions peuvent provoquer des défauts de page et des échecs dans le cache.  Si vous examinez le code que la bibliothèque MFC utilise, vous pouvez voir que vous pouvez écrire quelque chose de plus spécifique dans votre scénario pour améliorer les performances.  Comme `CArray` est un modèle, par exemple, vous pouvez fournir des spécialisations de `CArray` pour des types spécifiques.  
  
-   `CList`  [CList](../../mfc/reference/clist-class.md) est une liste à double liaison, si bien que l'insertion d'éléments est rapide à la tête, à la fin et à une position connue \(`POSITION`\) de la liste.  La recherche d'un élément par valeur ou index exige une recherche séquentielle, toutefois, laquelle peut être lente si la liste est longue.  Si votre code ne requiert pas de liste à double liaison, vous voudrez peut\-être reconsidérer l'utilisation de `CList`.  L'utilisation d'une liste à liaison unique économise la surcharge liée à la mise à jour d'un pointeur supplémentaire pour toutes les opérations, ainsi que la mémoire pour ce pointeur.  La mémoire supplémentaire n'est pas de grande ampleur, mais elle représente une autre opportunité de défauts de page ou d'échecs dans le cache.  
  
-   `IsKindOf` Cette fonction peut générer de nombreux appels et accéder à une grande quantité de mémoire dans diverses zones de données, entraînant ainsi une mauvaise localité de référence.  Il est utile pour une version Debug \(dans un appel ASSERT, par exemple\), mais essayez d'éviter de l'utiliser dans une version Release.  
  
-   `PreTranslateMessage` Utilisez `PreTranslateMessage` quand une arborescence particulière de fenêtres a besoin d'autres accélérateurs clavier ou quand vous devez insérer la gestion des messages dans la pompe de messages.  `PreTranslateMessage` modifie les messages de distribution MFC.  Si vous remplacez `PreTranslateMessage`, faites\-le seulement au niveau requis.  Par exemple, il n'est pas nécessaire de remplacer `CMainFrame::PreTranslateMessage` si seuls les messages destinés aux enfants d'une vue particulière vous intéressent.  Remplacez plutôt `PreTranslateMessage` pour la classe de vue.  
  
     Ne contournez pas le chemin de distribution normal en utilisant `PreTranslateMessage` pour traiter des messages quelconques envoyés vers des fenêtres quelconques.  Utilisez les [procédures de fenêtre](../../mfc/registering-window-classes.md) et les tables des messages MFC à cet effet.  
  
-   `OnIdle` Des événements inactifs peuvent survenir à des moments inattendus, par exemple entre des événements `WM_KEYDOWN` et `WM_KEYUP`.  Les minuteries peuvent fournir un moyen plus efficace de déclencher votre code.  Ne forcez pas les appels répétés à `OnIdle` en générant des messages faux ou en retournant toujours `TRUE` à partir d'une substitution d'`OnIdle`, ce qui ne permettrait jamais la mise en veille de votre thread.  À nouveau, une minuterie ou un thread distinct peuvent être plus appropriés.  
  
##  <a name="vcovrsharedlibraries"></a> Bibliothèques partagées  
 La réutilisation de code est souhaitable.  Toutefois, si vous envisagez d'utiliser le code de quelqu'un d'autre, vous devez vous assurer de savoir exactement ce qu'il fait dans les cas où les performances sont essentielles pour vous.  La meilleure façon de comprendre cela est de parcourir pas à pas le code source ou d'effectuer des mesures à l'aide d'outils tels que PView et l'Analyseur de performances.  
  
##  <a name="_core_heaps"></a> Tas  
 Utilisez plusieurs cas avec discernement.  Les tas supplémentaires créés avec `HeapCreate` et `HeapAlloc` vous permettent de gérer et de disposer d'un ensemble connexe d'allocations.  Ne validez pas trop de mémoire.  Si vous utilisez plusieurs tas, faites particulièrement attention à la quantité de mémoire initialement validée.  
  
 À la place de plusieurs tas, vous pouvez utiliser des fonctions d'assistance comme interface entre votre code et le tas par défaut.  Les fonctions d'assistance favorisent des stratégies d'allocation personnalisées susceptibles d'améliorer les performances de votre application.  Par exemple, si vous effectuez fréquemment de petites allocations, vous pouvez localiser ces allocations dans une même partie du tas par défaut.  Vous pouvez allouer un grand bloc de mémoire, puis utiliser une fonction d'assistance pour sous\-allouer à partir de ce bloc.  Dans ce cas, vous n'aurez pas de tas supplémentaires avec de la mémoire inutilisée car l'allocation provient du tas par défaut.  
  
 Dans certains cas, toutefois, l'utilisation du tas par défaut peut réduire la localité de référence.  Utilisez Process Viewer, Spy\+\+ ou l'Analyseur de performances pour mesurer les effets du déplacement des objets d'un tas à un autre.  
  
 Mesurez vos tas de manière à pouvoir rendre compte de chaque allocation sur le tas.  Utilisez les [routines de tas Debug](../Topic/CRT%20Debug%20Heap%20Details.md) de la bibliothèque Runtime C pour effectuer un point de contrôle sur votre tas et vider ce dernier.  Vous pouvez lire la sortie dans un tableur tel que Microsoft Excel et utiliser des tableaux croisés pour afficher les résultats.  Notez le nombre total, la taille et la distribution des allocations.  Comparez ces valeurs avec la taille des plages de travail.  Examinez également le clustering des objets de taille connexe.  
  
 Vous pouvez également utiliser les compteurs de performance pour analyser l'utilisation de la mémoire.  
  
##  <a name="_core_threads"></a> Threads  
 Pour les tâches en arrière\-plan, le traitement inactif effectif des événements peut être plus rapide que l'utilisation de threads.  Il est plus aisé de comprendre la localité de référence dans un programme à un seul thread.  
  
 Une bonne règle empirique consiste à utiliser un thread seulement si une notification du système d'exploitation sur laquelle vous bloquez se trouve à la racine du travail en arrière\-plan.  Les threads constituent la meilleure solution dans ce cas, car il est peu pratique de bloquer un thread principal sur un événement.  
  
 Les threads présentent également des problèmes de communication.  Vous devez gérer le lien de communication entre vos threads à l'aide d'une liste de messages ou en allouant et en utilisant de la mémoire partagée.  La gestion du lien de communication exige habituellement une synchronisation pour éviter les conditions de concurrence critique et les problèmes de blocage.  Cette complexité peut aisément donner naissance à des bogues et à des problèmes de performances.  
  
 Pour plus d'informations, voir [Traitement inactif de boucle](../../mfc/idle-loop-processing.md) et [Multithreading](../../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
##  <a name="_core_small_working_set"></a> Petite plage de travail  
 De petites plages de travail induisent une meilleure localité de référence, moins de défauts de pages et plus de correspondances dans le cache.  La plage de travail de processus constitue la métrique la plus proche fournie directement par le système d'exploitation pour mesurer la localité de référence.  
  
-   Pour définir les limites supérieure et inférieure de la page de travail, utilisez [SetProcessWorkingSetSize](http://msdn.microsoft.com/library/windows/desktop/ms683226.aspx).  
  
-   Pour obtenir les limites supérieure et inférieure de la page de travail, utilisez [GetProcessWorkingSetSize](http://msdn.microsoft.com/library/windows/desktop/ms686234.aspx).  
  
-   Pour afficher la taille de la plage de travail, utilisez Spy\+\+.  
  
## Voir aussi  
 [Optimisation du code](../../build/reference/optimizing-your-code.md)