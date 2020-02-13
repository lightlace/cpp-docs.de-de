---
title: concurrent_queue-Klasse
ms.date: 11/04/2016
f1_keywords:
- concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::clear
- CONCURRENT_QUEUE/concurrency::concurrent_queue::empty
- CONCURRENT_QUEUE/concurrency::concurrent_queue::get_allocator
- CONCURRENT_QUEUE/concurrency::concurrent_queue::push
- CONCURRENT_QUEUE/concurrency::concurrent_queue::try_pop
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_begin
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_end
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_size
helpviewer_keywords:
- concurrent_queue class
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
ms.openlocfilehash: 4e913af40b2218da5699da2659ec2e9189e32994
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143202"
---
# <a name="concurrent_queue-class"></a>concurrent_queue-Klasse

Die `concurrent_queue`-Klasse ist eine Sequenzcontainerklasse, die "First In, First Out"-Zugriff auf ihre Elemente zulässt. Sie aktiviert einen beschränkten Satz von parallelitätssicheren Vorgängen, z. B. `push` und `try_pop`. Die Parallelitäts Sicherheit bedeutet, dass Zeiger oder Iteratoren immer gültig sind. Es handelt sich nicht um eine Garantie der Element Initialisierung oder einer bestimmten Durchlauf Reihenfolge.

## <a name="syntax"></a>Syntax

