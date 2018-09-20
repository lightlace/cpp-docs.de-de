---
title: Concurrent_priority_queue-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::clear
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::empty
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::get_allocator
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::push
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::size
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::swap
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::try_pop
dev_langs:
- C++
helpviewer_keywords:
- concurrent_priority_queue class
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b87ac316c08f93a95f7791297b74cbbb20d5452a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413873"
---
# <a name="concurrentpriorityqueue-class"></a>concurrent_priority_queue-Klasse

Die `concurrent_priority_queue`-Klasse ist ein Container, der es mehreren Threads gleichzeitig ermöglicht, für Elemente die Vorgänge "push" und "pop" auszuführen. Elemente werden in Reihenfolge ihrer Priorität per pop ausgelesen, wenn die Priorität mit einem als Vorlagenargument angegebenen Funktionselement bestimmt wird.

## <a name="syntax"></a>Syntax

```
template <typename T,
    typename _Compare= std::less<T>,
    typename _Ax = std::allocator<T>
>,
    typename _Ax = std::allocator<T>> class concurrent_priority_queue;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente in der Prioritätswarteschlange gespeichert werden.

*Verglei_chen*<br/>
Der Typ des Funktionsobjekts, das zwei Elementwerte als Sortierschlüssel, um deren relative Reihenfolge in der Prioritätswarteschlange zu bestimmen, vergleichen kann. Dieses Argument ist optional, und das binäre Prädikat `less<T>` ist der Standardwert.

*_Ax*<br/>
Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und Aufhebung der speicherbelegung für die gleichzeitige Prioritätswarteschlange kapselt. Dieses Argument ist optional, und der Standardwert ist `allocator<T>`.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`allocator_type`|Ein Typ, der die zuweisungsklasse für das gleichzeitige Prioritätswarteschlange darstellt.|
|`const_reference`|Ein Typ, den stellt einen Konstanten auf ein Element des Typs in einer Prioritätswarteschlange für gleichzeitige gespeicherte Verweis.|
|`reference`|Ein Typ, der einen Verweis auf ein Element des Typs gespeichert, die in einer Prioritätswarteschlange für gleichzeitige darstellt.|
|`size_type`|Ein Typ, der die Anzahl der Elemente in einer Prioritätswarteschlange für gleichzeitige zählt.|
|`value_type`|Ein Typ, der in eine gleichzeitige Prioritätswarteschlange gespeicherten Datentyp darstellt.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[concurrent_priority_queue](#ctor)|Überladen. Erstellt eine gleichzeitige Prioritätswarteschlange an.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[clear](#clear)|Löscht alle Elemente in der gleichzeitigen Priorität. Diese Methode ist nicht nebenläufigkeitssicher.|
|[empty](#empty)|Testet, ob es sich bei die gleichzeitigen Prioritätswarteschlange zu diesem Zeitpunkt leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.|
|[get_allocator](#get_allocator)|Gibt eine Kopie der Zuweisung verwendet, um die der gleichzeitigen Prioritätswarteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.|
|[push](#push)|Überladen. Fügt ein Element in die Prioritätswarteschlange für gleichzeitige. Diese Methode ist nebenläufigkeitssicher.|
|[size](#size)|Gibt die Anzahl der Elemente in der Prioritätswarteschlange für gleichzeitige zurück. Diese Methode ist nebenläufigkeitssicher.|
|[swap](#swap)|Vertauscht den Inhalt von zwei gleichzeitige Priorität Warteschlangen. Diese Methode ist nicht nebenläufigkeitssicher.|
|[try_pop](#try_pop)|Entfernt, und gibt das Element der höchsten Priorität aus der Warteschlange zurück, wenn die Warteschlange nicht leer ist. Diese Methode ist nebenläufigkeitssicher.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator=](#operator_eq)|Überladen. Weist den Inhalt eines anderen `concurrent_priority_queue`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.|

## <a name="remarks"></a>Hinweise

Ausführliche Informationen zu den `concurrent_priority_queue` Klasse, finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`concurrent_priority_queue`

## <a name="requirements"></a>Anforderungen

**Header:** concurrent_priority_queue.h

**Namespace:** Parallelität

##  <a name="clear"></a> Deaktivieren

Löscht alle Elemente in der gleichzeitigen Priorität. Diese Methode ist nicht nebenläufigkeitssicher.

```
void clear();
```

### <a name="remarks"></a>Hinweise

`clear` ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für die gleichzeitige Prioritätswarteschlange aufrufen, wenn Sie diese Methode aufrufen. `clear` Gibt Arbeitsspeicher frei.

##  <a name="ctor"></a> concurrent_priority_queue

Erstellt eine gleichzeitige Prioritätswarteschlange an.

```
explicit concurrent_priority_queue(
    const allocator_type& _Al = allocator_type());

