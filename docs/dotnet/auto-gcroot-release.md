---
title: auto_gcroot::Release | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot::release
- auto_gcroot::release
- auto_gcroot.release
- msclr.auto_gcroot.release
dev_langs:
- C++
helpviewer_keywords:
- release method
ms.assetid: 40b253f0-154e-4d79-80a4-ff13199c3ff0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 63e3a934cd16c1a17a866df7186af7232eb1f152
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101784"
---
# <a name="autogcrootrelease"></a>auto_gcroot::release
Libère l’objet à partir de `auto_gcroot` management.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_element_type release();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 L’objet libéré.  
  
## <a name="example"></a>Exemple  
  
```  
// msl_auto_gcroot_release.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "ClassA constructor: " + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "ClassA destructor: " + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );     
   }  
};  
  
int main()  
{  
   ClassA^ a;  
  
   // create a new scope:  
   {  
      auto_gcroot<ClassA^> agc1 = gcnew ClassA( "first" );  
      auto_gcroot<ClassA^> agc2 = gcnew ClassA( "second" );  
      a = agc1.release();  
   }  
   // agc1 and agc2 go out of scope here  
  
   a->PrintHello();  
  
   Console::WriteLine( "done" );  
}  
```  
  
```Output  
ClassA constructor: first  
ClassA constructor: second  
ClassA destructor: second  
Hello from first A!  
done  
```  
  
## <a name="requirements"></a>Spécifications  
 **Fichier d’en-tête** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Voir aussi  
 [auto_gcroot, membres](../dotnet/auto-gcroot-members.md)   
 [auto_gcroot::~auto_gcroot](../dotnet/auto-gcroot-tilde-auto-gcroot.md)