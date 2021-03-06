---
title: pin_ptr (C + c++ / CLI) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- pin_ptr_cpp
- stdcli::language::pin_ptr
- pin_ptr
dev_langs:
- C++
helpviewer_keywords:
- pinning pointers
- pin_ptr keyword [C++]
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: afc99a352e0bde7918cab460293ff23061377551
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880164"
---
# <a name="pinptr-ccli"></a>pin_ptr (C++/CLI)
Déclare un *pointeur épingle*, qui est utilisé uniquement avec le common language runtime.  
  
## <a name="all-runtimes"></a>Tous les runtimes  
 (Aucune remarque pour cette fonctionnalité de langage ne s’applique à tous les runtimes.)  
  
## <a name="windows-runtime"></a>Windows Runtime  
 (Cette fonctionnalité de langage n'est pas pris en charge dans le Windows Runtime.)  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 A *pointeur épingle* est un pointeur intérieur qui empêche l’objet pointé de le déplacer sur le tas de garbage collection. Autrement dit, la valeur d’un pointeur épingle n’est pas modifiée par le common language runtime. Cela est nécessaire lorsque vous passez l’adresse d’une classe managée à une fonction non managée, afin que l’adresse ne changera pas de manière inattendue lors de la résolution de l’appel de fonction non managée.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;  
```  
  
### <a name="parameters"></a>Paramètres  
 *cv_qualifier*  
 `const` ou `volatile` qualificateurs. Par défaut, un pointeur épingle est `volatile`. Elle est redondante mais pas une erreur pour déclarer un pointeur épingle `volatile`.  
  
 *type*  
 Type d'élément `initializer`.  
  
 *var*  
 Le nom de la `pin_ptr` variable.  
  
 *initializer*  
 Un membre d’un type référence, un élément d’un tableau managé ou tout autre objet que vous pouvez affecter à un pointeur natif.  
  
### <a name="remarks"></a>Notes  
 A `pin_ptr` représente un sur-ensemble de la fonctionnalité d’un pointeur natif. Par conséquent, tout ce qui peut être assigné à un pointeur natif peut également être affecté à un `pin_ptr`. Un pointeur intérieur est autorisé à effectuer le même jeu d’opérations que les pointeurs natifs, y compris la comparaison et l’opération arithmétique de pointeur.  
  
 Un objet ou le sous-objet d’une classe managée peut être figée, auquel cas le common language runtime elle ne sera pas déplacée pendant le garbage collection. Son usage principal est de passer un pointeur vers des données managées comme paramètre réel d’un appel de fonction non managée. Pendant un cycle de collecte, le runtime inspecte les métadonnées créées pour le pointeur épingle et ne sera pas déplacée de l’élément vers laquelle il pointe.  
  
 L’épinglage d’un objet épingle également ses champs de valeur ; champs de primitive ou valeur de type. Toutefois, les champs sont déclarés par le handle de suivi (`%`) ne sont pas épinglés.  
  
 Épingler un sous-objet défini dans un objet managé a pour effet d’épinglage de l’objet entier.  
  
 Si le pointeur épingle est réaffecté pour pointer vers une nouvelle valeur, l’instance précédente vers lequel pointé est n’est plus considéré comme épinglé.  
  
 Un objet est épinglé uniquement pendant qu’un `pin_ptr` pointe vers elle. L’objet n’est plus épinglé lorsque son pointeur épingle est hors de portée ou est défini sur [nullptr](../windows/nullptr-cpp-component-extensions.md). Après le `pin_ptr` sort de la portée, l’objet qui a été épinglé peut être déplacées dans le segment de mémoire par le garbage collector. Les pointeurs natifs toujours pointent vers l’objet ne seront pas mis à jour et Annuler faisant référence à un d’eux peut déclencher une exception irrécupérable.  
  
 Si aucun des pointeurs épingle ne pointent vers l’objet (tous les pointeurs épingles est hors de portée, ont été réaffectés pour pointer vers d’autres objets ou ont été assignés [nullptr](../windows/nullptr-cpp-component-extensions.md)), l’objet ne peut ne pas être épinglé.  
  
 Un pointeur épingle peut pointer vers une poignée de référence de type valeur ou le handle du type boxed, membre d’un type managé ou un élément d’un tableau managé. Il ne peut pas pointer vers un type référence.  
  
 Prise d’adresse d’un `pin_ptr` que pointe vers un objet natif entraîne un comportement non défini.  
  
 Pointeurs épingle peuvent uniquement être déclarés en tant que variables locales non statiques sur la pile.  
  
 Pointeurs épingle ne peut pas être utilisés en tant que :  
  
-   paramètres de fonction  
  
-   le type de retour d’une fonction  
  
-   un membre d’une classe  
  
-   type de cible d’une conversion.  
  
 `pin_ptr` est dans le `cli` espace de noms. Pour plus d’informations, consultez [plateforme, par défaut et espaces de noms cli](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Pour plus d’informations sur les pointeurs intérieurs, consultez [interior_ptr (C + c++ / CLI)](../windows/interior-ptr-cpp-cli.md).  
  
 Pour plus d’informations sur les pointeurs épingle, consultez [Comment : pointeurs de code confidentiel et tableaux](../windows/how-to-pin-pointers-and-arrays.md) et [Comment : déclarer des pointeurs épingle et les Types valeur](../windows/how-to-declare-pinning-pointers-and-value-types.md).  
  
### <a name="requirements"></a>Spécifications  
 Option du compilateur : **/clr**  
  
### <a name="examples"></a>Exemples  
 **Exemple**  
  
 L’exemple suivant utilise `pin_ptr` pour contraindre la position du premier élément d’un tableau.  
  
```  
// pin_ptr_1.cpp  
// compile with: /clr   
using namespace System;  
#define SIZE 10  
  
#pragma unmanaged  
// native function that initializes an array  
void native_function(int* p) {  
   for(int i = 0 ; i < 10 ; i++)  
    p[i] = i;  
}  
#pragma managed  
  
public ref class A {  
private:  
   array<int>^ arr;   // CLR integer array  
  
public:  
   A() {  
      arr = gcnew array<int>(SIZE);  
   }  
  
   void load() {  
   pin_ptr<int> p = &arr[0];   // pin pointer to first element in arr  
   int* np = p;   // pointer to the first element in arr  
   native_function(np);   // pass pointer to native function  
   }  
  
   int sum() {  
      int total = 0;  
      for (int i = 0 ; i < SIZE ; i++)  
         total += arr[i];  
      return total;  
   }  
};  
  
int main() {  
   A^ a = gcnew A;  
   a->load();   // initialize managed array using the native function  
   Console::WriteLine(a->sum());  
}  
```  
  
 **Sortie**  
  
```Output  
45  
```  
  
 **Exemple**  
  
 L’exemple suivant montre qu’un pointeur intérieur peut être converti en un pointeur épingle, et que le type de retour de l’opérateur d’adresse (`&`) est un pointeur intérieur lorsque l’opérande est sur le tas managé.  
  
```  
// pin_ptr_2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   G() : i(1) {}  
   int i;  
};  
  
ref struct H {  
   H() : j(2) {}  
   int j;  
};  
  
int main() {  
   G ^ g = gcnew G;   // g is a whole reference object pointer  
   H ^ h = gcnew H;  
  
   interior_ptr<int> l = &(g->i);   // l is interior pointer  
  
   pin_ptr<int> k = &(h->j);   // k is a pinning interior pointer  
  
   k = l;   // ok  
   Console::WriteLine(*k);  
};  
```  
  
 **Sortie**  
  
```Output  
1  
```  
  
 **Exemple**  
  
 L’exemple suivant montre qu’un pointeur épingle peut être converti en un autre type.  
  
```  
// pin_ptr_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class ManagedType {  
public:  
   int i;  
};  
  
int main() {  
   ManagedType ^mt = gcnew ManagedType;  
   pin_ptr<int> pt = &mt->i;  
   *pt = 8;  
   Console::WriteLine(mt->i);  
  
   char *pc = ( char* ) pt;  
   *pc = 255;  
   Console::WriteLine(mt->i);  
}  
```  
  
 **Sortie**  
  
```Output  
8  
255  
```