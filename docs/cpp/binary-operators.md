---
title: Opérateurs binaires | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators [C++]
- operators [C++], binary
- binary operators [C++]
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b76250926ab89c14dfa26f0df3bb5571c1dae10
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408814"
---
# <a name="binary-operators"></a>Opérateurs binaires

Le tableau suivant affiche une liste des opérateurs qui peuvent être surchargés.

## <a name="redefinable-binary-operators"></a>Opérateurs binaires redéfinissables

|Opérateur|Name|
|--------------|----------|
|**,**|Virgule|
|**\!=**|Inégalité|
|**%**|Modulo|
|**%=**|Modulo/assignation|
|**&**|Opération de bits AND|
|**&&**|AND logique|
|**&=**|Opération de bits AND/assignation|
|**&#42;**|Multiplication|
|**&#42;=**|Multiplication/assignation|
|**+**|Addition|
|**+=**|Addition/assignation|
|**-**|Soustraction|
|**-=**|Soustraction/assignation|
|**->**|Sélection de membres|
|**->&#42;**|Sélection de pointeur de membre|
|**/**|Division|
|**/=**|Division/assignation|
|**<**|Inférieur à|
|**<<**|Décalage vers la gauche|
|**<<=**|Décalage vers la gauche/assignation|
|**<=**|Inférieur ou égal à|
|**=**|Attribution|
|**==**|Égalité|
|**>**|Supérieur à|
|**>=**|Supérieur ou égal à|
|**>>**|Décalage vers la droite|
|**>>=**|Décalage vers la droite/assignation|
|**^**|OR exclusive|
|**^=**|OR exclusive/assignation|
|**&#124;**|Opération de bits OR inclusive|
|**&#124;=**|OR inclusive au niveau du bit/assignation|
|**&#124;&#124;**|OR logique|

Pour déclarer une fonction d'opérateur binaire en tant que membre non statique, vous devez la déclarer comme suit :

> *RET-type* **opérateur** *op* **(** *arg* **)**

où *ret-type* est le type de retour, *op* est un des opérateurs répertoriés dans le tableau précédent, et *arg* est un argument de n’importe quel type.

Pour déclarer une fonction d'opérateur binaire en tant que fonction globale, vous devez la déclarer comme suit :

> *RET-type* **opérateur** *op* **(** _arg1_**,** _arg2_ **)**

où *ret-type* et *op* sont celles décrites pour les fonctions d’opérateur de membre et *arg1* et *arg2* sont des arguments. Au moins un des arguments doit être de type classe.

> [!NOTE]
> Il n’existe aucune restriction sur les types de retour des opérateurs binaires. En revanche, la plupart des opérateurs binaires définis par l’utilisateur retournent un type de classe ou une référence à un type de classe.

## <a name="see-also"></a>Voir aussi
 [Surcharge d'opérateur](../cpp/operator-overloading.md)