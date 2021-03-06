---
title: 'Comment : inclure des ressources au moment de la compilation | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
dev_langs:
- C++
helpviewer_keywords:
- compiling source code, including resources
- comments [C++], compiled files
- resources [Visual Studio], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 856d448b096910c322750eccc7447689b08b328e
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571335"
---
# <a name="how-to-include-resources-at-compile-time"></a>Comment : inclure des ressources au moment de la compilation
Normalement, il est facile et pratique d'utiliser la disposition par défaut de toutes les ressources dans un seul fichier de script de ressources (.rc). Toutefois, vous pouvez ajouter des ressources dans d’autres fichiers à votre projet actif au moment de la compilation en les répertoriant dans la **directives de compilation** zone le [boîte de dialogue Include des ressources](../windows/resource-includes-dialog-box.md).  
  
 Il existe plusieurs raisons qui justifient le placement des ressources dans un autre fichier que le fichier .rc principal :  
  
-   Vous souhaitez ajouter des commentaires à des instructions de ressource qui ne sont pas supprimées quand vous enregistrez le fichier .rc.  
  
     Les éditeurs de ressources ne lisent pas directement les fichiers .rc ou resource.h. Le compilateur de ressources les compile en fichiers .aps, qui sont consommés par les éditeurs de ressources. Ce fichier est une étape de compilation, qui stocke uniquement les données symboliques. Comme pour un processus de compilation normal, les informations non symboliques (par exemple les commentaires) sont ignorées durant le processus de compilation. Chaque fois que le fichier .aps n'est plus synchronisé au fichier .rc, le fichier .rc est régénéré (par exemple, quand vous effectuez un enregistrement, l'éditeur de ressources remplace les fichiers .rc et resource.h). Les changements apportés aux ressources sont conservés dans le fichier .rc, mais les commentaires disparaissent une fois le fichier .rc remplacé.  
  
-   Vous souhaitez inclure des ressources qui ont déjà été développées et testées, et qui n'ont pas besoin de modifications supplémentaires. (Les fichiers inclus mais dépourvus d'extension .rc ne sont pas modifiables par les éditeurs de ressources.)  
  
-   Vous souhaitez inclure des ressources utilisées par plusieurs projets différents, ou qui font partie d'un système de contrôle de version du code source et qui doivent donc exister dans un emplacement central où les modifications affectent tous les projets.  
  
-   Vous souhaitez inclure des ressources (par exemple des ressources RCDATA) qui ont un format personnalisé. Les ressources RCDATA peuvent avoir des spécifications particulières. Par exemple, vous ne pouvez pas utiliser une expression en tant que valeur pour le champ nameID. Pour plus d'informations, voir la documentation du [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 Si vous avez des sections dans vos fichiers .rc existants qui répondent à ces conditions, vous devez placer les sections dans un ou plusieurs fichiers .rc distincts et les incluent dans votre projet en utilisant le [boîte de dialogue Include des ressources](../windows/resource-includes-dialog-box.md). Le *nom_projet*fichier .rc2 créé dans le sous-répertoire \res d’un nouveau projet est utilisé à cet effet.  
  
### <a name="to-include-resources-in-your-project-at-compile-time"></a>Pour inclure des ressources dans votre projet au moment de la compilation  
  
1.  Placez les ressources dans un fichier de script de ressources portant un nom de fichier unique. N’utilisez pas *nom_projet*.rc, car il s’agit du nom de fichier utilisé pour le fichier de script de ressources principal.  
  
2.  Cliquez sur le fichier .rc (dans [affichage des ressources](../windows/resource-view-window.md)) et choisissez **Include des ressources** dans le menu contextuel.  
  
3.  Dans le **directives de compilation** zone, ajoutez le [#include](../preprocessor/hash-include-directive-c-cpp.md) directive de compilateur pour inclure le fichier de ressources dans le fichier de ressources principal dans l’environnement de développement.  
  
     Les ressources des fichiers inclus de cette façon sont intégrées à votre fichier exécutable au moment de la compilation. Elles ne sont pas directement modifiables quand vous travaillez sur le fichier .rc principal de votre projet. Vous devez ouvrir les fichiers .rc inclus séparément. Les fichiers inclus mais dépourvus d’extension .rc ne sont pas modifiables par les éditeurs de ressources.  
  
## <a name="requirements"></a>Configuration requise  
  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers de ressources](../windows/resource-files-visual-studio.md)   
 [Éditeurs de ressources](../windows/resource-editors.md)