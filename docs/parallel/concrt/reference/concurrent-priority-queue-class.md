---
title: Concurrent_priority_queue-Klasse | Microsoft Docs
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
ms.openlocfilehash: ed193eea8209611640b6d125d79ffec1748a7f7f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693665"
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
 `T`  
 Der Datentyp der Elemente in die Prioritätswarteschlange gespeichert werden.  
  
 `_Compare`  
 Der Typ des Funktionsobjekts ab, das zwei Elementwerte als Sortierschlüssel, um deren relative Reihenfolge in die Prioritätswarteschlange zu bestimmen, vergleichen kann. Dieses Argument ist optional, und das binäre Prädikat `less<T>` ist der Standardwert.  
  
 `_Ax`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und Freigabe von Arbeitsspeicher für die gleichzeitige Prioritätswarteschlange kapselt. Dieses Argument ist optional, und der Standardwert ist `allocator<T>`.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`allocator_type`|Ein Typ, der die zuweisungsklasse für das gleichzeitige Prioritätswarteschlange darstellt.|  
|`const_reference`|Ein Typ, den stellt ein konstantes auf ein Element des Typs in eine gleichzeitige Prioritätswarteschlange gespeicherten verweisen.|  
|`reference`|Ein Typ, der einen Verweis auf ein Element des Typs in eine gleichzeitige Prioritätswarteschlange gespeicherten darstellt.|  
|`size_type`|Ein Typ, der die Anzahl von Elementen in einer Prioritätswarteschlange für gleichzeitige zählt.|  
|`value_type`|Ein Typ, der in eine gleichzeitige Prioritätswarteschlange gespeicherten Datentyp darstellt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[concurrent_priority_queue](#ctor)|Überladen. Erstellt eine gleichzeitige Prioritätswarteschlange an.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[clear](#clear)|Löscht alle Elemente in der gleichzeitigen Priorität. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[empty](#empty)|Testet, ob die gleichzeitige Prioritätswarteschlange zu diesem Zeitpunkt leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.|  
|[get_allocator](#get_allocator)|Gibt eine Kopie der Zuweisung verwendet, um die gleichzeitige Prioritätswarteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.|  
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
 `_InputIterator`  
 Der Typ des Eingabeiterators.  
  
 `_Al`  
 Die mit diesem Objekt zu verwendende Zuweisungsklasse.  
  
 `_Init_capacity`  
 Die Anfangskapazität des `concurrent_priority_queue`-Objekts.  
  
 `_Begin`  
 Die Position des ersten Elements in dem zu kopierenden Elementbereich.  
  
 `_End`  
 Die Position des ersten Elements nach dem zu kopierenden Elementbereich.  
  
 `_Src`  
 Das `concurrent_priority_queue`-Quellobjekt, aus dem Elemente kopiert oder verschoben werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Alle Konstruktoren speichern ein Zuweisungsobjekt `_Al` und die Prioritätswarteschlange zu initialisieren.  
  
 Der erste Konstruktor gibt eine leere ursprüngliche Prioritätswarteschlange an und gibt optional eine Zuweisung.  
  
 Der zweite Konstruktor gibt eine Prioritätswarteschlange mit einer Anfangskapazität `_Init_capacity` und gibt optional eine Zuweisung.  
  
 Der dritte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte [ `_Begin`, `_End`) und gibt optional eine Zuweisung.  
  
 Die vierten und fünften Konstruktoren geben eine Kopie der Prioritätswarteschlange `_Src`.  
  
 Die sechsten und siebten Konstruktoren geben eine Verschiebung von der Prioritätswarteschlange `_Src`.  
  
##  <a name="empty"></a> leere 

 Testet, ob die gleichzeitige Prioritätswarteschlange zu diesem Zeitpunkt leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn zum Zeitpunkt der Prioritätswarteschlange leer die Funktion aufgerufen wurde war, `false` andernfalls.  
  
##  <a name="get_allocator"></a> get_allocator 

 Gibt eine Kopie der Zuweisung verwendet, um die gleichzeitige Prioritätswarteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie der Zuweisung zum Erstellen der `concurrent_priority_queue` Objekt.  
  
##  <a name="operator_eq"></a> Operator = 

 Weist den Inhalt eines anderen `concurrent_priority_queue`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
concurrent_priority_queue& operator= (const concurrent_priority_queue& _Src);

concurrent_priority_queue& operator= (concurrent_priority_queue&& _Src);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
 Das `concurrent_priority_queue`-Quellobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `concurrent_priority_queue`-Objekt.  
  
##  <a name="push"></a> Mithilfe von Push übertragen 

 Fügt ein Element in die Prioritätswarteschlange für gleichzeitige. Diese Methode ist nebenläufigkeitssicher.  
  
```
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```  
  
### <a name="parameters"></a>Parameter  
 `_Elem`  
 Das Element, das gleichzeitige Prioritätswarteschlange hinzugefügt werden.  
  
##  <a name="size"></a> Größe 

 Gibt die Anzahl der Elemente in der Prioritätswarteschlange für gleichzeitige zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in diesem `concurrent_priority_queue` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wird sichergestellt, dass die zurückgegebene Größe enthalten alle Elemente, die von Aufrufen an die Funktion hinzugefügt `push`. Er kann jedoch nicht die Ergebnisse der ausstehenden gleichzeitige Vorgänge wiedergeben.  
  
##  <a name="swap"></a> Swap 

 Vertauscht den Inhalt von zwei gleichzeitige Priorität Warteschlangen. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void swap(concurrent_priority_queue& _Queue);
```  
  
### <a name="parameters"></a>Parameter  
 `_Queue`  
 Die `concurrent_priority_queue` Objekt, das Inhalt mit austauschen.  
  
##  <a name="try_pop"></a> try_pop 

 Entfernt, und gibt das Element der höchsten Priorität aus der Warteschlange zurück, wenn die Warteschlange nicht leer ist. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool try_pop(reference _Elem);
```  
  
### <a name="parameters"></a>Parameter  
 `_Elem`  
 Ein Verweis auf eine Variable, die mit der höchsten Prioritätselement aufgefüllt wird, wenn die Warteschlange nicht leer ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn ein Wert per pop ausgelesen wurde, `false` andernfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)



