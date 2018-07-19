---
title: hash-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- stack/std::stack::container_type
- stack/std::stack::size_type
- stack/std::stack::value_type
- stack/std::stack::empty
- stack/std::stack::pop
- stack/std::stack::push
- stack/std::stack::size
- stack/std::stack::top
dev_langs:
- C++
helpviewer_keywords:
- std::stack [C++], container_type
- std::stack [C++], size_type
- std::stack [C++], value_type
- std::stack [C++], empty
- std::stack [C++], pop
- std::stack [C++], push
- std::stack [C++], size
- std::stack [C++], top
ms.assetid: 02151c1e-eab0-41b8-be94-a839ead78ecf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b933029f7180292e1c9e392bf2ab09e8dbcb204
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963224"
---
# <a name="stack-class"></a>stack-Klasse

Eine Vorlagencontainer-Adapterklasse, die die Funktionalität einschränkt, indem sie den Zugriff auf das Element beschränkt, das zuletzt zu einem zugrunde liegenden Containertyp hinzugefügt wurde. Die stack-Klasse wird verwendet, wenn es unverzichtbar ist, dass Stapelvorgänge nur für den Container ausgeführt werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Type, class Container= deque <Type>>
class stack
```

### <a name="parameters"></a>Parameter

*Typ* die Datentyp der Elemente im Stapel gespeichert werden.

*Container* den Typ des zugrunde liegenden Container verwendet, um den Stapel zu implementieren. Der Standardwert ist die Klasse `deque`*\<Type>*.

## <a name="remarks"></a>Hinweise

Die Elemente der Klasse `Type` , die im ersten Vorlagenparameter eines Stack-Objekts sind, sind gleichbedeutend mit [Value_type](#value_type) und muss mit dem Typ des Elements in der zugrunde liegenden Containerklasse `Container` vorgesehenen durch die zweiten Vorlagenparameter. Die `Type` muss zuweisbar sein, damit, dass es möglich, Objekte dieses Typs zu kopieren und Variablen dieses Typs Werte zuzuweisen.

Geeignete zugrunde liegende Containerklassen für Stack sind [doppelschlange](../standard-library/deque-class.md), [list-Klasse](../standard-library/list-class.md), und [vector-Klasse](../standard-library/vector-class.md), oder ein beliebiger sequenzcontainer, der die Vorgänge unterstützt `back`, `push_back`, und `pop_back`. Die zugrunde liegende Containerklasse wird im Containeradapter gekapselt, der nur den begrenzten Satz der Memberfunktionen des Sequenzcontainers als öffentliche Schnittstelle verfügbar macht.

Die Stack-Objekte sind auf Gleichheit vergleichbar nur, wenn die Elemente der Klasse `Type` auf Gleichheit vergleichbar sind, und sind kleiner-als vergleichbar nur, wenn die Elemente der Klasse `Type` kleiner-als vergleichbar sind.

- Die stack-Klasse unterstützt eine LIFO-Datenstruktur (Last In – First Out). Eine gute Analogie, um sich dies zu merken, ist ein Stapel von Tellern. Elemente (Teller) können eingefügt, überprüft oder nur vom Anfang des Stapels entnommen werden, was dem letzten Element am Ende des Basiscontainers entspricht. Die Beschränkung, nur auf das oberste Element zuzugreifen, ist der Grund für die Verwendung der stack-Klasse.

- Die [queue-Klasse](../standard-library/queue-class.md) unterstützt eine FIFO-Daten(First In – First Out). Eine gute Analogie, um sich dies zu merken, sind Personen, die an einem Bankschalter anstehen. Elemente (Personen) können am Ende der Schlange hinzugefügt werden und vom Anfang der Schlange entfernt werden. Sowohl der Anfang als auch das Ende einer Schlange können überprüft werden. Die in dieser Weise umgesetzte Beschränkung, nur auf das vorderste und das hinterste Element zugreifen zu können, ist der Grund für das Verwenden der queue-Klasse.

- In der [priority_queue-Klasse](../standard-library/priority-queue-class.md) sind deren Elemente so sortiert, dass sich das größte Element immer an der obersten Position befindet. Die Klasse unterstützt Einfügen eines Elements sowie die Prüfung und Entfernung des obersten Elements. Eine gute Analogie, um sich dies zu merken, sind Personen, die in einer Schlange stehen, in der sie nach Alter, Größe oder einem anderen Kriterium angeordnet sind.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[stack](#stack)|Erstellt ein `stack`-Objekt, das leer oder eine Kopie eines Basiscontainerobjekts ist.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[container_type](#container_type)|Ein Typ, der den Basiscontainer bereitstellt, der durch ein `stack`-Objekt übernommen werden soll.|
|[size_type](#size_type)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `stack` darstellen kann.|
|[value_type](#value_type)|Ein Typ, der den Typ des Objekts angibt, das in einem `stack`-Objekt als Element gespeichert wird.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[empty](#empty)|Testet, ob das `stack`-Objekt ist leer.|
|[pop](#pop)|Entfernt das Element aus der obersten Position des `stack`-Objekts.|
|[push](#push)|Fügt ein Element an der obersten Position des `stack`-Objekts hinzu.|
|[size](#size)|Gibt die Anzahl von Elementen in der `stack` zurück.|
|[top](#top)|Gibt einen Verweis auf das Element in der obersten Position des `stack`-Objekts zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<stack>

**Namespace:** std

## <a name="container_type"></a> stack::container_type

Ein Typ, der den anzupassenden Basiscontainer bereitstellt.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `Container` dar. Die drei Sequenzcontainerklassen der C++-Standardbibliothek, d.h. die Vektorklasse, die list-Klasse und die Standardklasse Deque, erfüllen die Anforderungen, um als Basiscontainer für ein stack-Objekt verwendet zu werden. Benutzerdefinierte Typen, die diese Anforderung erfüllen, können auch verwendet werden.

Weitere Informationen zu `Container` finden Sie im Abschnitt „Hinweise“ des Themas [stack-Klasse](../standard-library/stack-class.md).

### <a name="example"></a>Beispiel

Im Beispiel für [stack::stack](#stack) wird verdeutlicht, wie ein `container_type` deklariert und verwendet wird.

## <a name="empty"></a> stack::empty

Testet, ob ein Stack leer ist.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Stack leer ist; **FALSE**, wenn der Stack nicht leer ist.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="pop"></a> stack::pop

Entfernt das Element aus der obersten Position des Stacks.

```cpp
void pop();
```

### <a name="remarks"></a>Hinweise

Der Stack darf nicht leer sein, damit die Memberfunktion angewendet wird. Der Anfang des Stacks ist die Position des zuletzt hinzugefügten Elements und ist das letzte Element am Ende des Containers.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="push"></a> stack::push

Fügt ein Element am oberen Ende des Stacks hinzu.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parameter

*Val* das am Anfang des Stacks hinzugefügte Element.

### <a name="remarks"></a>Hinweise

Der Anfang des Stacks ist die Position des zuletzt hinzugefügten Elements und ist das letzte Element am Ende des Containers.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="size"></a> stack::size

Gibt die Anzahl der Elemente im Stack zurück.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Länge des Stacks.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="size_type"></a> stack::size_type

Ein Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in einem Stack darstellen kann.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `size_type` des Basiscontainers und vom Stack angepasst.

### <a name="example"></a>Beispiel

Im Beispiel für [size](#size) wird verdeutlicht, wie ein `size_type` deklariert und verwendet wird.

## <a name="stack"></a> stack::stack

Erstellt ein einen Stack, der leer oder eine Kopie eines Basiscontainerobjekts ist.

```cpp
stack();

explicit stack(const container_type& right);
```

### <a name="parameters"></a>Parameter

*richtige* den Container dem der erstellte Stack ist eine Kopie.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="top"></a> stack::top

Gibt einen Verweis auf ein Element am Anfang des Stacks zurück.

```cpp
reference top();

const_reference top() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das letzte Element im Container am Anfang des Stacks.

### <a name="remarks"></a>Hinweise

Der Stack darf nicht leer sein, damit die Memberfunktion angewendet wird. Der Anfang des Stacks ist die Position des zuletzt hinzugefügten Elements und ist das letzte Element am Ende des Containers.

Wenn der Rückgabewert von `top` zugewiesen ist eine `const_reference`, das Stack-Objekt kann nicht geändert werden. Wenn der Rückgabewert von `top` zugewiesen ist eine `reference`, kann das Stack-Objekt geändert werden.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="value_type"></a> stack::value_type

Ein Typ, der den Typ des Objekts angibt, das in einem Stack als Element gespeichert wird.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `value_type` des Basiscontainers und vom Stack angepasst.

### <a name="example"></a>Beispiel

```cpp
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

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
