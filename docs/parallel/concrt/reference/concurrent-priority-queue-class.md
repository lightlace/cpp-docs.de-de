---
title: Concurrent_priority_queue-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_priority_queue/concurrency::concurrent_priority_queue
dev_langs:
- C++
helpviewer_keywords:
- concurrent_priority_queue class
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 59bbd25f78294e1363b8acb49e45f364a9ae026e
ms.lasthandoff: 02/24/2017

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
 Der Datentyp der Elemente, die in die Prioritätswarteschlange gespeichert werden.  
  
 `_Compare`  
 Der Typ des Funktionsobjekts, das zwei Elementwerte als Sortierschlüssel bestimmen deren relative Reihenfolge in die Prioritätswarteschlange vergleichen kann. Dieses Argument ist optional, und das binäre Prädikat `less<``T``>` ist der Standardwert.  
  
 `_Ax`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und zur Freigabe des Arbeitsspeichers für die gleichzeitige Prioritätswarteschlange kapselt. Dieses Argument ist optional, und der Standardwert ist `allocator<``T``>`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`allocator_type`|Ein Typ, der die zuweisungsklasse für die gleichzeitige Prioritätswarteschlange darstellt.|  
|`const_reference`|Ein Typ, den reference darstellt, ein konstantes auf ein Element des Typs in eine gleichzeitige Prioritätswarteschlange gespeichert.|  
|`reference`|Ein Typ, der einen Verweis auf ein Element des Typs gespeichert, die in einer Prioritätswarteschlange für gleichzeitige darstellt.|  
|`size_type`|Ein Typ, der die Anzahl der Elemente in einer Prioritätswarteschlange für gleichzeitige zählt.|  
|`value_type`|Ein Typ, der in eine Warteschlange mit gleichzeitiger Priorität gespeicherten Datentyp darstellt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Concurrent_priority_queue-Konstruktor](#ctor)|Überladen. Erstellt eine gleichzeitige Prioritätswarteschlange.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Clear-Methode](#clear)|Löscht alle Elemente in der gleichzeitigen Priorität. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[Empty-Methode](#empty)|Testet, ob die gleichzeitige Prioritätswarteschlange Zeitpunkt leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.|  
|[Get_allocator-Methode](#get_allocator)|Gibt eine Kopie der Zuweisung verwendet, um die gleichzeitige Prioritätswarteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.|  
|[Push-Methode](#push)|Überladen. Fügt ein Element in die Prioritätswarteschlange für gleichzeitige. Diese Methode ist nebenläufigkeitssicher.|  
|[Size-Methode](#size)|Gibt die Anzahl der Elemente in der Warteschlange gleichzeitig Priorität zurück. Diese Methode ist nebenläufigkeitssicher.|  
|[Swap-Methode](#swap)|Vertauscht den Inhalt von zwei gleichzeitige Priorität Warteschlangen. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[Try_pop-Methode](#try_pop)|Entfernt, und gibt das Element der höchsten Priorität aus der Warteschlange zurück, wenn die Warteschlange nicht leer ist. Diese Methode ist nebenläufigkeitssicher.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator =-Operator](#operator_eq)|Überladen. Weist den Inhalt eines anderen `concurrent_priority_queue`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## <a name="remarks"></a>Hinweise  
 Ausführliche Informationen zu den `concurrent_priority_queue` Klasse, finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `concurrent_priority_queue`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concurrent_priority_queue.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namecleara-clear"></a><a name="clear"></a>Deaktivieren 

 Löscht alle Elemente in der gleichzeitigen Priorität. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void clear();
```  
  
### <a name="remarks"></a>Hinweise  
 `clear`ist nicht parallelitätssicher ist. Sie müssen sicherstellen, dass keine anderen Threads Methoden für die gleichzeitige Prioritätswarteschlange aufrufen, wenn Sie diese Methode aufrufen. `clear`wird kein Speicher freigegeben werden.  
  
##  <a name="a-namectora-concurrentpriorityqueue"></a><a name="ctor"></a>concurrent_priority_queue 

 Erstellt eine gleichzeitige Prioritätswarteschlange.  
  
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
  
 Der erste Konstruktor gibt eine leere ursprüngliche Prioritätswarteschlange und gibt optional eine Zuweisung.  
  
 Der zweite Konstruktor gibt eine Prioritätswarteschlange mit einer Anfangskapazität `_Init_capacity` und gibt optional eine Zuweisung.  
  
 Der dritte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte an [ `_Begin`, `_End`) und gibt optional eine Zuweisung.  
  
 Die vierten und fünften Konstruktoren geben eine Kopie der Prioritätswarteschlange `_Src`.  
  
 Die sechsten und siebten Konstruktoren geben eine Verschiebung der Prioritätswarteschlange `_Src`.  
  
##  <a name="a-nameemptya-empty"></a><a name="empty"></a>leere 

 Testet, ob die gleichzeitige Prioritätswarteschlange Zeitpunkt leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn zum Zeitpunkt die Prioritätswarteschlange leer die Funktion aufgerufen wurde war, `false` andernfalls.  
  
##  <a name="a-namegetallocatora-getallocator"></a><a name="get_allocator"></a>get_allocator 

 Gibt eine Kopie der Zuweisung verwendet, um die gleichzeitige Prioritätswarteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zuweisung erstellt eine Kopie der `concurrent_priority_queue` Objekt.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>Operator = 

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
  
##  <a name="a-namepusha-push"></a><a name="push"></a>Push 

 Fügt ein Element in die Prioritätswarteschlange für gleichzeitige. Diese Methode ist nebenläufigkeitssicher.  
  
```
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```  
  
### <a name="parameters"></a>Parameter  
 `_Elem`  
 Das Element, das die gleichzeitige Prioritätswarteschlange hinzugefügt werden.  
  
##  <a name="a-namesizea-size"></a><a name="size"></a>Größe 

 Gibt die Anzahl der Elemente in der Warteschlange gleichzeitig Priorität zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in diesem `concurrent_priority_queue` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Größe ist immer gehören alle Elemente, die durch Aufrufe der Funktion hinzugefügt `push`. Er kann jedoch nicht Ergebnisse ausstehende gleichzeitige Vorgänge wiedergeben.  
  
##  <a name="a-nameswapa-swap"></a><a name="swap"></a>Swap 

 Vertauscht den Inhalt von zwei gleichzeitige Priorität Warteschlangen. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void swap(concurrent_priority_queue& _Queue);
```  
  
### <a name="parameters"></a>Parameter  
 `_Queue`  
 Die `concurrent_priority_queue` -Objekt, das Inhalt getauscht.  
  
##  <a name="a-nametrypopa-trypop"></a><a name="try_pop"></a>try_pop 

 Entfernt, und gibt das Element der höchsten Priorität aus der Warteschlange zurück, wenn die Warteschlange nicht leer ist. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool try_pop(reference _Elem);
```  
  
### <a name="parameters"></a>Parameter  
 `_Elem`  
 Ein Verweis auf eine Variable, die mit der höchsten Priorität Elements aufgefüllt wird, wenn die Warteschlange nicht leer ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn ein Wert vom Stapel geholt wurde, `false` andernfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)




