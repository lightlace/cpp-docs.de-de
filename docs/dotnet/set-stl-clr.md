---
title: set (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::set
- cliext::operator!=
- cliext::operator<
- cliext::operator<=
- cliext::operator==
- cliext::operator>
- cliext::operator>=
- cliext::set::begin
- cliext::set::clear
- cliext::set::const_iterator
- cliext::set::const_reference
- cliext::set::const_reverse_iterator
- cliext::set::count
- cliext::set::difference_type
- cliext::set::empty
- cliext::set::end
- cliext::set::equal_range
- cliext::set::erase
- cliext::set::find
- cliext::set::generic_container
- cliext::set::generic_iterator
- cliext::set::generic_reverse_iterator
- cliext::set::generic_value
- cliext::set::insert
- cliext::set::iterator
- cliext::set::key_comp
- cliext::set::key_compare
- cliext::set::key_type
- cliext::set::lower_bound
- cliext::set::make_value
- cliext::set::operator=
- cliext::set::rbegin
- cliext::set::reference
- cliext::set::rend
- cliext::set::reverse_iterator
- cliext::set::set
- cliext::set::size
- cliext::set::size_type
- cliext::set::swap
- cliext::set::to_array
- cliext::set::upper_bound
- cliext::set::value_comp
- cliext::set::value_compare
- cliext::set::value_type
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- set class [STL/CLR]
- operator!= (set) member [STL/CLR]
- operator< (set) member [STL/CLR]
- operator<= (set) member [STL/CLR]
- operator== (set) member [STL/CLR]
- operator> (set) member [STL/CLR]
- operator>= (set) member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- set member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
ms.openlocfilehash: 612c0772504043a99f3a2ae9fa7da9c791076d6a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384646"
---
# <a name="set-stlclr"></a>set (STL/CLR)

Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge Sequenz von Elementen steuert, die bidirektionalen Zugriff hat. Verwenden Sie den Container `set` zum Verwalten von einer Sequenz von Elementen als (fast) mit Lastenausgleich geordneten Struktur der Knoten, jeweils ein Element zu speichern.

In der folgenden Beschreibung `GValue` ist identisch mit `GKey`, die wiederum ist identisch mit *Schlüssel* , wenn die zweite ein Ref-Typ ist, in diesem Fall ist es `Key^`.

## <a name="syntax"></a>Syntax

```cpp
template<typename Key>
    ref class set
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>Parameter

*Key*<br/>
Der Typ der Schlüsselkomponente eines Elements in der kontrollierten Sequenz.

## <a name="requirements"></a>Anforderungen

**Header:** \<cliext/set>

**Namespace:** Cliext

## <a name="declarations"></a>Deklarationen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|[set::const_iterator (STL/CLR)](#const_iterator)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|
|[set::const_reference (STL/CLR)](#const_reference)|Der Typ eines konstanten Verweises auf ein Element.|
|[set::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|
|[set::difference_type (STL/CLR)](#difference_type)|Der Typ eines Abstands zwischen den beiden Elementen mit (möglicherweise Vorzeichen).|
|[set::generic_container (STL/CLR)](#generic_container)|Der Typ der generischen Schnittstelle für den Container.|
|[set::generic_iterator (STL/CLR)](#generic_iterator)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|
|[set::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|
|[set::generic_value (STL/CLR)](#generic_value)|Der Typ eines Elements für die generische Schnittstelle für den Container.|
|[set::iterator (STL/CLR)](#iterator)|Der Typ eines Iterators für die gesteuerte Sequenz.|
|[set::key_compare (STL/CLR)](#key_compare)|Der Delegat für zwei Schlüssel.|
|[set::key_type (STL/CLR)](#key_type)|Der Typ eines Sortierschlüssels.|
|[set::reference (STL/CLR)](#reference)|Der Typ eines Verweises auf ein Element.|
|[set::reverse_iterator (STL/CLR)](#reverse_iterator)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|
|[set::size_type (STL/CLR)](#size_type)|Der Typ der eine Entfernung (negativ) zwischen zwei Elementen.|
|[set::value_compare (STL/CLR)](#value_compare)|Der Delegat für zwei Elementwerte.|
|[set::value_type (STL/CLR)](#value_type)|Der Typ eines Elements.|

|Memberfunktion|Beschreibung|
|---------------------|-----------------|
|[set::begin (STL/CLR)](#begin)|Legt den Anfang der kontrollierten Sequenz fest.|
|[set::clear (STL/CLR)](#clear)|Entfernt alle Elemente.|
|[set::count (STL/CLR)](#count)|Zählt Elemente, die einem angegebenen Schlüssel entsprechen.|
|[set::empty (STL/CLR)](#empty)|Testet, ob keine Elemente vorhanden sind.|
|[set::end (STL/CLR)](#end)|Legt das Ende der kontrollierten Sequenz fest.|
|[set::equal_range (STL/CLR)](#equal_range)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|
|[set::erase (STL/CLR)](#erase)|Entfernt Elemente an den angegebenen Positionen.|
|[set::find (STL/CLR)](#find)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|
|[set::insert (STL/CLR)](#insert)|Fügt Elemente hinzu.|
|[set::key_comp (STL/CLR)](#key_comp)|Kopiert der Delegat für zwei Schlüssel.|
|[set::lower_bound (STL/CLR)](#lower_bound)|Sucht den Anfang des Bereichs, der einem angegebenen Schlüssel entspricht.|
|[set::make_value (STL/CLR)](#make_value)|Erstellt ein Wertobjekt.|
|[set::rbegin (STL/CLR)](#rbegin)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|
|[set::rend (STL/CLR)](#rend)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|
|[set::set (STL/CLR)](#set)|Erstellt ein container-Objekt.|
|[set::size (STL/CLR)](#size)|Ermittelt die Anzahl von Elementen.|
|[set::swap (STL/CLR)](#swap)|Vertauscht den Inhalt von zwei Containern.|
|[set::to_array (STL/CLR)](#to_array)|Kopiert die kontrollierte Sequenz in ein neues Array.|
|[set::upper_bound (STL/CLR)](#upper_bound)|Sucht das Ende des Bereichs, der einem angegebenen Schlüssel entspricht.|
|[set::value_comp (STL/CLR)](#value_comp)|Kopiert der Delegat für zwei Elementwerte.|

|Operator|Beschreibung|
|--------------|-----------------|
|[set::operator= (STL/CLR)](#op_as)|Ersetzt die kontrollierte Sequenz.|
|[operator!= (set) (STL/CLR)](#op_neq)|Bestimmt, ob eine `set` Objekt ist nicht gleich einem anderen `set` Objekt.|
|[operator< (set) (STL/CLR)](#op_lt)|Bestimmt, ob eine `set` Objekt ist kleiner als ein anderes `set` Objekt.|
|[operator<= (set) (STL/CLR)](#op_lteq)|Bestimmt, ob eine `set` Objekt ist kleiner als oder gleich einem anderen `set` Objekt.|
|[operator== (set) (STL/CLR)](#op_eq)|Bestimmt, ob eine `set` Objekt ist gleich einem anderen `set` Objekt.|
|[operator> (set) (STL/CLR)](#op_gt)|Bestimmt, ob eine `set` Objekt ist größer als ein anderer `set` Objekt.|
|[operator>= (set) (STL/CLR)](#op_gteq)|Bestimmt, ob eine `set` Objekt ist größer als oder gleich einem anderen `set` Objekt.|

## <a name="interfaces"></a>Schnittstellen

|Interface|Beschreibung|
|---------------|-----------------|
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|
|<xref:System.Collections.IEnumerable>|Durch die Elemente der Sequenz.|
|<xref:System.Collections.ICollection>|Behalten Sie die Gruppe von Elementen.|
|<xref:System.Collections.Generic.IEnumerable%601>|Durch die Elemente der typisierte Sequenz.|
|<xref:System.Collections.Generic.ICollection%601>|Behalten Sie die Gruppe von typisierten Elementen.|
|ITree\<Schlüssel, Wert >|Behalten Sie die generischen Container.|

## <a name="remarks"></a>Hinweise

Das Objekt belegt und-Freigaben für die Sequenz, die es, wie die einzelnen Knoten steuert. Er fügt Elemente an, in eine (nahezu) mit Lastenausgleich-Struktur, die er geordnete hält, durch die Links zwischen Knoten nie durch Kopieren den Inhalt eines Knotens in ein anderes ändern. Das bedeutet, Sie können einfügen und Entfernen von Elementen ohne störende verbleibenden Elemente frei.

Das Objekt sortiert die Sequenz, indem ein Delegatobjekt gespeicherten des Typs aufrufen [Set:: key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md). Sie können das gespeicherte Delegatobjekt angeben, wenn Sie die Gruppe erstellen; Wenn Sie kein Delegatobjekt angeben, wird der Standardwert ist der Vergleich `operator<(key_type, key_type)`. Sie greifen auf diese gespeicherten Objekt durch Aufrufen der Memberfunktion [Set:: key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)`()`.

Solche ein Delegatobjekt muss eine strikte schwache Sortierung auf die Schlüssel des Typs anwenden [Set:: KEY_TYPE (STL/CLR)](../dotnet/set-key-type-stl-clr.md). Bedeutet, dass für alle Schlüssel, der zwei `X` und `Y`:

`key_comp()(X, Y)` Gibt der gleichen boolesche Ergebnis bei jedem Aufruf.

Wenn `key_comp()(X, Y)` ist "true", klicken Sie dann `key_comp()(Y, X)` muss auf falsch gesetzt sein.

Wenn `key_comp()(X, Y)` ist "true", klicken Sie dann `X` wird vor dem sortiert werden als `Y`.

Wenn `!key_comp()(X, Y) && !key_comp()(Y, X)` ist "true", klicken Sie dann `X` und `Y` gelten als die entsprechende Reihenfolge aufweisen.

Für jedes Element `X` vorausgeht, die `Y` in die kontrollierte Sequenz `key_comp()(Y, X)` ist "false". (Für das Objekt für den Standard-Delegaten verringern Sie Schlüssel nie im Wert.) Im Gegensatz zur Vorlagenklasse [festgelegt](../dotnet/set-stl-clr.md), ein Objekt der Vorlagenklasse `set` erfordert nicht, dass der Schlüssel für alle Elemente eindeutig sind. (Zwei oder mehr Tasten können die entsprechende Reihenfolge aufweisen.)

Jedes Element dient sowohl als eine Ey auch einen Wert. Die Sequenz wird so dargestellt, die Such-, Einfüge- und zum Entfernen eines beliebigen Elements mit einer Anzahl von Vorgängen proportional zum Logarithmus der Anzahl der Elemente in der Sequenz (logarithmischer Zeit) zulässt. Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.

Eine Gruppe unterstützt bidirektionale Iteratoren, was bedeutet, dass Sie schrittweise können, um benachbarte Elemente, die einen Iterator, der ein Element in der gesteuerten Sequenz angegeben. Ein spezieller Head-Knoten entspricht den von zurückgegeben Iterator [Set:: End (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Dieser Iterator das letzte Element in der kontrollierten Sequenz, erreichen können ggf. verringert werden. Können Sie einen Set-Iterator zum Erreichen des Head-Knotens erhöhen, und es wird dann gleich `end()`. Aber Sie können nicht den Iterator zurückgegeben, die von dereferenziert `end()`.

Beachten Sie, dass Sie nicht auf ein Set-Element, das direkt erhält die numerische Position verweisen können, –, der einen Iterator mit zufälligem Zugriff erfordert.

Ein Iterator Satz speichert ein Handle zum Knoten zugeordneten Gruppe, die wiederum ein Handle für den zugehörigen Container gespeichert. Sie können Iteratoren nur mit ihren zugehörigen Container-Objekten verwenden. Ein Iterator Satz bleibt gültig, solange der zugeordnete Knoten eine Gruppe zugeordnet ist. Darüber hinaus ein gültiger Iterator dereferencable – können sie Zugriff haben und ändern den Wert der Elements festlegt – solange sie nicht gleich ist `end()`.

Löschen oder Entfernen eines Elements Ruft den Destruktor für ihren gespeicherten Wert auf. Löschen den Container löscht alle Elemente. Daher wird ein Container, dessen Elementtyp einer Verweisklasse ist, keine Elemente des Containers nicht überdauern. Beachten Sie jedoch, dass ein Container für Handles verfügt *nicht* seine Elemente zerstören.

## <a name="members"></a>Member

## <a name="begin"></a>set::begin (STL/CLR)

Legt den Anfang der kontrollierten Sequenz fest.

### <a name="syntax"></a>Syntax

```cpp
iterator begin();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt einen bidirektionalen Iterator, der das erste Element der kontrollierten Sequenz oder direkt hinter das Ende einer leeren Sequenz bestimmt. Sie können damit einen Iterator abrufen, bestimmt die `current` Anfang der kontrollierten Sequenz, aber der Status kann ändern, wenn die Länge der kontrollierten Sequenz ändert.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_begin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    Myset::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*begin() = a
*++begin() = b
```

## <a name="clear"></a>set::clear (STL/CLR)

Entfernt alle Elemente.

### <a name="syntax"></a>Syntax

```cpp
void clear();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft effektiv [Set:: Erase (STL/CLR)](../dotnet/set-erase-stl-clr.md) `(` [Set:: begin (STL/CLR)](../dotnet/set-begin-stl-clr.md) `(),` [Set:: End (STL/CLR)](../dotnet/set-end-stl-clr.md) `())`. Damit können Sie sicherstellen, dass die kontrollierte Sequenz leer ist.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_clear.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

// add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 0
a b
size() = 0
```

## <a name="const_iterator"></a>set::const_iterator (STL/CLR)

Der Typ eines konstanten Iterators für die gesteuerte Sequenz.

### <a name="syntax"></a>Syntax

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt ein Objekt vom nicht angegebenen Typ `T2` , das als konstanter bidirektionaler Iterator für die gesteuerte Sequenz fungieren kann.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_const_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    Myset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="const_reference"></a>set::const_reference (STL/CLR)

Der Typ eines konstanten Verweises auf ein Element.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt einen konstanten Verweis auf ein Element.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_const_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    Myset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myset::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="const_reverse_iterator"></a>set::const_reverse_iterator (STL/CLR)

Der Typ eines Konstanten umgekehrten Iterators für die gesteuerte Sequenz...

### <a name="syntax"></a>Syntax

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt ein Objekt vom nicht angegebenen Typ `T4` , das als konstanter reverse-Iterator für die gesteuerte Sequenz dienen kann.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" reversed
    Myset::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="count"></a>set::count (STL/CLR)

Sucht die Anzahl von Elementen, die einem angegebenen Schlüssel entsprechen.

### <a name="syntax"></a>Syntax

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>Parameter

*key*<br/>
Der zu suchende Schlüsselwert.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Anzahl der Elemente zurück, in der kontrollierten Sequenz, die entsprechende Sortierung mit *Schlüssel*. Damit können Sie um die Anzahl der Elemente, die derzeit in der gesteuerten Sequenz zu ermitteln, die einem angegebenen Schlüssel entsprechen.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_count.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
a b c
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="difference_type"></a>set::difference_type (STL/CLR)

Die Typen des Abstands zwischen den beiden Elementen mit Vorzeichen.

### <a name="syntax"></a>Syntax

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt eine möglicherweise negative Elementanzahl.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_difference_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myset::difference_type diff = 0;
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

// compute negative difference
    diff = 0;
    for (Myset::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="empty"></a>set::empty (STL/CLR)

Testet, ob keine Elemente vorhanden sind.

### <a name="syntax"></a>Syntax

```cpp
bool empty();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt „true“ für eine leere gesteuerte Sequenz zurück. Dies ist äquivalent zum [Set:: Size (STL/CLR)](../dotnet/set-size-stl-clr.md)`() == 0`. Damit können Sie überprüfen, ob der Satz leer ist.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_empty.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="end"></a>set::end (STL/CLR)

Legt das Ende der kontrollierten Sequenz fest.

### <a name="syntax"></a>Syntax

```cpp
iterator end();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt einem bidirektionalen Iterator, der direkt hinter das Ende der kontrollierten Sequenz verweist. Damit können Sie einen Iterator abrufen, der das Ende der kontrollierten Sequenz bestimmt; der Status verfügt nicht geändert werden, wenn die Länge der kontrollierten Sequenz ändert.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_end.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last two items
    Myset::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
```

## <a name="equal_range"></a>set::equal_range (STL/CLR)

Sucht den Bereich, der einem angegebenen Schlüssel entspricht.

### <a name="syntax"></a>Syntax

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Parameter

*key*<br/>
Der zu suchende Schlüsselwert.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt ein Paar von Iteratoren `cliext::pair<iterator, iterator>(` [Set:: lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md) `(key),` [Set:: upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)`(key))`. Damit können Sie um des Bereichs von Elementen, die derzeit in der gesteuerten Sequenz zu ermitteln, die einem angegebenen Schlüssel entsprechen.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_equal_range.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
typedef Myset::pair_iter_iter Pairii;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

// display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("{0} ", *pair1.first);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
equal_range(L'x') empty = True
b
```

## <a name="erase"></a>set::erase (STL/CLR)

Entfernt Elemente an den angegebenen Positionen.

### <a name="syntax"></a>Syntax

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
size_type erase(key_type key)
```

#### <a name="parameters"></a>Parameter

*first*<br/>
Anfang des zu löschenden Bereichs.

*key*<br/>
Schlüssel-Wert zu löschen.

*last*<br/>
Ende der zu löschenden Bereichs.

*where*<br/>
Element löschen.

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion entfernt das Element der kontrollierten Sequenz verweist *, in denen*, und gibt einen Iterator, der das erste Element, das über das Element entfernt wurde, oder [Set:: End (STL/CLR) ](../dotnet/set-end-stl-clr.md) `()` Wenn kein solches Element vorhanden ist. Damit können Sie um ein einzelnes Element zu entfernen.

Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich [`first`, `last`), und gibt einen Iterator, der das erste Element entfernten Elemente hinaus verbliebene festlegt oder `end()` Wenn kein solches Element vorhanden ist... Damit können Sie um NULL oder mehr aufeinander folgende Elemente zu entfernen.

Die dritte Memberfunktion entfernt jedes Element der kontrollierten Sequenz, deren Schlüssel verfügt über entsprechende Reihenfolge, auf *Schlüssel*, und gibt die Anzahl die Anzahl der entfernten Elemente zurück. Damit können Sie entfernen und die Anzahl aller Elemente, die einen angegebenen Schlüssel entsprechen.

Jedes Element Löschung braucht Zeit proportional zum Logarithmus der Anzahl der Elemente der gesteuerten Sequenz.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_erase.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

// add elements and display " b c d e"
    c1.insert(L'd');
    c1.insert(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// erase all but end
    Myset::iterator it = c1.end();
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",
        *c1.erase(c1.begin(), --it));
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
erase(begin()) = b
b c d e
erase(begin(), end()-1) = e
size() = 1
```

## <a name="find"></a>set::find (STL/CLR)

Sucht ein Element, das einem angegebenen Schlüssel entspricht.

### <a name="syntax"></a>Syntax

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Parameter

*key*<br/>
Der zu suchende Schlüsselwert.

### <a name="remarks"></a>Hinweise

Verfügt über mindestens ein Element in der gesteuerten Sequenz entsprechende Sortierung mit *Schlüssel*, die Memberfunktion gibt einen Iterator zurück eins dieser Elemente; andernfalls [Set:: End (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Damit können Sie um ein Element derzeit in der gesteuerten Sequenz zu suchen, die einem angegebenen Schlüssel entspricht.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_find.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());
    System::Console::WriteLine("find {0} = {1}",
        L'b', *c1.find(L'b'));
    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
a b c
find A = False
find b = b
find C = False
```

## <a name="generic_container"></a>set::generic_container (STL/CLR)

Der Typ der generischen Schnittstelle für den Container.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt die generische Schnittstelle für diese Vorlage Container-Klasse.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_generic_container.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    gc1->insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify original and display generic
    c1.insert(L'e');
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c d
a b c d e
```

## <a name="generic_iterator"></a> set::generic_iterator (STL/CLR)

Der Typ eines Iterators für die Verwendung mit der generischen Schnittstelle für den Container.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt einen generischen Iterator, der mit der generischen Schnittstelle für diese Vorlage Container-Klasse verwendet werden kann.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_generic_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_iterator gcit = gc1->begin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="generic_reverse_iterator"></a> set::generic_reverse_iterator (STL/CLR)

Der Typ eines umgekehrten Iterators für die Verwendung mit der generischen Schnittstelle für den Container.

### <a name="syntax"></a>Syntax

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt einen generische reverse-Iterator, der mit der generischen Schnittstelle für diese Vorlage Container-Klasse verwendet werden kann.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_reverse_iterator gcit = gc1->rbegin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="generic_value"></a> set::generic_value (STL/CLR)

Der Typ eines Elements für die Verwendung mit der generischen Schnittstelle für den Container.

### <a name="syntax"></a>Syntax

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt ein Objekt des Typs `GValue` , beschreibt den gespeichertes Element-Wert für die Verwendung mit der generischen Schnittstelle für diese Vorlage Container-Klasse.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_generic_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_iterator gcit = gc1->begin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="insert"></a> set::insert (STL/CLR)

Fügt Elemente hinzu.

### <a name="syntax"></a>Syntax

```cpp
cliext::pair<iterator, bool> insert(value_type val);
iterator insert(iterator where, value_type val);
template<typename InIter>
    void insert(InIter first, InIter last);
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);
```

#### <a name="parameters"></a>Parameter

*first*<br/>
Anfang des Bereichs, der eingefügt.

*last*<br/>
Ende des Bereichs, der eingefügt.

*right*<br/>
Die Enumeration zum Einfügen.

*val*<br/>
Schlüssel-Wert einfügen.

*where*<br/>
Die Position, im Container zum Einfügen (nur Hint).

### <a name="remarks"></a>Hinweise

Jede der Memberfunktionen Fügt eine Sequenz, die von den verbleibenden Operanden angegeben.

Die erste Memberfunktion versucht, ein Element mit dem Wert einfügen *Val*, und gibt ein Paar von Werten `X`. Wenn `X.second` ist "true" `X.first` bestimmt das neu eingefügte Element; andernfalls `X.first` kennzeichnet ein Element mit entsprechender Sortierung, die bereits vorhanden ist und kein neues Element eingefügt wird. Damit können Sie ein einzelnes Element einfügen.

Die zweite Memberfunktion Fügt ein Element mit dem Wert *Val*mit *, in denen* als Hinweis (zur Verbesserung der Leistung), und gibt einen Iterator, der das neu eingefügte Element festlegt. Damit können Sie ein einzelnes Element einfügen, die neben einem Element möglicherweise, die Sie kennen.

Die dritte Memberfunktion fügt die Sequenz [`first`, `last`). Sie verwenden ihn zum Einfügen von NULL oder mehr Elementen, die aus einer anderen Sequenz kopiert haben.

Die vierte Memberfunktion fügt die Sequenz, die vom angegebenen die *rechten*. Damit können Sie eine Sequenz, die von einem Enumerator beschrieben einfügen.

Jedes Element einfügen braucht Zeit proportional zum Logarithmus der Anzahl der Elemente der gesteuerten Sequenz. Einfügen kann in amortisierter konstanter Zeit, jedoch auftreten, erhalten einen Hinweis, der ein Element, das neben der Einfügemarke festlegt.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_insert.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
typedef Myset::pair_iter_bool Pairib;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value, unique and duplicate
    Pairib pair1 = c1.insert(L'x');
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",
        *pair1.first, pair1.second);

    pair1 = c1.insert(L'b');
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",
        *pair1.first, pair1.second);

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value with hint
    System::Console::WriteLine("insert(begin(), L'y') = {0}",
        *c1.insert(c1.begin(), L'y'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an iterator range
    Myset c2;
    Myset::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an enumeration
    Myset c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
insert(L'x') = [x True]
insert(L'b') = [b False]
a b c x
insert(begin(), L'y') = y
a b c x y
a b c x
a b c x y
```

