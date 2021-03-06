---
title: -Zp (alignement des membres de la structure) | Documents Microsoft
ms.custom: ''
ms.date: 04/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1666da40f748d18c762eae19595692addcdbf78a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380860"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Alignement des membres de la structure)

Contrôle la façon dont les membres d’une structure sont compressés en mémoire et spécifie la même compression pour toutes les structures dans un module.

## <a name="syntax"></a>Syntaxe

> **/Zp**[**1**|**2**|**4**|**8** | **16**]

## <a name="remarks"></a>Notes

Lorsque vous spécifiez la **/Zp**_n_ option, chaque membre de structure après le premier est enregistré sur la taille du type du membre ou *n*-limites d’octets (où *n* est 1, 2, 4, 8 ou 16), plus petite étant retenue.

Les valeurs de livraison disponibles sont décrites dans le tableau suivant :

|/Zp argument|Effet|
|-|-|
|1|Compresse les structures sur des limites de 1 octet. Identique à **/Zp**.|
|2|Compresse les structures sur des limites de 2 octets.|
|4|Compresse les structures sur des limites de 4 octets.|
|8|Compresse les structures sur des limites de 8 octets (par défaut).|
|16| Compresse les structures sur des limites de 16 octets.|

Vous ne devez pas utiliser cette option sauf si vous avez des exigences d’alignement spécifique.

> [!WARNING]  
> Supposons que les en-têtes de C++ dans le Kit de développement logiciel Windows **/Zp8** de livraison. Mémoire peuvent être endommagées si le **/Zp** paramètre est modifié lors de l’utilisation des en-têtes du Kit de développement logiciel Windows.

Vous pouvez également utiliser [pack](../../preprocessor/pack.md) à la compression de structure de contrôle. Pour plus d'informations sur l'alignement, consultez :

- [align](../../cpp/align-cpp.md)

- [__alignof, opérateur](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [Exemples d’alignement de Structure](../../build/examples-of-structure-alignment.md) (x64 spécifique)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio

1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).

1. Sélectionnez le **C/C++** > **génération de Code** page de propriétés.

1. Modifier la **alignement des membres de Struct** propriété.

### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation

-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>Voir aussi

- [Options du compilateur](../../build/reference/compiler-options.md)   
- [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)
