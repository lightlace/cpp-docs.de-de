---
title: "stack-Klasse"
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
  - "std::stack"
  - "std.stack"
  - "stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Stapel Stack-Klasse"
  - "stack-Klasse"
ms.assetid: 02151c1e-eab0-41b8-be94-a839ead78ecf
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# stack-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Vorlagencontainer-Adapterklasse, die die Funktionalität einschränkt, indem sie den Zugriff auf das Element beschränkt, das zuletzt zu einem zugrunde liegenden Containertyp hinzugefügt wurde. Die stack-Klasse wird verwendet, wenn es unverzichtbar ist, dass Stapelvorgänge nur für den Container ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Type, class Container= deque <Type>>  
class stack  
```  
  
#### <a name="parameters"></a>Parameter  
 *Typ*  
 Der Datentyp der Elemente, die im Stapel gespeichert werden sollen.  
  
 `Container`  
 Der Typ des zugrunde liegenden Containers, der verwendet wird, um den Stapel zu implementieren. Der Standardwert ist die Klasse `deque`*\< Typ>*.  
  
## <a name="remarks"></a>Hinweise  
 Die Elemente der Klasse **Typ** in die erste Vorlage festgelegten Parameter, der ein Stapelobjekt sind gleichbedeutend mit [Werttyp](#stack__value_type) muss den Typ des Elements in der zugrunde liegenden Containerklasse entsprechen **Container** durch den zweiten Vorlagenparameter festgelegt. Die **Typ** zugewiesen werden, werden muss, ist es möglich, Objekte dieses Typs zu kopieren und Zuweisen von Werten zu Variablen dieses Typs.  
  
 Geeignet für Stapel zugrunde liegenden Containerklassen umfassen [Deque](../standard-library/deque-class.md), [list-Klasse](../standard-library/list-class.md), und [vector-Klasse](vector%20Class.md), oder einem anderen sequenzcontainer, der die Operationen unterstützt **wieder**, `push_back`, und `pop_back`. Die zugrunde liegende Containerklasse wird im Containeradapter gekapselt, der nur den begrenzten Satz der Memberfunktionen des Sequenzcontainers als öffentliche Schnittstelle verfügbar macht.  
  
 Im Stapel Objekte auf Gleichheit vergleichbar, wenn und nur dann, wenn die Elemente der Klasse **Typ** Gleichheit vergleichbar sind und weniger-als vergleichbar sein, wenn und nur dann, wenn die Elemente der Klasse **Typ** kleiner-als vergleichbar.  
  
-   Die stack-Klasse unterstützt eine LIFO-Datenstruktur (Last In – First Out). Eine gute Analogie, um sich dies zu merken, ist ein Stapel von Tellern. Elemente (Teller) können eingefügt, überprüft oder nur vom Anfang des Stapels entnommen werden, was dem letzten Element am Ende des Basiscontainers entspricht. Die Beschränkung, nur auf das oberste Element zuzugreifen, ist der Grund für die Verwendung der stack-Klasse.  
  
-   Die [queue-Klasse](../standard-library/queue-class.md) Datenstruktur einer First in, First Out (FIFO) unterstützt. Eine gute Analogie, um sich dies zu merken, sind Personen, die an einem Bankschalter anstehen. Elemente (Personen) können am Ende der Schlange hinzugefügt werden und vom Anfang der Schlange entfernt werden. Sowohl der Anfang als auch das Ende einer Schlange können überprüft werden. Die in dieser Weise umgesetzte Beschränkung, nur auf das vorderste und das hinterste Element zugreifen zu können, ist der Grund für das Verwenden der queue-Klasse.  
  
-   Die [Priority_queue-Klasse](../standard-library/priority-queue-class.md) sortiert die Elemente, damit das größte Element immer an der obersten Position befindet. Die Klasse unterstützt Einfügen eines Elements sowie die Prüfung und Entfernung des obersten Elements. Eine gute Analogie, um sich dies zu merken, sind Personen, die in einer Schlange stehen, in der sie nach Alter, Größe oder einem anderen Kriterium angeordnet sind.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[Stapel](#stack__stack)|Erstellt ein `stack`-Objekt, das leer oder eine Kopie eines Basiscontainerobjekts ist.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#stack__container_type)|Ein Typ, der den Basiscontainer bereitstellt, der durch ein `stack`-Objekt übernommen werden soll.|  
|[size_type](#stack__size_type)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `stack` darstellen kann.|  
|[Werttyp](#stack__value_type)|Ein Typ, der den Typ des Objekts angibt, das in einem `stack`-Objekt als Element gespeichert wird.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[leere](#stack__empty)|Testet, ob das `stack`-Objekt ist leer.|  
|[POP](#stack__pop)|Entfernt das Element aus der obersten Position des `stack`-Objekts.|  
|[Push](#stack__push)|Fügt ein Element an der obersten Position des `stack`-Objekts hinzu.|  
|[Größe](#stack__size)|Gibt die Anzahl von Elementen in der `stack` zurück.|  
|[Nach oben](#stack__top)|Gibt einen Verweis auf das Element in der obersten Position des `stack`-Objekts zurück.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Stapel>  
  
 **Namespace:** std  
  
##  <a name="a-namestackcontainertypea-stackcontainertype"></a><a name="stack__container_type"></a>  Stack:: container_type  
 Ein Typ, den grundlegenden Container angepasst werden.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Container` dar. Alle drei STL Sequenz Container-Klassen – Vector-Klasse List-Klasse und die Standard-Klasse Deque – erfüllen die Anforderungen, die für einen Stapelobjekt als Basis Container verwendet werden. Benutzerdefinierte Typen erfüllen diese Anforderung können auch verwendet werden.  
  
 Weitere Informationen zu `Container`, finden Sie im Abschnitt "Hinweise" der [stack-Klasse](../standard-library/stack-class.md) Thema.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Stack:: Stack](#stack__stack) ein Beispiel zum Deklarieren und Verwenden von `container_type`.  
  
##  <a name="a-namestackemptya-stackempty"></a><a name="stack__empty"></a>  Stack:: Empty  
 Testet, ob ein Stapel leer ist.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** wenn der Stapel leer, andernfalls ist **false** Wenn der Stapel nicht leer ist.  
  
### <a name="example"></a>Beispiel  
  
```  
// stack_empty.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack <int> s1, s2;  
  
   s1.push( 1 );  
  
   if ( s1.empty( ) )  
      cout << "The stack s1 is empty." << endl;  
   else  
      cout << "The stack s1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The stack s2 is empty." << endl;  
   else  
      cout << "The stack s2 is not empty." << endl;  
}  
```  
  
```Output  
The stack s1 is not empty.  
The stack s2 is empty.  
```  
  
##  <a name="a-namestackpopa-stackpop"></a><a name="stack__pop"></a>  Stack:: POP  
 Entfernt das Element von der obersten Position des Stapels.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Stapel muss die Memberfunktion anwenden nicht leer sein. Der Anfang des Stapels ist die Position der zuletzt hinzugefügte Element und das letzte Element am Ende des Containers.  
  
### <a name="example"></a>Beispiel  
  
```  
// stack_pop.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
  
   s1.pop( );  
  
   i = s1.size( );  
   cout << "After a pop, the stack length is "   
        << i << "." << endl;  
  
   i = s1.top( );  
   cout << "After a pop, the element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
After a pop, the stack length is 2.  
After a pop, the element at the top of the stack is 20.  
```  
  
##  <a name="a-namestackpusha-stackpush"></a><a name="stack__push"></a>  Stack:: Push  
 Fügt ein Element auf dem oberen Ende des Stapels.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>Parameter  
 ` val`  
 Das Element am Anfang des Stapels hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
 Der Anfang des Stapels ist die Position der zuletzt hinzugefügte Element und das letzte Element am Ende des Containers.  
  
### <a name="example"></a>Beispiel  
  
```  
// stack_push.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
```  
  
##  <a name="a-namestacksizea-stacksize"></a><a name="stack__size"></a>  Stack:: Size  
 Gibt die Anzahl der Elemente im Stapel zurück.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Länge des Stapels.  
  
### <a name="example"></a>Beispiel  
  
```  
// stack_size.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
   stack <int>::size_type i;  
  
   s1.push( 1 );  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   s1.push( 2 );  
   i = s1.size( );  
   cout << "The stack length is now " << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 1.  
The stack length is now 2.  
```  
  
##  <a name="a-namestacksizetypea-stacksizetype"></a><a name="stack__size_type"></a>  Stack:: size_type  
 Ein Ganzzahltyp ohne Vorzeichen, die die Anzahl der Elemente in einem Stapel darstellen kann.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für `size_type` des Basis-Containers vom Stapel angepasst.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Größe](#stack__size) ein Beispiel zum Deklarieren und Verwenden von `size_type`.  
  
##  <a name="a-namestackstacka-stackstack"></a><a name="stack__stack"></a>  Stack:: Stack  
 Erstellt einen Stapel, die leer ist oder, die eine Kopie einer Basis Container-Klasse.  
  
```  
stack();

explicit stack(const container_type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Der Container, der der konstruierte Stapel ist, eine Kopie sein soll.  
  
### <a name="example"></a>Beispiel  
  
```  
// stack_stack.cpp  
// compile with: /EHsc  
#include <stack>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares stack with default deque base container  
   stack <char> dsc1;  
  
   //Explicitly declares a stack with deque base container  
   stack <char, deque<char> > dsc2;  
  
   // Declares a stack with vector base containers  
   stack <int, vector<int> > vsi1;  
  
   // Declares a stack with list base container  
   stack <int, list<int> > lsi;  
  
   // The second member function copies elements from a container  
   vector<int> v1;  
   v1.push_back( 1 );  
   stack <int, vector<int> > vsi2( v1 );  
   cout << "The element at the top of stack vsi2 is "  
        << vsi2.top( ) << "." << endl;  
}  
```  
  
```Output  
The element at the top of stack vsi2 is 1.  
```  
  
##  <a name="a-namestacktopa-stacktop"></a><a name="stack__top"></a>  Stack:: Top  
 Gibt einen Verweis auf ein Element am Anfang des Stapels.  
  
```  
reference top();

