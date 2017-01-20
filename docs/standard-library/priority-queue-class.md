---
title: "priority_queue-Klasse"
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
  - "std.priority_queue"
  - "priority_queue"
  - "std::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "priority_queue-Klasse"
ms.assetid: 69fca9cc-a449-4be4-97b7-02ca5db9cbb2
caps.latest.revision: 25
caps.handback.revision: "25"
ms.author: "corob"
manager: "ghogen"
---
# priority_queue-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Vorlage Adapter Containerklasse, die eine Einschränkung des Beschränken des Zugriffs auf das oberste Element von einigen zugrunde liegenden Containertyp, der immer am größten ist, oder mit der höchsten Priorität Funktionalität bereitstellt. Die Priority_queue können neue Elemente hinzugefügt werden, und das oberste Element der Priority_queue überprüft oder entfernt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Type, class Container= vector <Type>, class Compare= less <typename Container ::value_type>>  
class priority_queue  
```  
  
#### <a name="parameters"></a>Parameter  
 *Typ*  
 Der Datentyp des Elements in der Priority_queue gespeichert werden.  
  
 `Container`  
 Der Typ des zugrunde liegenden Container verwendet, um die Priority_queue implementieren.  
  
 *Vergleichen*  
 Der Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel bestimmen deren relative Reihenfolge in der Priority_queue vergleichen können. Dieses Argument ist optional und das binäre Prädikat **weniger***\<***Typename** *Container***:: Value_type***>* ist der Standardwert.  
  
## <a name="remarks"></a>Hinweise  
 Die Elemente der Klasse **Typ** abgegeben, die in die erste Vorlage Parameter eines Warteschlangenobjekts sind gleichbedeutend mit [Value_type](#priority_queue__value_type) muss der Typ des Elements in der zugrunde liegenden Containerklasse entsprechen **Container** durch den zweiten Vorlagenparameter festgelegt. Die **Typ** zugewiesen werden, werden muss, ist es möglich, Objekte dieses Typs zu kopieren und Zuweisen von Werten zu Variablen dieses Typs.  
  
 Die Priority_queue sortiert die gesteuerte Sequenz, indem ein gespeichertes Funktionsobjekt Klasse aufrufen **Merkmale**. Im Allgemeinen müssen die Elemente der Vorwärtsiteratoren etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass beliebige zwei Elemente möglicherweise als gleichwertig bestimmt werden (in dem Sinne, dass keins geringer als das Andere ist), oder dass eins geringer als das Andere ist. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen. Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht.  
  
 Geeignete zugrunde liegenden Containerklassen für Priority_queue zählen [Deque-Klasse](../standard-library/deque-class.md) und der standardmäßige [vector-Klasse](vector%20Class.md) oder einem anderen sequenzcontainer, der die Operationen unterstützt `front`, `push_back`, und `pop_back` und einen Iterator mit wahlfreiem Zugriff. Die zugrunde liegende Containerklasse wird im Containeradapter gekapselt, der nur den begrenzten Satz der Memberfunktionen des Sequenzcontainers als öffentliche Schnittstelle verfügbar macht.  
  
 Hinzufügen und Entfernen von Elementen aus einem `priority_queue` beide logarithmische Komplexität haben. Zugreifen auf Elemente in einem `priority_queue` weist Konstante Komplexität.  
  
 Es gibt drei Arten von Container-Adaptern STL definiert: Stapel, Warteschlangen und Priority_queue. Jede schränkt die Funktionalität von einigen zugrunde liegenden Container-Klasse bietet eine präzise gesteuerte Oberfläche auf eine standard-Datenstruktur.  
  
-   Die [stack-Klasse](../standard-library/stack-class.md) Datenstruktur einer Last in, First Out (LIFO) unterstützt. Eine gute Analogie, um sich dies zu merken, ist ein Stapel von Tellern. Elemente (Teller) können eingefügt, überprüft oder nur vom Anfang des Stapels entnommen werden, was dem letzten Element am Ende des Basiscontainers entspricht. Die Beschränkung, nur auf das oberste Element zuzugreifen, ist der Grund für die Verwendung der stack-Klasse.  
  
-   Die [queue-Klasse](../standard-library/queue-class.md) Datenstruktur einer First in, First Out (FIFO) unterstützt. Eine gute Analogie, um sich dies zu merken, sind Personen, die an einem Bankschalter anstehen. Elemente (Personen) können am Ende der Schlange hinzugefügt werden und vom Anfang der Schlange entfernt werden. Sowohl der Anfang als auch das Ende einer Schlange können überprüft werden. Die Einschränkung für den Zugriff auf nur die Vorder- und Rückseite Elemente auf diese Weise ist der Grund für die Verwendung der Queue-Klasse.  
  
-   Priority_queue-Klasse sortiert die Elemente, damit das größte Element immer an der obersten Position befindet. Die Klasse unterstützt Einfügen eines Elements sowie die Prüfung und Entfernung des obersten Elements. Eine gute Analogie, um sich dies zu merken, sind Personen, die in einer Schlange stehen, in der sie nach Alter, Größe oder einem anderen Kriterium angeordnet sind.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[priority_queue](#priority_queue__priority_queue)|Erstellt eine `priority_queue` leer ist oder, ist eine Kopie eines Bereichs eines Containerobjekts Basis oder anderer `priority_queue`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#priority_queue__container_type)|Ein Typ, der den Basiscontainer bereitstellt, der durch ein `priority_queue`-Objekt übernommen werden soll.|  
|[size_type](#priority_queue__size_type)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `priority_queue` darstellen kann.|  
|[Werttyp](#priority_queue__value_type)|Ein Typ, der den Typ des Objekts angibt, das in einem `priority_queue`-Objekt als Element gespeichert wird.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[leere](#priority_queue__empty)|Testet, ob das `priority_queue`-Objekt ist leer.|  
|[POP](#priority_queue__pop)|Entfernt das größte Element von der `priority_queue` von der obersten Position.|  
|[Push](#priority_queue__push)|Fügt ein Element an der Prioritätswarteschlange anhand der Priorität des Elements vom Operator <.|  
|[Größe](#priority_queue__size)|Gibt die Anzahl von Elementen in der `priority_queue` zurück.|  
|[Nach oben](#priority_queue__top)|Gibt einen Const-Verweis auf das größte Element am Anfang der `priority_queue`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Warteschlange>  
  
 **Namespace:** std  
  
##  <a name="a-namepriorityqueuecontainertypea-priorityqueuecontainertype"></a><a name="priority_queue__container_type"></a>  priority_queue:: container_type  
 Ein Typ, den grundlegenden Container angepasst werden.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Container` dar. Die STL Sequenz Container-Klasse Deque und der Standard-Klasse-Vektor erfüllen die als Basis Container für ein Objekt Priority_queue verwendet werden. Benutzerdefinierte Typen, die die Anforderungen erfüllen können auch verwendet werden.  
  
 Weitere Informationen zu `Container`, finden Sie im Abschnitt "Hinweise" der [Priority_queue-Klasse](../standard-library/priority-queue-class.md) Thema.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Priority_queue](#priority_queue__priority_queue) ein Beispiel zum Deklarieren und Verwenden von `container_type`.  
  
##  <a name="a-namepriorityqueueemptya-priorityqueueempty"></a><a name="priority_queue__empty"></a>  priority_queue:: Empty  
 Testet, ob eine Priority_queue leer ist.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 **true** ist die Priority_queue leer ist; **false** Wenn die Priority_queue nicht leer ist.  
  
### <a name="example"></a>Beispiel  
  
```  
// pqueue_empty.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares priority_queues with default deque base container  
   priority_queue <int> q1, s2;  
  
   q1.push( 1 );  
  
   if ( q1.empty( ) )  
      cout << "The priority_queue q1 is empty." << endl;  
   else  
      cout << "The priority_queue q1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The priority_queue s2 is empty." << endl;  
   else  
      cout << "The priority_queue s2 is not empty." << endl;  
}  
```  
  
```Output  
The priority_queue q1 is not empty.  
The priority_queue s2 is empty.  
```  
  
##  <a name="a-namepriorityqueuepopa-priorityqueuepop"></a><a name="priority_queue__pop"></a>  priority_queue:: POP  
 Entfernt das größte Element von der Priority_queue von der obersten Position.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>Hinweise  
 Priority_queue darf nicht leer sein, damit die Memberfunktion angewendet wird. Am Anfang der Priority_queue wird immer von dem größten Element im Container belegt.  
  
### <a name="example"></a>Beispiel  
  
```  
// pqueue_pop.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue <int> q1, s2;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   priority_queue <int>::size_type i, iii;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
  
   q1.pop( );  
  
   iii = q1.size( );  
   cout << "After a pop, the priority_queue length is "   
        << iii << "." << endl;  
  
   const int& iv = q1.top( );  
   cout << "After a pop, the element at the top of the "  
        << "priority_queue is " << iv << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
After a pop, the priority_queue length is 2.  
After a pop, the element at the top of the priority_queue is 20.  
```  
  
##  <a name="a-namepriorityqueuepriorityqueuea-priorityqueuepriorityqueue"></a><a name="priority_queue__priority_queue"></a>  priority_queue:: priority_queue  
 Erstellt eine Priority_queue, die leer ist oder eine Kopie eines Bereichs ein Basis-Container-Objekt oder einem anderen Priority_queue ist.  
  
```  
priority_queue();

explicit priority_queue(const Traits&_comp);

priority_queue(const Traits&_comp, const container_type& _Cont);

priority_queue(const priority_queue& right);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last, const Traits&_comp);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last, const Traits&_comp, const container_type& _Cont);
```  
  
### <a name="parameters"></a>Parameter  
 *_ comp*  
 Die Vergleichsfunktion vom Typ **ConstTraits** verwendet, um die Elemente in der Priority_queue sortieren, die standardmäßig die Funktion des Containers Basis zu vergleichen.  
  
 `_Cont`  
 Der grundlegende Container, die den konstruierten Priority_queue ist eine Kopie.  
  
 ` right`  
 Die Priority_queue, die der erstellte Satz ist eine Kopie sein soll.  
  
 ` first`  
 Die Position des ersten Elements in dem zu kopierenden Elementbereich.  
  
 ` last`  
 Die Position des ersten Elements nach dem zu kopierenden Elementbereich.  
  
### <a name="remarks"></a>Hinweise  
 Jede der ersten drei Konstruktoren gibt eine leere ursprüngliche Priority_queue, die zweite auch Angabe des Typs der Vergleichsfunktion ( ` comp`) verwendet werden, in der Reihenfolge der Elemente und drittens explizit anzugeben, die `container_type` ( `_Cont`) verwendet werden. Das Schlüsselwort **explizite** werden bestimmte Arten automatischer Typumwandlung unterdrückt.  
  
 Der vierte Konstruktor gibt eine Kopie der Priority_queue ` right`.  
  
 Die letzten drei Konstruktoren kopieren den Bereich [ * First-und last-*) von einem Container und die Werte einer Priority_queue mit Explizitheit bei Angabe des Typs der Vergleichsfunktion der Klasse initialisieren **Merkmale** und `container_type`.  
  
### <a name="example"></a>Beispiel  
  
```  
// pqueue_ctor.cpp  
// compile with: /EHsc  
#include <queue>  
#include <vector>  
#include <deque>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The first member function declares priority_queue  
   // with a default vector base container  
   priority_queue <int> q1;  
   cout << "q1 = ( ";  
   while ( !q1.empty( ) )  
   {  
      cout << q1.top( ) << " ";  
      q1.pop( );  
   }  
   cout << ")" << endl;  
  
   // Explicitly declares a priority_queue with nondefault  
   // deque base container  
   priority_queue <int, deque <int> > q2;  
   q2.push( 5 );  
   q2.push( 15 );  
   q2.push( 10 );  
   cout << "q2 = ( ";  
   while ( !q2.empty( ) )  
   {  
      cout << q2.top( ) << " ";  
      q2.pop( );  
   }  
   cout << ")" << endl;  
  
   // This method of printing out the elements of a priority_queue  
   // removes the elements from the priority queue, leaving it empty  
   cout << "After printing, q2 has " << q2.size( ) << " elements." << endl;  
  
   // The third member function declares a priority_queue   
   // with a vector base container and specifies that the comparison   
   // function greater is to be used for ordering elements  
   priority_queue <int, vector<int>, greater<int> > q3;  
   q3.push( 2 );  
   q3.push( 1 );  
   q3.push( 3 );  
   cout << "q3 = ( ";  
   while ( !q3.empty( ) )  
   {  
      cout << q3.top( ) << " ";  
      q3.pop( );  
   }  
   cout << ")" << endl;  
  
   // The fourth member function declares a priority_queue and  
   // initializes it with elements copied from another container:  
   // first, inserting elements into q1, then copying q1 elements into q4  
   q1.push( 100 );  
   q1.push( 200 );  
   priority_queue <int> q4( q1 );  
   cout << "q4 = ( ";     
   while ( !q4.empty( ) )  
   {  
      cout << q4.top( ) << " ";  
      q4.pop( );  
   }  
   cout << ")" << endl;  
  
   // Creates an auxiliary vector object v5 to be used to initialize q5  
   vector <int> v5;  
   vector <int>::iterator v5_Iter;  
   v5.push_back( 10 );  
   v5.push_back( 30 );  
   v5.push_back( 20 );  
   cout << "v5 = ( " ;  
   for ( v5_Iter = v5.begin( ) ; v5_Iter != v5.end( ) ; v5_Iter++ )  
      cout << *v5_Iter << " ";  
   cout << ")" << endl;  
  
   // The fifth member function declares and  
   // initializes a priority_queue q5 by copying the  
   // range v5[ first,  last) from vector v5  
   priority_queue <int> q5( v5.begin( ), v5.begin( ) + 2 );  
   cout << "q5 = ( ";  
   while ( !q5.empty( ) )  
   {  
      cout << q5.top( ) << " ";  
      q5.pop( );  
   }  
   cout << ")" << endl;  
  
   // The sixth member function declares a priority_queue q6  
   // with a comparison function greater and initializes q6  
   // by copying the range v5[ first,  last) from vector v5  
   priority_queue <int, vector<int>, greater<int> >   
      q6( v5.begin( ), v5.begin( ) + 2 );  
   cout << "q6 = ( ";  
   while ( !q6.empty( ) )  
   {  
      cout << q6.top( ) << " ";  
      q6.pop( );  
   }  
   cout << ")" << endl;  
}  
```  
  
##  <a name="a-namepriorityqueuepusha-priorityqueuepush"></a><a name="priority_queue__push"></a>  priority_queue:: Push  
 Fügt ein Element an der Prioritätswarteschlange anhand der Priorität des Elements vom Operator <.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>Parameter  
 ` val`  
 Das Element am Anfang der Priority_queue hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
 Am Anfang der Priority_queue ist die Position das größte Element im Container.  
  
### <a name="example"></a>Beispiel  
  
```  
// pqueue_push.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue<int> q1;  
  
   q1.push( 10 );  
   q1.push( 30 );  
   q1.push( 20 );  
  
   priority_queue<int>::size_type i;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
```  
  
##  <a name="a-namepriorityqueuesizea-priorityqueuesize"></a><a name="priority_queue__size"></a>  priority_queue:: Size  
 Gibt die Anzahl der Elemente in der Priority_queue zurück.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Länge der der Priority_queue.  
  
### <a name="example"></a>Beispiel  
  
```  
// pqueue_size.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue <int> q1, q2;  
   priority_queue <int>::size_type i;  
  
   q1.push( 1 );  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   q1.push( 2 );  
   i = q1.size( );  
   cout << "The priority_queue length is now " << i << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 1.  
The priority_queue length is now 2.  
```  
  
##  <a name="a-namepriorityqueuesizetypea-priorityqueuesizetype"></a><a name="priority_queue__size_type"></a>  priority_queue:: size_type  
 Ein Ganzzahltyp ohne Vorzeichen, die die Anzahl der Elemente in einem Priority_queue darstellen kann.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den `size_type` des Basis-Containers angepasst, indem die Priority_queue.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Größe](#priority_queue__size) ein Beispiel zum Deklarieren und Verwenden von `size_type`.  
  
##  <a name="a-namepriorityqueuetopa-priorityqueuetop"></a><a name="priority_queue__top"></a>  priority_queue:: Top  
 Gibt einen konstanten Verweis auf das größte Element am oberen Rand von priority_queue.  
  
```  
const_reference top() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das größte Element, laut der **Merkmale** -Funktion, die Priority_queue-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Priority_queue darf nicht leer sein, damit die Memberfunktion angewendet wird.  
  
### <a name="example"></a>Beispiel  
  
```  
// pqueue_top.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue<int> q1;  
  
   q1.push( 10 );  
   q1.push( 30 );  
   q1.push( 20 );  
  
   priority_queue<int>::size_type i;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
```  
  
##  <a name="a-namepriorityqueuevaluetypea-priorityqueuevaluetype"></a><a name="priority_queue__value_type"></a>  priority_queue:: value_type  
 Ein Typ, der den Typ des Objekts als ein Element in einem Priority_queue darstellt.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den `value_type` des Basis-Containers angepasst, indem die Priority_queue.  
  
### <a name="example"></a>Beispiel  
  
```  
// pqueue_value_type.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares priority_queues with default deque base container  
   priority_queue<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   priority_queue<int> q1;  
   q1.push( AnInt );  
   cout << "The element at the top of the priority_queue is "  
        << q1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the priority_queue is 69.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

