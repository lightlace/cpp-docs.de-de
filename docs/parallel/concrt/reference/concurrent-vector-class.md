---
title: Concurrent_vector-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_vector/Concurrency::concurrent_vector
- concurrent_vector/concurrency::concurrent_vector
dev_langs:
- C++
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: fdc84a03c562a4efa336f62c0cf0a7529c420f95
ms.lasthandoff: 02/24/2017

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
 Der Typ, der das gespeicherte Zuweisungsobjekt darstellt, das Details zur Speicherbelegung und Aufhebung der Speicherbelegung für den gleichzeitigen Vektor kapselt. Dieses Argument ist optional, und der Standardwert ist `allocator<``T``>`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`allocator_type`|Ein Typ, der die zuweisungsklasse für den gleichzeitigen Vektor darstellt.|  
|`const_iterator`|Ein Typ, der einem Iterator mit wahlfreiem Zugriff, können bietet Lesen einer `const` Element in einem gleichzeitigen Vektor.|  
|`const_pointer`|Ein Typ, der ein Zeiger auf ein `const` Element in einem gleichzeitigen Vektor.|  
|`const_reference`|Ein Typ, der einen Verweis auf eine `const` Element in einem gleichzeitigen Vektor zum Lesen und Ausführen von gespeicherten `const` Vorgänge.|  
|`const_reverse_iterator`|Eine Typ, der einem Iterator mit wahlfreiem Zugriff, können bietet gelesen `const` Element im gleichzeitigen Vektor.|  
|`difference_type`|Ein Typ, die den mit Abstand zwischen zwei Elementen in einem gleichzeitigen Vektor bereitstellt.|  
|`iterator`|Ein Typ, die einen Iterator mit zufälligem Zugriff bereitstellt, der jedes Element in einem gleichzeitigen Vektor lesen kann. Änderung eines Elements mit dem Iterator ist nicht parallelitätssicher ist.|  
|`pointer`|Ein Typ, die einen Zeiger auf ein Element in einem gleichzeitigen Vektor bereitstellt.|  
|`reference`|Ein Typ, der einen Verweis auf ein Element in einem gleichzeitigen Vektor bereitstellt.|  
|`reverse_iterator`|Ein Typ, die einen Iterator mit zufälligem Zugriff bereitstellt, der jedes Element in einem reservierten gleichzeitigen Vektor lesen kann. Änderung eines Elements mit dem Iterator ist nicht parallelitätssicher ist.|  
|`size_type`|Ein Typ, der die Anzahl von Elementen in einem gleichzeitigen Vektor angibt.|  
|`value_type`|Ein Typ, der den in einem gleichzeitigen Vektor gespeicherten Datentyp darstellt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Concurrent_vector-Konstruktor](#ctor)|Überladen. Erstellt einen gleichzeitigen Vektor.|  
|[~ Concurrent_vector-Destruktor](#dtor)|Löscht alle Elemente und zerstört diesen gleichzeitigen Vektor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[assign-Methode](#assign)|Überladen. Löscht die Elemente des gleichzeitigen Vektors und weist ihm entweder `_N` Kopien von `_Item`, oder Werte aus dem Iteratorbereich [ `_Begin`, `_End`). Diese Methode ist nicht nebenläufigkeitssicher.|  
|[AT-Methode](#at)|Überladen. Bietet Zugriff auf das Element am angegebenen Index im gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch während des Wachstums des Vektors, solange Sie, die den Wert sichergestellt haben `_Index` ist kleiner als die Anzahl der gleichzeitigen Vektor.|  
|[Back-Methode](#back)|Überladen. Gibt einen Verweis oder einen `const` -Verweis auf das letzte Element im gleichzeitigen Vektor. Wenn Sie der gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.|  
|[Begin-Methode](#begin)|Überladen. Gibt einen Iterator vom Typ `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[Kapazität-Methode](#capacity)|Gibt die maximale Größe, auf die der gleichzeitige Vektor anwachsen kann, ohne zusätzlichen Speicher zu belegen. Diese Methode ist nebenläufigkeitssicher.|  
|[Cbegin-Methode](#cbegin)|Gibt einen Iterator vom Typ `const_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.|  
|[Cend-Methode](#cend)|Gibt einen Iterator vom Typ `const_iterator` bis zum Ende des gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[Clear-Methode](#clear)|Löscht alle Elemente im gleichzeitigen Vektor. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[Crbegin-Methode](#crbegin)|Gibt einen Iterator vom Typ `const_reverse_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.|  
|[Crend-Methode](#crend)|Gibt einen Iterator vom Typ `const_reverse_iterator` bis zum Ende des gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[Empty-Methode](#empty)|Testet, ob zum Zeitpunkt der gleichzeitige Vektor leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.|  
|[End-Methode](#end)|Überladen. Gibt einen Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende des gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[Front-Methode](#front)|Überladen. Gibt einen Verweis oder einen `const` Verweis auf das erste Element im gleichzeitigen Vektor. Wenn Sie der gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.|  
|[Get_allocator-Methode](#get_allocator)|Gibt eine Kopie der Zuweisung verwendet, um den gleichzeitigen Vektor zu erstellen. Diese Methode ist nebenläufigkeitssicher.|  
|[Grow_by-Methode](#grow_by)|Überladen. Vergrößert diesen gleichzeitigen Vektor von `_Delta` Elemente. Diese Methode ist nebenläufigkeitssicher.|  
|[Grow_to_at_least-Methode](#grow_to_at_least)|Vergrößert diesen gleichzeitigen Vektor, bis mindestens `_N` Elemente. Diese Methode ist nebenläufigkeitssicher.|  
|[Max_size-Methode](#max_size)|Gibt die maximale Anzahl von Elementen, die der gleichzeitige Vektor enthalten kann. Diese Methode ist nebenläufigkeitssicher.|  
|[Push_back-Methode](#push_back)|Überladen. Fügt das angegebene Element am Ende den gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[Rbegin-Methode](#rbegin)|Überladen. Gibt einen Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` an den Anfang der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[REND-Methode](#rend)|Überladen. Gibt einen Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` bis zum Ende des gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.|  
|[Reserve-Methode](#reserve)|Reserviert ausreichend Speicherplatz, um den gleichzeitigen Vektor auf Größe anwachsen `_N` ohne später mehr Speicher reservieren. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[Resize-Methode](#resize)|Überladen. Ändert die Größe des gleichzeitigen Vektor auf die angeforderte Größe, löschen oder Hinzufügen von Elementen nach Bedarf. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[Shrink_to_fit-Methode](#shrink_to_fit)|Komprimiert die interne Darstellung des gleichzeitigen Vektors Fragmentierung reduzieren und die Speicherverwendung zu optimieren. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[Size-Methode](#size)|Gibt die Anzahl der Elemente in den gleichzeitigen Vektor zurück. Diese Methode ist nebenläufigkeitssicher.|  
|[Swap-Methode](#swap)|Vertauscht den Inhalt zweier gleichzeitiger Vektoren. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator []-Operator](#operator_at)|Überladen. Bietet Zugriff auf das Element am angegebenen Index im gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch während des Wachstums des Vektors, solange Sie die Stellen, die des Werts `_Index` ist kleiner als die Anzahl der gleichzeitigen Vektor.|  
|[Operator =-Operator](#operator_eq)|Überladen. Weist den Inhalt eines anderen `concurrent_vector`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## <a name="remarks"></a>Hinweise  
 Ausführliche Informationen zu den `concurrent_vector` Klasse, finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concurrent_vector.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameassigna-assign"></a><a name="assign"></a>Zuweisen 

 Löscht die Elemente des gleichzeitigen Vektors und weist ihm entweder `_N` Kopien von `_Item`, oder Werte aus dem Iteratorbereich [ `_Begin`, `_End`). Diese Methode ist nicht nebenläufigkeitssicher.  
  
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
 Verweis auf einen Wert verwendet, um den gleichzeitigen Vektor auszufüllen.  
  
 `_Begin`  
 Ein Iterator zum ersten Element des Quellbereichs.  
  
 `_End`  
 Ein Iterator hinter dem letzten Element des Quellbereichs.  
  
### <a name="remarks"></a>Hinweise  
 `assign`ist nicht parallelitätssicher ist. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen.  
  
##  <a name="a-nameata-at"></a><a name="at"></a>am 

 Bietet Zugriff auf das Element am angegebenen Index im gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch während des Wachstums des Vektors, solange Sie, die den Wert sichergestellt haben `_Index` ist kleiner als die Anzahl der gleichzeitigen Vektor.  
  
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
 Die Version der Funktion `at` zurückgibt nicht `const` Verweis kann nicht verwendet werden, um von verschiedenen Threads gleichzeitig auf das Element schreiben. Ein anderes Synchronisierungsobjekt sollte zum Synchronisieren des gleichzeitigen Lese- und Schreibvorgänge für das gleiche Datenelement verwendet werden.  
  
 Löst die Methode `out_of_range` Wenn `_Index` ist größer als oder gleich der Größe des gleichzeitigen Vektors ist, und `range_error` ist der Index einem Bruchteil des Vektors. Ausführliche Informationen dazu, wie ein Vektor beschädigt werden kann, finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
##  <a name="a-namebacka-back"></a><a name="back"></a>Zurück 

 Gibt einen Verweis oder einen `const` -Verweis auf das letzte Element im gleichzeitigen Vektor. Wenn Sie der gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.  
  
```
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis oder ein `const` -Verweis auf das letzte Element im gleichzeitigen Vektor.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>beginnen 

 Gibt einen Iterator vom Typ `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `iterator` oder `const_iterator` an den Anfang der gleichzeitigen Vektor.  
  
##  <a name="a-namecapacitya-capacity"></a><a name="capacity"></a>Kapazität 

 Gibt die maximale Größe, auf die der gleichzeitige Vektor anwachsen kann, ohne zusätzlichen Speicher zu belegen. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type capacity() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Größe, auf die der gleichzeitige Vektor anwachsen kann, ohne zusätzlichen Speicher zu belegen.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu C++-Standardbibliothek `vector`, ein `concurrent_vector` Objekt nicht vorhandene Elemente verschieben, wenn es mehr Speicher belegt.  
  
##  <a name="a-namecbegina-cbegin"></a><a name="cbegin"></a>cbegin 

 Gibt einen Iterator vom Typ `const_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `const_iterator` am Anfang der gleichzeitigen Vektors.  
  
##  <a name="a-namecenda-cend"></a><a name="cend"></a>cend 

 Gibt einen Iterator vom Typ `const_iterator` bis zum Ende des gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `const_iterator` bis zum Ende des gleichzeitigen Vektor.  
  
##  <a name="a-namecleara-clear"></a><a name="clear"></a>Deaktivieren 

 Löscht alle Elemente im gleichzeitigen Vektor. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void clear();
```  
  
### <a name="remarks"></a>Hinweise  
 `clear`ist nicht parallelitätssicher ist. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen. `clear`gibt keine internen Arrays frei. Um interne Arrays freizugeben, rufen Sie die Funktion `shrink_to_fit` nach `clear`.  
  
##  <a name="a-namectora-concurrentvector"></a><a name="ctor"></a>concurrent_vector 

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
  
 Der erste Konstruktor Geben Sie einen leeren ursprünglichen Vektor und gibt den Belegungsfunktionstyp explizit an. verwendet werden.  
  
 Die zweiten und dritten Konstruktoren geben eine Kopie des parallel ausgeführten `_Vector`-Vektors an.  
  
 Der vierte Konstruktor gibt eine Verschiebung des gleichzeitigen `_Vector`-Vektors an.  
  
 Der fünfte Konstruktor gibt eine Wiederholung einer angegebenen Anzahl ( `_N`) von Elementen des Standardwerts für die Klasse `T`.  
  
 Der sechste Konstruktor gibt eine Wiederholung der ( `_N`) Elemente des Werts `_Item`.  
  
 Der letzte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte an [ `_Begin`, `_End`).  
  
##  <a name="a-namedtora-concurrentvector"></a><a name="dtor"></a>~ Concurrent_vector 

 Löscht alle Elemente und zerstört diesen gleichzeitigen Vektor.  
  
```
~concurrent_vector();
```  
  
##  <a name="a-namecrbegina-crbegin"></a><a name="crbegin"></a>crbegin 

 Gibt einen Iterator vom Typ `const_reverse_iterator` am Anfang der gleichzeitigen Vektors. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `const_reverse_iterator` am Anfang der gleichzeitigen Vektors.  
  
##  <a name="a-namecrenda-crend"></a><a name="crend"></a>crend 

 Gibt einen Iterator vom Typ `const_reverse_iterator` bis zum Ende des gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `const_reverse_iterator` bis zum Ende des gleichzeitigen Vektor.  
  
##  <a name="a-nameemptya-empty"></a><a name="empty"></a>leere 

 Testet, ob zum Zeitpunkt der gleichzeitige Vektor leer ist, wird diese Methode aufgerufen. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Vektor im Moment leer die Funktion aufgerufen wurde war, `false` andernfalls.  
  
##  <a name="a-nameenda-end"></a><a name="end"></a>Ende 

 Gibt einen Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende des gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `iterator` oder `const_iterator` bis zum Ende des gleichzeitigen Vektor.  
  
##  <a name="a-namefronta-front"></a><a name="front"></a>Vorderseite 

 Gibt einen Verweis oder einen `const` Verweis auf das erste Element im gleichzeitigen Vektor. Wenn Sie der gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert. Diese Methode ist nebenläufigkeitssicher.  
  
```
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis oder ein `const` Verweis auf das erste Element im gleichzeitigen Vektor.  
  
##  <a name="a-namegetallocatora-getallocator"></a><a name="get_allocator"></a>get_allocator 

 Gibt eine Kopie der Zuweisung verwendet, um den gleichzeitigen Vektor zu erstellen. Diese Methode ist nebenläufigkeitssicher.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zuweisung erstellt eine Kopie der `concurrent_vector` Objekt.  
  
##  <a name="a-namegrowbya-growby"></a><a name="grow_by"></a>grow_by 

 Vergrößert diesen gleichzeitigen Vektor von `_Delta` Elemente. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```  
  
### <a name="parameters"></a>Parameter  
 `_Delta`  
 Die Anzahl der Elemente, die an das Objekt angefügt werden soll.  
  
 `_Item`  
 Der Wert, der die neuen Elemente mit initialisiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator zum ersten Element angehängt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `_Item` nicht angegeben wird, werden die neuen Elemente werden Standardeinstellungen erstellt.  
  
##  <a name="a-namegrowtoatleasta-growtoatleast"></a><a name="grow_to_at_least"></a>grow_to_at_least 

 Vergrößert diesen gleichzeitigen Vektor, bis mindestens `_N` Elemente. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator grow_to_at_least(size_type _N);
```  
  
### <a name="parameters"></a>Parameter  
 `_N`  
 Die neue minimale Größe für das `concurrent_vector` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der an den Anfang der angefügten Sequenz bzw. das Element am Index NULL `_N` , wenn keine Elemente angefügt wurden.  
  
##  <a name="a-namemaxsizea-maxsize"></a><a name="max_size"></a>max_size 

 Gibt die maximale Anzahl von Elementen, die der gleichzeitige Vektor enthalten kann. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl der Elemente der `concurrent_vector` -Objekt enthalten kann.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>Operator = 

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
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>Operator] 

 Bietet Zugriff auf das Element am angegebenen Index im gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher für Lesevorgänge und auch während des Wachstums des Vektors, solange Sie die Stellen, die des Werts `_Index` ist kleiner als die Anzahl der gleichzeitigen Vektor.  
  
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
 Die Version des `operator []` zurückgibt nicht `const` Verweis kann nicht verwendet werden, um von verschiedenen Threads gleichzeitig auf das Element schreiben. Ein anderes Synchronisierungsobjekt sollte zum Synchronisieren des gleichzeitigen Lese- und Schreibvorgänge für das gleiche Datenelement verwendet werden.  
  
 Keine Überprüfung ausgeführt, um sicherzustellen, dass der Grenzen `_Index` ist ein gültiger Index im gleichzeitigen Vektor.  
  
##  <a name="a-namepushbacka-pushback"></a><a name="push_back"></a>push_back 

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
  
##  <a name="a-namerbegina-rbegin"></a><a name="rbegin"></a>rbegin 

 Gibt einen Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` an den Anfang der gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
```
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` an den Anfang der gleichzeitigen Vektor.  
  
##  <a name="a-namerenda-rend"></a><a name="rend"></a>REND 

 Gibt einen Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` bis zum Ende des gleichzeitigen Vektor. Diese Methode ist nebenläufigkeitssicher.  
  
```
reverse_iterator rend();

const_reverse_iterator rend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` bis zum Ende des gleichzeitigen Vektor.  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>Reservieren 

 Reserviert ausreichend Speicherplatz, um den gleichzeitigen Vektor auf Größe anwachsen `_N` ohne später mehr Speicher reservieren. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void reserve(size_type _N);
```  
  
### <a name="parameters"></a>Parameter  
 `_N`  
 Die Anzahl von Elementen, Speicherplatz zu reservieren.  
  
### <a name="remarks"></a>Hinweise  
 `reserve`ist nicht parallelitätssicher ist. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen. Die Kapazität des gleichzeitigen Vektors nach der Methodenrückgabe möglicherweise größer als die angeforderte Reservierung.  
  
##  <a name="a-nameresizea-resize"></a><a name="resize"></a>Ändern der Größe 

 Ändert die Größe des gleichzeitigen Vektor auf die angeforderte Größe, löschen oder Hinzufügen von Elementen nach Bedarf. Diese Methode ist nicht nebenläufigkeitssicher.  
  
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
 Der Wert der neuen Elemente, die in den Vektor hinzugefügt wird, wenn die neue Größe die ursprüngliche Größe überschreitet. Wenn der Wert weggelassen wird, werden die neuen Objekte den Standardwert für ihren Typ zugewiesen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Größe des Containers kleiner als die angeforderte Größe ist, werden dem Vektor Elemente hinzugefügt, bis die angeforderte Größe erreicht. Wenn die Größe des Containers größer als die angeforderte Größe ist, werden die Elemente am Ende des Containers gelöscht, bis der Container die Größe erreicht `_N`. Wenn die tatsächliche Größe des Containers der angeforderten Größe entspricht, wird keine Aktion durchgeführt.  
  
 `resize`ist nicht parallelitätssicher. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Methode aufrufen.  
  
##  <a name="a-nameshrinktofita-shrinktofit"></a><a name="shrink_to_fit"></a>shrink_to_fit 

 Komprimiert die interne Darstellung des gleichzeitigen Vektors Fragmentierung reduzieren und die Speicherverwendung zu optimieren. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void shrink_to_fit();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird intern Speicher verschiebt Elemente, erneut reserviert werden alle Iteratoren ungültig. `shrink_to_fit`ist nicht parallelitätssicher ist. Sie müssen sicherstellen, dass keine anderen Threads Methoden für den gleichzeitigen Vektor aufrufen, wenn Sie diese Funktion aufrufen.  
  
##  <a name="a-namesizea-size"></a><a name="size"></a>Größe 

 Gibt die Anzahl der Elemente in den gleichzeitigen Vektor zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in diesem `concurrent_vector` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Größe ist garantiert alle Elemente, die durch Aufrufe der Funktion angefügt sind `push_back`, oder vergrößern Sie Vorgänge, die vor dem Aufrufen dieser Methode abgeschlossen haben. Allerdings es auch Elemente enthalten, die zugeordnet sind aber noch von gleichzeitigen Aufrufen einer der Methoden Wachstum.  
  
##  <a name="a-nameswapa-swap"></a><a name="swap"></a>Swap 

 Vertauscht den Inhalt zweier gleichzeitiger Vektoren. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void swap(concurrent_vector& _Vector);
```  
  
### <a name="parameters"></a>Parameter  
 `_Vector`  
 Die `concurrent_vector` -Objekt, das Inhalt getauscht.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)




