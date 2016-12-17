---
title: "queue-Klasse"
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
  - "std.queue"
  - "std::queue"
  - "queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queue-Klasse"
ms.assetid: 28c20ab0-3a72-4185-9e0f-5a44eea0e204
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# queue-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Vorlage Adapter Containerklasse, die eine Einschränkung der Funktionalität für einen zugrunde liegenden Containertyp, Beschränken des Zugriffs auf die Vorder- und Rückseite Elemente bereitstellt. Elemente können an der Rückseite hinzugefügt oder entfernt Sie von der Vorderseite und Elemente am Ende der Warteschlange überprüft werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Type, class Container = deque <Type>>  
class queue  
```  
  
#### <a name="parameters"></a>Parameter  
 *Typ*  
 Der Datentyp der Elemente in der Warteschlange gespeichert werden  
  
 `Container`  
 Der Typ des zugrunde liegenden Container verwendet, um die Warteschlange zu implementieren.  
  
## <a name="remarks"></a>Hinweise  
 Die Elemente der Klasse **Typ** abgegeben, die in die erste Vorlage Parameter eines Warteschlangenobjekts sind gleichbedeutend mit [Value_type](#queue__value_type) muss der Typ des Elements in der zugrunde liegenden Containerklasse entsprechen **Container** durch den zweiten Vorlagenparameter festgelegt. Die **Typ** zugewiesen werden, werden muss, ist es möglich, Objekte dieses Typs zu kopieren und Zuweisen von Werten zu Variablen dieses Typs.  
  
 Geeignete zugrunde liegenden Containerklassen für die Warteschlange umfassen [Deque](../standard-library/deque-class.md) und [Liste](../standard-library/list-class.md), oder einem anderen sequenzcontainer, der die Operationen unterstützt `front`, **wieder**, `push_back`, und `pop_front`. Die zugrunde liegende Containerklasse wird im Containeradapter gekapselt, der nur den begrenzten Satz der Memberfunktionen des Sequenzcontainers als öffentliche Schnittstelle verfügbar macht.  
  
 Die Warteschlange Objekte auf Gleichheit vergleichbar, wenn und nur dann, wenn die Elemente der Klasse **Typ** Gleichheit vergleichbar sind und weniger-als vergleichbar sein, wenn und nur dann, wenn die Elemente der Klasse **Typ** kleiner-als vergleichbar.  
  
 Es gibt drei Arten von Container-Adaptern STL definiert: Stapel, Warteschlangen und Priority_queue. Jede schränkt die Funktionalität von einigen zugrunde liegenden Container-Klasse bietet eine präzise gesteuerte Oberfläche auf eine standard-Datenstruktur.  
  
-   Die [stack-Klasse](../standard-library/stack-class.md) Datenstruktur einer Last in, First Out (LIFO) unterstützt. Eine gute Analogie, um sich dies zu merken, ist ein Stapel von Tellern. Elemente (Teller) können eingefügt, überprüft oder nur vom Anfang des Stapels entnommen werden, was dem letzten Element am Ende des Basiscontainers entspricht. Die Beschränkung, nur auf das oberste Element zuzugreifen, ist der Grund für die Verwendung der stack-Klasse.  
  
-   Queue-Klasse unterstützt die Datenstruktur einer First in, First Out (FIFO). Eine gute Analogie, um sich dies zu merken, sind Personen, die an einem Bankschalter anstehen. Elemente (Personen) können am Ende der Schlange hinzugefügt werden und vom Anfang der Schlange entfernt werden. Sowohl der Anfang als auch das Ende einer Schlange können überprüft werden. Die Einschränkung für den Zugriff auf nur die Vorder- und Rückseite Elemente auf diese Weise ist der Grund für die Verwendung der Queue-Klasse.  
  
-   Die [Priority_queue-Klasse](../standard-library/priority-queue-class.md) sortiert die Elemente, damit das größte Element immer an der obersten Position befindet. Die Klasse unterstützt Einfügen eines Elements sowie die Prüfung und Entfernung des obersten Elements. Eine gute Analogie, um sich dies zu merken, sind Personen, die in einer Schlange stehen, in der sie nach Alter, Größe oder einem anderen Kriterium angeordnet sind.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[Warteschlange](#queue__queue)|Erstellt ein `queue`-Objekt, das leer oder eine Kopie eines Basiscontainerobjekts ist.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#queue__container_type)|Ein Typ, den grundlegenden Container von angepasst werden die `queue`.|  
|[size_type](#queue__size_type)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `queue` darstellen kann.|  
|[Werttyp](#queue__value_type)|Ein Typ, der den Typ des Objekts angibt, das in einem `queue`-Objekt als Element gespeichert wird.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[Zurück](#queue__back)|Gibt ein Verweis auf die letzte und die zuletzt Element auf der Rückseite des hinzugefügt der `queue`.|  
|[leere](#queue__empty)|Testet, ob das `queue`-Objekt ist leer.|  
|[Vorderseite](#queue__front)|Gibt einen Verweis auf das erste Element am Anfang der `queue`.|  
|[POP](#queue__pop)|Entfernt ein Element vom Anfang der `queue`.|  
|[Push](#queue__push)|Fügt ein Element an das Ende der `queue`.|  
|[Größe](#queue__size)|Gibt die Anzahl von Elementen in der `queue` zurück.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Warteschlange>  
  
 **Namespace:** std  
  
##  <a name="a-namequeuebacka-queueback"></a><a name="queue__back"></a>  Queue:: Back  
 Gibt ein Verweis auf die letzte und zuletzt Element an das Ende der Warteschlange hinzugefügt.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das letzte Element der Warteschlange. Wenn die Warteschlange leer ist, ist der Rückgabewert nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert von **wieder** zugewiesen ist ein `const_reference`, das Warteschlangenobjekt kann nicht geändert werden. Wenn der Rückgabewert von **wieder** zugewiesen ist eine **Verweis**, das Warteschlangenobjekt kann geändert werden.  
  
 Beim Kompilieren mit _SECURE_SCL 1 wird ein Laufzeitfehler auftreten, wenn Sie versuchen, ein Element in einer leeren Warteschlange zuzugreifen.  Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Beispiel  
  
```  
// queue_back.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 11 );  
  
   int& i = q1.back( );  
   const int& ii = q1.front( );  
  
   cout << "The integer at the back of queue q1 is " << i   
        << "." << endl;  
   cout << "The integer at the front of queue q1 is " << ii   
        << "." << endl;  
}  
```  
  
##  <a name="a-namequeuecontainertypea-queuecontainertype"></a><a name="queue__container_type"></a>  Queue:: container_type  
 Ein Typ, den grundlegenden Container angepasst werden.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Container` dar. Zwei STL-Containerklassen Sequenz – die List-Klasse und die standardmäßige Deque-Klasse – erfüllen die Anforderungen, die für ein Warteschlangenobjekt als Basis Container verwendet werden. Benutzerdefinierte Typen, die die Anforderungen erfüllen können auch verwendet werden.  
  
 Weitere Informationen zu `Container`, finden Sie im Abschnitt "Hinweise" der [queue-Klasse](../standard-library/queue-class.md) Thema.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Warteschlange](#queue__queue) für ein Beispiel zum Deklarieren und Verwenden von `container_type`.  
  
##  <a name="a-namequeueemptya-queueempty"></a><a name="queue__empty"></a>  Queue:: Empty  
 Testet, ob eine Warteschlange leer ist.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 **true** ist die Warteschlange leer ist; **false** wenn die Warteschlange nicht leer ist.  
  
### <a name="example"></a>Beispiel  
  
```  
// queue_empty.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
   // Declares queues with default deque base container  
   queue <int> q1, q2;  
  
   q1.push( 1 );  
  
   if ( q1.empty( ) )  
      cout << "The queue q1 is empty." << endl;  
   else  
      cout << "The queue q1 is not empty." << endl;  
  
   if ( q2.empty( ) )  
      cout << "The queue q2 is empty." << endl;  
   else  
      cout << "The queue q2 is not empty." << endl;  
}  
```  
  
```Output  
The queue q1 is not empty.  
The queue q2 is empty.  
```  
  
##  <a name="a-namequeuefronta-queuefront"></a><a name="queue__front"></a>  Queue:: Front  
 Gibt einen Verweis auf das erste Element am Anfang der Warteschlange zurück.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das erste Element der Warteschlange. Wenn die Warteschlange leer ist, ist der Rückgabewert nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert der `front` zugewiesen ist ein `const_reference`, das Warteschlangenobjekt kann nicht geändert werden. Wenn der Rückgabewert der `front` zugewiesen ist eine **Verweis**, das Warteschlangenobjekt kann geändert werden.  
  
 Die Memberfunktion gibt einen **Verweis** auf das erste Element der kontrollierten Sequenz, muss das nicht leer sein.  
  
 Beim Kompilieren mit _SECURE_SCL 1 wird ein Laufzeitfehler auftreten, wenn Sie versuchen, ein Element in einer leeren Warteschlange zuzugreifen.  Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Beispiel  
  
```  
// queue_front.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   int& ii = q1.back( );  
   int& iii = q1.front( );  
  
   cout << "The integer at the back of queue q1 is " << ii   
        << "." << endl;  
   cout << "The integer at the front of queue q1 is " << iii   
        << "." << endl;  
}  
```  
  
##  <a name="a-namequeuepopa-queuepop"></a><a name="queue__pop"></a>  Queue:: POP  
 Entfernt ein Element vom Anfang der Warteschlange.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Warteschlange muss die Memberfunktion anwenden nicht leer sein. Am Anfang der Warteschlange ist die Position der zuletzt hinzugefügte Element und das letzte Element am Ende des Containers.  
  
### <a name="example"></a>Beispiel  
  
```  
// queue_pop.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, s2;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   i = q1.front( );  
   cout << "The element at the front of the queue is "  
        << i << "." << endl;  
  
   q1.pop( );  
  
   i = q1.size( );  
   cout << "After a pop the queue length is "   
        << i << "." << endl;  
  
   i = q1. front ( );  
   cout << "After a pop, the element at the front of the queue is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 3.  
The element at the front of the queue is 10.  
After a pop the queue length is 2.  
After a pop, the element at the front of the queue is 20.  
```  
  
##  <a name="a-namequeuepusha-queuepush"></a><a name="queue__push"></a>  Queue:: Push  
 Fügt ein Element an das Ende der Warteschlange an.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>Parameter  
 `val`  
 Das Element an das Ende der Warteschlange hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
 Am Ende der Warteschlange ist die Position der zuletzt hinzugefügte Element und das letzte Element am Ende des Containers.  
  
### <a name="example"></a>Beispiel  
  
```  
// queue_push.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   i = q1.front( );  
   cout << "The element at the front of the queue is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 3.  
The element at the front of the queue is 10.  
```  
  
##  <a name="a-namequeuequeuea-queuequeue"></a><a name="queue__queue"></a>  Queue:: Queue  
 Erstellt eine Warteschlange, die leer ist oder eine Kopie eines Containerobjekts Basis ist.  
  
```  
queue();

explicit queue(const container_type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Die **const** Container, die denen die erstellte Warteschlange ist eine Kopie sein soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Basis Standardcontainer für die Warteschlange ist Deque. Sie können auch Liste als Basis Container angeben, Sie können jedoch angeben Vektor, da die erforderlichen fehlen `pop_front` Member-Funktion.  
  
### <a name="example"></a>Beispiel  
  
```  
// queue_queue.cpp  
// compile with: /EHsc  
#include <queue>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queue with default deque base container  
   queue <char> q1;  
  
   // Explicitly declares a queue with deque base container  
   queue <char, deque<char> > q2;  
  
   // These lines don't cause an error, even though they  
   // declares a queue with a vector base container  
   queue <int, vector<int> > q3;  
   q3.push( 10 );  
   // but the following would cause an error because vector has   
   // no pop_front member function  
   // q3.pop( );  
  
   // Declares a queue with list base container  
   queue <int, list<int> > q4;  
  
   // The second member function copies elements from a container  
   list<int> li1;  
   li1.push_back( 1 );  
   li1.push_back( 2 );  
   queue <int, list<int> > q5( li1 );  
   cout << "The element at the front of queue q5 is "  
        << q5.front( ) << "." << endl;  
   cout << "The element at the back of queue q5 is "  
        << q5.back( ) << "." << endl;  
}  
```  
  
```Output  
The element at the front of queue q5 is 1.  
The element at the back of queue q5 is 2.  
```  
  
##  <a name="a-namequeuesizea-queuesize"></a><a name="queue__size"></a>  Queue:: Size  
 Gibt die Anzahl der Elemente in der Warteschlange.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Länge der Warteschlange.  
  
### <a name="example"></a>Beispiel  
  
```  
// queue_size.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2;  
   queue <int>::size_type i;  
  
   q1.push( 1 );  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   q1.push( 2 );  
   i = q1.size( );  
   cout << "The queue length is now " << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 1.  
The queue length is now 2.  
```  
  
##  <a name="a-namequeuesizetypea-queuesizetype"></a><a name="queue__size_type"></a>  Queue:: size_type  
 Ein Ganzzahltyp ohne Vorzeichen, die die Anzahl der Elemente in einer Warteschlange darstellen kann.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den `size_type` des Basis-Containers angepasst, indem die Warteschlange.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Queue:: Front](#queue__front) ein Beispiel zum Deklarieren und Verwenden von `size_type`.  
  
##  <a name="a-namequeuevaluetypea-queuevaluetype"></a><a name="queue__value_type"></a>  Queue:: value_type  
 Ein Typ, der den Typ des Objekts als Element in einer Warteschlange gespeichert.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den `value_type` des Basis-Containers angepasst, indem die Warteschlange.  
  
### <a name="example"></a>Beispiel  
  
```  
// queue_value_type.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
   // Declares queues with default deque base container  
   queue<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   queue<int> q1;  
   q1.push(AnInt);  
   cout << "The element at the front of the queue is "  
        << q1.front( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the front of the queue is 69.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