## <a name="iterator"></a> set::iterator (STL/CLR)

Der Typ eines Iterators für die gesteuerte Sequenz.

### <a name="syntax"></a>Syntax

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt ein Objekt vom nicht angegebenen Typ `T1` , die als bidirektionaler Iterator für die gesteuerte Sequenz fungieren kann.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    Myset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="key_comp"></a> set::key_comp (STL/CLR)

Kopiert der Delegat für zwei Schlüssel.

### <a name="syntax"></a>Syntax

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt der Delegat verwendet, um die kontrollierte Sequenz sortiert zurück. Damit können Sie zwei Schlüssel vergleichen.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_key_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

// test a different ordering rule
    Myset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
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

## <a name="key_compare"></a> Set:: key_compare (STL/CLR)

Der Delegat für zwei Schlüssel.

### <a name="syntax"></a>Syntax

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die der Delegat, der die Reihenfolge der wichtigsten Argumente bestimmt.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_key_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

// test a different ordering rule
    Myset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
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

## <a name="key_type"></a> set::key_type (STL/CLR)

Der Typ eines Sortierschlüssels.

### <a name="syntax"></a>Syntax

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den Vorlagenparameter *Schlüssel*.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_key_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" using key_type
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myset::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="lower_bound"></a> set::lower_bound (STL/CLR)