const_reference top() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das letzte Element im Container am Anfang des Stapels.  
  
### <a name="remarks"></a>Hinweise  
 Der Stapel muss die Memberfunktion anwenden nicht leer sein. Der Anfang des Stapels ist die Position der zuletzt hinzugefügte Element und das letzte Element am Ende des Containers.  
  
 Wenn der Rückgabewert der **oben** zugewiesen ist ein `const_reference`, das Stack-Objekt kann nicht geändert werden. Wenn der Rückgabewert der **oben** zugewiesen ist eine **Verweis**, das Stack-Objekt geändert werden kann.  
  
### <a name="example"></a>Beispiel  
  
```  
// stack_top.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 1 );  
   s1.push( 2 );  
  
   int& i = s1.top( );  
   const int& ii = s1.top( );  
  
   cout << "The top integer of the stack s1 is "  
        << i << "." << endl;  
   i--;  
   cout << "The next integer down is "<< ii << "." << endl;  
}  
```  
  
```Output  
The top integer of the stack s1 is 2.  
The next integer down is 1.  
```  
  
##  <a name="a-namestackvaluetypea-stackvaluetype"></a><a name="stack__value_type"></a>  Stack:: value_type  
 Ein Typ, der den Typ des Objekts als Element in einem Stapel gespeichert darstellt.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für `value_type` des Basis-Containers vom Stapel angepasst.  
  
### <a name="example"></a>Beispiel  
  
```  
// stack_value_type.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   stack<int> s1;  
   s1.push( AnInt );  
   cout << "The element at the top of the stack is "  
        << s1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the stack is 69.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

