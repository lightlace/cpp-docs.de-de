---
title: Concurrent_unordered_multiset-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_unordered_multiset
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::concurrent_unordered_multiset
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::hash_function
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::insert
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::key_eq
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::swap
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_multiset::unsafe_erase
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_multiset class
ms.assetid: 219d7d67-1ff0-45f4-9400-e9cc272991a4
caps.latest.revision: 12
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
ms.openlocfilehash: 06c098d2ad38fbf4a7664f9046ac4f1e12b1044d
ms.lasthandoff: 03/17/2017

---
# <a name="concurrentunorderedmultiset-class"></a>concurrent_unordered_multiset-Klasse
Die `concurrent_unordered_multiset` Klasse ist ein parallelitätssicher Container, der steuert, eine variabler Länge Sequenz von Elementen vom Typ K. Die Sequenz wird dargestellt, auf eine Weise, die es parallelitätssichere ermöglicht anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe sind.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename K,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>
>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>> class concurrent_unordered_multiset : public details::_Concurrent_hash<details::_Concurrent_unordered_set_traits<K,
    details::_Hash_compare<K,
 _Hasher,
    key_equality>,
 _Allocator_type,
    true>>;
```   
  
#### <a name="parameters"></a>Parameter  
 `K`  
 Der Schlüsseltyp.  
  
 `_Hasher`  
 Der Hashfunktionsobjekttyp. Dieses Argument ist optional, und der Standardwert ist `std::hash<``K``>`.  
  
 `key_equality`  
 Der Gleichheitsvergleich-Funktionsobjekttyp. Dieses Argument ist optional, und der Standardwert ist `std::equal_to<``K``>`.  
  
 `_Allocator_type`  
 Der Typ, der das gespeicherte Zuweisungsobjekt darstellt, das Details zur Speicherbelegung und Aufhebung der Speicherbelegung für den gleichzeitigen Vektor kapselt. Dieses Argument ist optional, und der Standardwert ist `std::allocator<``K``>`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`allocator_type`|Der Typ einer Zuweisung für die Speicherverwaltung.|  
|`const_iterator`|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|`const_local_iterator`|Der Typ eines konstanten Bucketiterators für die gesteuerte Sequenz.|  
|`const_pointer`|Der Typ eines konstanten Zeigers auf ein Element.|  
|`const_reference`|Der Typ eines konstanten Verweises auf ein Element.|  
|`difference_type`|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|`hasher`|Der Typ der Hashfunktion.|  
|`iterator`|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|`key_equal`|Der Typ der Vergleichsfunktion.|  
|`key_type`|Der Typ eines Sortierschlüssels.|  
|`local_iterator`|Der Typ eines Bucketiterators für die gesteuerte Sequenz.|  
|`pointer`|Der Typ eines Zeigers auf ein Element.|  
|`reference`|Der Typ eines Verweises auf ein Element.|  
|`size_type`|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|`value_type`|Der Typ eines Elements.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[concurrent_unordered_multiset](#ctor)|Überladen. Erstellt eine gleichzeitige ungeordnete Multimenge.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[hash_function](#hash_function)|Gibt das gespeicherte Hashfunktionsobjekt zurück.|  
|[insert](#insert)|Überladen. Fügt dem `concurrent_unordered_multiset`-Objekt Elemente hinzu.|  
|[key_eq](#key_eq)|Das gespeicherte Gleichheitsvergleichsfunktionsobjekt.|  
|[swap](#swap)|Vertauscht den Inhalt von zwei `concurrent_unordered_multiset`-Objekten. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[unsafe_erase](#unsafe_erase)|Überladen. Entfernt Elemente aus der `concurrent_unordered_multiset` an angegebenen Positionen. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator=](#operator_eq)|Überladen. Weist den Inhalt eines anderen `concurrent_unordered_multiset`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## <a name="remarks"></a>Hinweise  
 Ausführliche Informationen zu den `concurrent_unordered_multiset` Klasse, finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_multiset`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concurrent_unordered_set.h  
  
 **Namespace:** Parallelität  
  
##  <a name="begin"></a>beginnen 

 Gibt einen Iterator, der auf das erste Element im gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator auf das erste Element im gleichzeitigen Container.  
  
##  <a name="cbegin"></a>cbegin 

 Gibt einen const-Iterator auf das erste Element im gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein const-Iterator auf das erste Element im gleichzeitigen Container.  
  
