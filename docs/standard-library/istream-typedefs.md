---
title: '&lt;istream&gt;, typedefs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: bea06c9799783feafaff1f68f4019463e452a4f2
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958853"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt;, typedefs

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>  iostream

Un type `basic_iostream` spécialisé sur **char**.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Notes

Le type est un synonyme de la classe de modèle [basic_iostream](../standard-library/basic-iostream-class.md), spécialisé pour les éléments de type **char** ayant les caractéristiques par défaut.

## <a name="istream"></a>  istream

Un type `basic_istream` spécialisé sur **char**.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Notes

Le type est un synonyme de la classe de modèle [basic_istream](../standard-library/basic-istream-class.md), spécialisé pour les éléments de type **char** ayant les caractéristiques par défaut.

## <a name="wiostream"></a>  wiostream

Un type `basic_iostream` spécialisé sur **wchar_t**.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Notes

Le type est un synonyme de la classe de modèle [basic_iostream](../standard-library/basic-iostream-class.md), spécialisé pour les éléments de type **wchar_t** ayant les caractéristiques par défaut.

## <a name="wistream"></a>  wistream

Un type `basic_istream` spécialisé sur **wchar_t**.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Notes

Le type est un synonyme de la classe de modèle [basic_istream](../standard-library/basic-istream-class.md), spécialisé pour les éléments de type **wchar_t** ayant les caractéristiques par défaut.

## <a name="see-also"></a>Voir aussi

[\<istream>](../standard-library/istream.md)<br/>
