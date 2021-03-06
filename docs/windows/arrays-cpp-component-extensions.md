---
title: Tableaux (Extensions du composant C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- cli::array
- details::array
- lang::array
dev_langs:
- C++
helpviewer_keywords:
- array keyword [C++]
- declaring arrays, about declaring arrays
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 21a1dd4f26db41f7e32f3f76fd3b4c82e513397a
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461687"
---
# <a name="arrays-c-component-extensions"></a>Tableaux (extensions du composant C++)
Le `Platform::Array<T>` type en C / c++ / CX, ou le **tableau** mot clé dans C++ / c++ / CLI, déclare un tableau d’un type spécifié et la valeur initiale.  
  
## <a name="all-platforms"></a>Toutes les plateformes  
 Le tableau doit être déclaré à l’aide du modificateur handle-to-object (^) après le crochet fermant (>) dans la déclaration.  
 Le nombre d’éléments du tableau ne fait pas partie du type. Une variable tableau peut faire référence à des tableaux de tailles différentes.  
  
 Contrairement à C++ standard, la mise en indice n’est pas un synonyme pour une opération arithmétique de pointeur et n’est pas commutative.  
  
 Pour plus d’informations sur les tableaux, consultez :  
  
-   [Guide pratique pour utiliser des tableaux dans C++-CLI](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
    
-   [Listes d’arguments de variable (...) (C++-CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows Runtime  
 Les tableaux sont des membres de la `Platform` espace de noms. Tableaux peuvent uniquement être unidimensionnels.  
  
### <a name="syntax"></a>Syntaxe  
  
 Le premier exemple de la syntaxe de la **ref nouvelle** mot clé d’agrégation pour allouer un tableau. Le deuxième exemple déclare un tableau local.  
  
```  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *qualificateurs* [facultatif]  
 Un ou plusieurs de ces spécificateurs de classe de stockage : [mutable](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [statique](../cpp/static-members-cpp.md).  
  
 *type de tableau*  
 Le type de la variable de tableau. Les types valides sont les classes Windows Runtime et types fondamentaux, les classes ref structs, les classes de valeur et les structures et des pointeurs natifs (`type*`).  
  
 *rang* [facultatif]  
 Le nombre de dimensions du tableau. Doit être 1.  
  
 *identifier*  
 Le nom de la variable de tableau.  
  
 *type de l’initialisation*  
 Le type des valeurs qui initialiser le tableau. En règle générale, *de type tableau* et *-type d’initialisation* sont du même type. Toutefois, les types peuvent être différents s’il existe une conversion à partir de *-type d’initialisation* à *de type tableau*— par exemple, si *-type d’initialisation* est dérivée de *de type tableau*.  
  
 *liste d’initialisation* [facultatif]  
 Une liste délimitée par des virgules des valeurs entre accolades qui initialisent les éléments du tableau. Par exemple, si *liste de taille de rang* ont été `(3)`, qui déclare un tableau unidimensionnel de 3 éléments, *liste d’initialisation* peut être `{1,2,3}`.  
  
### <a name="remarks"></a>Notes  
  
 Vous pouvez détecter au moment de la compilation si un type est un tableau de références comptabilisées avec `__is_ref_array(type)`. Pour plus d’informations, consultez [prise en charge du compilateur pour les Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### <a name="requirements"></a>Configuration requise  
 Option du compilateur : **/ZW**  
  
### <a name="examples"></a>Exemples  
 L’exemple suivant crée un tableau unidimensionnel qui comporte 100 éléments.  
  
```cpp  
// cwr_array.cpp  
// compile with: /ZW  
using namespace Platform;  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);  
   My1DArray[99] = ref new MyClass();  
}  
```  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
  
### <a name="syntax"></a>Syntaxe  
  
 Le premier exemple de la syntaxe de la **gcnew** mot clé pour allouer un tableau. Le deuxième exemple déclare un tableau local.  
  
```  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *qualificateurs* [facultatif]  
 Un ou plusieurs de ces spécificateurs de classe de stockage : [mutable](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [statique](../cpp/static-members-cpp.md).  
  
 *type de tableau*  
 Le type de la variable de tableau. Les types valides sont les classes Windows Runtime et les types fondamentaux, les classes ref et les structs, valeur classes et structs, les pointeurs natifs (`type*`) et les types POD (anciennes données brutes) natifs.  
  
 *rang* [facultatif]  
 Le nombre de dimensions du tableau. La valeur par défaut est 1 ; la valeur maximale est 32. Chaque dimension du tableau lui-même est un tableau.  
  
 *identifier*  
 Le nom de la variable de tableau.  
  
 *type de l’initialisation*  
 Le type des valeurs qui initialiser le tableau. En règle générale, *de type tableau* et *-type d’initialisation* sont du même type. Toutefois, les types peuvent être différents s’il existe une conversion à partir de *-type d’initialisation* à *de type tableau*— par exemple, si *-type d’initialisation* est dérivée de *de type tableau*.  
  
 *liste de taille de rang*  
 Une liste délimitée par des virgules de la taille de chaque dimension du tableau. Ou bien, si le *-liste d’initialisation* paramètre est spécifié, le compilateur peut déduire la taille de chaque dimension et *liste de taille de rang* peut être omis. 
  
 *liste d’initialisation* [facultatif]  
 Une liste délimitée par des virgules des valeurs entre accolades qui initialisent les éléments du tableau. Ou une liste délimitée par des virgules d’imbriquée *-liste d’initialisation* éléments qui initialisent les éléments dans un tableau multidimensionnel.  
  
 Par exemple, si *liste de taille de rang* ont été `(3)`, qui déclare un tableau unidimensionnel de 3 éléments, *liste d’initialisation* peut être `{1,2,3}`. Si *liste de taille de rang* ont été `(3,2,4)`, qui déclare un tableau tridimensionnel de 3 éléments dans la première dimension, 2 éléments dans la seconde et 4 éléments dans la troisième, *-liste d’initialisation* peut être `{{1,2,3},{0,0},{-5,10,-21,99}}`.)  
  
### <a name="remarks"></a>Notes  
  
 `array` est dans le [plateforme, par défaut et espaces de noms cli](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) espace de noms.  
  
 Tel que C++ standard, les indices de tableau sont de base zéro et est indicée de tableau en utilisant des crochets ([]). Contrairement à C++ standard, les index d’un tableau multidimensionnel sont spécifiés dans une liste d’indices pour chaque dimension au lieu d’un ensemble d’opérateurs de crochets ([et]) pour chaque dimension. Par exemple, *identificateur*[*index1*, *index2*] au lieu de *identificateur*[*index1*] [ *index2*].  
  
 Tous les tableaux managés héritent `System::Array`. Toute méthode ou propriété de `System::Array` peut être appliqué directement à la variable tableau.  
  
 Lorsque vous allouez un tableau dont le type élément est pointeur-pour une classe managée, les éléments sont initialisés à 0.  
  
 Lorsque vous allouez un tableau dont le type élément est un type valeur `V`, le constructeur par défaut `V` est appliqué à chaque élément du tableau. Pour plus d’informations, consultez [équivalents .NET Framework des types natifs C++ (C++ / c++ / CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md).  
  
 Au moment de la compilation, vous pouvez détecter si un type est une common language runtime (CLR) `__is_ref_array(type)`. Pour plus d’informations, consultez [prise en charge du compilateur pour les Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### <a name="requirements"></a>Configuration requise  
 Option du compilateur : **/clr**  
  
### <a name="examples"></a>Exemples  
 L’exemple suivant crée un tableau unidimensionnel qui comporte 100 éléments et un tableau tridimensionnel qui comporte 3 éléments dans la première dimension, 5 éléments dans la seconde et 6 éléments dans la troisième.  
  
```cpp  
// clr_array.cpp  
// compile with: /clr  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);  
   My1DArray[99] = gcnew MyClass();  
  
   // three-dimensional array  
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);  
   My3DArray[0,0,0] = gcnew MyClass();  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Extensions de composant pour les plateformes Runtime](../windows/component-extensions-for-runtime-platforms.md)