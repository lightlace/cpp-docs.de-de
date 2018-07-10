---
title: priority_queue-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- queue/std::priority_queue::container_type
- queue/std::priority_queue::size_type
- queue/std::priority_queue::value_type
- queue/std::priority_queue::empty
- queue/std::priority_queue::pop
- queue/std::priority_queue::push
- queue/std::priority_queue::size
- queue/std::priority_queue::top
dev_langs:
- C++
helpviewer_keywords:
- std::priority_queue [C++], container_type
- std::priority_queue [C++], size_type
- std::priority_queue [C++], value_type
- std::priority_queue [C++], empty
- std::priority_queue [C++], pop
- std::priority_queue [C++], push
- std::priority_queue [C++], size
- std::priority_queue [C++], top
ms.assetid: 69fca9cc-a449-4be4-97b7-02ca5db9cbb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 149d255dd82d0dff2d2ddb1101b38bf05c69673a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861915"
---
# <a name="priorityqueue-class"></a>priority_queue-Klasse

Eine Vorlagencontainer-Adapterklasse, die die Funktionalität einschränkt, indem sie den Zugriff auf das oberste Element eines zugrunde liegenden Containertyps beschränkt, das immer das größte oder wichtigste Element ist. Der Warteschlange mit hoher Priorität können neue Elemente hinzugefügt werden, und das oberste Element der Warteschlange mit hoher Priorität kann überprüft oder entfernt werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Type, class Container= vector <Type>, class Compare= less <typename Container ::value_type>>
class priority_queue
```

### <a name="parameters"></a>Parameter

*Typ* Elementdatentyp in Priority_queue gespeichert werden.

`Container` Der Typ des zugrunde liegenden Container verwendet, um die Priority_queue implementieren.

*Vergleichen Sie* der Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel, um deren relative Reihenfolge in Priority_queue zu bestimmen, vergleichen können. Dieses Argument ist optional und das binäre Prädikat **weniger***\<*** Typename** *Container ***:: Value_type*** >* ist der Standardwert.

## <a name="remarks"></a>Hinweise

Die Elemente der Klasse **Typ**, die im ersten Vorlagenparameter eines Warteschlangenobjekts festgelegt sind, sind gleichbedeutend mit [value_type](#value_type) und müssen mit dem Elementtyp in der zugrunde liegenden Containerklasse **Container** übereinstimmen, der im zweiten Vorlagenparameter festgelegt ist. Der **Type** muss zuweisbar sein, damit es möglich ist, Objekte dieses Typs zu kopieren und Variablen dieses Typs Werte zuzuweisen.

Der Warteschlange mit hoher Priorität sortiert die von ihr gesteuerte Sequenz, indem ein gespeichertes Funktionsobjekt vom Typ **Traits** aufruft. Im Allgemeinen müssen die Elemente der Vorwärtsiteratoren etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass beliebige zwei Elemente möglicherweise als gleichwertig bestimmt werden (in dem Sinne, dass keins geringer als das Andere ist), oder dass eins geringer als das Andere ist. Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen. Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht.

Geeignete zugrunde liegende Containerklassen für die Warteschlangenklasse mit hoher Priorität sind [deque-Klasse](../standard-library/deque-class.md) und die Standard-[vector-Klasse](../standard-library/vector-class.md) oder ein beliebiger Sequenzcontainer, der die Vorgänge von `front`, `push_back` und `pop_back` und einen Random-Access-Iterator unterstützt. Die zugrunde liegende Containerklasse wird im Containeradapter gekapselt, der nur den begrenzten Satz der Memberfunktionen des Sequenzcontainers als öffentliche Schnittstelle verfügbar macht.

Hinzufügen und Entfernen von Elementen aus einem `priority_queue`; beide haben logarithmische Komplexität. Zugreifen auf Elemente in einem `priority_queue` mit konstanter Komplexität.

Es gibt drei Arten von Containeradaptern, die von der C++-Standardbibliothek definiert werden: Stapel, Warteschlangen und Warteschlangen mit hoher Priorität. Jede schränkt die Funktionalität von einigen zugrunde liegenden Containerklassen ein, um eine präzise gesteuerte Oberfläche für eine Standarddatenstruktur anzubieten.

- Die [Stapelklasse](../standard-library/stack-class.md) unterstützt eine LIFO-Datenstruktur (Last In – First Out). Eine gute Analogie, um sich dies zu merken, ist ein Stapel von Tellern. Elemente (Teller) können eingefügt, überprüft oder nur vom Anfang des Stapels entnommen werden, was dem letzten Element am Ende des Basiscontainers entspricht. Die Beschränkung, nur auf das oberste Element zuzugreifen, ist der Grund für die Verwendung der stack-Klasse.

- Die [Warteschlangenklasse](../standard-library/queue-class.md) unterstützt eine FIFO-Datenstruktur (First In – First Out). Eine gute Analogie, um sich dies zu merken, sind Personen, die an einem Bankschalter anstehen. Elemente (Personen) können am Ende der Schlange hinzugefügt werden und vom Anfang der Schlange entfernt werden. Sowohl der Anfang als auch das Ende einer Schlange können überprüft werden. Die in dieser Weise umgesetzte Beschränkung, nur auf das vorderste und das hinterste Element zugreifen zu können, ist der Grund für das Verwenden der Warteschlangenklasse.

- In der Warteschlangenklasse mit hoher Priorität sortiert ihre Elemente so, dass sich das größte Element immer an der obersten Position befindet. Die Klasse unterstützt Einfügen eines Elements sowie die Prüfung und Entfernung des obersten Elements. Eine gute Analogie, um sich dies zu merken, sind Personen, die in einer Schlange stehen, in der sie nach Alter, Größe oder einem anderen Kriterium angeordnet sind.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[priority_queue](#priority_queue)|Erstellt ein `priority_queue`-Objekt, das leer oder eine Kopie eines Basiscontainerobjekts oder eines anderen `priority_queue` ist.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[container_type](#container_type)|Ein Typ, der den Basiscontainer bereitstellt, der durch ein `priority_queue`-Objekt übernommen werden soll.|
|[size_type](#size_type)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `priority_queue` darstellen kann.|
|[value_type](#value_type)|Ein Typ, der den Typ des Objekts angibt, das in einem `priority_queue`-Objekt als Element gespeichert wird.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[empty](#empty)|Testet, ob das `priority_queue`-Objekt ist leer.|
|[pop](#pop)|Entfernt das größte Element der `priority_queue` von der obersten Position.|
|[push](#push)|Fügt ein Element zur Warteschlange mit hoher Priorität anhand der Priorität des Elements des operator< hinzu.|
|[size](#size)|Gibt die Anzahl von Elementen in der `priority_queue` zurück.|
|[top](#top)|Gibt einen konstanten Verweis auf das größte Element am oberen Rand von `priority_queue` zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<queue>

**Namespace:** std

## <a name="container_type"></a> priority_queue::container_type

Ein Typ, der den anzupassenden Basiscontainer bereitstellt.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `Container` dar. Die Sequenzcontainerklassen der C++-Standardbibliothek `deque` und die Standardklasse `vector` erfüllen die Anforderungen, um als Basiscontainer für ein priority_queue-Objekt verwendet zu werden. Benutzerdefinierte Typen, die diese Anforderung erfüllen, können auch verwendet werden.

Weitere Informationen zu `Container` finden Sie im Abschnitt „Hinweise“ des Themas [priority_queue-Klasse](../standard-library/priority-queue-class.md).

### <a name="example"></a>Beispiel

Im Beispiel für [priority_queue](#priority_queue) wird verdeutlicht, wie `container_type` deklariert und verwendet wird.

## <a name="empty"></a> priority_queue::empty

Testet, ob eine priority_queue leer ist.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die priority_queue leer ist. **FALSE**, wenn die Priority_queue nicht leer ist.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="pop"></a> priority_queue::pop

Entfernt das größte Element der priority_queue von der obersten Position.

```cpp
void pop();
```

### <a name="remarks"></a>Hinweise

Priority_queue darf nicht leer sein, damit die Memberfunktion angewendet wird. Der Anfang der Warteschlange mit hoher Priorität wird immer von dem größten Element im Container belegt.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="priority_queue"></a> priority_queue::priority_queue

Erstellt eine Warteschlange mit hoher Priorität, die leer ist oder eine Kopie eines Bereichs eines Basiscontainerobjekt oder einer anderen Warteschlange mit hoher Priorität ist.

```cpp
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