##  <a name="cend"></a>cend 

 Gibt einen Konstanten Iterator, der auf den Speicherort adressiert, das letzte Element im gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein const-Iterator für den Speicherort adressiert, das letzte Element im gleichzeitigen Container.  
  
##  <a name="clear"></a>Deaktivieren 

 Löscht alle Elemente im gleichzeitigen Container. Diese Funktion ist nicht nebenläufigkeitssicher.  
  
```
void clear();
```  
  
##  <a name="ctor"></a>concurrent_unordered_multiset 

 Erstellt eine gleichzeitige ungeordnete Multimenge.  
  
```
explicit concurrent_unordered_multiset(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multiset(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_multiset(_Iterator first,
    _Iterator last,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multiset(
    const concurrent_unordered_multiset& _Uset);

concurrent_unordered_multiset(
    const concurrent_unordered_multiset& _Uset,
    const allocator_type& _Allocator);

concurrent_unordered_multiset(
    concurrent_unordered_multiset&& _Uset);
```  
  
### <a name="parameters"></a>Parameter  
 `_Iterator`  
 Der Typ des Eingabeiterators.  
  
 `_Number_of_buckets`  
 Die anfängliche Anzahl von Buckets für diese ungeordnete Multimenge.  
  
 `_Hasher`  
 Die Hashfunktion für diese ungeordnete Multimenge.  
  
 `key_equality`  
 Die Gleichheit Vergleichsfunktion für diese ungeordnete Multimenge.  
  
 `_Allocator`  
 Die Zuweisung für diese ungeordnete Multimenge.  
  
 `first`  
 `last`  
 `_Uset`  
 Die Quelle `concurrent_unordered_multiset` Objekt Elemente verschoben.  
  
### <a name="remarks"></a>Hinweise  
 Alle Konstruktoren speichern ein Zuweisungsobjekt `_Allocator` und initialisieren Sie die ungeordnete Multimenge.  
  
 Der erste Konstruktor gibt eine leere ursprüngliche Multimenge und explizit angibt, für die Anzahl der Buckets, Hash-Funktion, die Gleichheitsfunktion und der Zuweisung verwendet werden sollen.  
  
 Der zweite Konstruktor gibt eine Zuweisung für das ungeordnete Multimenge.  
  
 Der dritte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte an [ `_Begin`, `_End`).  
  
 Die vierten und fünften Konstruktoren geben eine Kopie der gleichzeitige ungeordnete Multimenge `_Uset`.  
  
 Der letzte Konstruktor gibt eine Verschiebung der gleichzeitige ungeordnete Multimenge `_Uset`.  
  
##  <a name="count"></a>Anzahl 

 Zählt die Anzahl der Elemente, die einem angegebenen Schlüssel entsprechen. Diese Funktion ist nebenläufigkeitssicher.  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der zu suchende Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von versuchen, wie oft der Schlüssel im Container angezeigt wird.  
  
##  <a name="empty"></a>leere 

 Testet, ob keine Elemente vorhanden sind. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die parallele Container leer ist, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Bei gleichzeitiger Einfüge-davon, ob die parallele Container leer ist das kann unmittelbar nach dem Aufrufen dieser Funktion vor dem Lesen des Rückgabewerts ist sogar ändern.  
  
##  <a name="end"></a>Ende 

 Gibt einen Iterator, der auf den Speicherort adressiert, das letzte Element im gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator für den Speicherort adressiert, das letzte Element im gleichzeitigen Container.  
  
##  <a name="equal_range"></a>equal_range 

 Sucht nach einem Bereich, der einem angegebenen Schlüssel entspricht. Diese Funktion ist nebenläufigkeitssicher.  
  
```
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der Schlüssel der zu suchende Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Paar](http://msdn.microsoft.com/en-us/32e72d66-3020-4cb9-92c3-f7a5fa7998ff) , in dem das erste Element ist ein Iterator zum Anfang und das zweite Element ist ein Iterator das Ende des Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Es ist möglich für gleichzeitige INSERT-Vorgänge, die dazu führen, dass zusätzliche Schlüssel nach der Begin-Iterator und vor den End-Iterator eingefügt werden.  
  
##  <a name="find"></a>Suchen 

 Sucht ein Element, das einem angegebenen Schlüssel entspricht. Diese Funktion ist nebenläufigkeitssicher.  
  
```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der Schlüssel der zu suchende Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf den Speicherort der das erste Element, das den angegebenen Schlüssel zugeordnet oder der Iterator `end()` Wenn kein solches Element vorhanden ist.  
  
