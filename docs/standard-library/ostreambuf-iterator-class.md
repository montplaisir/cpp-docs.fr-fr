---
title: "ostreambuf_iterator, classe │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- streambuf/std::ostreambuf_iterator
- ostreambuf_iterator
- iterator/std::ostreambuf_iterator::char_type
- iterator/std::ostreambuf_iterator::ostream_type
- iterator/std::ostreambuf_iterator::streambuf_type
- iterator/std::ostreambuf_iterator::traits_type
- iterator/std::ostreambuf_iterator::failed
dev_langs:
- C++
helpviewer_keywords:
- ostreambuf_iterator class
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 2f58e86e76e63d51739558b796e47dc3f5165d3f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="ostreambufiterator-class"></a>ostreambuf_iterator
La classe de modèle ostreambuf_iterator décrit un objet itérateur de sortie qui enregistre les éléments de caractères consécutifs dans le flux de sortie avec l’**opérateur>>** d’extraction. Les objets `ostreambuf_iterator` diffèrent de ceux de la [classe ostream_iterator](../standard-library/ostream-iterator-class.md), car ils présentent des caractères à la place d’un type générique dans le type d’objet inséré dans le flux de sortie.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class CharType = char class Traits = char_traits <CharType>>
```  
  
#### <a name="parameters"></a>Paramètres  
 `CharType`  
 Type qui représente le type de caractère pour l'objet ostreambuf_iterator. Cet argument est facultatif et sa valeur par défaut est `char`.  
  
 `Traits`  
 Type qui représente le type de caractère pour l'objet ostreambuf_iterator. Cet argument est facultatif et sa valeur par défaut est `char_traits`\< *CharType>.*  
  
## <a name="remarks"></a>Notes  
 La classe ostreambuf_iterator doit être conforme aux exigences d’un itérateur de sortie. Les algorithmes peuvent être enregistrés directement dans le flux de sortie à l'aide de `ostreambuf_iterator`. La classe fournit un itérateur de flux de bas niveau qui permet l'accès au flux d'E/S brut (sans mise en forme) sous la forme de caractères et permet de contourner la mise en mémoire tampon et les traductions de caractères associées aux itérateurs de flux de haut niveau.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|Construit un objet `ostreambuf_iterator` initialisé pour enregistrer des caractères dans le flux de sortie.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|Type qui fournit le type de caractère de `ostreambuf_iterator`.|  
|[ostream_type](#ostreambuf_iterator_ostream_type)|Type qui fournit le type de flux de `ostream_iterator`.|  
|[streambuf_type](#streambuf_type)|Type qui fournit le type de flux de `ostreambuf_iterator`.|  
|[traits_type](#traits_type)|Type qui fournit le type de caractéristique de `ostream_iterator`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[failed](#failed)|Teste l'échec d'une insertion dans la mémoire tampon du flux de sortie.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator*](#op_star)|Opérateur de suppression de référence utilisé pour implémenter l’expression d’itérateur de sortie * `i` = `x`.|  
|[operator++](#op_add_add)|Opérateur d'incrément non fonctionnel qui retourne un `ostreambuf_iterator` au même objet qu'il a traité avant que l'opération n'ait été appelée.|  
|[operator=](#op_eq)|L'opérateur insère un caractère dans la mémoire tampon du flux associé.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<iterator>  
  
 **Espace de noms :** std  
  
##  <a name="char_type"></a>  ostreambuf_iterator::char_type  
 Type qui fournit le type de caractère de `ostreambuf_iterator`.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **CharType**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostreambuf_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostreambuf_iterator<char>::char_type CHT1;  
   typedef ostreambuf_iterator<char>::traits_type CHTR1;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter:  
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output streambuf:  
   cout << "The characters written to the output stream\n"  
        << " by charOutBuf are: ";  
 *charOutBuf = 'O';  
   charOutBuf++;  
 *charOutBuf = 'U';  
   charOutBuf++;  
 *charOutBuf = 'T';  
   charOutBuf++;  
   cout << "." << endl;  
}  
\* Output:   
The characters written to the output stream  
 by charOutBuf are: OUT.  
*\  
```  
  
##  <a name="failed"></a>  ostreambuf_iterator::failed  
 Teste l'échec d'une insertion dans la mémoire tampon du flux de sortie.  
  
```
bool failed() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si aucune insertion dans le tampon de flux de sortie n’a échoué précédemment. **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne **true** si, dans une utilisation précédente du membre `operator=`, l’appel à **subf**_-> `sputc` avait retourné **eof**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostreambuf_iterator_failed.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   ostreambuf_iterator<char> charOut ( cout );  
  
 *charOut = 'a';  
   charOut ++;  
 *charOut  = 'b';  
   charOut ++;     
 *charOut = 'c';  
   cout << " are characters output individually." << endl;  
  
   bool b1 = charOut.failed ( );  
   if (b1)   
       cout << "At least one insertion failed." << endl;  
   else  
       cout << "No insertions failed." << endl;  
}  
\* Output:   
abc are characters output individually.  
No insertions failed.  
*\  
```  
  
