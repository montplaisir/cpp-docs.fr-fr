---
title: _InterlockedXor, fonctions intrinsèques | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedXor_nf
- _InterlockedXor_np
- _InterlockedXor64_HLERelease
- _InterlockedXor8_acq
- _InterlockedXor64_acq
- _InterlockedXor64_rel
- _InterlockedXor64_nf
- _InterlockedXor_acq
- _InterlockedXor16
- _InterlockedXor64_np
- _InterlockedXor64
- _InterlockedXor_HLEAcquire
- _InterlockedXor_HLERelease
- _InterlockedXor_cpp
- _InterlockedXor16_rel
- _InterlockedXor8_rel
- _InterlockedXor8
- _InterlockedXor64_HLEAcquire
- _InterlockedXor16_nf
- _InterlockedXor16_acq
- _InterlockedXor16_np
- _InterlockedXor8_fn
- _InterlockedXor8_np
- _InterlockedXor64_cpp
- _InterlockedXor_rel
- _InterlockedXor
dev_langs:
- C++
helpviewer_keywords:
- InterlockedXor intrinsic
- _InterlockedXor64 intrinsic
- InterlockedXor64 intrinsic
- _InterlockedXor intrinsic
ms.assetid: faef1796-cb5a-4430-b1e2-9d5eaf9b4a91
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7dea8e222660825824c8dc02405832da4395b69f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334121"
---
# <a name="interlockedxor-intrinsic-functions"></a>_InterlockedXor, fonctions intrinsèques
**Section spécifique à Microsoft**  
  
 Effectuer une opération ou exclusif (XOR) atomique au niveau du bit sur une variable partagée par plusieurs threads.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
long _InterlockedXor(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_acq(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_HLEAcquire(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_HLERelease(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_nf(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_np(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedXor_rel(  
   long volatile * Value,  
   long Mask  
);  
char _InterlockedXor8(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedXor8_acq(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedXor8_nf(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedXor8_np(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedXor8_rel(  
   char volatile * Value,  
   char Mask  
);  
short _InterlockedXor16(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedXor16_acq(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedXor16_nf (  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedXor16_np (  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedXor16_rel(  
   short volatile * Value,  
   short Mask  
);  
__int64 _InterlockedXor64(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedXor64_acq(  
   __int64 volatile * Value,  
   __int64 Mask  
);   
__int64 _InterlockedXor64_HLEAcquire(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedXor64_HLERelease(  
   __int64 volatile * Value,  
   __int64 Mask  
);   
__int64 _InterlockedXor64_nf(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedXor64_np(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedXor64_rel(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in, out] `Value`  
 Pointeur vers le premier opérande, à remplacer par le résultat.  
  
 [in] `Mask`  
 Deuxième opérande.  
  
## <a name="return-value"></a>Valeur de retour  
 Valeur d’origine du premier opérande.  
  
## <a name="requirements"></a>Spécifications  
  
|Intrinsèque|Architecture|En-tête|  
|---------------|------------------|------------|  
|`_InterlockedXor`, `_InterlockedXor8`, `_InterlockedXor16`, `_InterlockedXor64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
|`_InterlockedXor_acq`, `_InterlockedXor_nf`, `_InterlockedXor_rel`, `_InterlockedXor8_acq`, `_InterlockedXor8_nf`, `_InterlockedXor8_rel`, `_InterlockedXor16_acq`, `_InterlockedXor16_nf`, `_InterlockedXor16_rel`, `_InterlockedXor64_acq`, `_InterlockedXor64_nf`, `_InterlockedXor64_rel`,|ARM|\<intrin.h>|  
|`_InterlockedXor_np`, `_InterlockedXor8_np`, `_InterlockedXor16_np`, `_InterlockedXor64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
|`_InterlockedXor_HLEAcquire`, `_InterlockedXor_HLERelease`, `_InterlockedXor64_HLEAcquire`, `_InterlockedXor64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h>|  
  
## <a name="remarks"></a>Notes  
 Le nombre dans le nom de chaque fonction spécifie la taille en bits des arguments.  
  
 Sur les plateformes ARM, utilisez les fonctions intrinsèques avec des suffixes `_acq` et `_rel` si vous devez acquérir et libérer des éléments de la sémantique, comme le début et la fin d'une section critique. Les fonctions intrinsèques ARM avec un suffixe `_nf` (pour « no fence », « pas de délimitation ») n'agissent pas comme une barrière mémoire.  
  
 Les fonctions intrinsèques avec un suffixe `_np` (pour « no prefetch », « pas de prérécupération ») empêchent l'insertion par le compilateur d'une possible opération de prérécupération.  
  
 Sur les plateformes Intel qui prennent en charge les instructions HLE (Hardware Lock Elision), les fonctions intrinsèques avec les suffixes `_HLEAcquire` et `_HLERelease` comprennent une indication pour le processeur qui peut accélérer les performances en éliminant une étape d'écriture de verrou dans le matériel. Si ces fonctions intrinsèques sont appelées sur des plateformes qui ne prennent pas en charge HLE, l'indication est ignorée.  
  
## <a name="example"></a>Exemple  
  
```  
// _InterLockedXor.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedXor)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedXor(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
```Output  
0xffff0000 0xffff00 0xff00ff00  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)