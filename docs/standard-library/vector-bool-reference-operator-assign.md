---
title: vector&lt;bool&gt;::reference::operator= | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- =
- operator=
- vector<bool>::reference::operator=
- std::vector<bool>::reference::operator=
dev_langs: C++
helpviewer_keywords:
- = operator, with specific C++ Standard Library objects
- reference::operator=
ms.assetid: eed20d81-36b9-40b2-a3b6-340ed0bb4f34
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 067a351fee066612f09d44938c8a627797447402
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="vectorltboolgtreferenceoperator"></a>vector&lt;bool&gt;::reference::operator=
Assigne une valeur booléenne à un bit, ou la valeur détenue par un élément référencé à un bit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
reference& operator=(const reference& Right);

reference& operator=(bool Val);
```  
  
#### <a name="parameters"></a>Paramètres  
 `Right`  
 Référence d'élément dont la valeur doit être assignée au bit.  
  
 `Val`  
 Valeur booléenne à assigner au bit.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// vector_bool_ref_op_assign.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    print("The vector is: ", vb);  
  
    // Invoke vector<bool>::reference::operator=()  
    vector<bool>::reference refelem1 = vb[0];  
    vector<bool>::reference refelem2 = vb[1];  
    vector<bool>::reference refelem3 = vb[2];  
  
    bool b1 = refelem1;  
    bool b2 = refelem2;  
    bool b3 = refelem3;  
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;  
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;  
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;  
    cout << endl;  
  
    refelem2 = refelem1;  
  
    print("The vector after assigning refelem1 to refelem2 is now: ", vb);  
  
    refelem3 = true;  
  
    print("The vector after assigning false to refelem1 is now: ", vb);  
  
    // The initial values are still stored in the bool variables and remained unchanged  
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;  
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;  
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;  
    cout << endl;  
}  
  
```  
  
## <a name="output"></a>Sortie  
  
```  
The vector is: true false false true true  
The original value of the 1st element stored in a bool: true  
The original value of the 2nd element stored in a bool: false  
The original value of the 3rd element stored in a bool: false  
 
The vector after assigning refelem1 to refelem2 is now: true true false true true  
The vector after assigning false to refelem1 is now: true true true true true  
The original value of the 1st element still stored in a bool: true  
The original value of the 2nd element still stored in a bool: false  
The original value of the 3rd element still stored in a bool: false  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<vector>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [vector\<bool>::reference, classe](../standard-library/vector-bool-reference-class.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)
