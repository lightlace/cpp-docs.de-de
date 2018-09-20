---
title: Warteschlange mit hoher Priorität (STL/CLR) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue
- cliext::priority_queue::assign
- cliext::priority_queue::const_reference
- cliext::priority_queue::container_type
- cliext::priority_queue::difference_type
- cliext::priority_queue::empty
- cliext::priority_queue::generic_container
- cliext::priority_queue::generic_value
- cliext::priority_queue::get_container
- cliext::priority_queue::operator=
- cliext::priority_queue::pop
- cliext::priority_queue::priority_queue
- cliext::priority_queue::push
- cliext::priority_queue::reference
- cliext::priority_queue::size
- cliext::priority_queue::size_type
- cliext::priority_queue::to_array
- cliext::priority_queue::top
- cliext::priority_queue::top_item
- cliext::priority_queue::value_comp
- cliext::priority_queue::value_compare
- cliext::priority_queue::value_type
dev_langs:
- C++
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
- assign member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- priority_queue member [STL/CLR]
- push member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- top member [STL/CLR]
- top_item member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fd6d7ec3c4314f1a1798da3d5078b0409d44d026
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423909"
---
# <a name="priorityqueue-stlclr"></a>priority_queue (STL/CLR)

Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge sortierte Sequenz von Elementen, die eingeschränkten Zugriff steuert. Verwenden des Adapters Container `priority_queue` einen zugrunde liegenden Container als Prioritätswarteschlange zu verwalten.

In der folgenden Beschreibung `GValue` ist identisch mit *Wert* , wenn die zweite ein Ref-Typ ist, in diesem Fall ist es `Value^`. Auf ähnliche Weise `GContainer` ist identisch mit *Container* , wenn die zweite ein Ref-Typ ist, in diesem Fall ist es `Container^`.

## <a name="syntax"></a>Syntax

