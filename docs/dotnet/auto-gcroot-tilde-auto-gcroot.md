---
title: 'auto_gcroot :: ~ auto_gcroot | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_gcroot::~auto_gcroot
- ~auto_gcroot
- auto_gcroot.~auto_gcroot
- msclr::auto_gcroot::~auto_gcroot
- msclr.auto_gcroot.~auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot::~auto_gcroot
ms.assetid: 3c970d43-0cb1-4b27-8bee-0394d91b4739
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f0e99c7e99e8c6c68996ceea4d4a8120f6e048ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102421"
---
# <a name="autogcrootautogcroot"></a>auto_gcroot::~auto_gcroot
Le `auto_gcroot` destructeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
~auto_gcroot();  
```  
  
## <a name="remarks"></a>Notes  
 Le destructeur également destruction de l’objet détenu.  
  
## <a name="example"></a>Exemple  
  
```  
// msl_auto_gcroot_dtor.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
public:  
   ClassA() { Console::WriteLine( "ClassA constructor" ); }  
   ~ClassA() { Console::WriteLine( "ClassA destructor" ); }  
};  
  
int main()  
{  
   // create a new scope for a:  
   {  
      auto_gcroot<ClassA^> a = gcnew ClassA;  
   }  
   // a goes out of scope here, invoking its destructor  
   // which in turns destructs the ClassA object.  
  
   Console::WriteLine( "done" );  
}  
```  
  
```Output  
ClassA constructor  
ClassA destructor  
done  
```  
  
## <a name="requirements"></a>Spécifications  
 **Fichier d’en-tête** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Voir aussi  
 [auto_gcroot, membres](../dotnet/auto-gcroot-members.md)   
 [auto_gcroot::Release](../dotnet/auto-gcroot-release.md)   
 [auto_gcroot::auto_gcroot](../dotnet/auto-gcroot-auto-gcroot.md)