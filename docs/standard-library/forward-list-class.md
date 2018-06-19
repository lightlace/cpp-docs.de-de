---
title: forward_list-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- forward_list/std::forward_list
- forward_list/std::forward_list::allocator_type
- forward_list/std::forward_list::const_iterator
- forward_list/std::forward_list::const_pointer
- forward_list/std::forward_list::const_reference
- forward_list/std::forward_list::difference_type
- forward_list/std::forward_list::iterator
- forward_list/std::forward_list::pointer
- forward_list/std::forward_list::reference
- forward_list/std::forward_list::size_type
- forward_list/std::forward_list::value_type
- forward_list/std::forward_list::assign
- forward_list/std::forward_list::before_begin
- forward_list/std::forward_list::begin
- forward_list/std::forward_list::cbefore_begin
- forward_list/std::forward_list::cbegin
- forward_list/std::forward_list::cend
- forward_list/std::forward_list::clear
- forward_list/std::forward_list::emplace_after
- forward_list/std::forward_list::emplace_front
- forward_list/std::forward_list::empty
- forward_list/std::forward_list::end
- forward_list/std::forward_list::erase_after
- forward_list/std::forward_list::front
- forward_list/std::forward_list::get_allocator
- forward_list/std::forward_list::insert_after
- forward_list/std::forward_list::max_size
- forward_list/std::forward_list::merge
- forward_list/std::forward_list::pop_front
- forward_list/std::forward_list::push_front
- forward_list/std::forward_list::remove
- forward_list/std::forward_list::remove_if
- forward_list/std::forward_list::resize
- forward_list/std::forward_list::reverse
- forward_list/std::forward_list::sort
- forward_list/std::forward_list::splice_after
- forward_list/std::forward_list::swap
- forward_list/std::forward_list::unique
dev_langs:
- C++
helpviewer_keywords:
- std::forward_list
- std::forward_list::allocator_type
- std::forward_list::const_iterator
- std::forward_list::const_pointer
- std::forward_list::const_reference
- std::forward_list::difference_type
- std::forward_list::iterator
- std::forward_list::pointer
- std::forward_list::reference
- std::forward_list::size_type
- std::forward_list::value_type
- std::forward_list::assign
- std::forward_list::before_begin
- std::forward_list::begin
- std::forward_list::cbefore_begin
- std::forward_list::cbegin
- std::forward_list::cend
- std::forward_list::clear
- std::forward_list::emplace_after
- std::forward_list::emplace_front
- std::forward_list::empty
- std::forward_list::end
- std::forward_list::erase_after
- std::forward_list::front
- std::forward_list::get_allocator
- std::forward_list::insert_after
- std::forward_list::max_size
- std::forward_list::merge
- std::forward_list::pop_front
- std::forward_list::push_front
- std::forward_list::remove
- std::forward_list::remove_if
- std::forward_list::resize
- std::forward_list::reverse
- std::forward_list::sort
- std::forward_list::splice_after
- std::forward_list::swap
- std::forward_list::unique
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86e66d7f626943db2288cefdc6bedd5087f71c82
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848842"
---
# <a name="forwardlist-class"></a>forward_list-Klasse

Beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert. Die Sequenz wird als einfach verknüpfte Knotenliste gespeichert, die jeweils einen Member vom Typ `Type` enthält.

## <a name="syntax"></a>Syntax

