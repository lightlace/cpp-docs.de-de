---
title: "back_insert_iterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/std::back_insert_iterator"
  - "std::back_insert_iterator"
  - "back_insert_iterator"
  - "std.back_insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back_insert_iterator-Klasse"
ms.assetid: a1ee07f2-cf9f-46a1-8608-cfaf207f9713
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# back_insert_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen Iteratoradapter, der den Anforderungen eines Ausgabeiterators entspricht. Er fügt Elemente in das Ende einer Sequenz ein, anstatt sie zu überschreiben, und bietet somit Semantik, die sich von der Semantik zum Überschreiben unterscheidet, die von den Iteratoren der C++-Sequenzcontainer bereitgestellt wird. Die `back_insert_iterator`-Klasse ist für den Typ des Containers vorlagenbasiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Container>  
class back_insert_iterator;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Container`  
 Der Typ des Containers, an dessen Ende Elemente von einem `back_insert_iterator` eingefügt werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Der Container muss den Anforderungen einer Sequenz zum Einfügen am Ende entsprechen, in der es möglich ist, die Elemente am Ende der Sequenz in amortisierter konstanter Zeit einzufügen. STL-sequenzcontainer definiert die [Deque-Klasse](../standard-library/deque-class.md), [list-Klasse](../standard-library/list-class.md) und [vector-Klasse](vector%20Class.md) bieten die erforderliche `push_back` Member und erfüllen diese Anforderungen. Diese drei Container sowie Zeichenfolgen werden jeweils für die Verwendung mit `back_insert_iterator` angepasst. Ein `back_insert_iterator` muss immer mit seinem Container initialisiert werden.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[back_insert_iterator](#back_insert_iterator__back_insert_iterator)|Erstellt einen `back_insert_iterator`, der Elemente nach dem letzten Element in einen Container einfügt.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#back_insert_iterator__container_type)|Ein Typ, der einen Container für den `back_insert_iterator` bereitstellt.|  
|[Referenz](#back_insert_iterator__reference)|Ein Typ, der einen Verweis für den `back_insert_iterator` bereitstellt.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator *](#back_insert_iterator__operator_star)|Der Dereferenzierungsoperator, der zum Implementieren des ausgabeiteratorausdrucks * `i` = `x` für eine Einfügung.|  
|[Operator ++](#back_insert_iterator__operator_add_add)|Inkrementiert `back_insert_iterator` zum folgenden Speicherort, an dem ein Wert gespeichert werden kann.|  
|[Operator =](#back_insert_iterator__operator_eq)|Zuweisungsoperator, die zum Implementieren des ausgabeiteratorausdrucks * `i` = `x` für eine Einfügung.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: \< Iterator>  
  
 **Namespace:** std  
  
##  <a name="a-namebackinsertiteratorbackinsertiteratora-backinsertiteratorbackinsertiterator"></a><a name="back_insert_iterator__back_insert_iterator"></a>  back_insert_iterator:: back_insert_iterator  
 Erstellt einen `back_insert_iterator`, der Elemente nach dem letzten Element in einen Container einfügt.  
  
```  
 
explicit back_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Parameter  
 `_Cont`  
 Der Container, der die `back_insert_iterator` Fügen Sie ein Element in ein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `back_insert_iterator` für den Parameter-Container.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namebackinsertiteratorcontainertypea-backinsertiteratorcontainertype"></a><a name="back_insert_iterator__container_type"></a>  back_insert_iterator:: container_type  
 Ein Typ, der einen Container für den `back_insert_iterator` bereitstellt.  
  
```  
 
typedef Container  
container_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **Container**.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namebackinsertiteratoroperatorstara-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_star"></a>  back_insert_iterator:: Operator *  
 Der Dereferenzierungsoperator, der zum Implementieren des ausgabeiteratorausdrucks \* *ich* = *x*.  
  
```  
back_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Element auf der Rückseite der Container eingefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Zum Implementieren des ausgabeiteratorausdrucks **\*Iter** = **Wert**. Wenn **Iter** ist ein Iterator, der ein Element in einer Sequenz dann **\*Iter** = **Wert** ersetzt das Element mit dem Wert und die Gesamtzahl der Elemente in der Sequenz nicht ändert.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namebackinsertiteratoroperatoraddadda-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_add_add"></a>  back_insert_iterator::Operator++  
 Inkrementiert `back_insert_iterator` zum folgenden Speicherort, an dem ein Wert gespeichert werden kann.  
  
```  
back_insert_iterator<Container>& operator++();

back_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `back_insert_iterator` Adressierung der nächsten Position, an dem ein Wert gespeichert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Operatoren Preincrementation und Postincrementation zurückgibt das gleiche Ergebnis.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namebackinsertiteratoroperatoreqa-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_eq"></a>  back_insert_iterator:: Operator =  
 Fügt ab oder legt einen Wert auf den Back-End eines Containers.  
  
```  
back_insert_iterator<Container>& operator=(typename Container::const_reference val);

    back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Parameter  
 ` val`  
 Der Wert in den Container eingefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das letzte Element auf der Rückseite der Container eingefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Memberoperator ergibt `Container.push_back( val)`,  
  
 Gibt `*this`. Der zweite Operator für den Memberzugriff ausgewertet wird.  
  
 `container->push_back((typename Container::value_type&&)val)`,  
  
 Gibt `*this`.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namebackinsertiteratorreferencea-backinsertiteratorreference"></a><a name="back_insert_iterator__reference"></a>  back_insert_iterator:: Reference  
 Ein Typ, der einen Verweis für den `back_insert_iterator` bereitstellt.  
  
```  
 
typedef typename Container::reference reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt einen Verweis auf ein Element der Sequenz, die von den zugehörigen Container gesteuert.  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
## <a name="see-also"></a>Siehe auch  
 [\< Iterator>](../standard-library/iterator.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