```cpp
template<typename Value,
    typename Container>
    ref class priority_queue
        System::ICloneable,
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>
    { ..... };
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Der Typ eines Elements in der kontrollierten Sequenz.

*Container*<br/>
Der Typ des zugrunde liegenden Containers.

## <a name="requirements"></a>Anforderungen

**Header:** \<Cliext bzw. einer neuen Warteschlange >

**Namespace:** Cliext

## <a name="declarations"></a>Deklarationen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|[priority_queue::const_reference (STL/CLR)](#const_reference)|Der Typ eines konstanten Verweises auf ein Element.|
|[priority_queue::container_type (STL/CLR)](#container_type)|Der Typ des zugrunde liegenden Containers.|
|[priority_queue::difference_type (STL/CLR)](#difference_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|
|[priority_queue::generic_container (STL/CLR)](#generic_container)|Der Typ der generischen Schnittstelle für den Containeradapter.|
|[priority_queue::generic_value (STL/CLR)](#generic_value)|Der Typ eines Elements für die generische Schnittstelle für den Containeradapter.|
|[priority_queue::reference (STL/CLR)](#reference)|Der Typ eines Verweises auf ein Element.|
|[priority_queue::size_type (STL/CLR)](#size_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|
|[priority_queue::value_compare (STL/CLR)](#value_compare)|Der Delegat für zwei Elemente.|
|[priority_queue::value_type (STL/CLR)](#value_type)|Der Typ eines Elements.|

|Memberfunktion|Beschreibung|
|---------------------|-----------------|
|[priority_queue::assign (STL/CLR)](#assign)|Ersetzt alle Elemente.|
|[priority_queue::empty (STL/CLR)](#empty)|Testet, ob keine Elemente vorhanden sind.|
|[priority_queue::get_container (STL/CLR)](#get_container)|Greift auf die zugrunde liegenden Containers.|
|[priority_queue::pop (STL/CLR)](#pop)|Entfernt das Element Hghest Priorität.|
|[priority_queue::priority_queue (STL/CLR)](#priority_queue)|Erstellt ein container-Objekt.|
|[priority_queue::push (STL/CLR)](#push)|Fügt ein neues Element hinzu.|
|[priority_queue::size (STL/CLR)](#size)|Ermittelt die Anzahl von Elementen.|
|[priority_queue::top (STL/CLR)](#top)|Greift auf das Element der höchsten Priorität.|
|[priority_queue::to_array (STL/CLR)](#to_array)|Kopiert die kontrollierte Sequenz in ein neues Array.|
|[priority_queue::value_comp (STL/CLR)](#value_comp)|Kopiert der Delegat für zwei Elemente.|

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|[priority_queue::top_item (STL/CLR)](#top_item)|Greift auf das Element der höchsten Priorität.|

|Operator|Beschreibung|
|--------------|-----------------|
|[priority_queue::operator= (STL/CLR)](#op_as)|Ersetzt die kontrollierte Sequenz.|

## <a name="interfaces"></a>Schnittstellen

|Interface|Beschreibung|
|---------------|-----------------|
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|
|IPriorityQueue\<-Wert, der Container >|Behalten Sie die generischen Container-Adapter.|

## <a name="remarks"></a>Hinweise

Das Objekt weist speicherbelegungen und-Freigaben für die gesteuerte Sequenz durch eine zugrunde liegenden Containers, eines Typs `Container`, speichert `Value` Elemente und wächst nach Bedarf. Er hält die als Heap mit dem mit der höchsten Priorität-Element (Element der obersten) leicht zugänglich und Wechselmedien sortierte Sequenz. Das Objekt schränkt den Zugriff auf neue Elemente übertragen und entfernt wurde nur das mit der höchsten Priorität Element, Implementierung einer Prioritätswarteschlange.

Das Objekt sortiert die Sequenz, indem ein Delegatobjekt gespeicherten des Typs aufrufen [priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md). Sie können das gespeicherte Delegatobjekt angeben, beim Erstellen der Warteschlange mit hoher Priorität. Wenn Sie kein Delegatobjekt angeben, wird der Standardwert ist der Vergleich `operator<(value_type, value_type)`. Sie greifen auf diese gespeicherten Objekt durch Aufrufen der Memberfunktion [priority_queue:: value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)`()`.

Solche ein Delegatobjekt muss eine strikte schwache Sortierung für Werte vom Typ vorgeben [priority_queue:: value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md). Bedeutet, dass für alle Schlüssel, der zwei `X` und `Y`:

`value_comp()(X, Y)` Gibt der gleichen boolesche Ergebnis bei jedem Aufruf.

Wenn `value_comp()(X, Y)` ist "true", klicken Sie dann `value_comp()(Y, X)` muss auf falsch gesetzt sein.

Wenn `value_comp()(X, Y)` ist "true", klicken Sie dann `X` wird vor dem sortiert werden als `Y`.

Wenn `!value_comp()(X, Y) && !value_comp()(Y, X)` ist "true", klicken Sie dann `X` und `Y` gelten als die entsprechende Reihenfolge aufweisen.

Für jedes Element `X` vorausgeht, die `Y` in die kontrollierte Sequenz `key_comp()(Y, X)` ist "false". (Für das Objekt für den Standard-Delegaten verringern Sie Schlüssel nie im Wert.)

Das Element der höchsten Priorität ist daher eines der Elemente der vor jedem anderen Element nicht sortiert ist.

Da der zugrunde liegenden Container Elemente sortiert, die als Heap verfolgt:

Der Container muss Iteratoren mit zufälligem Zugriff unterstützen.

Elemente mit entsprechender Sortierung können in einer anderen Reihenfolge geholt werden, als sie per Push übertragen wurden. (Die Reihenfolge ist nicht stabil.)

Also gut für den zugrunde liegenden Container enthalten [Deque (STL/CLR)](../dotnet/deque-stl-clr.md) und [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md).

## <a name="members"></a>Member

## <a name="assign"></a> priority_queue:: Assign (STL/CLR)

Ersetzt alle Elemente.

### <a name="syntax"></a>Syntax

```cpp
void assign(priority_queue<Value, Container>% right);
```

#### <a name="parameters"></a>Parameter

*right*<br/>
Der Containeradapter, einfügen.

### <a name="remarks"></a>Hinweise

Die Memberfunktion weist `right.get_container()` in den zugrunde liegenden Container. Damit können Sie um den gesamten Inhalt der Warteschlange zu ändern.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_assign.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign a repetition of values
    Mypriority_queue c2;
    c2.assign(c1);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
```

## <a name="const_reference"></a> priority_queue::const_reference (STL/CLR)

Der Typ eines konstanten Verweises auf ein Element.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt einen konstanten Verweis auf ein Element.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_const_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display reversed contents " c b a"
    for (; !c1.empty(); c1.pop())
        {   // get a const reference to an element
        Mypriority_queue::const_reference cref = c1.top();
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="container_type"></a> priority_queue:: container_type (STL/CLR)

Der Typ des zugrunde liegenden Containers.

### <a name="syntax"></a>Syntax

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `Container` dar.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_container_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c" using container_type
    Mypriority_queue::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="difference_type"></a> priority_queue::difference_type (STL/CLR)

Die Typen des Abstands zwischen den beiden Elementen mit Vorzeichen.

### <a name="syntax"></a>Syntax

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt eine möglicherweise negative Elementanzahl.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_difference_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute negative difference
    Mypriority_queue::difference_type diff = c1.size();
    c1.push(L'd');
    c1.push(L'e');
    diff -= c1.size();
    System::Console::WriteLine("pushing 2 = {0}", diff);

    // compute positive difference
    diff = c1.size();
    c1.pop();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("popping 3 = {0}", diff);
    return (0);
    }
