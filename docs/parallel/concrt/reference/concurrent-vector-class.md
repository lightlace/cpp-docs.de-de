---
title: Concurrent_vector-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::assign
- CONCURRENT_VECTOR/concurrency::concurrent_vector::at
- CONCURRENT_VECTOR/concurrency::concurrent_vector::back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::begin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::capacity
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::clear
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::empty
- CONCURRENT_VECTOR/concurrency::concurrent_vector::end
- CONCURRENT_VECTOR/concurrency::concurrent_vector::front
- CONCURRENT_VECTOR/concurrency::concurrent_vector::get_allocator
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_by
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_to_at_least
- CONCURRENT_VECTOR/concurrency::concurrent_vector::max_size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::push_back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::reserve
- CONCURRENT_VECTOR/concurrency::concurrent_vector::resize
- CONCURRENT_VECTOR/concurrency::concurrent_vector::shrink_to_fit
- CONCURRENT_VECTOR/concurrency::concurrent_vector::size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::swap
dev_langs:
- C++
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68ea93c137962e48f8a627e9a9409e4e7fceef65
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163373"
---
# <a name="concurrentvector-class"></a>concurrent_vector-Klasse

Die `concurrent_vector`-Klasse ist eine Sequenzcontainerklasse, die zufälligen Zugriff auf jedes Element zulässt. Sie aktiviert parallelitätssichere Operationen für Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchlauf.

## <a name="syntax"></a>Syntax