```cpp
template <class Type,
    class Allocator = allocator<Type>>
class forward_list
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`Type`|Das in der Doppelschlange zu speichernde forward_list-Element.|
|`Allocator`|Das gespeicherte Zuordnungsobjekt, das Details zum Belegen und Freigeben des Arbeitsspeichers des forward_list-Elements kapselt. Dieser Parameter ist optional. Der Standardwert lautet allocator< `Type`>.|

## <a name="remarks"></a>Hinweise

Ein `forward_list`-Objekt nimmt für die Sequenz, die von ihm gesteuert wird, Speicherbelegungen und -freigaben über ein gespeichertes Objekt vor, das aus der Klasse `Allocator` abgeleitet wurde, die auf der [allocator-Klasse](../standard-library/allocator-class.md) basiert (im Allgemeinen als `std::allocator)` bekannt). Weitere Informationen finden Sie unter [Allocators](../standard-library/allocators.md). Ein Zuweisungsobjekt muss gleiche externe Schnittstelle wie ein Objekt der Vorlagenklasse `allocator` aufweisen.

> [!NOTE]
> Das gespeicherte Zuweisungsobjekt wird nicht kopiert, wenn das Containerobjekt zugewiesen wird.

Iteratoren, Zeiger und Verweise werden möglicherweise ungültig, wenn Elemente ihrer gesteuerten Sequenz von `forward_list` gelöscht werden. Durch die von `forward_list` auf der gesteuerten Sequenz durchgeführten Einfügungen und Verbindungen werden keine Iteratoren ungültig.

Hinzufügungen zur gesteuerten Sequenz können bei Aufrufen von [forward_list::insert_after](#insert_after) auftreten, welche die einzige Memberfunktion ist, die den Konstruktor `Type(const  T&)` aufruft. `forward_list` ruft möglicherweise auch Verschiebekonstruktoren auf. Wenn ein solcher Ausdruck eine Ausnahme auslöst, werden vom Containerobjekt keine neuen Elemente eingefügt, und die Ausnahme wird erneut ausgelöst. Daher wird ein Objekt der Vorlagenklasse `forward_list` bei Auftreten solche Ausnahmen in einem bekannten Zustand belassen.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[forward_list](#forward_list)|Konstruiert ein Objekt vom Typ `forward_list`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[allocator_type](#allocator_type)|Ein Typ, mit dem die Zuweisungsklasse für ein forward list-Objekt dargestellt wird.|
|[const_iterator](#const_iterator)|Ein Typ, der einen konstanten Iterator für die Vorwärtsliste bereitstellt.|
|[const_pointer](#const_pointer)|Ein Typ, der einen Zeiger auf ein `const`-Element in einer Vorwärtsliste bereitstellt.|
|[const_reference](#const_reference)|Ein Typ, der einen Konstantenverweis auf einer Vorwärtsliste gespeichertes Element bereitstellt.|
|[difference_type](#difference_type)|Ein Ganzzahltyp mit Vorzeichen, der dazu verwendet werden kann, die Anzahl von Elementen einer Vorwärtsliste in einen Bereich zwischen Elementen darzustellen, auf die von Iteratoren gezeigt wird.|
|[Iterator](#iterator)|Ein Typ, der einen Iterator für die Vorwärtsliste bereitstellt.|
|[Zeiger](#pointer)|Ein Typ, der einen Zeiger auf ein Element in der Vorwärtsliste bereitstellt.|
|[Verweis](#reference)|Ein Typ, der einen Verweis auf ein in der Vorwärtsliste gespeichertes Element bereitstellt.|
|[size_type](#size_type)|Ein Typ, der den Abstand ohne Vorzeichen zwischen zwei Elementen darstellt.|
|[value_type](#value_type)|Ein Typ, der den Typ des in einer Vorwärtsliste gespeicherten Elements darstellt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[assign](#assign)|Löscht Elemente aus einer Vorwärtsliste und kopiert einen neuen Satz von Elementen an eine Zielvorwärtsliste.|
|[before_begin](#before_begin)|Gibt einen Iterator zurück, der die Position vor dem ersten Element in einer Vorwärtsliste adressiert.|
|[begin](#begin)|Gibt einen Iterator zurück, der das erste Element in einer Vorwärtsliste adressiert.|
|[cbefore_begin](#cbefore_begin)|Gibt einen konstanten Iterator zurück, der die Position vor dem ersten Element in einer Vorwärtsliste adressiert.|
|[cbegin](#cbegin)|Gibt einen konstanten Iterator zurück, der das erste Element in einer Vorwärtsliste adressiert.|
|[cend](#cend)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Vorwärtsliste nachfolgt.|
|[clear](#clear)|Löscht alle Elemente einer Vorwärtsliste auf.|
|[emplace_after](#emplace_after)|Die Verschiebung erstellt ein neues Element nach einer angegebenen Position.|
|[emplace_front](#emplace_front)|Fügt ein direkt konstruiertes Element am Anfang der Liste ein.|
|[empty](#empty)|Testet, ob eine Vorwärtsliste leer ist.|
|[end](#end)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Vorwärtsliste nachfolgt.|
|[erase_after](#erase_after)|Entfernt Elemente nach einer angegebenen Position aus der Vorwärtsliste.|
|[Vorderseite](#front)|Gibt einen Verweis auf das erste Element in einer Vorwärtsliste zurück.|
|[get_allocator](#get_allocator)|Gibt eine Kopie des Zuordnungsobjekts zurück, das zum Erstellen der Vorwärtsliste verwendet wird.|
|[insert_after](#insert_after)|Fügt der Vorwärtsliste nach einer angegebenen Position Elemente hinzu.|
|[max_size](#max_size)|Gibt die Maximallänge einer Vorwärtsliste zurück.|
|[merge](#merge)|Entfernt die Elemente aus der Argumentliste, fügt sie in die Zielvorwärtsliste ein und sortiert den neuen, kombinierten Elementsatz in aufsteigender Reihenfolge oder in einer anderen angegebenen Reihenfolge.|
|[pop_front](#pop_front)|Löscht das Element am Anfang einer Vorwärtsliste.|
|[push_front](#push_front)|Fügt am Anfang einer Vorwärtsliste ein Element hinzu.|
|[remove](#remove)|Löscht Elemente in einer Vorwärtsliste, die einem angegebenen Wert entsprechen.|
|[remove_if](#remove_if)|Löscht Elemente aus einer Vorwärtsliste, für die ein angegebenes Prädikat erfüllt ist.|
|[resize](#resize)|Gibt eine neue Größe für eine Vorwärtsliste an.|
|[reverse](#reverse)|Kehrt die Reihenfolge um, in der die Elemente in einer Vorwärtsliste auftreten.|
|[sort](#sort)|Ordnet die Elemente in aufsteigender Reihenfolge oder einer durch ein Prädikat angegebenen Reihenfolge.|
|[splice_after](#splice_after)|Erneuert Links zwischen Knoten.|
|[swap](#swap)|Tauscht die Elemente zweier Vorwärtslisten aus.|
|[unique](#unique)|Entfernt benachbarte Elemente, die einen angegebenen Test bestehen.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Ersetzt die Elemente der Vorwärtsliste durch eine Kopie einer anderen Vorwärtsliste.|

## <a name="requirements"></a>Anforderungen

**Header:** \<forward_list>

**Namespace:** std

## <a name="allocator_type"></a> forward_list::allocator_type

Ein Typ, mit dem die Zuweisungsklasse für ein forward list-Objekt dargestellt wird.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Hinweise

`allocator_type` ist ein Synonym für den Vorlagenparameter „Allocator“.

## <a name="assign"></a> forward_list::assign

Löscht Elemente aus einer Vorwärtsliste und kopiert einen neuen Satz von Elementen an eine Zielvorwärtsliste.

```cpp
void assign(
    size_type Count,
    const Type& Val);