##  <a name="get_allocator"></a>get_allocator 

 Gibt das gespeicherte Zuweisungsobjekt für diesen gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das gespeicherte Zuweisungsobjekt für diesen gleichzeitigen Container.  
  
##  <a name="hash_function"></a>hash_function 

 Gibt das gespeicherte Hashfunktionsobjekt zurück.  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das gespeicherte hashfunktionsobjekt.  
  
##  <a name="insert"></a>Einfügen 

 Fügt dem `concurrent_unordered_multiset`-Objekt Elemente hinzu.  
  
```
iterator insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
iterator insert(
    V&& value);

template<class V>
typename std::enable_if<!std::is_same<const_iterator,
    typename std::remove_reference<V>::type>::value,
    iterator>::type insert(
    const_iterator _Where,
    V&& value);
```  
  
### <a name="parameters"></a>Parameter  
 `_Iterator`  
 Der iteratortyp für die Einfügung verwendet.  
  
 `V`  
 Der Typ, der der Wert eingefügt werden soll.  
  
 `value`  
 Der Wert eingefügt werden soll.  
  
 `_Where`  
 Die Startposition für eine Einfügemarke zu suchen.  
  
 `first`  
 Der Anfang des Bereichs, der eingefügt werden soll.  
  
 `last`  
 Das Ende des Bereichs, der eingefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf die Einfügeposition.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion fügt das Element `value` in der kontrollierten Sequenz, dann gibt den Iterator, der das eingefügte Element festlegt.  
  
 Die zweite Memberfunktion gibt einfügen ( `value`), wobei `_Where` als Ausgangspunkt in der kontrollierten Sequenz an der Einfügemarke zu suchen.  
  
 Die dritte Memberfunktion fügt die Sequenz von Elementwerten aus dem Bereich [ `first`, `last`).  
  
 Die letzten beiden Memberfunktionen Verhalten sich wie die ersten beiden, außer dass `value` wird zum Erstellen des eingefügten Wert.  
  
##  <a name="key_eq"></a>key_eq 

 Das gespeicherte Gleichheitsvergleichsfunktionsobjekt.  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das gespeicherte Gleichheitsvergleichsfunktionsobjekt.  
  
##  <a name="load_factor"></a>load_factor 

 Berechnet, und gibt den aktuellen Lastfaktor des Containers. Der Ladefaktor ist die Anzahl der Elemente im Container dividiert durch die Anzahl der Buckets.  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Ladefaktor für den Container.  
  
##  <a name="max_load_factor"></a>max_load_factor 

 Ruft ab oder legt den Höchstlastfaktor des Containers. Die Höchstlastfaktor liegt die größte Anzahl von Elementen in jeder Bucket sein kann, bevor der Container seiner internen Tabelle wächst.  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>Parameter  
 `_Newmax`  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Memberfunktion gibt den gespeicherten maximalen Lastfaktor zurück. Die zweite Memberfunktion gibt keinen Wert zurück, aber löst ein [Out_of_range](../../../standard-library/out-of-range-class.md) -Ausnahme aus, wenn Sie der angegebenen Lastfaktor ungültig ist...  
  
##  <a name="max_size"></a>max_size 

 Gibt die maximale Größe des gleichzeitigen Container durch die Zuweisung bestimmt. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Elementen, die in diesen gleichzeitigen Container eingefügt werden können.  
  
### <a name="remarks"></a>Hinweise  
 Diese Obergrenze Wert tatsächlich ist möglicherweise größer, was der Container tatsächlich enthalten kann.  
  
##  <a name="operator_eq"></a>Operator = 

 Weist den Inhalt eines anderen `concurrent_unordered_multiset`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
concurrent_unordered_multiset& operator= (const concurrent_unordered_multiset& _Uset);