```cpp
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente, die in der Warteschlange gespeichert werden sollen.

*_Ax*<br/>
Der Typ, der das gespeicherte Zuweisungs Objekt darstellt, das Details zur Zuordnung und Freigabe von Arbeitsspeicher für diese gleichzeitige Warteschlange kapselt. Dieses Argument ist optional, und der Standardwert ist `allocator<T>`.

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`allocator_type`|Ein Typ, der die zuordnerklasse für die gleichzeitige Warteschlange darstellt.|
|`const_iterator`|Ein Typ, der einen nicht Thread sicheren `const` Iterator über Elemente in einer gleichzeitigen Warteschlange darstellt.|
|`const_reference`|Ein Typ, der einen Verweis auf ein `const` Element bereitstellt, das in einer gleichzeitigen Warteschlange zum Lesen und ausführen `const` Vorgänge gespeichert ist.|
|`difference_type`|Ein Typ, der den Abstand mit Vorzeichen zwischen zwei Elementen in einer gleichzeitigen Warteschlange bereitstellt.|
|`iterator`|Ein Typ, der einen nicht Thread sicheren Iterator für die Elemente in einer gleichzeitigen Warteschlange darstellt.|
|`reference`|Ein Typ, der einen Verweis auf ein in einer gleichzeitigen Warteschlange gespeichertes Element bereitstellt.|
|`size_type`|Ein Typ, der die Anzahl der Elemente in einer gleichzeitigen Warteschlange zählt.|
|`value_type`|Ein Typ, der den in einer gleichzeitigen Warteschlange gespeicherten Datentyp darstellt.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[concurrent_queue](#ctor)|Ist überladen. Erstellt eine gleichzeitige Warteschlange.|
|[~ Concurrent_queue-Dekonstruktor](#dtor)|Zerstört die gleichzeitige Warteschlange.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Löschen](#clear)|Löscht die gleichzeitige Warteschlange und zerstört alle Elemente, die in die Warteschlange eingereiht sind Diese Methode ist nicht nebenläufigkeitssicher.|
|[empty](#empty)|Testet, ob die gleichzeitige Warteschlange zu dem Zeitpunkt, zu dem diese Methode aufgerufen wird, leer ist. Diese Methode ist nebenläufigkeitssicher.|
|[get_allocator](#get_allocator)|Gibt eine Kopie der Zuweisung zurück, die zum Erstellen der gleichzeitigen Warteschlange verwendet wird. Diese Methode ist nebenläufigkeitssicher.|
|[push](#push)|Ist überladen. Fügt ein Element am Ende der gleichzeitigen Warteschlange in die Warteschlange ein. Diese Methode ist nebenläufigkeitssicher.|
|[try_pop](#try_pop)|Entfernt ein Element aus der Warteschlange, wenn ein Element verfügbar ist. Diese Methode ist nebenläufigkeitssicher.|
|[unsafe_begin](#unsafe_begin)|Ist überladen. Gibt einen Iterator vom Typ `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Warteschlange zurück. Diese Methode ist nicht nebenläufigkeitssicher.|
|[unsafe_end](#unsafe_end)|Ist überladen. Gibt einen Iterator vom Typ `iterator` oder `const_iterator` am Ende der gleichzeitigen Warteschlange zurück. Diese Methode ist nicht nebenläufigkeitssicher.|
|[unsafe_size](#unsafe_size)|Gibt die Anzahl der Elemente in der Warteschlange zurück. Diese Methode ist nicht nebenläufigkeitssicher.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`concurrent_queue`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** Concurrent_queue. h

**Namespace:** Parallelität

## <a name="clear"></a>Klartext

Löscht die gleichzeitige Warteschlange und zerstört alle Elemente, die in die Warteschlange eingereiht sind Diese Methode ist nicht nebenläufigkeitssicher.

```cpp
void clear();
```

## <a name="ctor"></a>concurrent_queue

Erstellt eine gleichzeitige Warteschlange.

```cpp
explicit concurrent_queue(
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    const concurrent_queue& _OtherQ,
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    concurrent_queue&& _OtherQ,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_queue(_InputIterator _Begin,
    _InputIterator _End);
```

### <a name="parameters"></a>Parameter

*_InputIterator*<br/>
Der Typ des eingabeiterators, der einen Wertebereich angibt.

*_Al*<br/>
Die mit diesem Objekt zu verwendende Zuweisungsklasse.

*_OtherQ*<br/>
Das `concurrent_queue`-Quellobjekt, aus dem Elemente kopiert oder verschoben werden sollen.

*_Begin*<br/>
Die Position des ersten Elements in dem zu kopierenden Elementbereich.

*_End*<br/>
Die Position des ersten Elements nach dem zu kopierenden Elementbereich.

### <a name="remarks"></a>Bemerkungen

Alle Konstruktoren speichern ein zuordnerobjekt `_Al` und initialisieren die Warteschlange.

Der erste Konstruktor gibt eine leere anfängliche Warteschlange an und gibt explizit den zu verwendenden zuordnertyp an.

Der zweite Konstruktor gibt eine Kopie der gleichzeitigen Warteschlangen `_OtherQ`an.

Der dritte Konstruktor gibt eine Verschiebung der gleichzeitigen Warteschlangen `_OtherQ`an.

Der vierte Konstruktor gibt Werte an, die vom iteratorbereich (`_Begin``_End`) bereitgestellt werden.

## <a name="dtor"></a>~ concurrent_queue

Zerstört die gleichzeitige Warteschlange.

```cpp
~concurrent_queue();
```

## <a name="empty"></a>leer

Testet, ob die gleichzeitige Warteschlange zu dem Zeitpunkt, zu dem diese Methode aufgerufen wird, leer ist. Diese Methode ist nebenläufigkeitssicher.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

**true** , wenn die gleichzeitige Warteschlange zum Zeitpunkt der Betrachtung leer war, andernfalls **false** .

### <a name="remarks"></a>Bemerkungen

Wenngleich diese Methode in Bezug auf Aufrufe der Methoden `push`, `try_pop`und `empty`Parallelitäts sicher ist, ist der zurückgegebene Wert möglicherweise zu dem Zeitpunkt falsch, als er vom aufrufenden Thread überprüft wird.

## <a name="get_allocator"></a>get_allocator

Gibt eine Kopie der Zuweisung zurück, die zum Erstellen der gleichzeitigen Warteschlange verwendet wird. Diese Methode ist nebenläufigkeitssicher.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Kopie der Zuweisung, die zum Erstellen der gleichzeitigen Warteschlange verwendet wird.

## <a name="push"></a>Push

Fügt ein Element am Ende der gleichzeitigen Warteschlange in die Warteschlange ein. Diese Methode ist nebenläufigkeitssicher.

```cpp
void push(const T& _Src);

void push(T&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Das Element, das der Warteschlange hinzugefügt werden soll.

### <a name="remarks"></a>Bemerkungen

`push` ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`und `empty`Parallelitäts sicher.

## <a name="try_pop"></a>try_pop

Entfernt ein Element aus der Warteschlange, wenn ein Element verfügbar ist. Diese Methode ist nebenläufigkeitssicher.

```cpp
bool try_pop(T& _Dest);
```

### <a name="parameters"></a>Parameter

*_Dest*<br/>
Ein Verweis auf einen Speicherort zum Speichern des Elements aus der Warteschlange.

### <a name="return-value"></a>Rückgabewert

**true** , wenn ein Element erfolgreich aus der Warteschlange entfernt wurde, andernfalls **false** .

### <a name="remarks"></a>Bemerkungen

Wenn ein Element erfolgreich aus der Warteschlange entfernt wurde, empfängt der Parameter `_Dest` den Wert aus der Warteschlange, und der ursprüngliche Wert, der in der Warteschlange gespeichert ist, wird zerstört, und diese Funktion gibt **true**zurück. Wenn kein Element zum Entfernen aus der Warteschlange vorhanden ist, gibt diese Funktion `false` ohne Blockierung zurück, und der Inhalt des `_Dest`-Parameters ist nicht definiert.

`try_pop` ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`und `empty`Parallelitäts sicher.

## <a name="unsafe_begin"></a>unsafe_begin

Gibt einen Iterator vom Typ `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Warteschlange zurück. Diese Methode ist nicht nebenläufigkeitssicher.

```cpp
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `iterator` oder `const_iterator` am Anfang des gleichzeitigen Warteschlangen Objekts.

### <a name="remarks"></a>Bemerkungen

Die Iteratoren für die `concurrent_queue`-Klasse sind hauptsächlich für das Debuggen vorgesehen, da Sie langsam sind und die Iterationen in Bezug auf andere Warteschlangen Vorgänge nicht Parallelitäts sicher sind.

## <a name="unsafe_end"></a>unsafe_end

Gibt einen Iterator vom Typ `iterator` oder `const_iterator` am Ende der gleichzeitigen Warteschlange zurück. Diese Methode ist nicht nebenläufigkeitssicher.

```cpp
iterator unsafe_end();

const_iterator unsafe_end() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `iterator` oder `const_iterator` am Ende der gleichzeitigen Warteschlange.

### <a name="remarks"></a>Bemerkungen

Die Iteratoren für die `concurrent_queue`-Klasse sind hauptsächlich für das Debuggen vorgesehen, da Sie langsam sind und die Iterationen in Bezug auf andere Warteschlangen Vorgänge nicht Parallelitäts sicher sind.

## <a name="unsafe_size"></a>unsafe_size

Gibt die Anzahl der Elemente in der Warteschlange zurück. Diese Methode ist nicht nebenläufigkeitssicher.

```cpp
size_type unsafe_size() const;
```

### <a name="return-value"></a>Rückgabewert

Die Größe der gleichzeitigen Warteschlange.

### <a name="remarks"></a>Bemerkungen

`unsafe_size` ist nicht Parallelitäts sicher und kann zu falschen Ergebnissen führen, wenn er gleichzeitig mit Aufrufen der Methoden `push`, `try_pop`und `empty`aufgerufen wird.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
