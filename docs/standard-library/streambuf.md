---
title: '&lt;streambuf&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <streambuf>
dev_langs:
- C++
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 138ec5bb28e108751a7d4b03651826db38c098fa
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026930"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

Incluez l’en-tête standard iostreams \<streambuf> pour définir la classe de modèle [basic_streambuf](../standard-library/basic-streambuf-class.md), qui est essentielle au fonctionnement des classes iostreams. Cet en-tête est généralement inclus pour vous par l'un des autres en-tête iostream ; vous devez rarement l'inclure directement.

## <a name="syntax"></a>Syntaxe

```cpp
#include <streambuf>

```

### <a name="typedefs"></a>Typedef

|Nom de type|Description|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Une spécialisation de `basic_streambuf` qui utilise **char** en tant que les paramètres du modèle.|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|Une spécialisation de `basic_streambuf` qui utilise **wchar_t** en tant que les paramètres du modèle.|

### <a name="classes"></a>Classes

|Classe|Description|
|-|-|
|[basic_streambuf, classe](http://msdn.microsoft.com/d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|La classe de modèle décrit une classe de base abstraite pour dériver une mémoire tampon de flux qui contrôle la transmission des éléments depuis et vers une représentation spécifique d'un flux.|

## <a name="see-also"></a>Voir aussi

[Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)<br/>
[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream, programmation](../standard-library/iostream-programming.md)<br/>
[iostreams, conventions](../standard-library/iostreams-conventions.md)<br/>