concurrent_unordered_multiset& operator= (concurrent_unordered_multiset&& _Uset);
```  
  
### <a name="parameters"></a>Parameter  
 `_Uset`  
 Das `concurrent_unordered_multiset`-Quellobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `concurrent_unordered_multiset`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Löschen der vorhandenen Elemente in eine gleichzeitige ungeordnete Multimenge `operator=` kopiert oder verschiebt den Inhalt des `_Uset` in der gleichzeitige ungeordnete Multimenge.  
  
##  <a name="rehash"></a>Rehash 

 Erstellt die Hashtabelle neu.  
  
```
void rehash(size_type _Buckets);
```  
  
### <a name="parameters"></a>Parameter  
 `_Buckets`  
 Die gewünschte Anzahl von Buckets.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion ändert die Anzahl der Buckets in mindestens `_Buckets` und erstellt ggf. die Hashtabelle neu. Die Anzahl der Buckets muss eine Potenz von 2 sein. Wenn keine Potenz von 2, wird es auf die nächste größte Potenz von 2 aufgerundet.  
  
 Löst ein [Out_of_range](../../../standard-library/out-of-range-class.md) -Ausnahme aus, wenn die Anzahl der Buckets ungültig ist (0 oder größer als die maximale Anzahl von Buckets).  
  
##  <a name="size"></a>Größe 

 Gibt die Anzahl der Elemente in diesen gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Container.  
  
### <a name="remarks"></a>Hinweise  
 Bei gleichzeitiger einfügt kann die Anzahl der Elemente in dem parallele Container unmittelbar nach dem Aufrufen dieser Funktion vor dem Lesen des Rückgabewerts ist sogar ändern.  
  
##  <a name="swap"></a>Swap 

 Vertauscht den Inhalt von zwei `concurrent_unordered_multiset`-Objekten. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void swap(concurrent_unordered_multiset& _Uset);
```  
  
### <a name="parameters"></a>Parameter  
 `_Uset`  
 Das `concurrent_unordered_multiset` Objekt zum austauschen.  
  
##  <a name="unsafe_begin"></a>unsafe_begin 

 Gibt einen Iterator zurück, auf das erste Element in diesem Container für einen bestimmten Bucket.  
  
```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Bucket`  
 Der Bucket-Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf den Anfang des Buckets zeigt.  
  
##  <a name="unsafe_bucket"></a>unsafe_bucket 

 Gibt den Bucket-Index, den ein bestimmten Schlüssel in diesem Container zugeordnet ist.  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der Elementschlüssel gesucht wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bucket-Index für den Schlüssel in diesem Container.  
  
##  <a name="unsafe_bucket_count"></a>unsafe_bucket_count 

 Gibt die aktuelle Anzahl der Buckets in diesem Container zurück.  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Anzahl der Buckets in diesem Container.  
  
##  <a name="unsafe_bucket_size"></a>unsafe_bucket_size 

 Gibt die Anzahl der Elemente in einem bestimmten Bucket dieses Containers zurück.  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>Parameter  
 `_Bucket`  
 Der Bucket zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Anzahl der Buckets in diesem Container.  
  
##  <a name="unsafe_cbegin"></a>unsafe_cbegin 

 Gibt einen Iterator zurück, auf das erste Element in diesem Container für einen bestimmten Bucket.  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Bucket`  
 Der Bucket-Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf den Anfang des Buckets zeigt.  
  
##  <a name="unsafe_cend"></a>unsafe_cend 

 Gibt einen Iterator zurück, um den Speicherort adressiert, das letzte Element in einem bestimmten Bucket.  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Bucket`  
 Der Bucket-Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf den Anfang des Buckets zeigt.  
  
##  <a name="unsafe_end"></a>unsafe_end 

 Gibt einen Iterator zurück, auf das letzte Element in diesem Container für einen bestimmten Bucket.  
  
```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Bucket`  
 Der Bucket-Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf das Ende des Buckets.  
  
##  <a name="unsafe_erase"></a>unsafe_erase 

 Entfernt Elemente aus der `concurrent_unordered_multiset` an angegebenen Positionen. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
iterator unsafe_erase(
    const_iterator _Where);

iterator unsafe_erase(
    const_iterator first,
    const_iterator last);

size_type unsafe_erase(
    const key_type& KVal);
```  
  
### <a name="parameters"></a>Parameter  
 `_Where`  
 Die Position des Iterators, an der gelöscht werden soll.  
  
 `first`  
 `last`  
 `KVal`  
 Der Schlüsselwert, der gelöscht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die ersten beiden Memberfunktionen geben einen Iterator, der das erste Element verbleibt, nachdem alle Elemente entfernt wurden, zurück oder [End](#end)(), wenn kein solches Element vorhanden ist. Die dritte Memberfunktion gibt die Anzahl von Elementen zurück, die sie entfernt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion entfernt das Element, auf das durch `_Where` gezeigt wird. Die zweite Memberfunktion entfernt die Elemente im Bereich [ `_Begin`, `_End`).  
  
 Die dritte Memberfunktion entfernt die Elemente im Bereich von [Equal_range](#equal_range)(KVal).  
  
##  <a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count 

 Gibt die maximale Anzahl der Buckets in diesem Container zurück.  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl der Buckets in diesem Container.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)




