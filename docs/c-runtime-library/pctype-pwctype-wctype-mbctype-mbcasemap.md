---
title: _pctype, _pwctype, _wctype, _mbctype, _mbcasemap | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- pwctype
- pctype
- mbctype
- mbcasemap
- _mbcasemap
- _mbctype
- _pctype
- _wctype
- _pcwtype
dev_langs:
- C++
helpviewer_keywords:
- _wctype function
- _pwctype function
- _pctype function
- _mbctype function
- wctype function
- pwctype function
- pctype function
- mbcasemap function
- mbctype function
- _mbcasemap function
ms.assetid: 7f5e1107-c43b-4b9b-b387-781e6d2373cb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a98d570d0b43a33395a04b657b4dc2e97f9ba8e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391559"
---
# <a name="pctype-pwctype-wctype-mbctype-mbcasemap"></a>_pctype, _pwctype, _wctype, _mbctype, _mbcasemap
Ces variables globales contiennent des informations utilisées par les fonctions de classification des caractères. Elles sont réservées exclusivement à un usage interne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
extern const unsigned short *_pctype;  
extern const wctype_t *_pwctype;  
extern const unsigned short _wctype[];  
extern unsigned char _mbctype[];  
extern unsigned char _mbcasemap[];  
```  
  
## <a name="remarks"></a>Notes  
 Les informations contenues dans `_pctype`, `_pwctype` et `_wctype` sont utilisées en interne par les fonctions [isupper, _isupper_l, iswupper, _iswupper_l](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md), [islower, iswlower, _islower_l, _iswlower_l](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md), [isdigit, iswdigit, _isdigit_l, _iswdigit_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md), [isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md), [isspace, iswspace, _isspace_l, _iswspace_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md), [isalnum, iswalnum, _isalnum_l, _iswalnum_l](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md), [ispunct, iswpunct, _ispunct_l, _iswpunct_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md), [isgraph, iswgraph, _isgraph_l, _iswgraph_l](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md) et [iscntrl, iswcntrl, _iscntrl_l , _iswcntrl_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md), ainsi que les fonctions [toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md) et [tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md). Vous devez utiliser ces fonctions au lieu d’accéder à ces variables globales.  
  
 Les informations contenues dans `_mbctype` et `_mbcasemap` sont utilisées en interne par les fonctions [_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md), [_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md), [_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md), [_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md), [_ismbbalpha](reference/ismbbalpha-ismbbalpha-l.md), [_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md), [_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md), [_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md), [_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md), [_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md), [_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md), [_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md) et [_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md). Utilisez ces fonctions au lieu d’accéder aux variables globales.  
  
## <a name="requirements"></a>Configuration requise  
 Pas d’usage public.  
  
## <a name="see-also"></a>Voir aussi  
 [is, isw, routines](../c-runtime-library/is-isw-routines.md)   
 [__pctype_func](../c-runtime-library/pctype-func.md)