---
title: Concurrent_unordered_map-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::at
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::hash_function
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::insert
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::key_eq
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::swap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::unsafe_erase
dev_langs: C++
helpviewer_keywords: concurrent_unordered_map class
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 29eae25b01dcb3b76a6c3c13a8675b92048b2d22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="concurrentunorderedmap-class"></a>concurrent_unordered_map-Klasse
Die `concurrent_unordered_map`- Klasse ist ein parallelitätssicherer Container, mit dem eine Folge von Elementen variierender Länge des Typs `std::pair<const K, _Element_type>` gesteuert wird. Die Sequenz wird so dargestellt, dass parallelitätssichere Vorgänge für Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe ermöglicht werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename K,
    typename _Element_type,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<std::pair<const K,
    _Element_type>>
>,
 typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<std::pair<const K,
    _Element_type>>> class concurrent_unordered_map : public details::_Concurrent_hash<details::_Concurrent_unordered_map_traits<K,
    _Element_type,
 details::_Hash_compare<K,
    _Hasher,
 key_equality>,
    _Allocator_type,
 false>>;
```  
  
#### <a name="parameters"></a>Parameter  
 `K`  
 Der Schlüsseltyp.  
  
 `_Element_type`  
 Der zugeordnete Typ.  
  
 `_Hasher`  
 Der Hashfunktionsobjekttyp. Dieses Argument ist optional, und der Standardwert ist `std::hash<K>`.  
  
 `key_equality`  
 Der Gleichheitsvergleich-Funktionsobjekttyp. Dieses Argument ist optional, und der Standardwert ist `std::equal_to<K>`.  
  
 `_Allocator_type`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und zur Freigabe des Arbeitsspeichers für die gleichzeitige ungeordnete Zuordnung kapselt. Dieses Argument ist optional, und der Standardwert ist `std::allocator<std::pair<K`, `_Element_type>>`.  
  
## <a name="members"></a>Member  
  
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
|`mapped_type`|Der Typ eines zugeordneten Werts, der jedem Schlüssel zugeordnet ist.|  
|`pointer`|Der Typ eines Zeigers auf ein Element.|  
|`reference`|Der Typ eines Verweises auf ein Element.|  
|`size_type`|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|`value_type`|Der Typ eines Elements.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[concurrent_unordered_map](#ctor)|Überladen. Erstellt eine parallele ungeordneten Zuordnung.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[at](#at)|Überladen. Sucht ein Element in der `concurrent_unordered_map` mit einem angegebenen Schlüsselwert. Diese Methode ist nebenläufigkeitssicher.|  
|[hash_function](#hash_function)|Ruft das gespeicherte Hashfunktionsobjekt ab.|  
|[insert](#insert)|Überladen. Fügt dem `concurrent_unordered_map`-Objekt Elemente hinzu.|  
|[key_eq](#key_eq)|Ruft das gespeicherte Gleichheits-Vergleichsfunktionsobjekt ab.|  
|[swap](#swap)|Vertauscht den Inhalt von zwei `concurrent_unordered_map`-Objekten. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[unsafe_erase](#unsafe_erase)|Überladen. Entfernt Elemente aus der `concurrent_unordered_map` an angegebenen Positionen. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[[]-Operator](#operator_at)|Überladen. Sucht ein Element mit dem angegebenen Schlüssel oder fügt es ein. Diese Methode ist nebenläufigkeitssicher.|  
|[operator=](#operator_eq)|Überladen. Weist den Inhalt eines anderen `concurrent_unordered_map`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## <a name="remarks"></a>Hinweise  
 Ausführliche Informationen zu den `concurrent_unordered_map` Klasse, finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_map`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concurrent_unordered_map.h  
  
 **Namespace:** Parallelität  
  
##  <a name="at"></a>am 

 Sucht ein Element in der `concurrent_unordered_map` mit einem angegebenen Schlüsselwert. Diese Methode ist nebenläufigkeitssicher.  
  
