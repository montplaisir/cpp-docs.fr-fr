---
title: "&lt;bitset&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 84fe6a13-6f6e-4cdc-bf8f-6f65ab1134d4
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 99e42dab27a7ee03c42e9b1b5a35e94cc7ed050b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="ltbitsetgt-operators"></a>&lt;bitset&gt;, opérateurs
||||  
|-|-|-|  
|[operator&amp;](#op_amp)|[operator&gt;&gt;](#op_gt_gt)|[operator&lt;&lt;](#op_lt_lt)|  
|[operator^](#op_xor)|[operator|](#op_or)|  
  
##  <a name="op_amp"></a>  operator&amp;  
 Exécute une opération `AND` au niveau du bit entre deux bitsets.  
  
```  
template <size_t size>  
bitset<size>  
operator&(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Le premier des deux bitsets dont les éléments respectifs doivent être combinés avec l’opérateur `AND` au niveau du bit.  
  
 `right`  
 Le deuxième des deux bitsets dont les éléments respectifs doivent être combinés avec l’opérateur `AND` au niveau du bit.  
  
### <a name="return-value"></a>Valeur de retour  
 Bitset dont les éléments sont le résultat de l’exécution de l’opération `AND` sur les éléments correspondants de `left` et `right`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// bitset_and.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
int main()  
{  
   bitset<4> b1 ( string("0101") );  
   bitset<4> b2 ( string("0011") );  
   bitset<4> b3 = b1 & b2;  
   cout << "bitset 1: " << b1 << endl;  
   cout << "bitset 2: " << b2 << endl;  
   cout << "bitset 3: " << b3 << endl;  
}  
```  
  
```Output  
bitset 1: 0101  
bitset 2: 0011  
bitset 3: 0001  
```  
  
##  <a name="op_lt_lt"></a>  operator&lt;&lt;  
 Insère une représentation textuelle de la séquence de bits dans le flux de sortie.  
  
```  
 
template <class CharType, class Traits, size_t N>  
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,  
    const bitset<N>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Objet de type **bitset\<N>** qui doit être inséré dans le flux de sortie sous forme de chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Représentation textuelle d’une séquence de bits dans **ostr**.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle surcharge **operator<<** et autorise l’écriture d’un bitset sans d’abord le convertir en chaîne. La fonction de modèle est exécutée :  
  
 **ostr** << _ *Right*. [to_string](https://msdn.microsoft.com/library/2f93c55z.aspx) < **CharType**, **Traits**, **allocator**\< **CharType**> > ( )  
  
### <a name="example"></a>Exemple  
  
```cpp  
// bitset_op_insert.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 9 );  
  
   // bitset inserted into output stream directly  
   cout << "The ordered set of bits in the bitset<5> b1(9)"  
        << "\n can be output with the overloaded << as: ( "  
        << b1 << " )" << endl;  
  
   // Compare converting bitset to a string before  
   // inserting it into the output steam  
   string s1;  
   s1 =  b1.template to_string<char,   
      char_traits<char>, allocator<char> >( );  
   cout << "The string returned from the bitset b1"  
        << "\n by the member function to_string( ) is: "  
        << s1 << "." << endl;  
}  
```  
  
##  <a name="op_gt_gt"></a>  operator&gt;&gt;  
 Lit une chaîne de bits dans un bitset.  
  
```  
 
template <class CharType, class Traits, size_t Bits>  
basic_istream<CharType, Traits>& operator>> (
    basic_istream<CharType, Traits>& 
_Istr,  
    bitset<N>& 
    right);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Istr`  
 Chaîne entrée dans le flux d’entrée à insérer dans le bitset.  
  
 `right`  
 Bitset qui reçoit les bits du flux d’entrée.  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction de modèle retourne la chaîne `_Istr`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle surcharge **operator>>** pour stocker dans le bitset _ *Right* la valeur bitset( `str`), où `str` est un objet de type [basic_string](https://msdn.microsoft.com/library/syxtdd4f.aspx) < **CharType**, **Traits**, **allocator**\< **CharType**> > **&** extrait de `_Istr`.  
  
 La fonction de modèle extrait des éléments de `_Istr` et les insère dans le bitset jusqu’à ce que l’une de ces conditions soit remplie :  
  
-   Tous les éléments de bit ont été extraits du flux d’entrée et stockés dans le bitset.  
  
-   Le bitset est rempli avec les bits du flux d’entrée.  
  
-   Un élément d’entrée est rencontré, qui n’est ni 0, ni 1.  
  
### <a name="example"></a>Exemple  
  
```cpp  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
int main()  
{  
  
   bitset<5> b1;  
   cout << "Enter string of (0 or 1) bits for input into bitset<5>.\n"  
        << "Try bit string of length less than or equal to 5,\n"  
        << " (for example: 10110): ";  
   cin >>  b1;  
  
   cout << "The ordered set of bits entered from the "  
        << "keyboard\n has been input into bitset<5> b1 as: ( "  
        << b1 << " )" << endl;  
  
   // Truncation due to longer string of bits than length of bitset  
   bitset<2> b3;  
   cout << "Enter string of bits (0 or 1) for input into bitset<2>.\n"  
        << " Try bit string of length greater than 2,\n"  
        << " (for example: 1011): ";  
   cin >>  b3;  
  
   cout << "The ordered set of bits entered from the "  
        << "keyboard\n has been input into bitset<2> b3 as: ( "  
        << b3 << " )" << endl;  
  
   // Flushing the input stream  
   char buf[100];  
   cin.getline(&buf[0], 99);  
  
   // Truncation with non-bit value  
   bitset<5> b2;  
   cout << "Enter a string for input into  bitset<5>.\n"  
        << " that contains a character than is NOT a 0 or a 1,\n "  
        << " (for example: 10k01): ";  
   cin >>  b2;  
  
   cout << "The string entered from the keyboard\n"  
        << " has been input into bitset<5> b2 as: ( "  
        << b2 << " )" << endl;  
}  
```  
  
##  <a name="op_xor"></a>  operator^  
 Exécute une opération `EXCLUSIVE-OR` au niveau du bit entre deux bitsets.  
  
```  
template <size_t size>  
bitset<size>  
operator^(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Le premier des deux bitsets dont les éléments respectifs doivent être combinés avec l’opérateur `EXCLUSIVE-OR` au niveau du bit.  
  
 `right`  
 Le deuxième des deux bitsets dont les éléments respectifs doivent être combinés avec l’opérateur `EXCLUSIVE-OR` au niveau du bit.  
  
### <a name="return-value"></a>Valeur de retour  
 Bitset dont les éléments sont le résultat de l’exécution de l’opération `EXCLUSIVE-OR` sur les éléments correspondants de `left` et `right`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// bitset_xor.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
int main()  
{  
   bitset<4> b1 ( string("0101") );  
   bitset<4> b2 ( string("0011") );  
   bitset<4> b3 = b1 ^ b2;  
   cout << "bitset 1: " << b1 << endl;  
   cout << "bitset 2: " << b2 << endl;  
   cout << "bitset 3: " << b3 << endl;  
}  
```  
  
```Output  
bitset 1: 0101  
bitset 2: 0011  
bitset 3: 0110  
```  
  
##  <a name="op_or"></a>opérateur |  
 Exécute une opération `OR` au niveau du bit entre deux bitsets.  
  
```  
template <size_t size>  
bitset<size>  
operator|(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Le premier des deux bitsets dont les éléments respectifs doivent être combinés avec l’opérateur `OR` au niveau du bit.  
  
 `right`  
 Le deuxième des deux bitsets dont les éléments respectifs doivent être combinés avec l’opérateur `OR` au niveau du bit.  
  
### <a name="return-value"></a>Valeur de retour  
 Bitset dont les éléments sont le résultat de l’exécution de l’opération `OR` sur les éléments correspondants de `left` et `right`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// bitset_or.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
int main()  
{  
   bitset<4> b1 ( string("0101") );  
   bitset<4> b2 ( string("0011") );  
   bitset<4> b3 = b1 | b2;  
   cout << "bitset 1: " << b1 << endl;  
   cout << "bitset 2: " << b2 << endl;  
   cout << "bitset 3: " << b3 << endl;  
}  
```  
  
```Output  
bitset 1: 0101  
bitset 2: 0011  
bitset 3: 0111  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<bitset>](../standard-library/bitset.md)

