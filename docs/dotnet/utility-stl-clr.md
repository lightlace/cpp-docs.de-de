---
title: Hilfsprogramm (STL/CLR) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
dev_langs:
- C++
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 307d3c2f95d006ae36ff39cf3c16ff3fd65a4c34
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374235"
---
# <a name="utility-stlclr"></a>utility (STL/CLR)

Fügen Sie den STL/CLR-Header `<cliext/utility>` definiert die Vorlagenklasse `pair` und mehrere unterstützende Vorlagenfunktionen.

## <a name="syntax"></a>Syntax

```cpp
#include <utility>
```

## <a name="requirements"></a>Anforderungen

**Header:** \<Cliext/Hilfsprogramm >

**Namespace:** Cliext

## <a name="declarations"></a>Deklarationen

|Klasse|Beschreibung|
|-----------|-----------------|
|[pair (STL/CLR)](#pair)|Umschließen Sie ein Paar von Elementen.|

|Operator|Beschreibung|
|--------------|-----------------|
|[operator== (pair) (STL/CLR)](#op_eq)|Pair-gleich-Vergleich.|
|[operator!= (pair) (STL/CLR)](#op_neq)|Koppeln Sie nicht gleich-Vergleich ein.|
|[operator< (pair) (STL/CLR)](#op_lt)|Paar kleiner-als-Vergleich.|
|[Operator\<= (Paar) (STL/CLR)](#op_lteq)|Koppeln Sie kleiner oder gleich Vergleich.|
|[operator> (pair) (STL/CLR)](#op_gt)|Das Paar ist größer als-Vergleich.|
|[operator>= (pair) (STL/CLR)](#op_gteq)|Paar von größer als oder gleich-Vergleich.|

|Funktion|Beschreibung|
|--------------|-----------------|
|[make_pair (STL/CLR)](#make_pair)|Stellen Sie ein Paar von ein Paar von Werten.|

## <a name="members"></a>Member

##<a name="pair"></a> Paar (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das ein Paar von Werten umschließt.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    ref class pair;
```

#### <a name="parameters"></a>Parameter

*Wert1*<br/>
Der Typ des ersten einem Wrapper versehene Wert.

*Wert2*<br/>
Der Typ des zweiten einem Wrapper versehene Wert.

## <a name="members"></a>Member

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|[pair::first_type (STL/CLR)](#first_type)|Der Typ des ersten umschlossene Werts.|
|[pair::second_type (STL/CLR)](#second_type)|Der Typ des umschlossenen Sekundenwert.|

|Member-Objekt|Beschreibung|
|-------------------|-----------------|
|[pair::first (STL/CLR)](#first)|Der erste gespeicherte Wert.|
|[pair::second (STL/CLR)](#second)|Das zweite gespeicherte Wert.|

|Memberfunktion|Beschreibung|
|---------------------|-----------------|
|[pair::pair (STL/CLR)](#pair_pair)|Erstellt ein paarobjekt.|
|[pair::swap (STL/CLR)](#swap)|Vertauscht den Inhalt von zwei Wertepaaren.|

|Operator|Beschreibung|
|--------------|-----------------|
|[pair::operator= (STL/CLR)](#op_as)|Ersetzt das gespeicherte Paar von Werten.|

## <a name="remarks"></a>Hinweise

Das Objekt speichert ein Paar von Werten. Verwenden Sie diese Vorlagenklasse, zwei Werte in einem einzigen Objekt kombiniert. Darüber hinaus das Objekt `cliext::pair` (hier beschrieben) speichert nur von verwalteten Typen; verwenden Sie zum Speichern von ein Paar von nicht verwalteten Typen `std::pair`, deklariert in `<utility>`.

## <a name="first"></a> Pair::First (STL/CLR)

Der erste umschlossene Wert.

### <a name="syntax"></a>Syntax

```cpp
Value1 first;
```

### <a name="remarks"></a>Hinweise

Das Objekt speichert die erste einem Wrapper versehene Wert.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_first.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="first_type"></a> Pair::first_type (STL/CLR)

Der Typ des ersten umschlossene Werts.

### <a name="syntax"></a>Syntax

```cpp
typedef Value1 first_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den Vorlagenparameter *Value1*.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_first_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="op_as"></a> Pair:: Operator = (STL/CLR)

Ersetzt das gespeicherte Paar von Werten.

### <a name="syntax"></a>Syntax

```cpp
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*right*<br/>
-Paar kopiert.

### <a name="remarks"></a>Hinweise

Die Member-Operator Kopien *rechten* klicken Sie dann auf das Objekt, gibt `*this`. Damit können Sie das gespeicherte Paar von Werten mit einer Kopie der Werte in das gespeicherte Paar ersetzen *rechten*.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_as.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

// assign to a new pair
    cliext::pair<wchar_t, int> c2;
    c2 = c1;
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);
    return (0);
    }
```

```Output
[x, 3]
[x, 3]
```

## <a name="pair_pair"></a> Pair:: Pair (STL/CLR)

Erstellt ein paarobjekt.

### <a name="syntax"></a>Syntax

```cpp
pair();
pair(pair<Coll>% right);
pair(pair<Coll>^ right);
pair(Value1 val1, Value2 val2);
```

#### <a name="parameters"></a>Parameter

*right*<br/>
-Paar, zu speichern.

*Wert1*<br/>
Erste zu speichernde Wert.

*Wert2*<br/>
Zweite zu speichernde Wert.

### <a name="remarks"></a>Hinweise

Der Konstruktor:

`pair();`

Initialisiert das gespeicherte Paar mit den Standardwerten erstellt.

Der Konstruktor:

`pair(pair<Value1, Value2>% right);`

Initialisiert das gespeicherte Paar mit `right.` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) und `right.` [Pair:: Second (STL/CLR)](../dotnet/pair-second-stl-clr.md).

`pair(pair<Value1, Value2>^ right);`

Initialisiert das gespeicherte Paar mit `right->` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) und `right>` [Pair:: Second (STL/CLR)](../dotnet/pair-second-stl-clr.md).

Der Konstruktor:

`pair(Value1 val1, Value2 val2);`

Initialisiert das gespeicherte Paar mit *val1* und *val2*.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_construct.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
// construct an empty container
    cliext::pair<wchar_t, int> c1;
    System::Console::WriteLine("[{0}, {1}]",
        c1.first == L'\0' ? "\\0" : "??", c1.second);

// construct with a pair of values
    cliext::pair<wchar_t, int> c2(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

// construct by copying another pair
    cliext::pair<wchar_t, int> c3(c2);
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);

// construct by copying a pair handle
    cliext::pair<wchar_t, int> c4(%c3);
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);

    return (0);
    }
```

```Output
[\0, 0]
[x, 3]
[x, 3]
[x, 3]
```

## <a name="second"></a> Pair:: Second (STL/CLR)

Die zweite Wert Wrapper eingeschlossen ist.

### <a name="syntax"></a>Syntax

```cpp
Value2 second;
```

### <a name="remarks"></a>Hinweise

Das Objekt speichert die zweite einem Wrapper versehene Wert.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_second.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="second_type"></a> Pair::second_type (STL/CLR)

Der Typ des umschlossenen Sekundenwert.

### <a name="syntax"></a>Syntax

```cpp
typedef Value2 second_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den Vorlagenparameter *Value2*.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_second_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="swap"></a> Pair:: Swap (STL/CLR)

Vertauscht den Inhalt von zwei Wertepaaren.

### <a name="syntax"></a>Syntax

```cpp
void swap(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*right*<br/>
Paar, das Inhalt getauscht.

### <a name="remarks"></a>Hinweise

Die Memberfunktion tauscht das gespeicherte Paar von Werten zwischen `*this` und *rechten*.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_swap.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    cliext::deque<wchar_t> d2(5, L'x');
    Mycoll c2(%d2);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
x x x x x
x x x x x
a b c
```

## <a name="make_pair"></a> Make_pair (STL/CLR)

Stellen Sie eine `pair` von ein Paar von Werten.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);
```

#### <a name="parameters"></a>Parameter

*Wert1*<br/>
Der Typ des ersten umschlossene Werts.

*Wert2*<br/>
Der Typ des umschlossenen Sekundenwert.

*Erste*<br/>
Erste der zu umschließende Wert.

*Sekunde*<br/>
Zweite der zu umschließende Wert.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt `pair<Value1, Value2>(first, second)` zurück. Damit können Sie erstellen eine `pair<Value1, Value2>` Objekt in einem Paar von Werten.

### <a name="example"></a>Beispiel

```cpp
// cliext_make_pair.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    c1 = cliext::make_pair(L'y', 4);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    return (0);
    }
```

```Output
[x, 3]
[y, 4]
```

## <a name="op_neq"></a> Operator! = (Paar) (STL/CLR)

Koppeln Sie nicht gleich-Vergleich ein.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator!=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linken Paar, das verglichen werden soll.

*right*<br/>
Richtige Paar, das verglichen werden soll.

### <a name="remarks"></a>Hinweise

Gibt zurück, die Operatorfunktion `!(left == right)`. Damit können Sie testen, ob *linken* ist nicht identisch mit geordnet *rechten* Wenn die zwei Paare sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_ne.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] != [x 3] is {0}",
        c1 != c1);
    System::Console::WriteLine("[x 3] != [x 4] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] != [x 3] is False
[x 3] != [x 4] is True
```

## <a name="op_lt"></a> Operator&lt; (Paar) (STL/CLR)

Paar kleiner-als-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator<(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linken Paar, das verglichen werden soll.

*right*<br/>
Richtige Paar, das verglichen werden soll.

### <a name="remarks"></a>Hinweise

Gibt zurück, die Operatorfunktion `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second`. Damit können Sie testen, ob *linken* sortiert wird, ist die vor dem *rechten* Wenn die zwei Paare sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_lt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] < [x 3] is {0}",
        c1 < c1);
    System::Console::WriteLine("[x 3] < [x 4] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] < [x 3] is False
[x 3] < [x 4] is True
```

## <a name="op_lteq"></a> Operator&lt;= (Paar) (STL/CLR)

Koppeln Sie kleiner oder gleich Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator<=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linken Paar, das verglichen werden soll.

*right*<br/>
Richtige Paar, das verglichen werden soll.

### <a name="remarks"></a>Hinweise

Gibt zurück, die Operatorfunktion `!(right < left)`. Damit können Sie testen, ob *linken* wird nicht nach dem sortiert *rechten* Wenn die zwei Paare sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_le.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] <= [x 3] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] <= [x 3] is True
[x 4] <= [x 3] is False
```

## <a name="op_eq"></a> Operator == (Paar) (STL/CLR)

Pair-gleich-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator==(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linken Paar, das verglichen werden soll.

*right*<br/>
Richtige Paar, das verglichen werden soll.

### <a name="remarks"></a>Hinweise

Gibt zurück, die Operatorfunktion `left.first ==` `right.first &&` `left.second ==` `right.second`. Damit können Sie testen, ob *linken* sortiert wird, ist identisch mit *rechten* Wenn die zwei Paare sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_eq.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] == [x 3] is {0}",
        c1 == c1);
    System::Console::WriteLine("[x 3] == [x 4] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] == [x 3] is True
[x 3] == [x 4] is False
```

## <a name="op_gt"></a> Operator&gt; (Paar) (STL/CLR)

Das Paar ist größer als-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator>(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linken Paar, das verglichen werden soll.

*right*<br/>
Richtige Paar, das verglichen werden soll.

### <a name="remarks"></a>Hinweise

Gibt zurück, die Operatorfunktion `right` `<` `left`. Damit können Sie testen, ob *linken* sortiert wird, ist nach *rechten* Wenn die zwei Paare sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_gt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] > [x 3] is {0}",
        c1 > c1);
    System::Console::WriteLine("[x 4] > [x 3] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] > [x 3] is False
[x 4] > [x 3] is True
```

## <a name="op_gteq"></a> Operator&gt;= (Paar) (STL/CLR)

Paar von größer als oder gleich-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Value1,
    typename Value2>
    bool operator>=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linken Paar, das verglichen werden soll.

*right*<br/>
Richtige Paar, das verglichen werden soll.

### <a name="remarks"></a>Hinweise

Gibt zurück, die Operatorfunktion `!(left < right)`. Damit können Sie testen, ob *linken* ist nicht vor dem geordnet *rechten* Wenn die zwei Paare sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_pair_operator_ge.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] >= [x 3] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] >= [x 3] is True
[x 3] >= [x 4] is False
```