```
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
private details::_Concurrent_vector_base_v4;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente im Vektor gespeichert werden.

*_Ax*<br/>
Der Typ, der das gespeicherte Zuweisungsobjekt darstellt, das Details zur Speicherbelegung und Aufhebung der Speicherbelegung für den gleichzeitigen Vektor kapselt. Dieses Argument ist optional, und der Standardwert ist `allocator<T>`.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`allocator_type`|Ein Typ, der die zuweisungsklasse für den gleichzeitigen Vektor darstellt.|
|`const_iterator`|Ein Typ, der einem Iterator mit zufälligem Zugriff können bietet lesen eine `const` Element in einem gleichzeitigen Vektor.|
|`const_pointer`|Ein Typ, einen Zeiger auf eine `const` Element in einem gleichzeitigen Vektor.|
|`const_reference`|Ein Typ, einen Verweis auf eine `const` gespeichertes Element einen gleichzeitigen Vektor zum Lesen und ausführen `const` Vorgänge.|
|`const_reverse_iterator`|Eine Typ, der einem Iterator mit zufälligem Zugriff können bietet Lesen alle `const` Element in der gleichzeitigen Vektor.|
|`difference_type`|Ein Typ, die mit Abstand zwischen zwei Elementen in einem gleichzeitigen Vektor bereitstellt.|
|`iterator`|Ein Typ, die einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes Element in einen gleichzeitigen Vektor gelesen werden kann. Änderung eines Elements mithilfe des Iterators ist nicht nebenläufigkeitssicher.|
|`pointer`|Ein Typ, die einen Zeiger auf ein Element in einem gleichzeitigen Vektor bereitstellt.|
|`reference`|Ein Typ, die einen Verweis auf ein in einem gleichzeitigen Vektor gespeichertes Element bereitstellt.|
|`reverse_iterator`|Ein Typ, die einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes Element in einem umgekehrten Vektor auf der gleichzeitigen lesen kann. Änderung eines Elements mithilfe des Iterators ist nicht nebenläufigkeitssicher.|
|`size_type`|Ein Typ, der die Anzahl der Elemente in einem gleichzeitigen Vektor zählt.|
|`value_type`|Ein Typ, der in einen gleichzeitigen Vektor gespeicherten Datentyp darstellt.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[concurrent_vector](#ctor)|Überladen. Erstellt einen gleichzeitigen Vektor.|
|[~ Concurrent_vector-Destruktor](#dtor)|Löscht alle Elemente aus, und zerstört diesen gleichzeitigen Vektor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[assign](#assign)|Überladen. Löscht den gleichzeitigen Vektor Elemente und weist sie entweder `_N` Kopien `_Item`, oder Werte, angegeben durch den Iteratorbereich [ `_Begin`, `_End`). Diese Methode ist nicht nebenläufigkeitssicher.|
|[at](#at)|Überladen. Bietet Zugriff auf das Element am angegebenen Index in den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch während der den Vektor, wächst, solange Sie, die den Wert sichergestellt haben `_Index` ist kleiner als die Anzahl der gleichzeitigen Vektor.|
|[Rückseite](#back)|Überladen. Gibt einen Verweis oder einen `const` -Verweis auf das letzte Element in der gleichzeitigen Vektor. Wenn die gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.|
|[begin](#begin)|Überladen. Gibt einen Iterator des Typs `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.|
|[capacity](#capacity)|Gibt die maximale Größe, die auf die der gleichzeitige Vektor anwachsen kann, ohne mehr Arbeitsspeicher zu belegen. Diese Methode ist nebenläufigkeitssicher.|
|[cbegin](#cbegin)|Gibt einen Iterator des Typs `const_iterator` an den Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.|
|[cend](#cend)|Gibt einen Iterator des Typs `const_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|
|[clear](#clear)|Löscht alle Elemente in den gleichzeitigen Vektor. Diese Methode ist nicht nebenläufigkeitssicher.|
|[crbegin](#crbegin)|Gibt einen Iterator des Typs `const_reverse_iterator` an den Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.|
|[crend](#crend)|Gibt einen Iterator des Typs `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|
|[empty](#empty)|Testet, ob es sich bei der gleichzeitige Vektor zu diesem Zeitpunkt leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.|
|[end](#end)|Überladen. Gibt einen Iterator des Typs `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|
|[Vorderseite](#front)|Überladen. Gibt einen Verweis oder einen `const` Verweis auf das erste Element in den gleichzeitigen Vektor. Wenn die gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.|
|[get_allocator](#get_allocator)|Gibt eine Kopie der Zuweisung verwendet, um den gleichzeitigen Vektor zu erstellen. Diese Methode ist nebenläufigkeitssicher.|
|[grow_by](#grow_by)|Überladen. Vergrößert diese gleichzeitigen Vektor von `_Delta` Elemente. Diese Methode ist nebenläufigkeitssicher.|
|[grow_to_at_least](#grow_to_at_least)|Diese gleichzeitigen Vektor lange zunehmen, bis mindestens `_N` Elemente. Diese Methode ist nebenläufigkeitssicher.|
|[max_size](#max_size)|Gibt die maximale Anzahl von Elementen, die der gleichzeitige Vektor enthalten kann. Diese Methode ist nebenläufigkeitssicher.|
|[push_back](#push_back)|Überladen. Fügt das angegebene Element am Ende den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|
|[rbegin](#rbegin)|Überladen. Gibt einen Iterator des Typs `reverse_iterator` oder `const_reverse_iterator` an den Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.|
|[rend](#rend)|Überladen. Gibt einen Iterator des Typs `reverse_iterator` oder `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|
|[reserve](#reserve)|Reserviert genügend Speicherplatz für den gleichzeitigen Vektor auf Größe anwachsen `_N` ohne später mehr Speicher reservieren. Diese Methode ist nicht nebenläufigkeitssicher.|
|[resize](#resize)|Überladen. Ändert die Größe der gleichzeitigen Vektor auf die angeforderte Größe, löschen oder Hinzufügen von Elementen nach Bedarf. Diese Methode ist nicht nebenläufigkeitssicher.|
|[shrink_to_fit](#shrink_to_fit)|Komprimiert die interne Darstellung des gleichzeitigen Vektor zum Reduzieren der Fragmentierung und speicherauslastung zu optimieren. Diese Methode ist nicht nebenläufigkeitssicher.|
|[size](#size)|Gibt die Anzahl der Elemente in den gleichzeitigen Vektor zurück. Diese Methode ist nebenläufigkeitssicher.|
|[swap](#swap)|Vertauscht den Inhalt von zwei gleichzeitige Vektoren. Diese Methode ist nicht nebenläufigkeitssicher.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator[]](#operator_at)|Überladen. Bietet Zugriff auf das Element am angegebenen Index in den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch während der den Vektor, wächst, solange Sie haben sichergestellt, das den Wert `_Index` ist kleiner als die Anzahl der gleichzeitigen Vektor.|
|[operator=](#operator_eq)|Überladen. Weist den Inhalt eines anderen `concurrent_vector`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.|

## <a name="remarks"></a>Hinweise

Ausführliche Informationen zu den `concurrent_vector` Klasse, finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`_Concurrent_vector_base_v4`

`_Allocator_base`

`concurrent_vector`

## <a name="requirements"></a>Anforderungen

**Header:** concurrent_vector.h

**Namespace:** Parallelität

##  <a name="assign"></a> Weisen Sie

Löscht den gleichzeitigen Vektor Elemente und weist sie entweder `_N` Kopien `_Item`, oder Werte, angegeben durch den Iteratorbereich [ `_Begin`, `_End`). Diese Methode ist nicht nebenläufigkeitssicher.

```
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```

### <a name="parameters"></a>Parameter

*_InputIterator*<br/>
Der Typ des dem angegebenen Iterator.

*_N*<br/>
Die Anzahl der Elemente, die in den gleichzeitigen Vektor zu kopieren.

*_Item*<br/>
Verweis auf einen Wert verwendet, um den gleichzeitigen Vektor zu füllen.

*_Begin*<br/>
Ein Iterator für das erste Element des Quellbereichs.

*_Beenden*<br/>
Ein Iterator für die erste Position direkt hinter dem letzten Element des Quellbereichs.

### <a name="remarks"></a>Hinweise

`assign` ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen.

##  <a name="at"></a> an

Bietet Zugriff auf das Element am angegebenen Index in den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch während der den Vektor, wächst, solange Sie, die den Wert sichergestellt haben `_Index` ist kleiner als die Anzahl der gleichzeitigen Vektor.

```
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```

### <a name="parameters"></a>Parameter

*_Index*<br/>
Der Index des Elements, das abgerufen werden.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Element am angegebenen Index.

### <a name="remarks"></a>Hinweise

Die Version der Funktion `at` zurückgibt nicht `const` Verweis kann nicht verwendet werden, um von verschiedenen Threads gleichzeitig auf das Element schreiben. Ein anderes Synchronisierungsobjekt sollte zum Synchronisieren des gleichzeitigen Lese- und Schreibvorgänge mit dem gleichen Datenelement verwendet werden.

Löst die Methode `out_of_range` Wenn `_Index` ist größer als oder gleich der Anzahl der gleichzeitigen Vektor und `range_error` Wenn der Index für einen fehlerhaften Teil der Vektor ist. Weitere Informationen darüber, wie die ein Vektors beschädigt werden kann, finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).

##  <a name="back"></a> Zurück

Gibt einen Verweis oder einen `const` -Verweis auf das letzte Element in der gleichzeitigen Vektor. Wenn die gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.

```
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis oder ein `const` -Verweis auf das letzte Element in der gleichzeitigen Vektor.

##  <a name="begin"></a> beginnen

Gibt einen Iterator des Typs `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.

```
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Vektors.

##  <a name="capacity"></a> Kapazität

Gibt die maximale Größe, die auf die der gleichzeitige Vektor anwachsen kann, ohne mehr Arbeitsspeicher zu belegen. Diese Methode ist nebenläufigkeitssicher.

```
size_type capacity() const;
```

### <a name="return-value"></a>Rückgabewert

Die maximale Größe, die auf die der gleichzeitige Vektor anwachsen kann, ohne mehr Arbeitsspeicher zu belegen.

### <a name="remarks"></a>Hinweise

Im Gegensatz zu einer C++-Standardbibliothek `vector`, `concurrent_vector` Objekt werden die vorhandenen Elemente nicht verschoben, wenn es mehr Arbeitsspeicher belegt.

##  <a name="cbegin"></a> cbegin

Gibt einen Iterator des Typs `const_iterator` an den Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.

```
const_iterator cbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `const_iterator` an den Anfang der gleichzeitigen Vektors.

##  <a name="cend"></a> cend

Gibt einen Iterator des Typs `const_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.

```
const_iterator cend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `const_iterator` bis zum Ende der gleichzeitigen Vektor.

##  <a name="clear"></a> Deaktivieren

Löscht alle Elemente in den gleichzeitigen Vektor. Diese Methode ist nicht nebenläufigkeitssicher.

```
void clear();
```

### <a name="remarks"></a>Hinweise

`clear` ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen. `clear` Gibt die internen Arrays nicht frei. Um die internen Arrays freizugeben, rufen Sie die Funktion `shrink_to_fit` nach `clear`.

##  <a name="ctor"></a> concurrent_vector

Erstellt einen gleichzeitigen Vektor.

```
explicit concurrent_vector(
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector(
    const concurrent_vector<T,
    M>& _Vector,
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    concurrent_vector&& _Vector);

explicit concurrent_vector(
    size_type _N);

concurrent_vector(
    size_type _N,
    const_reference _Item,
    const allocator_type& _Al = allocator_type());

template<class _InputIterator>
concurrent_vector(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());
```

### <a name="parameters"></a>Parameter

*M*<br/>
Der allocator-Typ des Quellvektors.

*_InputIterator*<br/>
Der Typ des Eingabeiterators.

*_Al*<br/>
Die mit diesem Objekt zu verwendende Zuweisungsklasse.

*_Vector*<br/>
Das `concurrent_vector`-Quellobjekt, aus dem Elemente kopiert oder verschoben werden sollen.

*_N*<br/>
Die Anfangskapazität des `concurrent_vector`-Objekts.

*_Item*<br/>
Der Wert der Elemente im erstellten Objekt.

*_Begin*<br/>
Die Position des ersten Elements in dem zu kopierenden Elementbereich.

*_Beenden*<br/>
Die Position des ersten Elements nach dem zu kopierenden Elementbereich.

### <a name="remarks"></a>Hinweise

Von allen Konstruktoren wird ein `_Al`-Zuweisungsobjekt gespeichert und der Vektor initialisiert.

Der erste Konstruktor Geben Sie einen leeren ursprünglichen Vektor und gibt Sie den Zuweisungstyp explizit an. verwendet werden.

Die zweiten und dritten Konstruktoren geben eine Kopie des parallel ausgeführten `_Vector`-Vektors an.

Der vierte Konstruktor gibt eine Verschiebung des gleichzeitigen `_Vector`-Vektors an.

Der fünfte Konstruktor gibt eine Wiederholung einer angegebenen Anzahl ( `_N`) von Elementen des Standardwerts für die Klasse `T`.

Der sechste Konstruktor gibt eine Wiederholung von ( `_N`)-Elementen des Werts `_Item`.

Der letzte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte [ `_Begin`, `_End`).

##  <a name="dtor"></a> ~ Concurrent_vector

Löscht alle Elemente aus, und zerstört diesen gleichzeitigen Vektor.

```
~concurrent_vector();
```

##  <a name="crbegin"></a> crbegin

Gibt einen Iterator des Typs `const_reverse_iterator` an den Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.

```
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `const_reverse_iterator` an den Anfang der gleichzeitigen Vektors.

##  <a name="crend"></a> crend

Gibt einen Iterator des Typs `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.

```
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor.

##  <a name="empty"></a> leere

Testet, ob es sich bei der gleichzeitige Vektor zu diesem Zeitpunkt leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.

```
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn zum Zeitpunkt der Vektor leer die Funktion aufgerufen war wurde, **"false"** andernfalls.

##  <a name="end"></a> Ende

Gibt einen Iterator des Typs `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.

```
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Vektor.

##  <a name="front"></a> Vorderseite

Gibt einen Verweis oder einen `const` Verweis auf das erste Element in den gleichzeitigen Vektor. Wenn die gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.

```
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis oder ein `const` Verweis auf das erste Element in den gleichzeitigen Vektor.

##  <a name="get_allocator"></a> get_allocator

Gibt eine Kopie der Zuweisung verwendet, um den gleichzeitigen Vektor zu erstellen. Diese Methode ist nebenläufigkeitssicher.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Kopie der Zuweisung, die zum Erstellen der `concurrent_vector` Objekt.

##  <a name="grow_by"></a> grow_by

Vergrößert diese gleichzeitigen Vektor von `_Delta` Elemente. Diese Methode ist nebenläufigkeitssicher.

```
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```

### <a name="parameters"></a>Parameter

*_Delta*<br/>
Die Anzahl von Elementen, die an das Objekt angefügt werden soll.

*_Item*<br/>
Der Wert, der die neuen Elemente mit initialisiert.

### <a name="return-value"></a>Rückgabewert

Ein Iterator zum ersten Element angefügt wird.

### <a name="remarks"></a>Hinweise

Wenn `_Item` nicht angegeben ist, wird die neue Elemente sind die Standardeinstellungen erstellt.

##  <a name="grow_to_at_least"></a> grow_to_at_least

Diese gleichzeitigen Vektor lange zunehmen, bis mindestens `_N` Elemente. Diese Methode ist nebenläufigkeitssicher.

```
iterator grow_to_at_least(size_type _N);
```

### <a name="parameters"></a>Parameter

*_N*<br/>
Der neue minimale Größe für die `concurrent_vector` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der an den Anfang der angefügten Sequenz oder das Element am Index verweist `_N` , wenn keine Elemente angefügt wurden.

##  <a name="max_size"></a> max_size

Gibt die maximale Anzahl von Elementen, die der gleichzeitige Vektor enthalten kann. Diese Methode ist nebenläufigkeitssicher.

```
size_type max_size() const;
```

### <a name="return-value"></a>Rückgabewert

Die maximale Anzahl von Elementen der `concurrent_vector` Objekt enthalten kann.

##  <a name="operator_eq"></a> Operator =

Weist den Inhalt eines anderen `concurrent_vector`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.

```
concurrent_vector& operator= (
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector& operator= (
    const concurrent_vector<T, M>& _Vector);

concurrent_vector& operator= (
    concurrent_vector&& _Vector);
```

### <a name="parameters"></a>Parameter

*M*<br/>
Der allocator-Typ des Quellvektors.

*_Vector*<br/>
Das `concurrent_vector`-Quellobjekt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das `concurrent_vector`-Objekt.

##  <a name="operator_at"></a> []-Operator

Bietet Zugriff auf das Element am angegebenen Index in den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch während der den Vektor, wächst, solange Sie haben sichergestellt, das den Wert `_Index` ist kleiner als die Anzahl der gleichzeitigen Vektor.

```
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```

### <a name="parameters"></a>Parameter

*_Index*<br/>
Der Index des Elements, das abgerufen werden.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Element am angegebenen Index.

### <a name="remarks"></a>Hinweise

Die Version des `operator []` zurückgibt nicht `const` Verweis kann nicht verwendet werden, um von verschiedenen Threads gleichzeitig auf das Element schreiben. Ein anderes Synchronisierungsobjekt sollte zum Synchronisieren des gleichzeitigen Lese- und Schreibvorgänge mit dem gleichen Datenelement verwendet werden.

Keine Überprüfung wird durchgeführt, um sicherzustellen, dass der Begrenzungen `_Index` ist ein gültiger Index in den gleichzeitigen Vektor.

##  <a name="push_back"></a> push_back

Fügt das angegebene Element am Ende den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.

```
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```

### <a name="parameters"></a>Parameter

*_Item*<br/>
Der Wert, der angefügt werden.

### <a name="return-value"></a>Rückgabewert

Ein Iterator für das Element angehängt.

##  <a name="rbegin"></a> rbegin

Gibt einen Iterator des Typs `reverse_iterator` oder `const_reverse_iterator` an den Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.

```
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` an den Anfang der gleichzeitigen Vektors.

##  <a name="rend"></a> REND

Gibt einen Iterator des Typs `reverse_iterator` oder `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.

```
reverse_iterator rend();

const_reverse_iterator rend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor.

##  <a name="reserve"></a> Hostreserven

Reserviert genügend Speicherplatz für den gleichzeitigen Vektor auf Größe anwachsen `_N` ohne später mehr Speicher reservieren. Diese Methode ist nicht nebenläufigkeitssicher.

```
void reserve(size_type _N);
```

### <a name="parameters"></a>Parameter

*_N*<br/>
Die Anzahl von Elementen, die Speicherplatz für die zu reservieren.

### <a name="remarks"></a>Hinweise

`reserve` ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen. Die Kapazität der gleichzeitigen Vektor nach der Methodenrückgabe möglicherweise größer als der angeforderten Reservierung.

##  <a name="resize"></a> Ändern der Größe

Ändert die Größe der gleichzeitigen Vektor auf die angeforderte Größe, löschen oder Hinzufügen von Elementen nach Bedarf. Diese Methode ist nicht nebenläufigkeitssicher.

```
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```

### <a name="parameters"></a>Parameter

*_N*<br/>
Die neue Größe des der Concurrent_vector.

*val*<br/>
Der Wert der neuen Elemente, die dem Vektor hinzugefügt wird, wenn die neue Größe die Originalgröße übersteigt. Wenn der Wert ausgelassen wird, werden die neuen Objekte den Standardwert für ihren Typ zugewiesen.

### <a name="remarks"></a>Hinweise

Wenn die Größe des Containers kleiner als die angeforderte Größe ist, werden dem Vektor Elemente hinzugefügt, bis die angeforderte Größe erreicht. Wenn die Größe des Containers die angeforderte Größe übersteigt, werden die Elemente am Ende des Containers gelöscht, bis der Container die Größe erreicht `_N`. Wenn die tatsächliche Größe des Containers der angeforderten Größe entspricht, wird keine Aktion durchgeführt.

`resize` ist nicht parallelitätssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen.

##  <a name="shrink_to_fit"></a> shrink_to_fit

Komprimiert die interne Darstellung des gleichzeitigen Vektor zum Reduzieren der Fragmentierung und speicherauslastung zu optimieren. Diese Methode ist nicht nebenläufigkeitssicher.

```
void shrink_to_fit();
```

### <a name="remarks"></a>Hinweise

Diese Methode belegt intern Arbeitsspeicher Verschiebt Elemente, erneut alle Iteratoren für ungültig zu erklären. `shrink_to_fit` ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Funktion aufrufen.

##  <a name="size"></a> Größe

Gibt die Anzahl der Elemente in den gleichzeitigen Vektor zurück. Diese Methode ist nebenläufigkeitssicher.

```
size_type size() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in dieser `concurrent_vector` Objekt.

### <a name="remarks"></a>Hinweise

Die zurückgegebene Größe ist garantiert, alle Elemente, die durch Aufrufe der Funktion angefügt eingeschlossen `push_back`, oder Erweiterungen, die vor dem Aufrufen dieser Methode abgeschlossen wurden. Aber es kann auch enthalten Elemente, die zugewiesen werden, aber immer noch in Bearbeitung von gleichzeitigen Aufrufen einer der Methoden Wachstum.

##  <a name="swap"></a> Swap

Vertauscht den Inhalt von zwei gleichzeitige Vektoren. Diese Methode ist nicht nebenläufigkeitssicher.

```
void swap(concurrent_vector& _Vector);
```

### <a name="parameters"></a>Parameter

*_Vector*<br/>
Die `concurrent_vector` Objekt, das Inhalt getauscht.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)