Sucht den Anfang des Bereichs, der einem angegebenen Schlüssel entspricht.

### <a name="syntax"></a>Syntax

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Parameter

*key*<br/>
Der zu suchende Schlüsselwert.

### <a name="remarks"></a>Hinweise

Die Memberfunktion bestimmt das erste Element `X` in der kontrollierten Sequenz, die Sortierung *Schlüssel*. Wenn kein solches Element vorhanden ist, gibt es [Set:: End (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`; andernfalls wird einen Iterator, `X`. Damit können Sie derzeit suchen den Anfang einer Sequenz von Elementen in der kontrollierten Sequenz, die einen angegebenen Schlüssel entsprechen.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_lower_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    System::Console::WriteLine("*lower_bound(L'a') = {0}",
        *c1.lower_bound(L'a'));
    System::Console::WriteLine("*lower_bound(L'b') = {0}",
        *c1.lower_bound(L'b'));
    return (0);
    }
```

```Output
a b c
lower_bound(L'x')==end() = True
*lower_bound(L'a') = a
*lower_bound(L'b') = b
```

## <a name="make_value"></a> set::make_value (STL/CLR)

Erstellt ein Wertobjekt.

### <a name="syntax"></a>Syntax

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>Parameter

*key*<br/>
Schlüssel-Wert verwenden.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt ein `value_type` Objekts, dessen Schlüssel *Schlüssel*. Damit können Sie um ein Objekt kann mit anderen Memberfunktionen zu erstellen.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_make_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(Myset::make_value(L'a'));
    c1.insert(Myset::make_value(L'b'));
    c1.insert(Myset::make_value(L'c'));

// display contents " a b c"
    for each (Myset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="op_as"></a> set::operator= (STL/CLR)

Ersetzt die kontrollierte Sequenz.

### <a name="syntax"></a>Syntax

```cpp
set<Key>% operator=(set<Key>% right);
```

#### <a name="parameters"></a>Parameter

*right*<br/>
Der zu kopierende Container.

### <a name="remarks"></a>Hinweise

Die Member-Operator Kopien *rechten* klicken Sie dann auf das Objekt, gibt `*this`. Damit können Sie die kontrollierte Sequenz durch eine Kopie der kontrollierten Sequenz in ersetzen *rechten*.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_operator_as.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (Myset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2 = c1;
// display contents " a b c"
    for each (Myset::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="rbegin"></a> set::rbegin (STL/CLR)

Legt den Anfang der umgekehrten kontrollierten Sequenz fest.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt einen umgekehrten Iterator, der das letzte Element der kontrollierten Sequenz oder unmittelbar nach dem Anfang einer leeren Sequenz bestimmt. Daher wird die `beginning` der umgekehrten Sequenz. Sie können damit einen Iterator abrufen, bestimmt die `current` Anfang der kontrollierten Sequenz in umgekehrter Reihenfolge, aber der Status kann ändern, wenn die Länge der kontrollierten Sequenz ändert.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_rbegin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items in reversed sequence
    Myset::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
```

## <a name="reference"></a> set::reference (STL/CLR)

Der Typ eines Verweises auf ein Element.

### <a name="syntax"></a>Syntax

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt einen Verweis auf ein Element.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    Myset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myset::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="rend"></a> set::rend (STL/CLR)

Legt das Ende der umgekehrten kontrollierten Sequenz fest.

### <a name="syntax"></a>Syntax

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt einem umgekehrten Iterator, der zeigt unmittelbar nach dem Anfang der kontrollierten Sequenz zurück. Daher wird die `end` der umgekehrten Sequenz. Sie können damit einen Iterator abrufen, bestimmt die `current` Ende der kontrollierten Sequenz in umgekehrter Reihenfolge, aber der Status kann ändern, wenn die Länge der kontrollierten Sequenz ändert.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_rend.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    Myset::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
```

## <a name="reverse_iterator"></a> set::reverse_iterator (STL/CLR)

Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.

### <a name="syntax"></a>Syntax

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt ein Objekt vom nicht angegebenen Typ `T3` , die als reverse-Iterator für die gesteuerte Sequenz fungieren kann.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" reversed
    Myset::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="set"></a> set::set (STL/CLR)

Erstellt ein container-Objekt.

### <a name="syntax"></a>Syntax

```cpp
set();
explicit set(key_compare^ pred);
set(set<Key>% right);
set(set<Key>^ right);
template<typename InIter>
    setset(InIter first, InIter last);
template<typename InIter>
    set(InIter first, InIter last,
        key_compare^ pred);
set(System::Collections::Generic::IEnumerable<GValue>^ right);
set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
```

#### <a name="parameters"></a>Parameter

*first*<br/>
Anfang des Bereichs, der eingefügt.

*last*<br/>
Ende des Bereichs, der eingefügt.

*Pred*<br/>
Sortieren Prädikat für die gesteuerte Sequenz.

*right*<br/>
Einzufügendes Objekt bzw. einzufügender Bereich.

### <a name="remarks"></a>Hinweise

Der Konstruktor:

`set();`

Initialisiert die kontrollierte Sequenz ohne Elemente, mit der standardmäßigen Reihenfolge Prädikat `key_compare()`. Damit können Sie eine leere gesteuerte Sequenz, mit der standardmäßigen Reihenfolge Prädikat angeben.

Der Konstruktor:

`explicit set(key_compare^ pred);`

Initialisiert die kontrollierte Sequenz ohne Elemente, mit der Sortierung Prädikat *Pred*. Damit können Sie eine leere gesteuerte Sequenz, mit dem angegebenen Prädikat für die Sortierung angeben.

Der Konstruktor:

`set(set<Key>% right);`

Initialisiert die kontrollierte Sequenz durch die Sequenz [`right.begin()`, `right.end()`), mit der standardmäßigen Reihenfolge Prädikat. Damit können Sie eine gesteuerte Sequenz angeben, die eine Kopie der gesteuerte Sequenz durch die Set-Objekt ist *rechten*, mit der standardmäßigen Reihenfolge Prädikat.

Der Konstruktor:

`set(set<Key>^ right);`

Initialisiert die kontrollierte Sequenz durch die Sequenz [`right->begin()`, `right->end()`), mit der standardmäßigen Reihenfolge Prädikat. Damit können Sie eine gesteuerte Sequenz angeben, die eine Kopie der gesteuerte Sequenz durch die Set-Objekt ist *rechten*, mit der standardmäßigen Reihenfolge Prädikat.

Der Konstruktor:

`template<typename InIter> set(InIter first, InIter last);`

Initialisiert die kontrollierte Sequenz durch die Sequenz [`first`, `last`), mit der standardmäßigen Reihenfolge Prädikat. Damit können Sie der gesteuerten Sequenz eine Kopie einer anderen Sequenz, mit der standardmäßigen Reihenfolge Prädikat erstellen.

Der Konstruktor:

`template<typename InIter> set(InIter first, InIter last, key_compare^ pred);`

Initialisiert die kontrollierte Sequenz durch die Sequenz [`first`, `last`), mit der Sortierung Prädikat *Pred*. Damit können Sie um der gesteuerten Sequenz eine Kopie einer anderen Sequenz, mit dem angegebenen Prädikat für die Sortierung zu erstellen.

Der Konstruktor:

`set(System::Collections::Generic::IEnumerable<Key>^ right);`

Initialisiert die kontrollierte Sequenz durch die Sequenz, die vom Enumerator festgelegt *rechten*, mit der standardmäßigen Reihenfolge Prädikat. Damit können Sie um der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die von einem Enumerator, mit der standardmäßigen Reihenfolge Prädikat beschrieben zu erstellen.

Der Konstruktor:

`set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

Initialisiert die kontrollierte Sequenz durch die Sequenz, die vom Enumerator festgelegt *rechten*, mit der Sortierung Prädikat *Pred*. Damit können Sie um der gesteuerten Sequenz eine Kopie einer anderen Sequenz durch ein Enumerator, mit dem angegebenen Prädikat für die Sortierung beschrieben zu erstellen.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_construct.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
// construct an empty container
    Myset c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an ordering rule
    Myset c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range
    Myset c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range and an ordering rule
    Myset c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration
    Myset c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration and an ordering rule
    Myset c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct from a generic container
    Myset c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    Myset c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
a b c
size() = 0
c b a
a b c
c b a
a b c
c b a
c b a
a b c
```

## <a name="size"></a> set::size (STL/CLR)

Ermittelt die Anzahl von Elementen.

### <a name="syntax"></a>Syntax

```cpp
size_type size();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Länge der gesteuerten Sequenz zurück. Damit können Sie die Anzahl der Elemente, die derzeit in der kontrollierten Sequenz bestimmt. Wenn Sie besonders interessierenden lediglich, ob die Reihenfolge größer, finden Sie unter hat [Set:: Empty (STL/CLR)](../dotnet/set-empty-stl-clr.md)`()`.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_size.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

// add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 3 starting with 3
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="size_type"></a> set::size_type (STL/CLR)

Der Typ eines Abstands zwischen den beiden Elementen mit Vorzeichen.

### <a name="syntax"></a>Syntax

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt eine nicht Negative Elementanzahl.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_size_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myset::size_type diff = 0;
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="swap"></a> set::swap (STL/CLR)

Vertauscht den Inhalt von zwei Containern.

### <a name="syntax"></a>Syntax

```cpp
void swap(set<Key>% right);
```

#### <a name="parameters"></a>Parameter

*right*<br/>
Container für den Tausch von Inhalten.

### <a name="remarks"></a>Hinweise

Die Memberfunktion tauscht die kontrollierten Sequenzen zwischen `this` und *rechten*. Dies erfolgt in konstanter Zeit aus, und es löst keine Ausnahmen aus. Sie verwenden es als eine schnelle Möglichkeit, den Inhalt von zwei Containern austauschen.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_swap.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    Myset c2;
    c2.insert(L'd');
    c2.insert(L'e');
    c2.insert(L'f');
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
d e f
d e f
a b c
```

## <a name="to_array"></a> set::to_array (STL/CLR)

Kopiert die kontrollierte Sequenz in ein neues Array.

### <a name="syntax"></a>Syntax

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt ein Array mit der kontrollierten Sequenz zurück. Damit können Sie eine Kopie der kontrollierten Sequenz in Arrayform abrufen.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_to_array.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.insert(L'd');
    for each (wchar_t elem in c1)
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
a b c d
a b c
```

## <a name="upper_bound"></a> set::upper_bound (STL/CLR)

Sucht das Ende des Bereichs, der einem angegebenen Schlüssel entspricht.

### <a name="syntax"></a>Syntax

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Parameter

*key*<br/>
Der zu suchende Schlüsselwert.

### <a name="remarks"></a>Hinweise

Die Memberfunktion bestimmt das letzte Element `X` in der kontrollierten Sequenz, die Sortierung *Schlüssel*. Wenn kein solches Element vorhanden ist, oder wenn `X` ist das letzte Element in der gesteuerten Sequenz ist, gibt [Set:: End (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`; andernfalls wird einen Iterator, der das erste Element nach `X`. Damit können Sie derzeit suchen das Ende einer Sequenz von Elementen in der kontrollierten Sequenz, die einen angegebenen Schlüssel entsprechen.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_upper_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    System::Console::WriteLine("*upper_bound(L'a') = {0}",
        *c1.upper_bound(L'a'));
    System::Console::WriteLine("*upper_bound(L'b') = {0}",
        *c1.upper_bound(L'b'));
    return (0);
    }
```

```Output
a b c
upper_bound(L'x')==end() = True
*upper_bound(L'a') = b
*upper_bound(L'b') = c
```

## <a name="value_comp"></a> set::value_comp (STL/CLR)

Kopiert der Delegat für zwei Elementwerte.

### <a name="syntax"></a>Syntax

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt der Delegat verwendet, um die kontrollierte Sequenz sortiert zurück. Damit können Sie zwei Elementwerte vergleichen.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_value_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="value_compare"></a> Set:: value_compare (STL/CLR)

Der Delegat für zwei Elementwerte.

### <a name="syntax"></a>Syntax

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die der Delegat, der die Reihenfolge der Werteargumente bestimmt.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_value_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="value_type"></a> set::value_type (STL/CLR)

Der Typ eines Elements.

### <a name="syntax"></a>Syntax

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `generic_value`.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_value_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" using value_type
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myset::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="op_neq"></a> operator!= (set) (STL/CLR)

Listen Sie nicht gleich-Vergleich ein.

### <a name="syntax"></a>Syntax

```cpp
template<typename Key>
    bool operator!=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Gibt zurück, die Operatorfunktion `!(left == right)`. Damit können Sie testen, ob *linken* ist nicht identisch mit geordnet *rechten* Wenn die beiden Sätze sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_operator_ne.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] != [a b c] is {0}",
        c1 != c1);
    System::Console::WriteLine("[a b c] != [a b d] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] != [a b c] is False
[a b c] != [a b d] is True
```

## <a name="op_lt"></a> operator&lt; (set) (STL/CLR)

Liste kleiner als Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Key>
    bool operator<(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Der Operator-Funktion gibt "true" zurück, wenn, für die niedrigste Position `i` für die `!(right[i] < left[i])` es ist auch, die "true" `left[i] < right[i]`. Andernfalls wird `left->size() < right->size()` damit können Sie testen, ob *linken* sortiert ist, bevor Sie *rechten* Wenn die beiden Sätze sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_operator_lt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] < [a b c] is {0}",
        c1 < c1);
    System::Console::WriteLine("[a b c] < [a b d] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] < [a b c] is False
[a b c] < [a b d] is True
```

## <a name="op_lteq"></a> operator&lt;= (set) (STL/CLR)

Kleiner oder gleich Liste Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Key>
    bool operator<=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Gibt zurück, die Operatorfunktion `!(right < left)`. Damit können Sie testen, ob *linken* wird nicht nach dem sortiert *rechten* Wenn die beiden Sätze sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_operator_le.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] <= [a b c] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] <= [a b c] is True
[a b d] <= [a b c] is False
```

## <a name="op_eq"></a> operator== (set) (STL/CLR)

Liste-gleich-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Key>
    bool operator==(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Die Operatorfunktion gibt "true" nur dann, wenn die Sequenzen von gesteuert *linken* und *rechten* die gleiche Länge aufweisen und für jede Position `i`, `left[i] ==` `right[i]`. Damit können Sie testen, ob *linken* sortiert wird, ist identisch mit *rechten* Wenn die beiden Sätze sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_operator_eq.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] == [a b c] is {0}",
        c1 == c1);
    System::Console::WriteLine("[a b c] == [a b d] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] == [a b c] is True
[a b c] == [a b d] is False
```

## <a name="op_gt"></a> operator&gt; (set) (STL/CLR)

Die Liste ist größer als-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Key>
    bool operator>(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Gibt zurück, die Operatorfunktion `right` `<` `left`. Damit können Sie testen, ob *linken* sortiert wird, ist nach *rechten* Wenn die beiden Sätze sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_operator_gt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] > [a b c] is {0}",
        c1 > c1);
    System::Console::WriteLine("[a b d] > [a b c] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] > [a b c] is False
[a b d] > [a b c] is True
```

## <a name="op_gteq"></a> operator&gt;= (set) (STL/CLR)

Liste, die größer als oder gleich-Vergleich.

### <a name="syntax"></a>Syntax

```cpp
template<typename Key>
    bool operator>=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>Parameter

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Gibt zurück, die Operatorfunktion `!(left < right)`. Damit können Sie testen, ob *linken* ist nicht vor dem geordnet *rechten* Wenn die beiden Sätze sind im Vergleich elementweise.

### <a name="example"></a>Beispiel

```cpp
// cliext_set_operator_ge.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] >= [a b c] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] >= [a b c] is True
[a b c] >= [a b d] is False
```