```

```Output
c a b
pushing 2 = -2
popping 3 = 3
```

## <a name="empty"></a> priority_queue:: Empty (STL/CLR)

Testet, ob keine Elemente vorhanden sind.

### <a name="syntax"></a>Syntax

```cpp
bool empty();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt „true“ für eine leere gesteuerte Sequenz zurück. Dies ist äquivalent zum [priority_queue:: Size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)`() == 0`. Damit können Sie überprüfen, ob die Priority_queue leer ist.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_empty.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.pop();
    c1.pop();
    c1.pop();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
c a b
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="generic_container"></a> priority_queue::generic_container (STL/CLR)

Der Typ der generischen Schnittstelle für den Container.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::IPriorityQueue<Value>
    generic_container;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt die generische Schnittstelle für diese Container Adapter-Vorlagenklasse.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_generic_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mypriority_queue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->push(L'd');
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.push(L'e');
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
d c b a
e d b a c
```

## <a name="generic_value"></a> priority_queue::generic_value (STL/CLR)

Der Typ eines Elements für die Verwendung mit der generischen Schnittstelle für den Container.

### <a name="syntax"></a>Syntax

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt ein Objekt des Typs `GValue` , beschreibt den gespeichertes Element-Wert für die Verwendung mit der generischen Schnittstelle für diese Vorlage Container-Klasse. (`GValue` ist entweder `value_type` oder `value_type^` Wenn `value_type` ist ein Ref-Typ.)

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_generic_value.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get interface to container
    Mypriority_queue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display in priority order using generic_value
    for (; !gc1->empty(); gc1->pop())
        {
        Mypriority_queue::generic_value elem = gc1->top();

        System::Console::Write("{0} ", elem);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
c b a
```

## <a name="get_container"></a> priority_queue:: get_container (STL/CLR)

Greift auf die zugrunde liegenden Containers.

### <a name="syntax"></a>Syntax

```cpp
container_type get_container();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt den zugrunde liegenden Container zurück. Damit können Sie um die Einschränkungen, die vom Container Wrapper zu umgehen.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_get_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="op_as"></a> priority_queue::Operator = (STL/CLR)

Ersetzt die kontrollierte Sequenz.

### <a name="syntax"></a>Syntax

```cpp
priority_queue <Value, Container>% operator=(priority_queue <Value, Container>% right);
```

#### <a name="parameters"></a>Parameter

*right*<br/>
Der Containeradapter, zu kopieren.

### <a name="remarks"></a>Hinweise

Die Member-Operator Kopien *rechten* klicken Sie dann auf das Objekt, gibt `*this`. Damit können Sie die kontrollierte Sequenz durch eine Kopie der kontrollierten Sequenz in ersetzen *rechten*.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_operator_as.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mypriority_queue c2;
    c2 = c1;
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
```

## <a name="pop"></a> priority_queue:: POP (STL/CLR)

Entfernt das Element der höchsten Proirity.

### <a name="syntax"></a>Syntax

```cpp
void pop();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion entfernt das Element der höchsten Priorität der kontrollierten Sequenz, die nicht leer sein darf. Sie verwenden, um ein Element an der Rückseite die Warteschlange zu verkürzen.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_pop.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop();
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
b a
```

## <a name="priority_queue"></a> priority_queue:: priority_queue (STL/CLR)

Erstellt ein Containerobjekt für den Adapter.

### <a name="syntax"></a>Syntax

```cpp
priority_queue();
priority_queue(priority_queue<Value, Container> right);
priority_queue(priority_queue<Value, Container> right);
explicit priority_queue(value_compare^ pred);
priority_queue(value_compare^ pred, container_type% cont);
template<typename InIt>
    priority_queue(InIt first, InIt last);
template<typename InIt>
    priority_queue(InIt first, InIt last,
        value_compare^ pred);
template<typename InIt>
    priority_queue(InIt first, InIt last,
        value_compare^ pred, container_type% cont);
```

#### <a name="parameters"></a>Parameter

*Inhalt*<br/>
Der zu kopierende Container.

*Erste*<br/>
Anfang des Bereichs, der eingefügt.

*last*<br/>
Ende des Bereichs, der eingefügt.