void assign(
    initializer_list<Type> IList);

template <class InputIterator>
void assign(InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`first`|Der Anfang des Ersetzungsbereichs.|
|`last`|Das Ende des Ersetzungsbereichs.|
|`count`|Die Anzahl zuzuweisender Elemente.|
|`val`|Der jedem Element zuzuweisende Wert.|
|`Type`|Der Typ des Werts.|
|`IList`|Das zu kopierende initializer_list-Element.|

### <a name="remarks"></a>Hinweise

Wenn "forward_list" ein Ganzzahltyp ist, verhält sich die erste Memberfunktion genau wie `assign((size_type)First, (Type)Last)`. Andernfalls ersetzt die Memberfunktion die von `*this` gesteuerte Sequenz durch die Sequenz [ `First, Last)`, die sich nicht mit der ursprünglichen gesteuerten Sequenz überschneiden darf.

Die zweite Memberfunktion ersetzt die Sequenz, die von `*this` durch eine Wiederholung von `Count`-Elementen des Werts `Val` gesteuert wird.

Die dritte Memberfunktion kopiert die Elemente von "initializer_list" in "forward_list".

## <a name="before_begin"></a> forward_list::before_begin

Gibt einen Iterator zurück, der die Position vor dem ersten Element in einer Vorwärtsliste adressiert.

```cpp
const_iterator before_begin() const;
iterator before_begin();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Forward-Iterator zurück, der unmittelbar vor das erste Element der Sequenz zeigt (bzw. unmittelbar vor das Ende einer leeren Sequenz)

### <a name="remarks"></a>Hinweise

## <a name="begin"></a> forward_list::begin

Gibt einen Iterator zurück, der das erste Element in einer Vorwärtsliste adressiert.

```cpp
const_iterator begin() const;
iterator begin();
```

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der auf das erste Element der Sequenz zeigt (bzw. unmittelbar hinter das Ende einer leeren Sequenz).

### <a name="remarks"></a>Hinweise

## <a name="cbefore_begin"></a> forward_list::cbefore_begin

Gibt einen konstanten Iterator zurück, der die Position vor dem ersten Element in einer Vorwärtsliste adressiert.

```cpp
const_iterator cbefore_begin() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Forward-Iterator zurück, der unmittelbar vor das erste Element der Sequenz zeigt (bzw. unmittelbar vor das Ende einer leeren Sequenz)

### <a name="remarks"></a>Hinweise

## <a name="cbegin"></a> forward_list::cbegin

Gibt einen `const`-Iterator zurück, mit dem das erste Element im Bereich behandelt wird.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `const`-Forward-Access-Iterator, der auf das erste Element des Bereichs zeigt oder die Position direkt hinter dem Ende eines leeren Bereichs (für einen leeren Bereich gilt `cbegin() == cend()`).

### <a name="remarks"></a>Hinweise

Bei dem Rückgabewert `cbegin` können die Elemente im Bereich nicht geändert werden.

Sie können diese Memberfunktion anstelle der `begin()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. Normalerweise wird sie zusammen mit dem [auto](../cpp/auto-cpp.md)-Typableitungs-Schlüsselwort verwendet, wie im folgenden Beispiel gezeigt. Im folgenden Beispiel ist `Container` ein beliebiger, änderbarer (nicht `const`) Container, der `begin()` und `cbegin()` unterstützt.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();
// i2 is Container<T>::const_iterator
```

## <a name="cend"></a> forward_list::cend

Gibt einen `const`-Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines Bereichs unmittelbar nachfolgt.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Forward-Access-Iterator, der auf eine Position unmittelbar hinter dem Ende des Bereichs verweist.

### <a name="remarks"></a>Hinweise

`cend` wird verwendet, um zu testen, ob ein Iterator das Ende seines Bereichs übergeben hat.

Sie können diese Memberfunktion anstelle der `end()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. Normalerweise wird sie zusammen mit dem [auto](../cpp/auto-cpp.md)-Typableitungs-Schlüsselwort verwendet, wie im folgenden Beispiel gezeigt. Im folgenden Beispiel ist `Container` ein beliebiger änderbarer (Nicht-`const`-)Container, der `end()` und `cend()` unterstützt.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Der von `cend` zurückgegebene Wert darf nicht dereferenziert werden.

## <a name="clear"></a> forward_list::clear

Löscht alle Elemente einer Vorwärtsliste auf.

```cpp
void clear();
```

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ruft `erase_after(before_begin(), end()).` auf.

## <a name="const_iterator"></a> forward_list::const_iterator

Ein Typ, der einen konstanten Iterator für die Vorwärtsliste bereitstellt.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Hinweise

`const_iterator` beschreibt ein Objekt, das als konstanter Forward-Iterator für die gesteuerte Sequenz fungieren kann. Es wird hier als ein Synonym für einen durch Implementierung definierten Typ beschrieben.

## <a name="const_pointer"></a> forward_list::const_pointer

Ein Typ, der einen Zeiger auf ein `const`-Element in einer Vorwärtsliste bereitstellt.

```cpp
typedef typename Allocator::const_pointer
    const_pointer;
```

### <a name="remarks"></a>Hinweise

## <a name="const_reference"></a> forward_list::const_reference

Ein Typ, der einen Konstantenverweis auf einer Vorwärtsliste gespeichertes Element bereitstellt.

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Hinweise

## <a name="difference_type"></a> forward_list::difference_type

Ein Ganzzahltyp mit Vorzeichen, der dazu verwendet werden kann, die Anzahl von Elementen einer Vorwärtsliste in einen Bereich zwischen Elementen darzustellen, auf die von Iteratoren gezeigt wird.

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Hinweise

`difference_type` beschreibt ein Objekt, das die Differenz zwischen den Adressen von zwei beliebigen Elementen in der gesteuerten Sequenz darstellen kann.

## <a name="emplace_after"></a> forward_list::emplace_after

Die Verschiebung erstellt ein neues Element nach einer angegebenen Position.

```cpp
template <class T>
iterator emplace_after(const_iterator Where, Type&& val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`Where`|Die Position in der forward_list-Klasse, an der das neue Element erstellt wird.|
|`val`|Das Konstruktorargument|

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das neu eingefügte Element entwirft

### <a name="remarks"></a>Hinweise

Diese Memberfunktion fügt ein Element mit dem Konstruktorargument `val` direkt hinter dem Element ein, auf das `Where` in der gesteuerten Sequenz zeigt. Das Verhalten entspricht andernfalls [forward_list::insert_after](#insert_after).

## <a name="emplace_front"></a> forward_list::emplace_front

Fügt ein direkt konstruiertes Element am Anfang der Liste ein.

```cpp
template <class Type>
void emplace_front(Type&& val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`val`|Das am Anfang der Vorwärtsliste hinzugefügte Element|

### <a name="remarks"></a>Hinweise

Diese Memberfunktion fügt ein Element mit dem Konstruktorargument `_ val` am Ende der gesteuerten Sequenz ein.

Wenn eine Ausnahme ausgelöst wird, bleibt der Container unverändert, und die Ausnahme wird erneut ausgelöst.

## <a name="empty"></a> forward_list::empty

Testet, ob eine Vorwärtsliste leer ist.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

`true`, wenn die forward_list-Klasse leer ist, andernfalls `false`.

## <a name="end"></a> forward_list::end

Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Vorwärtsliste nachfolgt.

```cpp
const_iterator end() const;
iterator end();
```

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der auf eine Position unmittelbar hinter dem Ende der Sequenz verweist.

## <a name="erase_after"></a> forward_list::erase_after

Entfernt Elemente nach einer angegebenen Position aus der Vorwärtsliste.

```cpp
iterator erase_after(const_iterator Where);
iterator erase_after(const_iterator first, const_iterator last);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`Where`|Die Position in der forward_list-Klasse, an der das Element gelöscht wird|
|`first`|Der Anfang des zu löschenden Bereichs|
|`last`|Das Ende des zu löschenden Bereichs|

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das erste über die entfernten Elemente hinaus verbliebene Element festlegt, oder [forward_list::end](#end), wenn kein solches Element vorhanden ist.

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion entfernt das Element der gesteuerten Sequenz direkt hinter `Where`.

Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich `( first,  last)` (keiner der beiden Endpunkte ist beinhaltet).

Das Löschen von `N`-Elementen verursacht `N`-Destruktoraufrufe. Eine [Neuzuordnung](../standard-library/forward-list-class.md) findet statt, damit Iteratoren und Verweise für die gelöschten Elemente ungültig werden.

Von der Memberfunktionen wird nie eine Ausnahme ausgelöst.

## <a name="forward_list"></a> forward_list::forward_list

Konstruiert ein Objekt vom Typ `forward_list`.

```cpp
forward_list();
explicit forward_list(const Allocator& Al);
explicit forward_list(size_type Count);
forward_list(size_type Count, const Type& Val);
forward_list(size_type Count, const Type& Val, const Allocator& Al);
forward_list(const forward_list& Right);
forward_list(const forward_list& Right, const Allocator& Al);
forward_list(forward_list&& Right);
forward_list(forward_list&& Right, const Allocator& Al);
forward_list(initializer_list<Type> IList, const Alloc& Al);
template <class InputIterator>
forward_list(InputIterator First, InputIterator Last);
template <class InputIterator>
forward_list(InputIterator First, InputIterator Last, const Allocator& Al);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`Al`|Die mit diesem Objekt zu verwendende Zuweisungsklasse.|
|`Count`|Die Anzahl von Elementen in der erstellten Liste.|
|`Val`|Der Wert der Elemente in der erstellten Liste.|
|`Right`|Die Liste, deren Kopie die erstellte Liste ist.|
|`First`|Die Position des ersten Elements in dem zu kopierenden Elementbereich.|
|`Last`|Die Position des ersten Elements nach dem zu kopierenden Elementbereich.|
|`IList`|Das zu kopierende initializer_list-Element.|

### <a name="remarks"></a>Hinweise

Alle Konstruktoren speichern [allocator](../standard-library/allocator-class.md)-Element und initialisieren die gesteuerte Sequenz. Das Zuweisungsobjekt ist das Argument `Al`, sofern es vorhanden ist. Beim Kopierkonstruktor ist es ` right.get_allocator()`. Andernfalls ist der Wert `Allocator()`.

Die ersten beiden Konstruktoren geben eine leere gesteuerte Sequenz an.

Der dritte Konstruktor gibt eine Wiederholung der `Count`-Elemente des Werts `Type()` an.

Die vierten und fünften Konstruktoren geben eine Wiederholung von `Count`-Elementen des Werts `Val` an.

Mit dem sechsten Konstruktor wird eine Kopie der Sequenz angegeben, die von `Right` gesteuert wird. Wenn `InputIterator` ein Ganzzahltyp ist, geben die folgenden zwei Konstruktoren eine Wiederholung von `(size_type)First`-Elementen des Werts `(Type)Last` an. Andernfalls geben die folgenden zwei Konstruktoren die Sequenz `[First, Last)` an.

Der neunte und zehnte Konstruktor sind mit dem sechsten identisch, haben aber einen [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md)-Verweis.

Der letzte Konstruktor gibt die ursprüngliche gesteuerte Sequenz mit einem Objekt der Klasse `initializer_list<Type>` an.

## <a name="front"></a> forward_list::front

Gibt einen Verweis auf das erste Element in einer Vorwärtsliste zurück.

```cpp
reference front();
const_reference front() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das erste Element der gesteuerten Sequenz, das nicht leer sein darf

## <a name="get_allocator"></a> forward_list::get_allocator

Gibt eine Kopie des Zuordnungsobjekts zurück, das zum Erstellen der Vorwärtsliste verwendet wird.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Rückgabewert

Das gespeicherte [allocator](../standard-library/allocator-class.md)-Objekt

## <a name="insert_after"></a> forward_list::insert_after

Fügt der Vorwärtsliste nach einer angegebenen Position Elemente hinzu.

```cpp
iterator insert_after(const_iterator Where, const Type& Val);
void insert_after(const_iterator Where, size_type Count, const Type& Val);
void insert_after(const iterator Where, initializer_list<Type> IList);
iterator insert_after(const_iterator Where, Type&& Val);
template <class InputIterator>
void insert_after(const_iterator Where, InputIterator First, InputIterator Last);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`Where`|Die Position in der Zielvorwärtsliste, an der das erste Element eingefügt wird.|
|`Count`|Die Anzahl einzufügender Elemente.|
|`First`|Der Anfang des Einfügebereichs.|
|`Last`|Das Ende des Einfügebereichs.|
|`Val`|Das Element hinzugefügt Vorwärtsliste.|
|`IList`|Das einzufügende initializer_list-Element.|

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das neu eingefügte Element festlegt (nur erste und letzte Memberfunktionen).

### <a name="remarks"></a>Hinweise

Jede der Memberfunktionseinfügungen – direkt nach dem Element, auf das von `Where` in der gesteuerten Sequenz gezeigt wird – eine Sequenz, die von den verbleibenden Operanden angegeben wird.

Die erste Memberfunktion fügt ein Element ein, das den Wert `Val` aufweist und ein Iterator zurückgibt, der das neu eingefügte Element festlegt.

Die zweite Memberfunktion fügt eine Wiederholung der `Count`-Elemente des Werts `Val` ein.

Wenn `InputIterator` ein Ganzzahltyp ist, verhält sich die dritte Memberfunktion genau wie `insert(it, (size_type)First, (Type)Last)`. Andernfalls wird die Sequenz `[First, Last)` eingefügt, die die ursprüngliche gesteuerte Sequenz nicht überschneiden darf.

Die vierte Memberfunktion fügt die Sequenz ein, die vom Objekt der Klasse `initializer_list<Type>` angegeben wird.

Die letzte Memberfunktion ist mit der ersten identisch, hat aber einen [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md)-Verweis.

Das Einfügen von `N`-Elementen verursacht `N`-Konstruktoraufrufe. Eine [Neuzuordnung](../standard-library/forward-list-class.md) erfolgt, es werden aber keine Iteratoren oder Verweise ungültig.

Wird während der Einfügung bei einem oder mehreren Elementen eine Ausnahme ausgelöst wird, wird der Container unverändert belassen, und die Ausnahme wird erneut ausgelöst.

## <a name="iterator"></a> forward_list::iterator

Ein Typ, der einen Iterator für die Vorwärtsliste bereitstellt.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Hinweise

`iterator` beschreibt ein Objekt, das als Forward-Iterator für die gesteuerte Sequenz fungieren kann. Es wird hier als ein Synonym für einen durch Implementierung definierten Typ beschrieben.

## <a name="max_size"></a> forward_list::max_size

Gibt die Maximallänge einer Vorwärtsliste zurück.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge der längsten Sequenz, die das Objekt steuern kann

### <a name="remarks"></a>Hinweise

## <a name="merge"></a> forward_list::merge

Kombiniert zwei sortierte Sequenzen zu einer einzigen sortierte Sequenz zeitlich linear. Entfernt die Elemente aus der Argumentliste und fügt sie in `forward_list` ein. Die beiden Listen sollten von dem gleichen Funktionenvergleichsobjekt sortiert werden, bevor `merge` aufgerufen wird. Die kombinierte Liste wird nach dem Funktionenvergleichsobjekt sortiert.

```cpp
void merge(forward_list& right);
template <class Predicate>
void merge(forward_list& right, Predicate comp);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`right`|Die forward_list-Klasse, aus der zusammengeführt wird|
|`comp`|Der Funktionenvergleichsobjekt, das zum Sortieren der Elemente verwendet wird|

### <a name="remarks"></a>Hinweise

`forward_list::merge` Entfernt Elemente aus der `forward_list` `right`, und fügt sie in dieser `forward_list`. Beide Sequenzen müssen nach dem gleichen Prädikat sortiert werden, wie unten beschrieben. Die kombinierte Ereignissequenz wird ebenfalls nach diesem Funktionenvergleichssobjekt sortiert.

Für die Iteratoren `Pi` und `Pj`, die Elemente an den Positionen `i` und `j` festlegen, erzwingt die erste Memberfunktion die Reihenfolge `!(*Pj < *Pi)`, immer wenn `i < j` vorliegt. (Die Elemente werden in aufsteigender Reihenfolge (`ascending`) sortiert.) Die zweite Memberfunktion erzwingt die Reihenfolge `! comp(*Pj, *Pi)`, immer wenn `i < j` vorliegt.

In der ursprünglichen gesteuerten Sequenz werden in der resultierenden gesteuerten Sequenz keine Elementpaare rückgängig gemacht. Wenn ein Elementpaar in der resultierenden gesteuerten Sequenz identisch ist ( `!(*Pi < *Pj) && !(*Pj < *Pi)`), erscheint ein Element aus der ursprünglichen gesteuerten Sequenz vor einem Element aus der von `right` gesteuerten Sequenz.

Eine Ausnahme tritt nur dann auf, wenn `comp` eine Ausnahme auslöst. In diesem Fall bleibt die gesteuerten Sequenz in einer nicht vorgegebenen Reihenfolge, und die Ausnahme wird erneut ausgelöst.

## <a name="op_eq"></a> forward_list::operator=

Ersetzt die Elemente der Vorwärtsliste durch eine Kopie einer anderen Vorwärtsliste.

```cpp
forward_list& operator=(const forward_list& right);
forward_list& operator=(initializer_list<Type> IList);
forward_list& operator=(forward_list&& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`right`|forward_list-Klasse, die in die forward_list-Klasse kopiert wird|
|`IList`|Ein Initialisierer mit geschweiften Klammern, der sich wie eine Sequenz von Elementen des Typs `Type` verhält.|

### <a name="remarks"></a>Hinweise

Der Memberoperator ersetzt die gesteuerte Sequenz durch eine Kopie der von `right` gesteuerten Sequenz.

Der zweite Memberoperator ersetzt die gesteuerte Sequenz durch ein Objekt der Klasse `initializer_list<Type>`.

Die letzte Memberfunktion ist identisch mit der ersten, hat aber einen [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md)-Verweis.

## <a name="pointer"></a> forward_list::pointer

Ein Typ, der einen Zeiger auf ein Element in der Vorwärtsliste bereitstellt.

```cpp
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Hinweise

## <a name="pop_front"></a> forward_list::pop_front

Löscht das Element am Anfang einer Vorwärtsliste.

```cpp
void pop_front();
```

### <a name="remarks"></a>Hinweise

Das erste Element der forward_list-Klasse darf nicht leer sein.

Die Memberfunktionen löst nie eine Ausnahme aus.

## <a name="push_front"></a> forward_list::push_front

Fügt am Anfang einer Vorwärtsliste ein Element hinzu.

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`val`|Das am Anfang der Vorwärtsliste hinzugefügte Element|

### <a name="remarks"></a>Hinweise

Wenn eine Ausnahme ausgelöst wird, bleibt der Container unverändert, und die Ausnahme wird erneut ausgelöst.

## <a name="reference"></a> forward_list::reference

Ein Typ, der einen Verweis auf ein in der Vorwärtsliste gespeichertes Element bereitstellt.

```cpp
typedef typename Allocator::reference reference;
```

### <a name="remarks"></a>Hinweise

## <a name="remove"></a> forward_list::remove

Löscht Elemente in einer Vorwärtsliste, die einem angegebenen Wert entsprechen.

```cpp
void remove(const Type& val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`val`|Der Wert, der, sofern er von einem Element gehalten wird, das Entfernen dieses Elements aus der Liste verursacht.|

### <a name="remarks"></a>Hinweise

Die Memberfunktion entfernt alle Elemente aus der kontrollierten Sequenz, die vom Iterator `P` bestimmt wurden, für den `*P ==  val`

Die Memberfunktionen löst nie eine Ausnahme aus.

## <a name="remove_if"></a> forward_list::remove_if

Löscht Elemente aus einer Vorwärtsliste, für die ein angegebenes Prädikat erfüllt ist.

```cpp
template <class Predicate>
void remove_if(Predicate pred);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`pred`|Das unäre Prädikat, das bei Erfüllung durch ein Element das Löschen dieses Elements in der Liste zur Folge hat.|

### <a name="remarks"></a>Hinweise

Die Memberfunktion entfernt alle Elemente aus der kontrollierten Sequenz, die vom Iterator `P` bestimmt wurden, für den ` pred(*P)` TRUE ist.

Eine Ausnahme tritt nur dann auf, wenn `pred` eine Ausnahme auslöst. In diesem Fall bleibt die gesteuerten Sequenz in einem nicht vorgegebenen Zustand, und die Ausnahme wird erneut ausgelöst.

## <a name="resize"></a> forward_list::resize

Gibt eine neue Größe für eine Vorwärtsliste an.

```cpp
void resize(size_type _Newsize);
void resize(size_type _Newsize, const Type& val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`_Newsize`|Die Anzahl der Elemente im Vorwärtsliste, deren Größe angepasst wurde|
|`val`|Der für die Auffüllung zu nutzende Wert|

### <a name="remarks"></a>Hinweise

Die Memberfunktionen stellen beide sicher, dass die Anzahl der Elemente in der Liste fortan `_Newsize` beträgt. Wenn die gesteuerte Sequenz verlängert werden muss, fügt die erste Memberfunktion Elemente mit dem Wert `Type()` an, während die zweite Memberfunktion Elemente mit dem Wert `val` anfügt. Damit die gesteuerte Sequenz kürzer wird, rufen beide Memberfunktionen `erase_after(begin() + _Newsize - 1, end())` auf.

## <a name="reverse"></a> forward_list::reverse

Kehrt die Reihenfolge um, in der die Elemente in einer Vorwärtsliste auftreten.

```cpp
void reverse();
```

### <a name="remarks"></a>Hinweise

## <a name="size_type"></a> forward_list::size_type

Ein Typ, der den Abstand ohne Vorzeichen zwischen zwei Elementen darstellt.

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="remarks"></a>Hinweise

Der unsignierte Ganzzahltyp beschreibt ein Objekt, das die Länge jeder kontrollierten Sequenz darstellen kann.

## <a name="sort"></a> forward_list::sort

Ordnet die Elemente in aufsteigender Reihenfolge oder einer durch ein Prädikat angegebenen Reihenfolge.

```cpp
void sort();
template <class Predicate>
void sort(Predicate pred);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`pred`|Das Sortierungsprädikat|

### <a name="remarks"></a>Hinweise

Beide Memberfunktionen sortieren die Elemente in der gesteuerten Sequenz mithilfe eines Prädikats, wie unten beschrieben.

Für die Iteratoren `Pi` und `Pj`, die Elemente an den Positionen `i` und `j` festlegen, erzwingt die erste Memberfunktion die Reihenfolge `!(*Pj < *Pi)`, immer wenn `i < j` vorliegt. (Die Elemente werden in aufsteigender Reihenfolge (`ascending`) sortiert.) Die Membervorlagenfunktion erzwingt die Reihenfolge `! pred(*Pj, *Pi)`, immer wenn `i < j` vorliegt. In der ursprünglichen gesteuerten Sequenz werden in der resultierenden gesteuerten Sequenz keine sortierten Elementpaare rückgängig gemacht. (Die Sortierung ist stabil.)

Eine Ausnahme tritt nur dann auf, wenn `pred` eine Ausnahme auslöst. In diesem Fall bleibt die gesteuerten Sequenz in einer nicht vorgegebenen Reihenfolge, und die Ausnahme wird erneut ausgelöst.

## <a name="splice_after"></a> forward_list::splice_after

Entfernt Elemente aus einer Quell-forward_list und fügt sie in eine Ziel-forward_list ein.

```cpp
// insert the entire source forward_list
void splice_after(const_iterator Where, forward_list& Source);
void splice_after(const_iterator Where, forward_list&& Source);

// insert one element of the source forward_list
void splice_after(const_iterator Where, forward_list& Source, const_iterator Iter);
void splice_after(const_iterator Where, forward_list&& Source, const_iterator Iter);

// insert a range of elements from the source forward_list
void splice_after(
    const_iterator Where,
    forward_list& Source,
    const_iterator First,
    const_iterator Last);

void splice_after(
    const_iterator Where,
    forward_list&& Source,
    const_iterator First,
    const_iterator Last);
```

### <a name="parameters"></a>Parameter

`Where` Die Position in der Ziel-Forward_list, nach dem Einfügen.

`Source` Der Quell-Forward_list, die in der Ziel-Forward_list eingefügt werden soll.

`Iter` Das Element, aus der Quell-Forward_list eingefügt werden soll.

`First` Das erste Element im Bereich, das aus der Quell-Forward_list eingefügt werden soll.

`Last` Die erste Position hinter dem Bereich, aus der Quell-Forward_list eingefügt werden soll.

### <a name="remarks"></a>Hinweise

Das erste Paar von Memberfunktionen fügt die durch `Source` gesteuerte Sequenz direkt hinter dem Element in der gesteuerten Sequenz ein, auf die von `Where` gezeigt wird. Es entfernt auch alle Elemente aus `Source`. ( `&Source` darf nicht gleich `this` sein.)

Das zweite Paar von Memberfunktionen entfernt das Element direkt hinter `Iter` in der durch `Source` gesteuerten Sequenz und fügt es hinter dem Element in der gesteuerten Sequenz ein, auf die von `Where` gezeigt wird. (Wenn `Where == Iter || Where == ++Iter` ist, findet keine Änderung statt.)

Das dritte Paar von Memberfunktionen (Bereich-Splice) fügt den von `(First, Last)` festgelegten Unterbereich aus der durch `Source` gesteuerten Sequenz direkt hinter dem Element in der gesteuerten Sequenz ein, auf die von `Where` gezeigt wird. Es entfernt auch den Original-Unterbereich aus der durch `Source` gespeicherten Sequenz. (Wenn `&Source == this` ist, darf der Bereich `(First, Last)` nicht das Element enthalten, auf das von `Where` gezeigt wird.)

Wenn der Bereichs-Splice `N`-Elemente und `&Source != this` einfügt, wird ein Objekt der [iterator](#iterator)-Klasse um das `N`-vergrößert erhöht.

Keine Iteratoren, Zeiger oder Verweise, die zusammengeführte Elemente bezeichnen, werden ungültig.

### <a name="example"></a>Beispiel

```cpp
// forward_list_splice_after.cpp
// compile with: /EHsc /W4
#include <forward_list>
#include <iostream>

using namespace std;

template <typename S> void print(const S& s) {
    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{
    forward_list<int> c1{ 10, 11 };
    forward_list<int> c2{ 20, 21, 22 };
    forward_list<int> c3{ 30, 31 };
    forward_list<int> c4{ 40, 41, 42, 43 };

    forward_list<int>::iterator where_iter;
    forward_list<int>::iterator first_iter;
    forward_list<int>::iterator last_iter;

    cout << "Beginning state of lists:" << endl;
    cout << "c1 = ";
    print(c1);
    cout << "c2 = ";
    print(c2);
    cout << "c3 = ";
    print(c3);
    cout << "c4 = ";
    print(c4);

    where_iter = c2.begin();
    ++where_iter; // start at second element
    c2.splice_after(where_iter, c1);
    cout << "After splicing c1 into c2:" << endl;
    cout << "c1 = ";
    print(c1);
    cout << "c2 = ";
    print(c2);

    first_iter = c3.begin();
    c2.splice_after(where_iter, c3, first_iter);
    cout << "After splicing the first element of c3 into c2:" << endl;
    cout << "c3 = ";
    print(c3);
    cout << "c2 = ";
    print(c2);

    first_iter = c4.begin();
    last_iter = c4.end();
    // set up to get the middle elements
    ++first_iter;
    c2.splice_after(where_iter, c4, first_iter, last_iter);
    cout << "After splicing a range of c4 into c2:" << endl;
    cout << "c4 = ";
    print(c4);
    cout << "c2 = ";
    print(c2);
}

```

```Output
Beginning state of lists:c1 = (10) (11)c2 = (20) (21) (22)c3 = (30) (31)c4 = (40) (41) (42) (43)After splicing c1 into c2:c1 =c2 = (20) (21) (10) (11) (22)After splicing the first element of c3 into c2:c3 = (30)c2 = (20) (21) (31) (10) (11) (22)After splicing a range of c4 into c2:c4 = (40) (41)c2 = (20) (21) (42) (43) (31) (10) (11) (22)
```

## <a name="swap"></a> forward_list::swap

Tauscht die Elemente zweier Vorwärtslisten aus.

```cpp
void swap(forward_list& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`right`|Die forward_list-Klasse, die auszutauschende Elemente bereitstellt|

### <a name="remarks"></a>Hinweise

Die Memberfunktion tauscht die kontrollierten Sequenzen zwischen `*this` und `right` aus. Wenn `get_allocator() ==  right.get_allocator()`, führt sie dies in einer konstanten Zeit aus, löst keine Ausnahmen aus und macht keine Verweise, Zeiger oder Iteratoren ungültig, die Elemente in den beiden gesteuerten Sequenzen bestimmen. Andernfalls führt Sie proportional zur Anzahl der Elemente in den beiden kontrollierten Sequenzen eine Reihe von Elementzuweisungen und Konstruktoraufrufe aus.

## <a name="unique"></a> forward_list::unique

Entfernt alle bis auf das erste Element aus jeder aufeinander folgenden Gruppe gleicher Elemente

```cpp
void unique();
template <class BinaryPredicate>
void unique(BinaryPredicate comp);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`comp`|Das binäre Prädikat, das zum Vergleichen von aufeinander folgenden Elementen verwendet wird.|

### <a name="remarks"></a>Hinweise

Behält das erste von jedem eindeutigen Element und entfernt die übrigen Die Elemente müssen sortiert werden, sodass Elemente mit gleichem Wert in der Liste nebeneinander angezeigt werden.

Die erste Memberfunktion entfernt jedes Element aus der gesteuerten Sequenz, das identisch mit dem vorherigen Element ist. Für die Iteratoren `Pi` und `Pj`, die Elemente an den Positionen `i` und `j` bestimmen, entfernt die zweite Memberfunktion jedes Element, für das `i + 1 == j &&  comp(*Pi, *Pj)` gilt.

Für eine gesteuerte Sequenz der Länge `N` (> 0) wird das Prädikat ` comp(*Pi, *Pj)` `N - 1`-Mal ausgewertet.

Eine Ausnahme tritt nur dann auf, wenn `comp` eine Ausnahme auslöst. In diesem Fall bleibt die gesteuerten Sequenz in einem nicht vorgegebenen Zustand, und die Ausnahme wird erneut ausgelöst.

## <a name="value_type"></a> forward_list::value_type

Ein Typ, der den Typ des in einer Vorwärtsliste gespeicherten Elements darstellt.

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Hinweise

Der Typ stellt ein Synonym für den Vorlagenparameter _ `Ty` dar.

## <a name="see-also"></a>Siehe auch

[<forward_list>](../standard-library/forward-list.md)<br/>