```
mapped_type& at(const key_type& KVal);

const mapped_type& at(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der Schlüsselwert, das gesucht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf den Datenwert des gefundenen Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Argumentschlüsselwert nicht gefunden wird, löst die Funktion ein Objekt der `out_of_range`-Klasse aus.  
  
##  <a name="begin"></a>beginnen 

 Gibt einen Iterator auf das erste Element in der gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator auf das erste Element in der gleichzeitigen Container.  
  
##  <a name="cbegin"></a>cbegin 

 Gibt einen Konstanten Iterator auf das erste Element in der gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Konstanten Iterator auf das erste Element in der gleichzeitigen Container.  
  
##  <a name="cend"></a>cend 

 Gibt einen Konstanten Iterator auf den Speicherort adressiert, das letzte Element in der gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine const-Iterator für den Speicherort adressiert, das letzte Element in der gleichzeitigen Container.  
  
##  <a name="clear"></a>Deaktivieren 

 Löscht alle Elemente in der gleichzeitigen Container. Diese Funktion ist nicht nebenläufigkeitssicher.  
  
```
void clear();
```  
  
##  <a name="ctor"></a>concurrent_unordered_map 

 Erstellt eine parallele ungeordneten Zuordnung.  
  
```
explicit concurrent_unordered_map(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_map(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_map(_Iterator _Begin,
    _Iterator _End,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_map(
    const concurrent_unordered_map& _Umap);

concurrent_unordered_map(
    const concurrent_unordered_map& _Umap,
    const allocator_type& _Allocator);

concurrent_unordered_map(
    concurrent_unordered_map&& _Umap);
```  
  
### <a name="parameters"></a>Parameter  
 `_Iterator`  
 Der Typ des Eingabeiterators.  
  
 `_Number_of_buckets`  
 Die anfängliche Anzahl von Buckets für diese ungeordneten Zuordnung.  
  
 `_Hasher`  
 Die Hashfunktion für diese ungeordneten Zuordnung.  
  
 `key_equality`  
 Die Gleichheit Vergleichsfunktion für diese ungeordneten Zuordnung.  
  
 `_Allocator`  
 Die Zuweisung für diese ungeordneten Zuordnung.  
  
 `_Begin`  
 Die Position des ersten Elements in dem zu kopierenden Elementbereich.  
  
 `_End`  
 Die Position des ersten Elements nach dem zu kopierenden Elementbereich.  
  
 `_Umap`  
 Das `concurrent_unordered_map`-Quellobjekt, aus dem Elemente kopiert oder verschoben werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Alle Konstruktoren speichern ein Zuweisungsobjekt `_Allocator` und initialisieren die ungeordnete Zuordnung.  
  
 Der erste Konstruktor gibt eine leere ursprüngliche Zuordnung an und gibt explizit an die Anzahl der Buckets, geben Sie die Hashfunktion, der auf Gleichheitsfunktion und der Zuweisung verwendet werden soll.  
  
 Der zweite Konstruktor gibt eine Zuweisung für die der ungeordneten Zuordnung.  
  
 Der dritte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte [ `_Begin`, `_End`).  
  
 Die vierten und fünften Konstruktoren geben eine Kopie der gleichzeitigen ungeordneten Zuordnung `_Umap`.  
  
 Der letzte Konstruktor gibt eine Verschiebung des parallele ungeordneten Zuordnung `_Umap`.  
  
##  <a name="count"></a>Anzahl 

 Zählt die Anzahl von Elementen, die einem angegebenen Schlüssel entsprechen. Diese Funktion ist nebenläufigkeitssicher.  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der zu suchende Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von denen Anzahl der Häufigkeit, mit die der Schlüssel im Container angezeigt wird.  
  
##  <a name="empty"></a>leere 

 Testet, ob keine Elemente vorhanden sind. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der gleichzeitigen Container leer ist, ist `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Bei gleichzeitigen Einfügevorgängen kann, und zwar unabhängig davon, ob die parallele Container leer ist geändert werden unmittelbar nach dem Aufrufen dieser Funktion vor der Rückgabewert auch gelesen wird.  
  
##  <a name="end"></a>Ende 

 Gibt einen Iterator, der auf den Speicherort adressiert, das letzte Element in der gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator auf den Speicherort adressiert, der das letzte Element in der gleichzeitigen Container.  
  
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
 Der Schlüsselwert gesucht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Paar](http://msdn.microsoft.com/en-us/c5a37023-d939-4eb2-ae24-ce8e0cd4505d) , in dem das erste Element ist ein Iterator zum Anfang und das zweite Element ist ein Iterator zum Ende des Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Es ist möglich, dass gleichzeitige einfügungen, die dazu führen, dass zusätzliche Schlüssel nach der Begin-Iterator und vor den End-Iterator eingefügt werden.  
  
##  <a name="find"></a>Suchen 

 Sucht ein Element, das einem angegebenen Schlüssel entspricht. Diese Funktion ist nebenläufigkeitssicher.  
  
```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der Schlüsselwert gesucht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf den Speicherort der verweist der das erste Element, das den angegebenen Schlüssel zugeordnet oder der Iterator `end()` Wenn kein solches Element vorhanden ist.  
  
##  <a name="get_allocator"></a>get_allocator 

 Gibt das gespeicherte Zuweisungsobjekt für diesen gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das gespeicherte Zuweisungsobjekt für diesen gleichzeitigen Container.  
  
##  <a name="hash_function"></a>hash_function 

 Ruft das gespeicherte Hashfunktionsobjekt ab.  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das gespeicherte hashfunktionsobjekt.  
  
##  <a name="insert"></a>Einfügen 

 Fügt dem `concurrent_unordered_map`-Objekt Elemente hinzu.  
  
```
std::pair<iterator,
    bool> insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
std::pair<iterator,
    bool> insert(
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
 Der itertatortyp für die Einfügung verwendet.  
  
 `V`  
 Der Typ des Werts in der Zuordnung eingefügt werden soll.  
  
 `value`  
 Der Wert eingefügt werden soll.  
  
 `_Where`  
 Die Anfangsposition eine Einfügemarke gesucht werden soll.  
  
 `first`  
 Der Anfang des Bereichs, der eingefügt.  
  
 `last`  
 Das Ende des Bereichs, der eingefügt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Paar, das ein Iterator und einem booleschen Wert enthält. Finden Sie im Abschnitt "Hinweise" Weitere Details.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion bestimmt, ob ein Element X in der Sequenz vorhanden ist, dessen Schlüssel hat, der entsprechende Reihenfolge `value`. Wenn nicht der Fall, wird die derartiges Element X erstellt und initialisiert sie mit `value`. Die Funktion dann bestimmt den Iterator `where` , der festlegt, X. Wenn eine Einfügung aufgetreten ist, gibt die Funktion `std::pair(where, true)`. Andernfalls wird zurückgegeben `std::pair(where, false)`.  
  
 Die zweite Memberfunktion gibt Insert ( `value`), wobei `_Where` als Ausgangspunkt in der kontrollierten Sequenz, für die Einfügemarke gesucht werden soll.  
  
 Die dritte Memberfunktion fügt die Sequenz von Elementwerten, aus dem Bereich [ `first`, `last`).  
  
 Die letzten beiden Memberfunktionen Verhalten sich wie die ersten beiden, außer dass `value` wird verwendet, um den eingefügten Wert zu erstellen.  
  
##  <a name="key_eq"></a>key_eq 

 Ruft das gespeicherte Gleichheits-Vergleichsfunktionsobjekt ab.  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das gespeicherte Gleichheitsvergleichsfunktionsobjekt.  
  
##  <a name="load_factor"></a>load_factor 

 Berechnet, und gibt den aktuellen Lastfaktor des Containers. Der Ladefaktor ist die Anzahl der Elemente im Container dividiert durch die Anzahl der Buckets an.  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Ladefaktor für den Container.  
  
##  <a name="max_load_factor"></a>max_load_factor 

 Ruft ab oder legt den maximalen Lastfaktor des Containers. Vom Höchstlastfaktor liegt die höchste Anzahl von Elementen in jeder Bucket sein kann, bevor der Container seine interne Tabelle vergrößert wird.  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>Parameter  
 `_Newmax`  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Memberfunktion gibt den gespeicherten maximalen Lastfaktor zurück. Die zweite Memberfunktion gibt keinen Wert zurück, aber löst ein [Out_of_range](../../../standard-library/out-of-range-class.md) -Ausnahme aus, wenn Sie der angegebenen Lastfaktor ungültig ist...  
  
##  <a name="max_size"></a>max_size 

 Gibt die maximale Größe der gleichzeitigen Container, von der Zuweisung bestimmt. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Elementen, die in diesen gleichzeitigen Container eingefügt werden können.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert für die obere Grenze kann tatsächlich größer sein als was Container tatsächlich aufnehmen kann.  
  
##  <a name="operator_at"></a>[]-Operator 

 Sucht ein Element mit dem angegebenen Schlüssel oder fügt es ein. Diese Methode ist nebenläufigkeitssicher.  
  
```
mapped_type& operator[](const key_type& kval);

mapped_type& operator[](key_type&& kval);
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der Schlüsselwert  
  
 Suchen oder einfügen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf den Datenwert des Elements gefunden wurde oder eingefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Argumentschlüsselwert nicht gefunden wird, wird er zusammen mit dem Standardwert des Datentyps eingefügt.  
  
 `operator[]`kann zum Einfügen von Elementen in einer Zuordnung verwendet werden `m` mit `m[key] = DataValue;`, wobei `DataValue` ist der Wert der `mapped_type` des Elements mit einem Schlüsselwert der `key`.  
  
 Wenn `operator[]` zum Einfügen von Elementen verwendet wird, gibt der zurückgegebene Verweis nicht an, ob eine Einfügung ein bereits vorhandenes Element ändert oder ein neues erstellt. Die Memberfunktionen `find` und [einfügen](#insert) können verwendet werden, um zu bestimmen, ob ein Element mit einem angegebenen Schlüssel bereits vor einer Einfügung vorhanden ist.  
  
##  <a name="operator_eq"></a>Operator = 

 Weist den Inhalt eines anderen `concurrent_unordered_map`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
concurrent_unordered_map& operator= (const concurrent_unordered_map& _Umap);

concurrent_unordered_map& operator= (concurrent_unordered_map&& _Umap);
```  
  
### <a name="parameters"></a>Parameter  
 `_Umap`  
 Das `concurrent_unordered_map`-Quellobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `concurrent_unordered_map`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem alle vorhandenen Elemente gelöscht, einen gleichzeitigen Vektor `operator=` kopiert oder verschiebt den Inhalt der `_Umap` in den gleichzeitigen Vektor.  
  
##  <a name="rehash"></a>Rehash- 

 Erstellt die Hashtabelle neu.  
  
```
void rehash(size_type _Buckets);
```  
  
### <a name="parameters"></a>Parameter  
 `_Buckets`  
 Die gewünschte Anzahl von Buckets.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion ändert die Anzahl der Buckets in mindestens `_Buckets` und erstellt ggf. die Hashtabelle neu. Die Anzahl der Buckets muss eine Potenz von 2 sein. Wenn keine Potenz von 2, wird er auf die nächste größten Potenz von 2 aufgerundet werden.  
  
 Löst ein [Out_of_range](../../../standard-library/out-of-range-class.md) -Ausnahme aus, wenn die Anzahl der Buckets ungültig ist (0 oder größer als die maximale Anzahl von Buckets).  
  
##  <a name="size"></a>Größe 

 Gibt die Anzahl der Elemente in diesen gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Container.  
  
### <a name="remarks"></a>Hinweise  
 Bei gleichzeitigen Einfügevorgängen kann die Anzahl der Elemente in der gleichzeitigen Container ändern, unmittelbar bevor der Rückgabewert auch gelesen wurde, wird durch das Aufrufen dieser Funktion.  
  
##  <a name="swap"></a>Swap 

 Vertauscht den Inhalt von zwei `concurrent_unordered_map`-Objekten. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void swap(concurrent_unordered_map& _Umap);
```  
  
### <a name="parameters"></a>Parameter  
 `_Umap`  
 Die `concurrent_unordered_map` Objekt für den Tauschvorgang.  
  
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
 Ein Iterator, der auf den Anfang des Buckets verweist.  
  
##  <a name="unsafe_bucket"></a>unsafe_bucket 

 Gibt den Bucket-Index, den ein bestimmten Schlüssel in diesem Container zugeordnet.  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der Elementschlüssel gesucht wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der Bucket für den Schlüssel in diesem Container.  
  
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
 Der Bucket gesucht werden soll.  
  
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
 Ein Iterator, der auf den Anfang des Buckets verweist.  
  
##  <a name="unsafe_cend"></a>unsafe_cend 

 Gibt einen Iterator zurück, um den Speicherort adressiert, das letzte Element in einem bestimmten Bucket.  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Bucket`  
 Der Bucket-Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf den Anfang des Buckets verweist.  
  
##  <a name="unsafe_end"></a>unsafe_end 

 Gibt einen Iterator zurück, bis zum letzten Element in diesem Container für einen bestimmten Bucket.  
  
```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Bucket`  
 Der Bucket-Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf das Ende der Buckets verweist.  
  
##  <a name="unsafe_erase"></a>unsafe_erase 

 Entfernt Elemente aus der `concurrent_unordered_map` an angegebenen Positionen. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
iterator unsafe_erase(
    const_iterator _Where);

iterator unsafe_erase(
    const_iterator _Begin,
    const_iterator _End);

size_type unsafe_erase(
    const key_type& KVal);
```  
  
### <a name="parameters"></a>Parameter  
 `_Where`  
 Die Position des Iterators, an der gelöscht werden soll.  
  
 `_Begin`  
 Die Position des ersten Elements im Bereich von Elementen, die gelöscht werden.  
  
 `_End`  
 Die Position des ersten Elements hinter dem Bereich von Elementen, die gelöscht werden.  
  
 `KVal`  
 Der Schlüsselwert, der gelöscht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die ersten beiden Memberfunktionen geben einen Iterator zurück, der das erste Element festlegt, das länger als alle anderen entfernten Elementen verbleibt, oder er gibt `concurrent_unordered_map::end`() zurück, wenn kein solches Element vorhanden ist. Die dritte Memberfunktion gibt die Anzahl von Elementen zurück, die sie entfernt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion entfernt das Element der kontrollierten Sequenz verweist `_Where`. Die zweite Memberfunktion entfernt die Elemente im Bereich [ `_Begin`, `_End`).  
  
 Die dritte Memberfunktion entfernt die Elemente im Bereich, der von `concurrent_unordered_map::equal_range`(KVal).  
  
##  <a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count 

 Gibt die maximale Anzahl der Buckets in diesem Container zurück.  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Buckets, die in diesem Container.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)



