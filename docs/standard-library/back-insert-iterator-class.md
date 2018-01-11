---
title: "back_insert_iterator, classe │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::back_insert_iterator
- iterator/std::back_insert_iterator::container_type
- iterator/std::back_insert_iterator::reference
dev_langs: C++
helpviewer_keywords:
- std::back_insert_iterator [C++]
- std::back_insert_iterator [C++], container_type
- std::back_insert_iterator [C++], reference
ms.assetid: a1ee07f2-cf9f-46a1-8608-cfaf207f9713
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc2cde9149a1b1871a88c193ebd5730f76dc7224
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="backinsertiterator-class"></a>back_insert_iterator, classe
Décrit un adaptateur d’itérateur qui répond aux exigences d’un itérateur de sortie. Elle insère, plutôt que remplace, des éléments de la fin d'une séquence et fournit ainsi une sémantique différente de la sémantique de remplacement fournie par les itérateurs des conteneurs de la séquence C++. La classe `back_insert_iterator` est mise en modèle d'après le type de conteneur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Container>  
class back_insert_iterator;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Container`  
 Type de conteneur à la fin duquel des éléments doivent être insérés par un `back_insert_iterator`.  
  
## <a name="remarks"></a>Notes  
 Le conteneur doit répondre aux exigences d’une insertion de fin de séquence où il est possible d’insérer des éléments à la fin de la séquence dans le temps fixe amorti. Les conteneurs de séquences de bibliothèque C++ Standard définis par la [classe deque](../standard-library/deque-class.md), la [classe list](../standard-library/list-class.md) et la [classe vector](../standard-library/vector-class.md) fournissent la fonction membre `push_back` nécessaire et répondent aux exigences. Ces trois conteneurs, ainsi que les chaînes, peuvent être adaptés pour être utilisés avec des `back_insert_iterator`. Un `back_insert_iterator` doit toujours être initialisé avec son conteneur.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[back_insert_iterator](#back_insert_iterator)|Construit `back_insert_iterator` qui insère des éléments après le dernier élément d'un conteneur.|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[container_type](#container_type)|Type qui fournit un conteneur pour le `back_insert_iterator`.|  
|[reference](#reference)|Type qui fournit une référence pour le `back_insert_iterator`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator*](#op_star)|Opérateur de suppression de référence utilisé pour implémenter l’expression d’itérateur de sortie * `i` = `x` pour une insertion de fin.|  
|[operator++](#op_add_add)|Incrémente le `back_insert_iterator` à l'emplacement suivant où une valeur peut être stockée.|  
|[operator=](#op_eq)|Opérateur d’assignation utilisé pour implémenter l’expression d’itérateur de sortie * `i` = `x` pour une insertion de fin.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête** : \<iterator>  
  
 **Espace de noms :** std  
  
##  <a name="back_insert_iterator"></a>  back_insert_iterator::back_insert_iterator  
 Construit `back_insert_iterator` qui insère des éléments après le dernier élément d'un conteneur.  
  
```   
explicit back_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Cont`  
 Conteneur dans lequel `back_insert_iterator` doit insérer un élément.  
  
### <a name="return-value"></a>Valeur de retour  
 `back_insert_iterator` pour le paramètre container.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// back_insert_iterator_back_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The initial vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   // Insertions with member function  
   back_inserter ( vec ) = 40;  
   back_inserter ( vec ) = 50;  
  
   // Alternatively, insertions can be done with template function  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 600;  
   backiter++;  
 *backiter = 700;  
  
   cout << "After the insertions, the vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The initial vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec is: ( 1 2 3 40 50 600 700 ).  
```  
  
##  <a name="container_type"></a>  back_insert_iterator::container_type  
 Type qui fournit un conteneur pour le `back_insert_iterator`.  
  
```   
typedef Container  
container_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **Container**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// back_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back (  i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The original vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::container_type vec1 = vec;  
   back_inserter ( vec1 ) = 40;  
  
   cout << "After the insertion, the vector is: ( ";  
   for ( vIter = vec1.begin ( ) ; vIter != vec1.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector vec is: ( 1 2 3 ).  
After the insertion, the vector is: ( 1 2 3 40 ).  
```  
  
##  <a name="op_star"></a>  back_insert_iterator::operator*  
 Opérateur de suppression de référence utilisé pour implémenter l’expression d’itérateur de sortie \* *i* = *x*.  
  
```  
back_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’élément inséré à la fin du conteneur.  
  
### <a name="remarks"></a>Notes  
 Utilisé pour implémenter l’expression d’itérateur de sortie **\*Iter** = **value**. Si **Iter** est un itérateur qui cible un élément dans une séquence, alors **\*Iter** = **value** remplace cet élément par value et ne change pas le nombre total d’éléments dans la séquence.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// back_insert_iterator_back_insert.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec becomes: ( 1 2 3 10 20 ).  
```  
  
##  <a name="op_add_add"></a>  back_insert_iterator::operator++  
 Incrémente le `back_insert_iterator` à l'emplacement suivant où une valeur peut être stockée.  
  
```  
back_insert_iterator<Container>& operator++();
back_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 `back_insert_iterator` qui cible l’emplacement suivant où une valeur peut être stockée.  
  
### <a name="remarks"></a>Notes  
 Les opérateurs de préincrémentation et de postincrémentation retournent le même résultat.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// back_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 3 ; ++i )    
   {  
      vec.push_back ( 10 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 30;  
   backiter++;      // Increment to the next element  
 *backiter = 40;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 10 20 ).  
After the insertions, the vector vec becomes: ( 10 20 30 40 ).  
```  
  
##  <a name="op_eq"></a>  back_insert_iterator::operator=  
 Ajoute ou pousse une valeur à la fin d’un conteneur.  
  
```  
back_insert_iterator<Container>& operator=(typename Container::const_reference val);
back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
 `val`  
 Valeur à insérer dans le conteneur.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence au dernier élément inséré à la fin du conteneur.  
  
### <a name="remarks"></a>Notes  
 Le premier opérateur membre évalue `Container.push_back( val)`,  
  
 puis retourne `*this`. Le deuxième opérateur membre évalue  
  
 `container->push_back((typename Container::value_type&&)val)`,  
  
 puis retourne `*this`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// back_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
##  <a name="reference"></a>  back_insert_iterator::reference  
 Type qui fournit une référence pour le `back_insert_iterator`.  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit une référence à un élément de la séquence contrôlée par le conteneur associé.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// back_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::reference   
        RefLast = *(vec.end ( ) - 1 );  
   cout << "The last element in the vector vec is: "   
        << RefLast << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
The last element in the vector vec is: 3.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<iterator>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)
