---
title: Directives de préprocesseur | Documents Microsoft
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5621c1a338ea6870d15dca65c303d4ac2bf8c7a
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122593"
---
# <a name="preprocessor-directives"></a>Directives de préprocesseur

Directives de préprocesseur, telles que `#define` et **#ifdef**, sont généralement utilisées pour rendre les programmes sources faciles à modifier et à compiler dans différents environnements d’exécution. Les directives contenues dans le fichier source indiquent au préprocesseur d'exécuter des actions spécifiques. Par exemple, le préprocesseur peut remplacer des jetons dans le texte, insérer le contenu d'autres fichiers dans le fichier source ou supprimer la compilation d'une partie du fichier en supprimant des sections de texte. Les lignes de préprocesseur sont reconnues et exécutées avant l'expansion macro. Par conséquent, si une macro se développe en quelque chose qui ressemble à une commande de préprocesseur, cette commande n’est pas reconnue par le préprocesseur.

Les déclarations de préprocesseur utilisent le même jeu de caractères que les instructions de fichier source, sauf que les séquences d'échappement ne sont pas prises en charge. Le jeu de caractères utilisé dans les instructions de préprocesseur est identique à la [jeu de caractères d’exécution](http://msdn.microsoft.com/en-us/a7901c61-524d-47c6-beb6-d9dacc2e72ed). Le préprocesseur reconnaît aussi les valeurs de caractères négatives.

Le préprocesseur reconnaît les directives suivantes :

|||||
|-|-|-|-|
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||

Le signe dièse (**#**) doit être le premier caractère d’un espace blanc sur la ligne contenant la directive ; les espaces blancs peuvent apparaître entre le signe dièse et la première lettre de la directive. Certaines directives incluent des arguments ou des valeurs. Tout texte qui suit une directive (sauf un argument ou une valeur qui fait partie de la directive) doit être précédé du délimiteur de commentaire sur une ligne (**//**) ou compris entre des délimiteurs de commentaire ( __/ \*\*/__).   Les lignes contenant des directives de préprocesseur peuvent être poursuivies en faisant immédiatement précéder le marqueur de fin de ligne par une barre oblique inverse (**\\**).

Les directives de préprocesseur peuvent apparaître n'importe où dans un fichier source, mais elles s'appliquent uniquement au reste du fichier source.

## <a name="see-also"></a>Voir aussi

[Opérateurs de préprocesseur](../preprocessor/preprocessor-operators.md)  
[Macros prédéfinies](../preprocessor/predefined-macros.md)  
[Informations de référence sur le préprocesseur C/C++](../preprocessor/c-cpp-preprocessor-reference.md)  
