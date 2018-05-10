---
title: Concurrent_vector-Klasse | Microsoft Docs
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
ms.openlocfilehash: e120e072fb3f56788cbf39fbbc3887f5c816f4ef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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
 `T`  
 Der Datentyp der Elemente im Vektor gespeichert werden.  
  
 `_Ax`  
 Der Typ, der das gespeicherte Zuweisungsobjekt darstellt, das Details zur Speicherbelegung und Aufhebung der Speicherbelegung für den gleichzeitigen Vektor kapselt. Dieses Argument ist optional, und der Standardwert ist `allocator<T>`.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`allocator_type`|Ein Typ, der die zuweisungsklasse für den gleichzeitigen Vektor darstellt.|  
|`const_iterator`|Ein Typ, der einem Iterator mit zufälligem Zugriff können bietet lesen eine `const` Element in einen gleichzeitigen Vektor.|  
|`const_pointer`|Ein Typ, der ein Zeiger auf eine `const` Element in einen gleichzeitigen Vektor.|  
|`const_reference`|Ein Typ, der einen Verweis auf eine `const` in einen gleichzeitigen Vektor zum Lesen und Ausführen gespeichertes Element `const` Vorgänge.|  
|`const_reverse_iterator`|Ein Typ, der einem Iterator mit zufälligem Zugriff können bietet gelesen `const` Element in den gleichzeitigen Vektor.|  
|`difference_type`|Ein Typ, der Abstands mit Vorzeichen zwischen zwei Elementen in einen gleichzeitigen Vektor bereitstellt.|  
|`iterator`|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, der ein Element in einen gleichzeitigen Vektor gelesen werden kann. Die Änderung eines Elements mit den Iterator ist nicht nebenläufigkeitssicher.|  
|`pointer`|Ein Typ, der einen Zeiger auf ein Element in einen gleichzeitigen Vektor bereitstellt.|  
|`reference`|Ein Typ, der einen Verweis auf ein in einen gleichzeitigen Vektor gespeichertes Element bereitstellt.|  
|`reverse_iterator`|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, der jedes Element in einem umgekehrten gleichzeitigen Vektor gelesen werden kann. Die Änderung eines Elements mit den Iterator ist nicht nebenläufigkeitssicher.|  
|`size_type`|Ein Typ, der die Anzahl der Elemente in einen gleichzeitigen Vektor zählt.|  
|`value_type`|Ein Typ, der in einen gleichzeitigen Vektor gespeicherten Datentyp darstellt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[concurrent_vector](#ctor)|Überladen. Erstellt einen gleichzeitigen Vektor.|  
|[~ Concurrent_vector-Destruktor](#dtor)|Löscht alle Elemente aus, und zerstört diesen gleichzeitigen Vektor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[assign](#assign)|Überladen. Löscht die Elemente von den gleichzeitigen Vektor und weist ihm entweder `_N` Kopien `_Item`, oder durch den Iteratorbereich angegebenen Werte [ `_Begin`, `_End`). Diese Methode ist nicht nebenläufigkeitssicher.|  
|[at](#at)|Überladen. Bietet Zugriff auf das Element am angegebenen Index in den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch beim wächst des Vektors, solange Sie, die den Wert sichergestellt haben `_Index` ist kleiner als die Größe von den gleichzeitigen Vektor.|  
|[Rückseite](#back)|Überladen. Gibt einen Verweis oder einen `const` -Verweis auf das letzte Element in den gleichzeitigen Vektor. Wenn Sie der gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.|  
|[begin](#begin)|Überladen. Gibt einen Iterator vom Typ `iterator` oder `const_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.|  
|[capacity](#capacity)|Gibt die maximale Größe, die auf die der gleichzeitige Vektor anwachsen kann, ohne zusätzlichen Speicher zu belegen. Diese Methode ist nebenläufigkeitssicher.|  
|[cbegin](#cbegin)|Gibt einen Iterator vom Typ `const_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.|  
|[cend](#cend)|Gibt einen Iterator vom Typ `const_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[clear](#clear)|Löscht alle Elemente in den gleichzeitigen Vektor. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[crbegin](#crbegin)|Gibt einen Iterator vom Typ `const_reverse_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.|  
|[crend](#crend)|Gibt einen Iterator vom Typ `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[empty](#empty)|Testet, ob zum Zeitpunkt der gleichzeitige Vektor leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.|  
|[end](#end)|Überladen. Gibt einen Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[Vorderseite](#front)|Überladen. Gibt einen Verweis oder einen `const` Verweis auf das erste Element in den gleichzeitigen Vektor. Wenn Sie der gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.|  
|[get_allocator](#get_allocator)|Gibt eine Kopie der Zuweisung verwendet, um den gleichzeitigen Vektor zu erstellen. Diese Methode ist nebenläufigkeitssicher.|  
|[grow_by](#grow_by)|Überladen. Vergrößert dieses gleichzeitigen Vektor von `_Delta` Elemente. Diese Methode ist nebenläufigkeitssicher.|  
|[grow_to_at_least](#grow_to_at_least)|Diese gleichzeitigen Vektor wächst, bis sie mindestens verfügt `_N` Elemente. Diese Methode ist nebenläufigkeitssicher.|  
|[max_size](#max_size)|Gibt die maximale Anzahl von Elementen, die der gleichzeitige Vektor aufnehmen kann. Diese Methode ist nebenläufigkeitssicher.|  
|[push_back](#push_back)|Überladen. Fügt das angegebene Element am Ende den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[rbegin](#rbegin)|Überladen. Gibt einen Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.|  
|[rend](#rend)|Überladen. Gibt einen Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[reserve](#reserve)|Reserviert ausreichend Speicherplatz, um den gleichzeitigen Vektor an Größe zunehmen darf `_N` ohne später mehr Speicher reservieren. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[resize](#resize)|Überladen. Ändert die Größe von den gleichzeitigen Vektor auf die angeforderte Größe, löschen oder Hinzufügen von Elementen nach Bedarf. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[shrink_to_fit](#shrink_to_fit)|Komprimiert die interne Darstellung des den gleichzeitigen Vektor Fragmentierung zu verringern und die Speicherverwendung zu optimieren. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[size](#size)|Gibt die Anzahl der Elemente in den gleichzeitigen Vektor zurück. Diese Methode ist nebenläufigkeitssicher.|  
|[swap](#swap)|Vertauscht den Inhalt von zwei gleichzeitige Vektoren. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator[]](#operator_at)|Überladen. Bietet Zugriff auf das Element am angegebenen Index in den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch beim Vergrößern des Vektors, solange Sie haben sichergestellt, dass, die den Wert `_Index` ist kleiner als die Größe von den gleichzeitigen Vektor.|  
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
  
##  <a name="assign"></a> Zuweisen 

 Löscht die Elemente von den gleichzeitigen Vektor und weist ihm entweder `_N` Kopien `_Item`, oder durch den Iteratorbereich angegebenen Werte [ `_Begin`, `_End`). Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```  
  
### <a name="parameters"></a>Parameter  
 `_InputIterator`  
 Der Typ des angegebenen Iterators.  
  
 `_N`  
 Die Anzahl der Elemente, die in den gleichzeitigen Vektor zu kopieren.  
  
 `_Item`  
 Verweis auf einen Wert verwendet, um den gleichzeitigen Vektor zu füllen.  
  
 `_Begin`  
 Ein Iterator zum ersten Element des Quellbereichs.  
  
 `_End`  
 Ein Iterator um eine Position hinter dem letzten Element des Quellbereichs.  
  
### <a name="remarks"></a>Hinweise  
 `assign` ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen.  
  
##  <a name="at"></a> am 

 Bietet Zugriff auf das Element am angegebenen Index in den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch beim wächst des Vektors, solange Sie, die den Wert sichergestellt haben `_Index` ist kleiner als die Größe von den gleichzeitigen Vektor.  
  
```
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Index des Elements, das abgerufen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Element am angegebenen Index.  
  
### <a name="remarks"></a>Hinweise  
 Die Version der Funktion `at` zurückgibt nicht `const` Verweis kann nicht verwendet werden, um von anderen Threads gleichzeitig auf das Element schreiben. Ein anderes Synchronisierungsobjekt sollte zum Synchronisieren des gleichzeitigen Lese- und Schreibvorgänge mit der gleichen Data-Element verwendet werden.  
  
 Löst die Methode `out_of_range` Wenn `_Index` ist größer als oder gleich der Größe von den gleichzeitigen Vektor und `range_error` , wenn der Index für eine fehlerhafte Teil der Vektor ist. Ausführliche Informationen dazu, wie ein Vektor beschädigt werden kann, finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
##  <a name="back"></a> Zurück 

 Gibt einen Verweis oder einen `const` -Verweis auf das letzte Element in den gleichzeitigen Vektor. Wenn Sie der gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.  
  
```
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis oder ein `const` -Verweis auf das letzte Element in den gleichzeitigen Vektor.  
  
##  <a name="begin"></a> Beginnen 

 Gibt einen Iterator vom Typ `iterator` oder `const_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `iterator` oder `const_iterator` am Anfang der gleichzeitigen Vektors.  
  
##  <a name="capacity"></a> Kapazität 

 Gibt die maximale Größe, die auf die der gleichzeitige Vektor anwachsen kann, ohne zusätzlichen Speicher zu belegen. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type capacity() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Größe, auf die der gleichzeitige Vektor anwachsen kann, ohne zusätzlichen Speicher zu belegen.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu C++-Standardbibliothek `vector`ein `concurrent_vector` Objekt nicht vorhandene Elemente verschieben, wenn es mehr Arbeitsspeicher belegt.  
  
##  <a name="cbegin"></a> cbegin 

 Gibt einen Iterator vom Typ `const_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `const_iterator` am Anfang der gleichzeitigen Vektors.  
  
##  <a name="cend"></a> cend 

 Gibt einen Iterator vom Typ `const_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
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
 `clear` ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen. `clear` keine frei internen Arrays. Um interne Arrays freizugeben, rufen Sie die Funktion `shrink_to_fit` nach `clear`.  
  
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
 `M`  
 Der allocator-Typ des Quellvektors.  
  
 `_InputIterator`  
 Der Typ des Eingabeiterators.  
  
 `_Al`  
 Die mit diesem Objekt zu verwendende Zuweisungsklasse.  
  
 `_Vector`  
 Das `concurrent_vector`-Quellobjekt, aus dem Elemente kopiert oder verschoben werden sollen.  
  
 `_N`  
 Die Anfangskapazität des `concurrent_vector`-Objekts.  
  
 `_Item`  
 Der Wert der Elemente im erstellten Objekt.  
  
 `_Begin`  
 Die Position des ersten Elements in dem zu kopierenden Elementbereich.  
  
 `_End`  
 Die Position des ersten Elements nach dem zu kopierenden Elementbereich.  
  
### <a name="remarks"></a>Hinweise  
 Von allen Konstruktoren wird ein `_Al`-Zuweisungsobjekt gespeichert und der Vektor initialisiert.  
  
 Der erste Konstruktor Geben Sie einen leeren ursprünglichen Vektor und gibt explizit an die Allocator-Typ. verwendet werden.  
  
 Die zweiten und dritten Konstruktoren geben eine Kopie des parallel ausgeführten `_Vector`-Vektors an.  
  
 Der vierte Konstruktor gibt eine Verschiebung des gleichzeitigen `_Vector`-Vektors an.  
  
 Der fünfte Konstruktor gibt eine Wiederholung einer angegebenen Anzahl ( `_N`) von Elementen des Standardwerts für die Klasse `T`.  
  
 Der sechste Konstruktor gibt eine Wiederholung von ( `_N`) Elementen des Werts `_Item`.  
  
 Der letzte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte [ `_Begin`, `_End`).  
  
##  <a name="dtor"></a> ~ Concurrent_vector 

 Löscht alle Elemente aus, und zerstört diesen gleichzeitigen Vektor.  
  
```
~concurrent_vector();
```  
  
##  <a name="crbegin"></a> crbegin 

 Gibt einen Iterator vom Typ `const_reverse_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `const_reverse_iterator` am Anfang der gleichzeitigen Vektors.  
  
##  <a name="crend"></a> crend 

 Gibt einen Iterator vom Typ `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor.  
  
##  <a name="empty"></a> leere 

 Testet, ob zum Zeitpunkt der gleichzeitige Vektor leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn zum Zeitpunkt der Vektor leer die Funktion aufgerufen wurde war, `false` andernfalls.  
  
##  <a name="end"></a> Ende 

 Gibt einen Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende der gleichzeitigen Vektor.  
  
##  <a name="front"></a> Vorderseite 

 Gibt einen Verweis oder einen `const` Verweis auf das erste Element in den gleichzeitigen Vektor. Wenn Sie der gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.  
  
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
 Eine Kopie der Zuweisung zum Erstellen der `concurrent_vector` Objekt.  
  
##  <a name="grow_by"></a> grow_by 

 Vergrößert dieses gleichzeitigen Vektor von `_Delta` Elemente. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```  
  
### <a name="parameters"></a>Parameter  
 `_Delta`  
 Die Anzahl von Elementen, auf das Objekt angefügt werden soll.  
  
 `_Item`  
 Der Wert, mit dem neue Elemente zu initialisieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator zum ersten Element angehängt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `_Item` nicht angegeben wird, werden die neuen Elemente werden standardmäßig erstelltes.  
  
##  <a name="grow_to_at_least"></a> grow_to_at_least 

 Diese gleichzeitigen Vektor wächst, bis sie mindestens verfügt `_N` Elemente. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator grow_to_at_least(size_type _N);
```  
  
### <a name="parameters"></a>Parameter  
 `_N`  
 Die neue Mindestgröße für die `concurrent_vector` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der zum Anfang der Sequenz angefügt oder auf das Element an Index verweist `_N` , wenn keine Elemente angefügt wurden.  
  
##  <a name="max_size"></a> max_size 

 Gibt die maximale Anzahl von Elementen, die der gleichzeitige Vektor aufnehmen kann. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Elementen der `concurrent_vector` Objekt aufnehmen kann.  
  
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
 `M`  
 Der allocator-Typ des Quellvektors.  
  
 `_Vector`  
 Das `concurrent_vector`-Quellobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `concurrent_vector`-Objekt.  
  
##  <a name="operator_at"></a> []-Operator 

 Bietet Zugriff auf das Element am angegebenen Index in den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch beim Vergrößern des Vektors, solange Sie haben sichergestellt, dass, die den Wert `_Index` ist kleiner als die Größe von den gleichzeitigen Vektor.  
  
```
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der Index des Elements, das abgerufen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Element am angegebenen Index.  
  
### <a name="remarks"></a>Hinweise  
 Die Version des `operator []` zurückgibt nicht `const` Verweis kann nicht verwendet werden, um von anderen Threads gleichzeitig auf das Element schreiben. Ein anderes Synchronisierungsobjekt sollte zum Synchronisieren des gleichzeitigen Lese- und Schreibvorgänge mit der gleichen Data-Element verwendet werden.  
  
 Keine Überprüfung wird ausgeführt, um sicherzustellen, dass der Grenzen `_Index` ist ein gültiger Index in den gleichzeitigen Vektor.  
  
##  <a name="push_back"></a> push_back 

 Fügt das angegebene Element am Ende den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```  
  
### <a name="parameters"></a>Parameter  
 `_Item`  
 Der anzufügende Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator zum Element angehängt.  
  
##  <a name="rbegin"></a> rbegin 

 Gibt einen Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.  
  
```
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` am Anfang der gleichzeitigen Vektors.  
  
##  <a name="rend"></a> REND 

 Gibt einen Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
```
reverse_iterator rend();

const_reverse_iterator rend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` bis zum Ende der gleichzeitigen Vektor.  
  
##  <a name="reserve"></a> Hostreserven 

 Reserviert ausreichend Speicherplatz, um den gleichzeitigen Vektor an Größe zunehmen darf `_N` ohne später mehr Speicher reservieren. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void reserve(size_type _N);
```  
  
### <a name="parameters"></a>Parameter  
 `_N`  
 Die Anzahl von Elementen, Speicherplatz zu reservieren.  
  
### <a name="remarks"></a>Hinweise  
 `reserve` ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen. Die Kapazität von den gleichzeitigen Vektor nach der Methodenrückgabe möglicherweise größer als der angeforderten Reservierung.  
  
##  <a name="resize"></a> zum Ändern der Größe 

 Ändert die Größe von den gleichzeitigen Vektor auf die angeforderte Größe, löschen oder Hinzufügen von Elementen nach Bedarf. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```  
  
### <a name="parameters"></a>Parameter  
 `_N`  
 Die neue Größe für die Concurrent_vector.  
  
 `val`  
 Der Wert der neuen Elemente, die in den Vektor hinzugefügt wird, wenn die neue Größe die Originalgröße übersteigt. Wenn der Wert ausgelassen wird, werden die neuen Objekte den Standardwert für ihren Typ zugewiesen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Größe des Containers kleiner als die angeforderte Größe ist, werden die Elemente in den Vektor hinzugefügt, bis die angeforderte Größe erreicht. Wenn die Größe des Containers die angeforderte Größe übersteigt, werden die Elemente am Ende des Containers gelöscht, bis der Container die Größe erreicht `_N`. Wenn die tatsächliche Größe des Containers der angeforderten Größe entspricht, wird keine Aktion durchgeführt.  
  
 `resize` ist nicht parallelitätssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen.  
  
##  <a name="shrink_to_fit"></a> shrink_to_fit 

 Komprimiert die interne Darstellung des den gleichzeitigen Vektor Fragmentierung zu verringern und die Speicherverwendung zu optimieren. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void shrink_to_fit();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird intern Arbeitsspeicher Verschiebt Elemente, neu zugewiesen werden alle Iteratoren ungültig. `shrink_to_fit` ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Funktion aufrufen.  
  
##  <a name="size"></a> Größe 

 Gibt die Anzahl der Elemente in den gleichzeitigen Vektor zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in diesem `concurrent_vector` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wird sichergestellt, dass die zurückgegebene Größe enthalten alle Elemente, die durch Aufrufe der Funktion angefügt `push_back`, oder die Vergrößerung der Vorgänge, die vor dem Aufrufen dieser Methode abgeschlossen haben. Allerdings es auch Elemente enthalten, die zugewiesen werden, aber immer noch in Bearbeitung durch gleichzeitige Aufrufe von einer der Methoden Wachstum.  
  
##  <a name="swap"></a> Swap 

 Vertauscht den Inhalt von zwei gleichzeitige Vektoren. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void swap(concurrent_vector& _Vector);
```  
  
### <a name="parameters"></a>Parameter  
 `_Vector`  
 Die `concurrent_vector` Objekt, das Inhalt mit austauschen.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)



