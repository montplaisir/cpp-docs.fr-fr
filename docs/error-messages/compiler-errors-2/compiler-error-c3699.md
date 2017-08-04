---
title: "Erreur du compilateur C3699 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3699"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3699"
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3699
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : impossible d'utiliser cette indirection sur le type 'type'  
  
 Une tentative d'utilisation de l'indirection qui n'est pas autorisée sur `type` a été effectuée.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3699 :  
  
```  
// C3699.cpp  
// compile with: /clr /c  
using namespace System;  
int main() {  
   String * s;   // C3699  
   // try the following line instead  
   // String ^ s2;  
}  
```  
  
## Exemple  
 Une propriété triviale ne peut pas posséder de type référence.  Pour plus d'informations, consultez [property](../../windows/property-cpp-component-extensions.md).  L'exemple suivant génère l'erreur C3699 :  
  
```  
// C3699_b.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String % x;   // C3699  
   property System::String ^ y;   // OK  
};  
```  
  
## Exemple  
 L'équivalent d'une syntaxe « pointeur vers pointeur » est un handle vers une référence de suivi.  L'exemple suivant génère l'erreur C3699 :  
  
```  
// C3699_c.cpp  
// compile with: /clr /c  
using namespace System;  
void Test(String ^^ i);   // C3699  
void Test2(String ^% i);  
```