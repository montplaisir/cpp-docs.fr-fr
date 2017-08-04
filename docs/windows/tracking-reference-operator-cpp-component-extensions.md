---
title: "Tracking Reference Operator (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "%"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tracking references"
  - "% tracking reference [C++]"
ms.assetid: 142a7269-ab69-4b54-a6d7-833bef06228f
caps.latest.revision: 31
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Tracking Reference Operator (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une *référence de suivi* \(`%`\) se comporte comme une référence C\+\+ ordinaire \(`&`\), sauf que lorsqu'un objet est assigné à une référence de suivi, le nombre de références de l'objet est incrémenté.  
  
## Toutes les plateformes  
 Une référence de suivi possède les caractéristiques suivantes.  
  
-   L'assignation d'un objet à une référence de suivi provoque l'incrémentation du nombre de références de l'objet.  
  
-   Une référence native \(&\) est le résultat obtenu lorsque vous déréférencez un \*.  Une référence de suivi \(%\) est le résultat obtenu lorsque vous déréférencez un ^.  Tant que vous avez une référence % à un objet, l'objet reste actif en mémoire.  
  
-   L'opérateur d'accès aux membres point \(`.`\) est utilisé pour accéder à un membre de l'objet.  
  
-   Les références de suivi sont valides pour les types valeur et les handles \(par exemple `String^`\).  
  
-   Une valeur null ou `nullptr` ne peut pas être assignée à une référence de suivi.  Une référence de suivi peut être réassignée à un autre objet valide autant de fois que nécessaire.  
  
-   Une référence de suivi ne peut pas être utilisée comme opérateur de prise d'adresse unaire.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Une référence de suivi se comporte comme une référence C\+\+ standard, sauf qu'un % inclus un comptage des références.  L'extrait de code suivant montre comment effectuer une conversion entre les types % et ^ :  
  
```  
Foo^ spFoo = ref new Foo();  
Foo% srFoo = *spFoo;  
Foo^ spFoo2 = %srFoo;  
```  
  
 L'exemple suivant montre comment passer un ^ en fonction qui accepte un %.  
  
```  
  
ref class Foo sealed {};  
  
    // internal or private  
    void UseFooHelper(Foo% f)  
    {  
        auto x = %f;  
    }  
  
    // public method on ABI boundary  
    void UseFoo(Foo^ f)  
    {  
        if (f != nullptr) { UseFooHelper(*f); }  
    }  
  
```  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 En C\+\+\/CLI, vous pouvez utiliser une référence de suivi à un handle quand vous établissez une liaison à un objet de type CLR sur le tas récupéré par le garbage collector.  
  
 Dans le CLR, la valeur d'une variable de référence de suivi est mise à jour automatiquement chaque fois que le garbage collector déplace l'objet référencé.  
  
 Une référence de suivi peut être déclarée uniquement sur la pile.  Une référence de suivi ne peut pas être membre d'une classe.  
  
 Il est impossible d'avoir une référence C\+\+ native à un objet sur le tas récupéré par le garbage collector.  
  
 Pour plus d'informations sur les références de suivi en C\+\+\/CLI, consultez :  
  
-   [Comment : utiliser des références de suivi dans C\+\+\/CLI](../dotnet/how-to-use-tracking-references-in-cpp-cli.md)  
  
-   [Comment : utiliser des références de suivi et des types de valeur](../misc/how-to-use-tracking-references-and-value-types.md)  
  
-   [Comment : utiliser des références de suivi et des pointeurs intérieurs](../misc/how-to-use-tracking-references-and-interior-pointers.md)  
  
-   [Comment : écrire des fonctions de modèle qui prennent des paramètres de référence, de valeur ou natifs](../misc/how-to-write-template-functions-that-take-native-value-or-reference-parameters.md)  
  
### Exemples  
 **Exemple**  
  
 L'exemple suivant pour C\+\+\/CLI montre comment utiliser une référence de suivi avec des types managés et natifs.  
  
```  
// tracking_reference_1.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   int i;  
};  
  
value struct MyStruct {  
   int k;  
};  
  
int main() {  
   MyClass ^ x = ref new MyClass;  
   MyClass ^% y = x;   // tracking reference handle to reference object   
  
   int %ti = x->i;   // tracking reference to member of reference type  
  
   int j = 0;  
   int %tj = j;   // tracking reference to object on the stack  
  
   int * pi = new int[2];  
   int % ti2 = pi[0];   // tracking reference to object on native heap  
  
   int *% tpi = pi;   // tracking reference to native pointer  
  
   MyStruct ^ x2 = ref new MyStruct;  
   MyStruct ^% y2 = x2;   // tracking reference to value object  
  
   MyStruct z;  
   int %tk = z.k;   // tracking reference to member of value type  
  
   delete[] pi;  
}  
  
```  
  
 **Exemple**  
  
 L'exemple suivant pour C\+\+\/CLI montre comment lier une référence de suivi à un tableau.  
  
```  
// tracking_reference_2.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   array<int> ^ a = ref new array< Int32 >(5);  
   a[0] = 21;  
   Console::WriteLine(a[0]);  
   array<int> ^% arr = a;  
   arr[0] = 222;  
   Console::WriteLine(a[0]);  
}  
```  
  
 **Sortie**  
  
  **21**  
 **222**