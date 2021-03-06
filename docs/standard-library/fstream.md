---
title: '&lt;fstream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <fstream>
dev_langs:
- C++
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b716248c6fe9d0734cd580800c9254cf01f2a17
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962872"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

Définit plusieurs classes qui prennent en charge les opérations iostreams sur des séquences stockées dans des fichiers externes.

## <a name="syntax"></a>Syntaxe

```cpp
#include <fstream>

```

### <a name="typedefs"></a>Typedef

|Nom de type|Description|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Un type `basic_filebuf` spécialisé sur **char** paramètres de modèle.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Un type `basic_fstream` spécialisé sur **char** paramètres de modèle.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Un type `basic_ifstream` spécialisé sur **char** paramètres de modèle.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Un type `basic_ofstream` spécialisé sur **char** paramètres de modèle.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Un type `basic_fstream` spécialisé sur **wchar_t** paramètres de modèle.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Un type `basic_ifstream` spécialisé sur **wchar_t** paramètres de modèle.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Un type `basic_ofstream` spécialisé sur **wchar_t** paramètres de modèle.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Un type `basic_filebuf` spécialisé sur **wchar_t** paramètres de modèle.|

### <a name="classes"></a>Classes

|Classe|Description|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|La classe de modèle décrit une mémoire tampon de flux qui contrôle la transmission d'éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`, vers et à partir d'une séquence d'éléments stockés dans un fichier externe.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|La classe de modèle décrit un objet qui contrôle l’insertion et l’extraction d’éléments et objets encodés à l’aide d’une mémoire tampon de flux de classe [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**,  **TR**>, avec des éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|La classe de modèle décrit un objet qui contrôle l’extraction d’éléments et objets encodés à partir d’une mémoire tampon de flux de classe [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, avec des éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|La classe de modèle décrit un objet qui contrôle l’insertion d’éléments et objets encodés dans une mémoire tampon de flux de classe [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, avec des éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`.|

## <a name="see-also"></a>Voir aussi

[Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)<br/>
[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream, programmation](../standard-library/iostream-programming.md)<br/>
[iostreams, conventions](../standard-library/iostreams-conventions.md)<br/>
