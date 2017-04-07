---
title: Concurrent_queue-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 21
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d2af8483f38a14454e3aa1aecf28864bab1c6a1a
ms.lasthandoff: 03/17/2017

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
 Der Datentyp der Elemente, die in der Warteschlange gespeichert werden.  
  
 `_Ax`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und zur Freigabe des Arbeitsspeichers für diese gleichzeitigen Warteschlange kapselt. Dieses Argument ist optional, und der Standardwert ist `allocator<``T``>`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`allocator_type`|Ein Typ, der die zuweisungsklasse für die gleichzeitige Warteschlange darstellt.|  
|`const_iterator`|Ein Typ, der eine nicht threadsichere `const` Iterator über Elemente in einer gleichzeitigen Warteschlange.|  
|`const_reference`|Ein Typ, der einen Verweis auf eine `const` Element in einer gleichzeitigen Warteschlange zum Lesen und Ausführen von gespeicherten `const` Vorgänge.|  
|`difference_type`|Ein Typ, die den mit Abstand zwischen zwei Elementen in einer gleichzeitigen Warteschlange bereitstellt.|  
|`iterator`|Ein Typ, der einen nicht threadsicheren Iterator über die Elemente in einer gleichzeitigen Warteschlange darstellt.|  
|`reference`|Ein Typ, der einen Verweis auf ein Element in einer gleichzeitigen Warteschlange bereitstellt.|  
|`size_type`|Ein Typ, der die Anzahl von Elementen in einer gleichzeitigen Warteschlange angibt.|  
|`value_type`|Ein Typ, der in einer gleichzeitigen Warteschlange gespeicherten Datentyp darstellt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[concurrent_queue](#ctor)|Überladen. Erstellt eine gleichzeitige Warteschlange.|  
|[~ Concurrent_queue-Destruktor](#dtor)|Zerstört die gleichzeitige Warteschlange.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[clear](#clear)|Löscht die gleichzeitige Warteschlange und zerstört alle derzeit zur Warteschlange hinzugefügten Elemente. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[empty](#empty)|Testet, ob zum Zeitpunkt die gleichzeitige Warteschlange leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.|  
|[get_allocator](#get_allocator)|Gibt eine Kopie der Zuweisung verwendet, um die parallele Warteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.|  
|[push](#push)|Überladen. Fügt ein Element am Ende der gleichzeitigen Warteschlange. Diese Methode ist nebenläufigkeitssicher.|  
|[try_pop](#try_pop)|Entfernt ein Element aus der Warteschlange, sofern verfügbar. Diese Methode ist nebenläufigkeitssicher.|  
|[unsafe_begin](#unsafe_begin)|Überladen. Gibt einen Iterator vom Typ `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[unsafe_end](#unsafe_end)|Überladen. Gibt einen Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[unsafe_size](#unsafe_size)|Gibt die Anzahl der Elemente in der Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `concurrent_queue`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concurrent_queue.h  
  
 **Namespace:** Parallelität  
  
##  <a name="clear"></a>Deaktivieren 

 Löscht die gleichzeitige Warteschlange und zerstört alle derzeit zur Warteschlange hinzugefügten Elemente. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void clear();
```  
  
##  <a name="ctor"></a>concurrent_queue 

 Erstellt eine gleichzeitige Warteschlange.  
  
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
 Der Typ des Eingabeiterators, der einen Bereich von Werten angibt.  
  
 `_Al`  
 Die mit diesem Objekt zu verwendende Zuweisungsklasse.  
  
 `_OtherQ`  
 Das `concurrent_queue`-Quellobjekt, aus dem Elemente kopiert oder verschoben werden sollen.  
  
 `_Begin`  
 Die Position des ersten Elements in dem zu kopierenden Elementbereich.  
  
 `_End`  
 Die Position des ersten Elements nach dem zu kopierenden Elementbereich.  
  
### <a name="remarks"></a>Hinweise  
 Alle Konstruktoren speichern ein Zuweisungsobjekt `_Al` und initialisieren die Warteschlange.  
  
 Der erste Konstruktor gibt eine leere ursprüngliche Warteschlange und gibt explizit den Allocator-Typ verwendet werden.  
  
 Der zweite Konstruktor gibt eine Kopie der gleichzeitigen Warteschlange `_OtherQ`.  
  
 Der dritte Konstruktor gibt eine Verschiebung des gleichzeitigen Warteschlange `_OtherQ`.  
  
 Der vierte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte an [ `_Begin`, `_End`).  
  
##  <a name="dtor"></a>~ Concurrent_queue 

 Zerstört die gleichzeitige Warteschlange.  
  
```
~concurrent_queue();
```  
  
##  <a name="empty"></a>leere 

 Testet, ob zum Zeitpunkt die gleichzeitige Warteschlange leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn zum Zeitpunkt die gleichzeitige Warteschlange leer wir gesucht war, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Während dieser Methode parallelitätssicher ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`, und `empty`, der zurückgegebene Wert möglicherweise falsch sein, die Zeit, die er vom aufrufenden Thread überprüft wird.  
  
##  <a name="get_allocator"></a>get_allocator 

 Gibt eine Kopie der Zuweisung verwendet, um die parallele Warteschlange zu erstellen. Diese Methode ist nebenläufigkeitssicher.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie der Zuweisung verwendet, um die parallele Warteschlange zu erstellen.  
  
##  <a name="push"></a>Push 

 Fügt ein Element am Ende der gleichzeitigen Warteschlange. Diese Methode ist nebenläufigkeitssicher.  
  
```
void push(const T& _Src);

void push(T&& _Src);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
 Das Element, das der Warteschlange hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 `push`parallelitätssicher ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`, und `empty`.  
  
##  <a name="try_pop"></a>try_pop 

 Entfernt ein Element aus der Warteschlange, sofern verfügbar. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool try_pop(T& _Dest);
```  
  
### <a name="parameters"></a>Parameter  
 `_Dest`  
 Ein Verweis auf einen Speicherort zum Speichern des Elements aus der Warteschlange entfernt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn ein Element erfolgreich aus der Warteschlange entfernt wurde `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Element erfolgreich aus der Warteschlange entfernt wurde der Parameter `_Dest` empfängt den Warteschlange entfernten Wert, der ursprüngliche Wert in die Warteschlange eingereiht wird zerstört, und diese Funktion gibt `true`. Wenn kein Element aus der Warteschlange entfernt wurde, gibt diese Funktion `false` ohne Blockieren und den Inhalt der `_Dest` Parameter sind nicht definiert.  
  
 `try_pop`parallelitätssicher ist in Bezug auf Aufrufe der Methoden `push`, `try_pop`, und `empty`.  
  
##  <a name="unsafe_begin"></a>unsafe_begin 

 Gibt einen Iterator vom Typ `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `iterator` oder `const_iterator` an den Anfang des gleichzeitigen Warteschlangenobjekts.  
  
### <a name="remarks"></a>Hinweise  
 Die Iteratoren für die `concurrent_queue` Klasse dienen in erster Linie für das Debuggen, wie sie langsam sind, und die Iteration ist nicht parallelitätssicher ist in Bezug auf andere Warteschlangenoperationen.  
  
##  <a name="unsafe_end"></a>unsafe_end 

 Gibt einen Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
iterator unsafe_end();

const_iterator unsafe_end() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Warteschlange.  
  
### <a name="remarks"></a>Hinweise  
 Die Iteratoren für die `concurrent_queue` Klasse dienen in erster Linie für das Debuggen, wie sie langsam sind, und die Iteration ist nicht parallelitätssicher ist in Bezug auf andere Warteschlangenoperationen.  
  
##  <a name="unsafe_size"></a>unsafe_size 

 Gibt die Anzahl der Elemente in der Warteschlange. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
size_type unsafe_size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe der gleichzeitigen Warteschlange.  
  
### <a name="remarks"></a>Hinweise  
 `unsafe_size`ist nicht parallelitätssicher und kann falsche Ergebnisse erzeugen, wenn gleichzeitig mit Aufrufen der Methoden aufgerufen `push`, `try_pop`, und `empty`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

