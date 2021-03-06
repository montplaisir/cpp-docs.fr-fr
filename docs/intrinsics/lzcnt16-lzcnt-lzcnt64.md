---
title: __lzcnt16, __lzcnt, __lzcnt64 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
dev_langs:
- C++
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86e04182cf673674e1f1ba8c073b624760bc4809
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332791"
---
# <a name="lzcnt16-lzcnt-lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64
**Section spécifique à Microsoft**  
  
 Le nombre de début nombre des zéros dans 16-, 32 ou 64 bits.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned short __lzcnt16(  
   unsigned short value  
);  
unsigned int __lzcnt(  
   unsigned int value  
);  
unsigned __int64 __lzcnt64(  
   unsigned __int64 value  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `value`  
 Les 16, 32 ou entier non signé 64 bits pour rechercher des zéros non significatifs.  
  
## <a name="return-value"></a>Valeur de retour  
 Le nombre de zéros d’en-tête dans le `value` paramètre. Si `value` est égal à zéro, la valeur de retour est la taille de l’opérande d’entrée (16, 32 ou 64). Si le bit de poids de `value` est 1, la valeur de retour est égale à zéro.  
  
## <a name="requirements"></a>Spécifications  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__lzcnt16`|AMD : Manipulation de Bit avancées (ABM)<br /><br /> Intel : Haswell|  
|`__lzcnt`|AMD : Manipulation de Bit avancées (ABM)<br /><br /> Intel : Haswell|  
|`__lzcnt64`|AMD : Avancée de Manipulation de bits (ABM) en mode 64 bits.<br /><br /> Intel : Haswell|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
## <a name="remarks"></a>Notes  
 Chacune de ces fonctions intrinsèques génère le `lzcnt` instruction.  La taille de la valeur que la `lzcnt` instruction retourne une valeur est identique à la taille de son argument.  En mode 32 bits ne des aucun 64 bits registres à caractère général, par conséquent, ne 64 bits `lzcnt`.  
  
 Pour déterminer la prise en charge matérielle pour le `lzcnt` appel le `__cpuid` intrinsèque avec `InfoType=0x80000001` et vérifiez le bit 5 de `CPUInfo[2] (ECX)`. Ce bit sera égale à 1 si l’instruction est prise en charge et 0 dans le cas contraire. Si vous exécutez le code qui utilise cet intrinsèque sur du matériel qui ne prend pas en charge la `lzcnt` instruction, les résultats sont imprévisibles.  
  
 Sur les processeurs Intel ne prenant pas en charge la `lzcnt` instruction, l’instruction octet d’encodage est exécutée en tant que `bsr` (bit analyse inverse). Si la portabilité du code est un critère important, envisagez d’utiliser le `_BitScanReverse` intrinsèque à la place. Pour plus d’informations, consultez [_BitScanReverse, _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).  
  
## <a name="example"></a>Exemple  
  
```  
// Compile this test with: /EHsc  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __lzcnt16(us[i]);  
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __lzcnt(ui[i]);  
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
```Output  
__lzcnt16(0x0) = 16  
__lzcnt16(0xff) = 8  
__lzcnt16(0xffff) = 0  
__lzcnt(0x0) = 32  
__lzcnt(0xff) = 24  
__lzcnt(0xffff) = 16  
__lzcnt(0xffffffff) = 0  
```  
  
**FIN de la section spécifique à Microsoft**  
 Des parties de ce contenu sont Copyright 2007 par Advanced Micro Devices, Inc. Tous droits réservés. Reproduit avec l’autorisation d’Advanced Micro Devices, Inc.  
  
## <a name="see-also"></a>Voir aussi  
 [compilateur, fonctions intrinsèques](../intrinsics/compiler-intrinsics.md)