explicit concurrent_priority_queue(
    size_type _Init_capacity,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_priority_queue(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());

concurrent_priority_queue(
    const concurrent_priority_queue& _Src);

concurrent_priority_queue(
    const concurrent_priority_queue& _Src,
    const allocator_type& _Al);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src,
    const allocator_type& _Al);
```

### <a name="parameters"></a>Parameter

*_InputIterator*<br/>
Der Typ des Eingabeiterators.

*_Al*<br/>
Die mit diesem Objekt zu verwendende Zuweisungsklasse.

*_Init_capacity*<br/>
Die Anfangskapazität des `concurrent_priority_queue`-Objekts.

*_Begin*<br/>
Die Position des ersten Elements in dem zu kopierenden Elementbereich.

*_Beenden*<br/>
Die Position des ersten Elements nach dem zu kopierenden Elementbereich.

*_Src*<br/>
Das `concurrent_priority_queue`-Quellobjekt, aus dem Elemente kopiert oder verschoben werden sollen.

### <a name="remarks"></a>Hinweise

Alle Konstruktoren speichern ein Zuweisungsobjekt `_Al` und die Prioritätswarteschlange zu initialisieren.

Der erste Konstruktor gibt eine leere ursprüngliche Prioritätswarteschlange und gibt optional eine Zuweisung.

Der zweite Konstruktor gibt eine Prioritätswarteschlange mit einer Anfangskapazität `_Init_capacity` und gibt optional eine Zuweisung.

Der dritte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte [ `_Begin`, `_End`) und gibt optional eine Zuweisung.

Die vierten und fünften Konstruktoren geben eine Kopie der Prioritätswarteschlange `_Src`.

Die sechsten und siebten Konstruktoren geben eine Verschiebung der Prioritätswarteschlange `_Src`.

##  <a name="empty"></a> leere

Testet, ob es sich bei die gleichzeitigen Prioritätswarteschlange zu diesem Zeitpunkt leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.

```
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

`true` Wenn die Prioritätswarteschlange im Moment leer die Funktion aufgerufen war wurde, `false` andernfalls.

##  <a name="get_allocator"></a> get_allocator

Gibt eine Kopie der Zuweisung verwendet, um die der gleichzeitigen Prioritätswarteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Kopie der Zuweisung, die zum Erstellen der `concurrent_priority_queue` Objekt.

##  <a name="operator_eq"></a> Operator =

Weist den Inhalt eines anderen `concurrent_priority_queue`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.

```
concurrent_priority_queue& operator= (const concurrent_priority_queue& _Src);

concurrent_priority_queue& operator= (concurrent_priority_queue&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Das `concurrent_priority_queue`-Quellobjekt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das `concurrent_priority_queue`-Objekt.

##  <a name="push"></a> Pushbenachrichtigungen

Fügt ein Element in die Prioritätswarteschlange für gleichzeitige. Diese Methode ist nebenläufigkeitssicher.

```
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```

### <a name="parameters"></a>Parameter

*_Elem*<br/>
Das Element, das gleichzeitige Prioritätswarteschlange hinzugefügt werden.

##  <a name="size"></a> Größe

Gibt die Anzahl der Elemente in der Prioritätswarteschlange für gleichzeitige zurück. Diese Methode ist nebenläufigkeitssicher.

```
size_type size() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in dieser `concurrent_priority_queue` Objekt.

### <a name="remarks"></a>Hinweise

Die zurückgegebene Größe ist garantiert, alle Elemente, die durch Aufrufe der Funktion hinzugefügt eingeschlossen `push`. Allerdings kann es die Ergebnisse der ausstehenden gleichzeitige Vorgänge nicht wider.

##  <a name="swap"></a> Swap

Vertauscht den Inhalt von zwei gleichzeitige Priorität Warteschlangen. Diese Methode ist nicht nebenläufigkeitssicher.

```
void swap(concurrent_priority_queue& _Queue);
```

### <a name="parameters"></a>Parameter

*_Fronty*<br/>
Die `concurrent_priority_queue` Objekt, das Inhalt getauscht.

##  <a name="try_pop"></a> try_pop

Entfernt, und gibt das Element der höchsten Priorität aus der Warteschlange zurück, wenn die Warteschlange nicht leer ist. Diese Methode ist nebenläufigkeitssicher.

```
bool try_pop(reference _Elem);
```

### <a name="parameters"></a>Parameter

*_Elem*<br/>
Ein Verweis auf eine Variable, die mit dem höchsten Prioritätselement, aufgefüllt wird, wenn die Warteschlange nicht leer ist.

### <a name="return-value"></a>Rückgabewert

`true` Wenn ein Wert vom Stapel geholt, war, `false` andernfalls.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)

