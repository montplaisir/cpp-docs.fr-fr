---
title: __debugbreak | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __debugbreak_cpp
- __debugbreak
dev_langs:
- C++
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a3dcead3129c87b2d02f8822019af763c0fe8b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340175"
---
# <a name="debugbreak"></a>__debugbreak
**Section spécifique à Microsoft**  
  
 Génère un point d'arrêt dans votre code, où l'utilisateur sera invité à exécuter le débogueur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __debugbreak();  
```  
  
## <a name="requirements"></a>Spécifications  
  
|Intrinsèque|Architecture|Header|  
|---------------|------------------|------------|  
|`__debugbreak`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
  
## <a name="remarks"></a>Notes  
 Le `__debugbreak` compilateur intrinsèque, comme dans [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), est une manière Win32 portable pour provoquer un point d’arrêt.  
  
> [!NOTE]
>  Lors de la compilation avec **/CLR**, une fonction contenant `__debugbreak` sera compilé en langage MSIL. `asm int 3` entraîne la compilation d'une fonction en code natif. Pour plus d’informations, consultez [__asm](../assembler/inline/asm.md).  
  
 Par exemple :  
  
```  
main() {  
   __debugbreak();  
}  
```  
  
 est similaire à :  
  
```  
main() {  
   __asm {  
      int 3  
   }  
}  
```  
  
 sur un ordinateur x86.  
  
 Cette routine est disponible uniquement en tant qu'intrinsèque.  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md)   
 [Mots clés](../cpp/keywords-cpp.md)