*Pred*<br/>
Sortieren Prädikat für die gesteuerte Sequenz.

*right*<br/>
Einzufügendes Objekt bzw. einzufügender Bereich.

### <a name="remarks"></a>Hinweise

Der Konstruktor:

`priority_queue();`

erstellt einen leeren umschlossenen Container, mit der standardmäßigen Reihenfolge Prädikat an. Damit können Sie eine leere gesteuerte Sequenz, mit der standardmäßigen Reihenfolge Prädikat angeben.

Der Konstruktor:

`priority_queue(priority_queue<Value, Container>% right);`

erstellt einen Wrapper-Container, die eine Kopie des `right.get_container()`, mit der Sortierung Prädikat `right.value_comp()`. Damit können Sie eine gesteuerte Sequenz angeben, die eine Kopie der gesteuerte Sequenz durch das Queue-Objekt ist *rechten*, mit der gleichen Reihenfolge Prädikat.

Der Konstruktor:

`priority_queue(priority_queue<Value, Container>^ right);`

erstellt einen Wrapper-Container, die eine Kopie des `right->get_container()`, mit der Sortierung Prädikat `right->value_comp()`. Damit können Sie eine gesteuerte Sequenz angeben, die eine Kopie der gesteuerte Sequenz durch das Queue-Objekt ist `*right`, mit der gleichen Reihenfolge Prädikat.

Der Konstruktor:

`explicit priority_queue(value_compare^ pred);`

erstellt einen leeren umschlossenen Container, mit der Sortierung Prädikat *Pred*. Damit können Sie eine leere gesteuerte Sequenz, mit dem angegebenen Prädikat für die Sortierung angeben.

Der Konstruktor:

`priority_queue(value_compare^ pred, container_type cont);`

erstellt einen leeren umschlossenen Container, mit der Sortierung Prädikat *Pred*, legt dann alle Elemente der *Forts* damit können Sie eine gesteuerte Sequenz aus einem vorhandenen Container aus, geben Sie mit der angegebene sortierungsprädikat

Der Konstruktor:

`template<typename InIt> priority_queue(InIt first, InIt last);`

erstellt einen leeren umschlossenen Container, mit dem standardmäßigen Sortierung Prädikat und überträgt die Sequenz [`first`, `last`). Damit können Sie eine gesteuerte Sequenz aus einem angegebenen Eqeuence, mit dem angegebenen Prädikat für die Sortierung angeben.

Der Konstruktor:

`template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`

erstellt einen leeren umschlossenen Container, mit der Sortierung Prädikat *Pred*, legt dann die Sequenz [`first`, `last`). Damit können Sie eine gesteuerte Sequenz aus einem angegebenen Seqeuence, mit dem angegebenen Prädikat für die Sortierung angeben.

Der Konstruktor:

`template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`