##  <a name="op_star"></a>  ostreambuf_iterator::operator*  
 Opérateur de suppression de référence non fonctionnel, utilisé pour implémenter l’expression d’itérateur de sortie \* *i* = *x*.  
  
```
ostreambuf_iterator<CharType, Traits>& operator*();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Objet itérateur ostreambuf.  
  
### <a name="remarks"></a>Notes  
 Cet opérateur fonctionne uniquement dans l’expression d’itérateur de sortie \* *i* = *x* pour envoyer les caractères de sortie dans la mémoire tampon du flux. Appliqué à un itérateur ostreambuf, il retourne l’itérateur. **\*iter** retourne **iter**,  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostreambuf_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;   // no effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';  
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="op_add_add"></a>  ostreambuf_iterator::operator++  
 Opérateur d’incrémentation non fonctionnel qui retourne un itérateur ostream au même caractère qu’il a traité avant l’appel de l’opération.  
  
```
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence au caractère initialement traité ou à un objet défini par l’implémentation qui peut être converti en `ostreambuf_iterator`\< **CharType**, **Traits**>.  
  
### <a name="remarks"></a>Notes  
 L’opérateur est utilisé pour implémenter l’expression d’itérateur de sortie \* *i* = *x*.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostreambuf_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;      // No effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';     
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="op_eq"></a>  ostreambuf_iterator::operator=  
 L'opérateur insère un caractère dans la mémoire tampon du flux associé.  
  
```
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Char`  
 Caractère à insérer dans la mémoire tampon du flux.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence au caractère inséré dans la mémoire tampon du flux.  
  
### <a name="remarks"></a>Notes  
 Opérateur d’assignation utilisé pour implémenter l’expression d’itérateur de sortie \* *i* = *x* en vue de l’écriture dans un flux de sortie.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostreambuf_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;      // No effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';     
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="ostreambuf_iterator_ostreambuf_iterator"></a>  ostreambuf_iterator::ostreambuf_iterator  
 Construit un objet `ostreambuf_iterator` initialisé pour enregistrer des caractères dans le flux de sortie.  
  
```
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `strbuf`  
 Objet de sortie streambuf utilisé pour initialiser le pointeur de mémoire tampon du flux de sortie.  
  
 `Ostr`  
 Objet de sortie stream pour initialiser le pointeur de mémoire tampon du flux de sortie.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise le pointeur de mémoire tampon du flux de sortie avec `strbuf`.  
  
 Le deuxième constructeur initialise le pointeur de mémoire tampon du flux de sortie avec `Ostr`. `rdbuf`. Le pointeur stocké ne doit pas être un pointeur null.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostreambuf_iteratorOstreambuf_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   ostreambuf_iterator<char> charOut ( cout );  
  
 *charOut = 'O';  
   charOut ++;  
 *charOut  = 'U';  
   charOut ++;     
 *charOut = 'T';  
   cout << " are characters output individually." << endl;  
  
   ostreambuf_iterator<char> strOut ( cout );  
   string str = "These characters are being written to the output stream.\n ";  
   copy ( str.begin ( ), str. end ( ), strOut );  
}  
\* Output:   
OUT are characters output individually.  
These characters are being written to the output stream.  
*\  
```  
  
##  <a name="ostreambuf_iterator_ostream_type"></a>  ostreambuf_iterator::ostream_type  
 Type qui fournit le type de flux de `ostream_iterator`.  
  
```
typedef basicOstream<CharType, Traits> ostream_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `basicOstream`\< **CharType**, **Traits**>  
  
### <a name="example"></a>Exemple  
  Pour savoir comment déclarer et utiliser `ostream_type`, consultez l’exemple [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator).  
  
##  <a name="streambuf_type"></a>  ostreambuf_iterator::streambuf_type  
 Type qui fournit le type de flux de `ostreambuf_iterator`.  
  
```
typedef basic_streambuf<CharType, Traits> streambuf_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `basic_streambuf`\< **CharType**, **Traits**>, une classe stream pour les mémoires tampons d’E/S qui devient la classe `streambuf` quand le type est spécialisé sur le type de caractères `char`.  
  
### <a name="example"></a>Exemple  
  Pour savoir comment déclarer et utiliser `streambuf_type`, consultez l’exemple [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator).  
  
##  <a name="traits_type"></a>  ostreambuf_iterator::traits_type  
 Type qui fournit le type de caractéristique de `ostream_iterator`.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **Traits**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostreambuf_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostreambuf_iterator<char>::char_type CHT1;  
   typedef ostreambuf_iterator<char>::traits_type CHTR1;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter:  
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output streambuf:  
   cout << "The characters written to the output stream\n"  
        << " by charOutBuf are: ";  
 *charOutBuf = 'O';  
   charOutBuf++;  
 *charOutBuf = 'U';  
   charOutBuf++;  
 *charOutBuf = 'T';  
   charOutBuf++;  
   cout << "." << endl;  
}  
\* Output:   
The characters written to the output stream  
 by charOutBuf are: OUT.  
*\  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<iterator>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)



