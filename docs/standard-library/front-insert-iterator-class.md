---
title: "front_insert_iterator-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "iterator/std::front_insert_iterator"
  - "std::front_insert_iterator"
  - "std.front_insert_iterator"
  - "front_insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "front_insert_iterator-Klasse"
ms.assetid: a9a9c075-136a-4419-928b-c4871afa033c
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# front_insert_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen Iteratoradapter, der den Anforderungen eines Ausgabeiterators entspricht. Er fügt Elemente in den Anfang einer Sequenz ein, anstatt sie zu überschreiben, und bietet somit Semantik, die sich von der Semantik zum Überschreiben unterscheidet, die von den Iteratoren der C++-Sequenzcontainer bereitgestellt wird. Die `front_insert_iterator`-Klasse ist für den Typ des Containers vorlagenbasiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Container>  
class front_insert_iterator;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Container`  
 Der Typ des Containers, an dessen Anfang Elemente von einem `front_insert_iterator` eingefügt werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Der Container muss den Anforderungen einer Sequenz zum Einfügen am Anfang entsprechen, in der es möglich ist, die Elemente am Anfang der Sequenz in amortisierter konstanter Zeit einzufügen. Der Standard Template Library-sequenzcontainer definiert die [Deque-Klasse](../standard-library/deque-class.md) und [list-Klasse](../standard-library/list-class.md) bieten die erforderliche `push_front` Member und erfüllen diese Anforderungen. Im Gegensatz dazu sequenzcontainer definiert die [vector-Klasse](vector%20Class.md) erfüllen diese Anforderungen nicht und kann nicht angepasst werden mit `front_insert_iterator`s. Ein `front_insert_iterator` muss immer mit seinem Container initialisiert werden.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[front_insert_iterator](#front_insert_iterator__front_insert_iterator)|Damit wird ein Iterator erstellt, mit dem Elemente an den Anfang eines bestimmten Containerobjekts eingefügt werden können.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#front_insert_iterator__container_type)|Ein Typ, der den Container darstellt, in dem eine Einfügung am Anfang vorgenommen werden soll.|  
|[Referenz](#front_insert_iterator__reference)|Ein Typ, der einen Verweis auf ein Element in einer Sequenz enthält, die durch den zugehörigen Container gesteuert wird.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator *](#front_insert_iterator__operator_star)|Der Dereferenzierungsoperator, der zum Implementieren des ausgabeiteratorausdrucks * `i` = `x` für eine Einfügung am Anfang.|  
|[Operator ++](#front_insert_iterator__operator_add_add)|Inkrementiert `front_insert_iterator` zum folgenden Speicherort, an dem ein Wert gespeichert werden kann.|  
|[Operator =](#front_insert_iterator__operator_eq)|Zuweisungsoperator, die zum Implementieren des ausgabeiteratorausdrucks * `i` = `x` für eine Einfügung am Anfang.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: \< Iterator>  
  
 **Namespace:** std  
  
##  <a name="a-namefrontinsertiteratorcontainertypea-frontinsertiteratorcontainertype"></a><a name="front_insert_iterator__container_type"></a>  front_insert_iterator:: container_type  
 Ein Typ, der den Container darstellt, in dem eine Einfügung am Anfang vorgenommen werden soll.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **Container**.  
  
### <a name="example"></a>Beispiel  
  
```  
// front_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> >::container_type L2 = L1;  
   front_inserter ( L2 ) = 20;  
   front_inserter ( L2 ) = 10;  
   front_inserter ( L2 ) = 40;  
  
   list <int>::iterator vIter;  
   cout << "The list L2 is: ( ";  
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L2 is: ( 40 10 20 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratorfrontinsertiteratora-frontinsertiteratorfrontinsertiterator"></a><a name="front_insert_iterator__front_insert_iterator"></a>  front_insert_iterator:: front_insert_iterator  
 Damit wird ein Iterator erstellt, mit dem Elemente an den Anfang eines bestimmten Containerobjekts eingefügt werden können.  
  
```  
explicit front_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Parameter  
 `_Cont`  
 Die Container-Objekt, in dem die `front_insert_iterator` zum Einfügen von Elementen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `front_insert_iterator` für den Parameter-Container-Objekt.  
  
### <a name="example"></a>Beispiel  
  
```  
// front_insert_iterator_front_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for (i = -1 ; i < 9 ; ++i )    
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   // Using the member function to insert an element  
   front_inserter ( L ) = 20;  
  
   // Alternatively, one may use the template function  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatorstara-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_star"></a>  front_insert_iterator:: Operator *  
 Dereferenziert den einfügen-Iterator, der ihm adressierten Element zurückzugeben.  
  
```  
front_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Member-Funktion gibt den Wert des adressierten Elements zurück.  
  
### <a name="remarks"></a>Hinweise  
 Zum Implementieren des ausgabeiteratorausdrucks **\*Iter** = **Wert**. Wenn **Iter** ist ein Iterator, der ein Element in einer Sequenz dann **\*Iter** = **Wert** ersetzt das Element mit dem Wert und die Gesamtzahl der Elemente in der Sequenz nicht ändert.  
  
### <a name="example"></a>Beispiel  
  
```  
// front_insert_iterator_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for ( i = -1 ; i < 9 ; ++i )   
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 20;  
  
   // Alternatively, you may use  
   front_inserter ( L ) = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatoraddadda-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_add_add"></a>  front_insert_iterator::Operator++  
 Inkrementiert `back_insert_iterator` zum folgenden Speicherort, an dem ein Wert gespeichert werden kann.  
  
```  
front_insert_iterator<Container>& operator++();

front_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `front_insert_iterator` Adressierung der nächsten Position, an dem ein Wert gespeichert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Operatoren Preincrementation und Postincrementation zurückgibt das gleiche Ergebnis.  
  
### <a name="example"></a>Beispiel  
  
```  
// front_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatoreqa-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_eq"></a>  front_insert_iterator:: Operator =  
 (Per Push) Fügt einen Wert auf der Vorderseite des Containers.  
  
```  
front_insert_iterator<Container>& operator=(typename Container::const_reference val);

front_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Parameter  
 ` val`  
 Der Wert, der den Container zugewiesen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das letzte Element am Anfang des Containers eingefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Memberoperator ergibt `container.push_front( val)`, dann gibt `*this`.  
  
 Der zweite Operator für den Memberzugriff ausgewertet wird.  
  
 `container->push_front((typename Container::value_type&&) val)`,  
  
 Gibt `*this`.  
  
### <a name="example"></a>Beispiel  
  
```  
// front_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratorreferencea-frontinsertiteratorreference"></a><a name="front_insert_iterator__reference"></a>  front_insert_iterator:: Reference  
 Ein Typ, der einen Verweis auf ein Element in einer Sequenz enthält, die durch den zugehörigen Container gesteuert wird.  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="example"></a>Beispiel  
  
```  
// front_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L;  
   front_insert_iterator<list<int> > fiivIter( L );  
 *fiivIter = 10;  
 *fiivIter = 20;  
 *fiivIter = 30;  
  
   list<int>::iterator LIter;  
   cout << "The list L is: ( ";  
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++)  
      cout << *LIter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator<list<int> >::reference   
        RefFirst = *(L.begin ( ));  
   cout << "The first element in the list L is: "   
        << RefFirst << "." << endl;  
}  
\* Output:   
The list L is: ( 30 20 10 ).  
The first element in the list L is: 30.  
*\  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\< Iterator>](../standard-library/iterator.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