erstellt einen leeren umschlossenen Container, mit der Sortierung Prädikat *Pred*, legt dann alle Elemente der *Forts* sowie die Sequenz [`first`, `last`). Damit können Sie eine gesteuerte Sequenz aus einem vorhandenen Container und einem angegebenen Seqeuence, mit dem angegebenen Prädikat für die Sortierung angeben.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_construct.cpp
// compile with: /clr
#include <cliext/queue>
#include <cliext/deque>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
typedef cliext::deque<wchar_t> Mydeque;
int main()
    {
// construct an empty container
    Mypriority_queue c1;
    Mypriority_queue::container_type^ wc1 = c1.get_container();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    for each (wchar_t elem in wc1)
        c2.push(elem);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule by copying an underlying container
    Mypriority_queue c2x =
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);
   for each (wchar_t elem in c2x.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    Mypriority_queue c3(wc1->begin(), wc1->end());
    for each (wchar_t elem in c3.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mypriority_queue c4(wc1->begin(), wc1->end(),
        cliext::greater<wchar_t>());
    for each (wchar_t elem in c4.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range, another container, and an ordering rule
    Mypriority_queue c5(wc1->begin(), wc1->end(),
        cliext::greater<wchar_t>(), *wc1);
    for each (wchar_t elem in c5.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct from a generic container
    Mypriority_queue c6(c3);
    for each (wchar_t elem in c6.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Mypriority_queue c7(%c3);
    for each (wchar_t elem in c7.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule, by copying an underlying container
    Mypriority_queue c8 =
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);
    for each (wchar_t elem in c8.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
size() = 0
c a b
size() = 0
a c b
a c b
c a b
a c b
a a b c c b
c a b
c a b
a c b
```

## <a name="push"></a> priority_queue:: Push (STL/CLR)

Fügt ein neues Element hinzu.

### <a name="syntax"></a>Syntax

```cpp
void push(value_type val);
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion Fügt ein Element mit Wert `val` in der kontrollierten Sequenz, und sortiert die gesteuerte Sequenz, um die Heapordnung beizubehalten. Damit können Sie ein anderes Element zur Warteschlange hinzugefügt.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_push.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="reference"></a> priority_queue::Reference (STL/CLR)

Der Typ eines Verweises auf ein Element.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt einen Verweis auf ein Element.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify top of priority_queue and redisplay
    Mypriority_queue::reference ref = c1.top();
    ref = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
x a b
```

## <a name="size"></a> priority_queue:: Size (STL/CLR)

Ermittelt die Anzahl von Elementen.

### <a name="syntax"></a>Syntax

```cpp
size_type size();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Länge der gesteuerten Sequenz zurück. Damit können Sie die Anzahl der Elemente, die derzeit in der kontrollierten Sequenz bestimmt. Wenn Sie besonders interessierenden lediglich, ob die Reihenfolge größer, finden Sie unter hat [priority_queue:: Empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)`()`.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_size.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // pop an item and reinspect
    c1.pop();
    System::Console::WriteLine("size() = {0} after popping", c1.size());

    // add two elements and reinspect
    c1.push(L'a');
    c1.push(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
c a b
size() = 3 starting with 3
size() = 2 after popping
size() = 4 after adding 2
```

## <a name="size_type"></a> priority_queue:: size_type (STL/CLR)

Der Typ eines Abstands zwischen den beiden Elementen mit Vorzeichen.

### <a name="syntax"></a>Syntax

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt eine nicht Negative Elementanzahl.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_size_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mypriority_queue::size_type diff = c1.size();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("size difference = {0}", diff);
    return (0);
    }
```

```Output
c a b
size difference = 2
```

## <a name="to_array"></a> priority_queue::to_array (STL/CLR)

Kopiert die kontrollierte Sequenz in ein neues Array.

### <a name="syntax"></a>Syntax

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt ein Array mit der kontrollierten Sequenz zurück. Damit können Sie eine Kopie der kontrollierten Sequenz in Arrayform abrufen.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_to_array.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push(L'd');
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
d c b a
c a b
```

## <a name="top"></a> priority_queue:: Top (STL/CLR)

Greift auf das Element der höchsten Priorität.

### <a name="syntax"></a>Syntax

```cpp
reference top();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt einen Verweis auf das Element der obersten (höchsten Priorität) der gesteuerten Sequenz, die nicht leer sein darf. Damit können Sie das Element der höchsten Priorität, zugreifen, wenn Sie wissen, dass es vorhanden ist.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_top.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("top() = {0}", c1.top());

    // alter last item and reinspect
    c1.top() = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

## <a name="top_item"></a> priority_queue:: die top_item (STL/CLR)

Greift auf das Element der höchsten Priorität.

### <a name="syntax"></a>Syntax

```cpp
property value_type back_item;
```

### <a name="remarks"></a>Hinweise

Die Eigenschaft greift auf das Element der obersten (höchsten Priorität) der gesteuerten Sequenz, die nicht leer sein darf. Sie verwenden ihn zum Lesen oder schreiben das Element der höchsten Priorität, wenn Sie wissen, dass es vorhanden ist.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_top_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("top_item = {0}", c1.top_item);

    // alter last item and reinspect
    c1.top_item = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
top_item = c
x a b
```

## <a name="value_comp"></a> priority_queue:: value_comp (STL/CLR)

Kopiert der Delegat für zwei Elemente.

### <a name="syntax"></a>Syntax

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt der Delegat verwendet, um die kontrollierte Sequenz sortiert zurück. Damit können Sie zwei Werte vergleichen.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_value_comp.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    vcomp = c2.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="value_compare"></a> priority_queue::value_compare (STL/CLR)

Der Delegat für zwei Werte.

### <a name="syntax"></a>Syntax

```cpp
binary_delegate<value_type, value_type, int> value_compare;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den Delegaten, der bestimmt, ob das erste Argument, damit die zweite geordnet ist.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_value_compare.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    vcomp = c2.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="value_type"></a> priority_queue:: value_type (STL/CLR)

Der Typ eines Elements.

### <a name="syntax"></a>Syntax

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den Vorlagenparameter *Wert*.

### <a name="example"></a>Beispiel

```cpp
// cliext_priority_queue_value_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display reversed contents " a b c" using value_type
    for (; !c1.empty(); c1.pop())
        {   // store element in value_type object
        Mypriority_queue::value_type val = c1.top();

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```