---
title: ConvertStringToBSTR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- ConvertStringToBSTR
dev_langs:
- C++
helpviewer_keywords:
- ConvertStringToBSTR function
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c579437ef0d5bd786b7066756b8e0bac4fa59e4a
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408500"
---
# <a name="convertstringtobstr"></a>ConvertStringToBSTR
**Section spécifique à Microsoft**  
  
 Convertit un `char *` valeur à un `BSTR`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
BSTR __stdcall ConvertStringToBSTR(const char* pSrc)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *pSrc*  
 A `char *` variable.  
  
## <a name="example"></a>Exemple  
  
```cpp 
// ConvertStringToBSTR.cpp  
#include <comutil.h>  
#include <stdio.h>  
  
#pragma comment(lib, "comsuppw.lib")  
#pragma comment(lib, "kernel32.lib")  
  
int main() {  
   char* lpszText = "Test";  
   printf_s("char * text: %s\n", lpszText);  
  
   BSTR bstrText = _com_util::ConvertStringToBSTR(lpszText);  
   wprintf_s(L"BSTR text: %s\n", bstrText);  
  
   SysFreeString(bstrText);  
}  
```  
  
```Output  
char * text: Test  
BSTR text: Test  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<comutil.h >  
  
 **Lib :** comsuppw.lib ou comsuppwd.lib (voir [/Zc : wchar_t (wchar_t est un Type natif)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) pour plus d’informations)  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions globales COM du compilateur](../cpp/compiler-com-global-functions.md)