---
title: Concurrent_queue-Klasse | Microsoft Docs
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
ms.openlocfilehash: a9a3ee82b8b81532b4e63f080ad321a93725ce41
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="concurrentqueue-class"></a>concurrent_queue-Klasse
Die `concurrent_queue`-Klasse ist eine Sequenzcontainerklasse, die "First In, First Out"-Zugriff auf ihre Elemente zulässt. Sie aktiviert einen beschränkten Satz von parallelitätssicheren Vorgängen, z. B. `push` und `try_pop`.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Elemente in der Warteschlange gespeichert werden.  
  
 `_Ax`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und Freigabe von Arbeitsspeicher für diesen gleichzeitigen Warteschlange kapselt. Dieses Argument ist optional, und der Standardwert ist `allocator<T>`.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`allocator_type`|Ein Typ, der die zuweisungsklasse für die gleichzeitige Warteschlange darstellt.|  
|`const_iterator`|Ein Typ, der eine nicht threadsichere `const` Iterator für Elemente in einer gleichzeitigen Warteschlange.|  
|`const_reference`|Ein Typ, der einen Verweis auf eine `const` in einer gleichzeitigen Warteschlange zum Lesen und Ausführen gespeichertes Element `const` Vorgänge.|  
|`difference_type`|Ein Typ, der Abstands mit Vorzeichen zwischen zwei Elementen in einer gleichzeitigen Warteschlange bereitstellt.|  
|`iterator`|Ein Typ, der einen Thread-sichere Iterator über die Elemente in einer gleichzeitigen Warteschlange darstellt.|  
|`reference`|Ein Typ, der einen Verweis auf ein in einer gleichzeitigen Warteschlange gespeichertes Element bereitstellt.|  
|`size_type`|Ein Typ, der die Anzahl von Elementen in einer gleichzeitigen Warteschlange zählt.|  
|`value_type`|Ein Typ, der in einer gleichzeitigen Warteschlange gespeicherten Datentyp darstellt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[concurrent_queue](#ctor)|Überladen. Erstellt eine gleichzeitige Warteschlange an.|  
|[~ Concurrent_queue-Destruktor](#dtor)|Zerstört die gleichzeitige Warteschlange an.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[clear](#clear)|Löscht die gleichzeitige Warteschlange, zerstört alle derzeit in die Warteschlange eingereihten Elemente. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[empty](#empty)|Testet, ob zum Zeitpunkt die gleichzeitige Warteschlange leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.|  
|[get_allocator](#get_allocator)|Gibt eine Kopie der Zuweisung verwendet, um den gleichzeitigen Warteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.|  
|[push](#push)|Überladen. Fügt ein Element am Ende der gleichzeitigen Warteschlange. Diese Methode ist nebenläufigkeitssicher.|  
|[try_pop](#try_pop)|Entfernt ein Element aus der Warteschlange an, wenn ein solcher verfügbar ist. Diese Methode ist nebenläufigkeitssicher.|  
|[unsafe_begin](#unsafe_begin)|Überladen. Gibt einen Iterator vom Typ `iterator` oder `const_iterator` am Anfang der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[unsafe_end](#unsafe_end)|Überladen. Gibt einen Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[unsafe_size](#unsafe_size)|Gibt die Anzahl der Elemente in der Warteschlange zurück. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `concurrent_queue`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concurrent_queue.h  
  
 **Namespace:** Parallelität  
  
##  <a name="clear"></a> Deaktivieren 

 Löscht die gleichzeitige Warteschlange, zerstört alle derzeit in die Warteschlange eingereihten Elemente. Diese Methode ist nicht nebenläufigkeitssicher.  
  
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
 `_InputIterator`  
 Der Typ des input-Iterator, der einen Bereich von Werten angibt.  
  
 `_Al`  
 Die mit diesem Objekt zu verwendende Zuweisungsklasse.  
  
 `_OtherQ`  
 Das `concurrent_queue`-Quellobjekt, aus dem Elemente kopiert oder verschoben werden sollen.  
  
 `_Begin`  
 Die Position des ersten Elements in dem zu kopierenden Elementbereich.  
  
 `_End`  
 Die Position des ersten Elements nach dem zu kopierenden Elementbereich.  
  
### <a name="remarks"></a>Hinweise  
 Alle Konstruktoren speichern ein Zuweisungsobjekt `_Al` und initialisieren Sie die Warteschlange.  
  
 Der erste Konstruktor gibt eine leere ursprüngliche Warteschlange und gibt explizit an die Allocator-Typ verwendet werden.  
  
 Der zweite Konstruktor gibt eine Kopie der gleichzeitigen Warteschlange `_OtherQ`.  
  
 Der dritte Konstruktor gibt eine Verschiebung des gleichzeitigen Warteschlange `_OtherQ`.  
  
 Der vierte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte [ `_Begin`, `_End`).  
  
##  <a name="dtor"></a> ~concurrent_queue 

 Zerstört die gleichzeitige Warteschlange an.  
  
```
~concurrent_queue();
```  
  
##  <a name="empty"></a> leere 

 Testet, ob zum Zeitpunkt die gleichzeitige Warteschlange leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn zum Zeitpunkt die gleichzeitige Warteschlange leer erläutert war, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Während dieser Methode parallelitätssicher ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`, und `empty`, der zurückgegebene Wert ist möglicherweise falsch nach der Zeit, die er vom aufrufenden Thread überprüft wird.  
  
##  <a name="get_allocator"></a> get_allocator 

 Gibt eine Kopie der Zuweisung verwendet, um den gleichzeitigen Warteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie der Zuweisung verwendet, um den gleichzeitigen Warteschlange zu erstellen.  
  
##  <a name="push"></a> Mithilfe von Push übertragen 

 Fügt ein Element am Ende der gleichzeitigen Warteschlange. Diese Methode ist nebenläufigkeitssicher.  
  
```
void push(const T& _Src);

void push(T&& _Src);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
 Das Element, das der Warteschlange hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 `push` parallelitätssicher ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`, und `empty`.  
  
##  <a name="try_pop"></a> try_pop 

 Entfernt ein Element aus der Warteschlange an, wenn ein solcher verfügbar ist. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool try_pop(T& _Dest);
```  
  
### <a name="parameters"></a>Parameter  
 `_Dest`  
 Ein Verweis auf einen Speicherort zum Speichern des Warteschlange entfernte Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn ein Element erfolgreich aus der Warteschlange entfernt wurde `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Element erfolgreich aus der Warteschlange entfernt wurde der Parameter `_Dest` empfängt den Warteschlange entfernten Wert, der ursprüngliche Wert in die Warteschlange eingereiht wird zerstört, und diese Funktion gibt `true`. Wenn kein Element aus der Warteschlange entfernt wurde, gibt diese Funktion `false` ohne Blockierung und den Inhalt der `_Dest` Parameter sind nicht definiert.  
  
 `try_pop` parallelitätssicher ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`, und `empty`.  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

 Gibt einen Iterator vom Typ `iterator` oder `const_iterator` am Anfang der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `iterator` oder `const_iterator` am Anfang der gleichzeitigen Warteschlange-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Iteratoren für den `concurrent_queue` Klasse dienen in erster Linie für das Debuggen, wie sie sind langsam und Iteration ist nicht nebenläufigkeitssicher in Bezug auf andere Warteschlangenvorgänge.  
  
##  <a name="unsafe_end"></a> unsafe_end 

 Gibt einen Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
iterator unsafe_end();

const_iterator unsafe_end() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Warteschlange.  
  
### <a name="remarks"></a>Hinweise  
 Die Iteratoren für den `concurrent_queue` Klasse dienen in erster Linie für das Debuggen, wie sie sind langsam und Iteration ist nicht nebenläufigkeitssicher in Bezug auf andere Warteschlangenvorgänge.  
  
##  <a name="unsafe_size"></a> unsafe_size 

 Gibt die Anzahl der Elemente in der Warteschlange zurück. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
size_type unsafe_size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe der gleichzeitigen Warteschlange.  
  
### <a name="remarks"></a>Hinweise  
 `unsafe_size` ist nicht nebenläufigkeitssicher und können falsche Ergebnisse erzeugen, wenn gleichzeitig mit Aufrufen der Methoden aufgerufen `push`, `try_pop`, und `empty`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
