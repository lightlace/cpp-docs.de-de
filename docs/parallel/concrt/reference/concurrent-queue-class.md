---
title: Concurrent_queue-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- concurrent_queue class
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41e4c6f3a540f44f6cec0d94ffab74d65a1ffe52
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386586"
---
# <a name="concurrentqueue-class"></a>concurrent_queue-Klasse

Die `concurrent_queue`-Klasse ist eine Sequenzcontainerklasse, die "First In, First Out"-Zugriff auf ihre Elemente zulässt. Sie aktiviert einen beschränkten Satz von parallelitätssicheren Vorgängen, z. B. `push` und `try_pop`.

## <a name="syntax"></a>Syntax

```
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente, die in der Warteschlange gespeichert werden.

*_Ax*<br/>
Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und Aufhebung der speicherbelegung für diese gleichzeitigen Warteschlange kapselt. Dieses Argument ist optional, und der Standardwert ist `allocator<T>`.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`allocator_type`|Ein Typ, der die zuweisungsklasse für der gleichzeitigen Warteschlange darstellt.|
|`const_iterator`|Ein Typ, eine nicht threadsichere darstellt `const` Iterator über die Elemente in einer gleichzeitigen Warteschlange.|
|`const_reference`|Ein Typ, einen Verweis auf eine `const` gespeichertes Element zum Lesen und Ausführen einer gleichzeitigen Warteschlange `const` Vorgänge.|
|`difference_type`|Ein Typ, die der Abstands mit Vorzeichen zwischen zwei Elementen in einer gleichzeitigen Warteschlange bereitstellt.|
|`iterator`|Ein Typ, der einen nicht threadsichere Iterator über die Elemente in einer gleichzeitigen Warteschlange darstellt.|
|`reference`|Ein Typ, die einen Verweis auf ein in einer Warteschlange für gleichzeitige gespeichertes Element bereitstellt.|
|`size_type`|Ein Typ, der die Anzahl der Elemente in einer Warteschlange für gleichzeitige zählt.|
|`value_type`|Ein Typ, der den in einer gleichzeitigen Warteschlange gespeicherten Datentyp darstellt.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[concurrent_queue](#ctor)|Überladen. Erstellt eine gleichzeitige Warteschlange an.|
|[~ Concurrent_queue-Destruktor](#dtor)|Zerstört die gleichzeitige Warteschlange an.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[clear](#clear)|Löscht die gleichzeitige Warteschlange, zerstört alle derzeit die Elemente in die Warteschlange eingereiht. Diese Methode ist nicht nebenläufigkeitssicher.|
|[empty](#empty)|Testet, ob es sich bei die gleichzeitige Warteschlange derzeit leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.|
|[get_allocator](#get_allocator)|Gibt eine Kopie der Zuweisung verwendet, um der gleichzeitigen Warteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.|
|[push](#push)|Überladen. Fügt ein Element am Ende der gleichzeitigen Warteschlange. Diese Methode ist nebenläufigkeitssicher.|
|[try_pop](#try_pop)|Entfernt ein Element aus der Warteschlange, sofern verfügbar. Diese Methode ist nebenläufigkeitssicher.|
|[unsafe_begin](#unsafe_begin)|Überladen. Gibt einen Iterator des Typs `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.|
|[unsafe_end](#unsafe_end)|Überladen. Gibt einen Iterator des Typs `iterator` oder `const_iterator` an das Ende der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.|
|[unsafe_size](#unsafe_size)|Gibt die Anzahl der Elemente in der Warteschlange zurück. Diese Methode ist nicht nebenläufigkeitssicher.|

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`concurrent_queue`

## <a name="requirements"></a>Anforderungen

**Header:** concurrent_queue.h

**Namespace:** Parallelität

##  <a name="clear"></a> Deaktivieren

Löscht die gleichzeitige Warteschlange, zerstört alle derzeit die Elemente in die Warteschlange eingereiht. Diese Methode ist nicht nebenläufigkeitssicher.

```
void clear();
```

##  <a name="ctor"></a> concurrent_queue

Erstellt eine gleichzeitige Warteschlange an.

```
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
Der Typ der Eingabe-Iterator, der angibt, einen Bereich von Werten.

*_Al*<br/>
Die mit diesem Objekt zu verwendende Zuweisungsklasse.

*_OtherQ*<br/>
Das `concurrent_queue`-Quellobjekt, aus dem Elemente kopiert oder verschoben werden sollen.

*_Begin*<br/>
Die Position des ersten Elements in dem zu kopierenden Elementbereich.

*_Beenden*<br/>
Die Position des ersten Elements nach dem zu kopierenden Elementbereich.

### <a name="remarks"></a>Hinweise

Alle Konstruktoren speichern ein Zuweisungsobjekt `_Al` und initialisieren Sie die Warteschlange.

Der erste Konstruktor gibt eine leere ursprüngliche Warteschlange und gibt explizit den Zuweisungstyp verwendet werden.

Der zweite Konstruktor gibt eine Kopie der gleichzeitigen Warteschlange `_OtherQ`.

Der dritte Konstruktor gibt eine Verschiebung der gleichzeitigen Warteschlange `_OtherQ`.

Der vierte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte [ `_Begin`, `_End`).

##  <a name="dtor"></a> ~concurrent_queue

Zerstört die gleichzeitige Warteschlange an.

```
~concurrent_queue();
```

##  <a name="empty"></a> leere

Testet, ob es sich bei die gleichzeitige Warteschlange derzeit leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.

```
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

`true` Wenn zum Zeitpunkt die gleichzeitige Warteschlange leer erläutert war, `false` andernfalls.

### <a name="remarks"></a>Hinweise

Während dieser Methode parallelitätssicher ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`, und `empty`, der zurückgegebene Wert möglicherweise falsch sein, die Zeit, die er durch den aufrufenden Thread überprüft wird.

##  <a name="get_allocator"></a> get_allocator

Gibt eine Kopie der Zuweisung verwendet, um der gleichzeitigen Warteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Kopie der Zuweisung verwendet, um der gleichzeitigen Warteschlange zu erstellen.

##  <a name="push"></a> Pushbenachrichtigungen

Fügt ein Element am Ende der gleichzeitigen Warteschlange. Diese Methode ist nebenläufigkeitssicher.

```
void push(const T& _Src);

void push(T&& _Src);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>
Das Element der Warteschlange hinzugefügt werden.

### <a name="remarks"></a>Hinweise

`push` parallelitätssicher ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`, und `empty`.

##  <a name="try_pop"></a> try_pop

Entfernt ein Element aus der Warteschlange, sofern verfügbar. Diese Methode ist nebenläufigkeitssicher.

```
bool try_pop(T& _Dest);
```

### <a name="parameters"></a>Parameter

*_Dest*<br/>
Ein Verweis auf einen Speicherort zum Speichern des Elements aus der Warteschlange entfernt.

### <a name="return-value"></a>Rückgabewert

`true` Wenn ein Element erfolgreich aus der Warteschlange entfernt wurde `false` andernfalls.

### <a name="remarks"></a>Hinweise

Wenn ein Element erfolgreich aus der Warteschlange entfernt wurde. der Parameter `_Dest` empfängt den aus der Warteschlange entfernte Wert, der ursprüngliche Wert in die Warteschlange eingereiht wird zerstört, und diese Funktion gibt `true`. Wenn kein Element aus der Warteschlange entfernt wurde, gibt diese Funktion `false` ohne Blockieren und den Inhalt der `_Dest` Parameter sind nicht definiert.

`try_pop` parallelitätssicher ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`, und `empty`.

##  <a name="unsafe_begin"></a> unsafe_begin

Gibt einen Iterator des Typs `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.

```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Queue-Objekt.

### <a name="remarks"></a>Hinweise

Die Iteratoren für den `concurrent_queue` Klasse dienen in erster Linie für das Debuggen, wie sie langsam sind, und die Iteration ist nicht nebenläufigkeitssicher in Bezug auf andere Warteschlangenvorgänge.

##  <a name="unsafe_end"></a> unsafe_end

Gibt einen Iterator des Typs `iterator` oder `const_iterator` an das Ende der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.

```
iterator unsafe_end();

const_iterator unsafe_end() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator vom Typ `iterator` oder `const_iterator` an das Ende der gleichzeitigen Warteschlange.

### <a name="remarks"></a>Hinweise

Die Iteratoren für den `concurrent_queue` Klasse dienen in erster Linie für das Debuggen, wie sie langsam sind, und die Iteration ist nicht nebenläufigkeitssicher in Bezug auf andere Warteschlangenvorgänge.

##  <a name="unsafe_size"></a> unsafe_size

Gibt die Anzahl der Elemente in der Warteschlange zurück. Diese Methode ist nicht nebenläufigkeitssicher.

```
size_type unsafe_size() const;
```

### <a name="return-value"></a>Rückgabewert

Die Größe der gleichzeitigen Warteschlange.

### <a name="remarks"></a>Hinweise

`unsafe_size` ist nicht nebenläufigkeitssicher und können falsche Ergebnisse erzeugen, wenn gleichzeitig Aufrufen der Methoden mit dem Namen `push`, `try_pop`, und `empty`.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