*_ Comp* die Vergleichsfunktion vom Typ **ConstTraits** verwendet zum Sortieren der Elemente in Priority_queue, dem standardmäßig Teil des Basiscontainers verglichen werden soll.

`_Cont` Der Basis Container, die konstruierte Priority_queue ist eine Kopie.

`right` Der ist der erstellte Satz Kopie Priority_queue.

`first` Die Position des ersten Elements in dem zu kopierenden Elementbereich.

`last` Die Position des ersten Elements hinter dem zu kopierenden Elementbereich.

### <a name="remarks"></a>Hinweise

Die ersten drei Konstruktoren geben eine ursprünglich leere Warteschlange mit hoher Priorität an. Dabei gibt der zweite Konstruktor auch den Typ der Vergleichsfunktion (`comp`) an, der zum Angeben der Reihenfolge der Elemente verwendet wird, und der dritte Konstruktor gibt explizit den zu verwendenden `container_type` ( `_Cont`) an. Mit dem Schlüsselwort **explicit** werden bestimmte Arten automatischer Typumwandlungen unterdrückt.

Der vierte Konstruktor gibt eine Kopie de Warteschlange mit hoher Priorität `right` an.

Die letzten drei Konstruktoren Kopieren des Bereichs [* ersten, letzten *) einige Container und verwenden Sie die Werte ein Priority_queue mit erhöhen sich die Explizitheit bei Angabe des Typs der Vergleichsfunktion der Klasse initialisieren **Traits** und `container_type`.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="push"></a> priority_queue::push

Fügt ein Element zur Warteschlange mit hoher Priorität anhand der Priorität des Elements des operator< hinzu.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parameter

`val` Das Element am oberen Rand von Priority_queue hinzugefügt.

### <a name="remarks"></a>Hinweise

Am Anfang der Warteschlange mit hoher Priorität befindet sich das größte Element im Container.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="size"></a> priority_queue::size

Gibt die Anzahl der Elemente in der Warteschlange mit hoher Priorität zurück.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Länge der Warteschlange mit hoher Priorität.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="size_type"></a> priority_queue::size_type

Ein Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in einer Warteschlange mit hoher Priorität darstellen kann.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für das `size_type` des Basiscontainers, der von der Warteschlange mit hoher Priorität angepasst wurde.

### <a name="example"></a>Beispiel

Im Beispiel für [size](#size) wird verdeutlicht, wie ein `size_type` deklariert und verwendet wird.

## <a name="top"></a> priority_queue::top

Gibt einen konstanten Verweis auf das größte Element am oberen Rand von priority_queue.

```cpp
const_reference top() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das größte durch die **Traits**-Funktion festgelegte Element, ein Objekt der Warteschlange mit hoher Priorität.

### <a name="remarks"></a>Hinweise

Priority_queue darf nicht leer sein, damit die Memberfunktion angewendet wird.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="value_type"></a> priority_queue::value_type

Ein Typ, der den Typ des Objekts angibt, das als Element in einer Warteschlange mit hoher Priorität gespeichert wird.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für das `value_type` des Basiscontainers, der von der Warteschlange mit hoher Priorität angepasst wurde.

### <a name="example"></a>Beispiel

```cpp
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

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
