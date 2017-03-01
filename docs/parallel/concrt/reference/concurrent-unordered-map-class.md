---
title: Concurrent_unordered_map-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_unordered_map/concurrency::concurrent_unordered_map
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_map class
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
caps.latest.revision: 13
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
ms.sourcegitcommit: 19244e5527207f852256e646abd18ad298fb28cd
ms.openlocfilehash: ec35d0e410efcc7861df0ab39ad561de04518d91
ms.lasthandoff: 02/24/2017

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
 Der Hashfunktionsobjekttyp. Dieses Argument ist optional, und der Standardwert ist `std::hash<``K``>`.  
  
 `key_equality`  
 Der Gleichheitsvergleich-Funktionsobjekttyp. Dieses Argument ist optional, und der Standardwert ist `std::equal_to<``K``>`.  
  
 `_Allocator_type`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und zur Freigabe des Arbeitsspeichers für die gleichzeitige ungeordnete Zuordnung kapselt. Dieses Argument ist optional und der Standardwert ist `std::allocator<std::pair<``K`, `_Element_type``>>`.  
  
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
|`mapped_type`|Der Typ eines zugeordneten Werts, der jedem Schlüssel zugeordnet ist.|  
|`pointer`|Der Typ eines Zeigers auf ein Element.|  
|`reference`|Der Typ eines Verweises auf ein Element.|  
|`size_type`|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|`value_type`|Der Typ eines Elements.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Concurrent_unordered_map-Konstruktor](#ctor)|Überladen. Erstellt eine parallele ungeordneten Zuordnung.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AT-Methode](#at)|Überladen. Sucht ein Element in der `concurrent_unordered_map` mit einem angegebenen Schlüsselwert. Diese Methode ist nebenläufigkeitssicher.|  
|[Hash_function-Methode](#hash_function)|Ruft das gespeicherte Hashfunktionsobjekt ab.|  
|[Insert-Methode](#insert)|Überladen. Fügt dem `concurrent_unordered_map`-Objekt Elemente hinzu.|  
|[Key_eq-Methode](#key_eq)|Ruft das gespeicherte Gleichheits-Vergleichsfunktionsobjekt ab.|  
|[Swap-Methode](#swap)|Vertauscht den Inhalt von zwei `concurrent_unordered_map`-Objekten. Diese Methode ist nicht nebenläufigkeitssicher.|  
|[Unsafe_erase-Methode](#unsafe_erase)|Überladen. Entfernt Elemente aus der `concurrent_unordered_map` an angegebenen Positionen. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator []-Operator](#operator_at)|Überladen. Sucht ein Element mit dem angegebenen Schlüssel oder fügt es ein. Diese Methode ist nebenläufigkeitssicher.|  
|[Operator =-Operator](#operator_eq)|Überladen. Weist den Inhalt eines anderen `concurrent_unordered_map`-Objekts diesem Objekt zu. Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## <a name="remarks"></a>Hinweise  
 Ausführliche Informationen zu den `concurrent_unordered_map` Klasse, finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_map`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concurrent_unordered_map.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameata-at"></a><a name="at"></a>am 

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
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>beginnen 

 Gibt einen Iterator, der auf das erste Element im gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator auf das erste Element im gleichzeitigen Container.  
  
##  <a name="a-namecbegina-cbegin"></a><a name="cbegin"></a>cbegin 

 Gibt einen const-Iterator auf das erste Element im gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein const-Iterator auf das erste Element im gleichzeitigen Container.  
  
##  <a name="a-namecenda-cend"></a><a name="cend"></a>cend 

 Gibt einen Konstanten Iterator, der auf den Speicherort adressiert, das letzte Element im gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein const-Iterator für den Speicherort adressiert, das letzte Element im gleichzeitigen Container.  
  
##  <a name="a-namecleara-clear"></a><a name="clear"></a>Deaktivieren 

 Löscht alle Elemente im gleichzeitigen Container. Diese Funktion ist nicht nebenläufigkeitssicher.  
  
```
void clear();
```  
  
##  <a name="a-namectora-concurrentunorderedmap"></a><a name="ctor"></a>concurrent_unordered_map 

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
  
 Der erste Konstruktor gibt eine leere ursprüngliche Zuordnung und explizit angibt, für die Anzahl der Buckets, Hash-Funktion, die Gleichheitsfunktion und der Zuweisung verwendet werden sollen.  
  
 Der zweite Konstruktor gibt eine Zuweisung für das ungeordnete Zuordnung an.  
  
 Der dritte Konstruktor gibt vom Iteratorbereich bereitgestellte Werte an [ `_Begin`, `_End`).  
  
 Die vierten und fünften Konstruktoren geben eine Kopie für die gleichzeitige ungeordnete Zuordnung `_Umap`.  
  
 Der letzte Konstruktor gibt eine Verschiebung der die gleichzeitige ungeordnete Zuordnung `_Umap`.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>Anzahl 

 Zählt die Anzahl der Elemente, die einem angegebenen Schlüssel entsprechen. Diese Funktion ist nebenläufigkeitssicher.  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der zu suchende Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von versuchen, wie oft der Schlüssel im Container angezeigt wird.  
  
##  <a name="a-nameemptya-empty"></a><a name="empty"></a>leere 

 Testet, ob keine Elemente vorhanden sind. Diese Methode ist nebenläufigkeitssicher.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die parallele Container leer ist, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Bei gleichzeitiger fügt davon, ob die parallele Container leer ist das kann unmittelbar nach dem Aufrufen dieser Funktion vor dem Lesen des Rückgabewerts ist sogar ändern.  
  
##  <a name="a-nameenda-end"></a><a name="end"></a>Ende 

 Gibt einen Iterator, der auf den Speicherort adressiert, das letzte Element im gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator für den Speicherort adressiert, das letzte Element im gleichzeitigen Container.  
  
##  <a name="a-nameequalrangea-equalrange"></a><a name="equal_range"></a>equal_range 

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
 Ein [Paar](http://msdn.microsoft.com/en-us/c5a37023-d939-4eb2-ae24-ce8e0cd4505d) , in dem das erste Element ist ein Iterator zum Anfang und das zweite Element ist ein Iterator das Ende des Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Es ist möglich für gleichzeitige INSERT-Vorgänge, die dazu führen, dass zusätzliche Schlüssel nach der Begin-Iterator und vor den End-Iterator eingefügt werden.  
  
##  <a name="a-namefinda-find"></a><a name="find"></a>Suchen 

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
  
##  <a name="a-namegetallocatora-getallocator"></a><a name="get_allocator"></a>get_allocator 

 Gibt das gespeicherte Zuweisungsobjekt für diesen gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das gespeicherte Zuweisungsobjekt für diesen gleichzeitigen Container.  
  
##  <a name="a-namehashfunctiona-hashfunction"></a><a name="hash_function"></a>hash_function 

 Ruft das gespeicherte Hashfunktionsobjekt ab.  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das gespeicherte hashfunktionsobjekt.  
  
##  <a name="a-nameinserta-insert"></a><a name="insert"></a>Einfügen 

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
 Der iteratortyp für die Einfügung verwendet.  
  
 `V`  
 Der Typ des Werts in die Karte eingefügt werden soll.  
  
 `value`  
 Der Wert eingefügt werden soll.  
  
 `_Where`  
 Die Startposition für eine Einfügemarke zu suchen.  
  
 `first`  
 Der Anfang des Bereichs, der eingefügt werden soll.  
  
 `last`  
 Das Ende des Bereichs, der eingefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Paar, die einen Iterator und einen booleschen Wert enthält. Finden Sie weitere Details finden Sie im Abschnitt "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion bestimmt, ob ein Element X in der Sequenz vorhanden ist, dessen Schlüssel hat Sortierung der `value`. Wenn nicht, es wird eine solche ein Element X erstellt und initialisiert sie mit `value`. Die Funktion bestimmt dann, den Iterator `where` X kennzeichnet. Wenn eine Einfügung aufgetreten ist, gibt die Funktion `std::pair(where, true)`. Andernfalls gibt es `std::pair(where, false)`.  
  
 Die zweite Memberfunktion gibt einfügen ( `value`), wobei `_Where` als Ausgangspunkt in der kontrollierten Sequenz an der Einfügemarke zu suchen.  
  
 Die dritte Memberfunktion fügt die Sequenz von Elementwerten aus dem Bereich [ `first`, `last`).  
  
 Die letzten beiden Memberfunktionen Verhalten sich wie die ersten beiden, außer dass `value` wird zum Erstellen des eingefügten Wert.  
  
##  <a name="a-namekeyeqa-keyeq"></a><a name="key_eq"></a>key_eq 

 Ruft das gespeicherte Gleichheits-Vergleichsfunktionsobjekt ab.  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das gespeicherte Gleichheitsvergleichsfunktionsobjekt.  
  
##  <a name="a-nameloadfactora-loadfactor"></a><a name="load_factor"></a>load_factor 

 Berechnet, und gibt den aktuellen Lastfaktor des Containers. Der Lastfaktor ist die Anzahl der Elemente im Container dividiert durch die Anzahl der Buckets.  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Lastfaktor für den Container.  
  
##  <a name="a-namemaxloadfactora-maxloadfactor"></a><a name="max_load_factor"></a>max_load_factor 

 Ruft ab oder legt den Höchstlastfaktor des Containers. Die Höchstlastfaktor liegt die größte Anzahl von Elementen in jeder Bucket sein kann, bevor der Container seiner internen Tabelle wächst.  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>Parameter  
 `_Newmax`  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Memberfunktion gibt den gespeicherten maximalen Lastfaktor zurück. Die zweite Memberfunktion gibt keinen Wert zurück, aber löst ein [Out_of_range](../../../standard-library/out-of-range-class.md) -Ausnahme aus, wenn Sie der angegebenen Lastfaktor ungültig ist...  
  
##  <a name="a-namemaxsizea-maxsize"></a><a name="max_size"></a>max_size 

 Gibt die maximale Größe des gleichzeitigen Container durch die Zuweisung bestimmt. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Elementen, die in diesen gleichzeitigen Container eingefügt werden können.  
  
### <a name="remarks"></a>Hinweise  
 Diese Obergrenze Wert tatsächlich ist möglicherweise größer, was der Container tatsächlich enthalten kann.  
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>Operator] 

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
 Ein Verweis auf den Datenwert des gefundenen oder eingefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Argumentschlüsselwert nicht gefunden wird, wird er zusammen mit dem Standardwert des Datentyps eingefügt.  
  
 `operator[]`zum Einfügen von Elementen in einer Zuordnung verwendet werden kann `m` mit `m[key] = DataValue;`, wobei `DataValue` ist der Wert der `mapped_type` des Elements mit dem Schlüsselwert `key`.  
  
 Wenn `operator[]` zum Einfügen von Elementen verwendet wird, gibt der zurückgegebene Verweis nicht an, ob eine Einfügung ein bereits vorhandenes Element ändert oder ein neues erstellt. Die Memberfunktionen `find` und [einfügen](#insert) können verwendet werden, um zu bestimmen, ob ein Element mit dem angegebenen Schlüssel bereits vor einer Einfügung vorhanden ist.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>Operator = 

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
 Nach dem Löschen der vorhandenen Elemente eines gleichzeitigen Vektors, `operator=` kopiert oder verschiebt den Inhalt des `_Umap` im gleichzeitigen Vektor.  
  
##  <a name="a-namerehasha-rehash"></a><a name="rehash"></a>Rehash 

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
  
##  <a name="a-namesizea-size"></a><a name="size"></a>Größe 

 Gibt die Anzahl der Elemente in diesen gleichzeitigen Container zurück. Diese Methode ist nebenläufigkeitssicher.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Container.  
  
### <a name="remarks"></a>Hinweise  
 Bei gleichzeitiger einfügt kann die Anzahl der Elemente in dem parallele Container unmittelbar nach dem Aufrufen dieser Funktion vor dem Lesen des Rückgabewerts ist sogar ändern.  
  
##  <a name="a-nameswapa-swap"></a><a name="swap"></a>Swap 

 Vertauscht den Inhalt von zwei `concurrent_unordered_map`-Objekten. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
void swap(concurrent_unordered_map& _Umap);
```  
  
### <a name="parameters"></a>Parameter  
 `_Umap`  
 Das `concurrent_unordered_map` Objekt zum austauschen.  
  
##  <a name="a-nameunsafebegina-unsafebegin"></a><a name="unsafe_begin"></a>unsafe_begin 

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
  
##  <a name="a-nameunsafebucketa-unsafebucket"></a><a name="unsafe_bucket"></a>unsafe_bucket 

 Gibt den Bucket-Index, den ein bestimmten Schlüssel in diesem Container zugeordnet ist.  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Parameter  
 `KVal`  
 Der Elementschlüssel gesucht wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bucket-Index für den Schlüssel in diesem Container.  
  
##  <a name="a-nameunsafebucketcounta-unsafebucketcount"></a><a name="unsafe_bucket_count"></a>unsafe_bucket_count 

 Gibt die aktuelle Anzahl der Buckets in diesem Container zurück.  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Anzahl der Buckets in diesem Container.  
  
##  <a name="a-nameunsafebucketsizea-unsafebucketsize"></a><a name="unsafe_bucket_size"></a>unsafe_bucket_size 

 Gibt die Anzahl der Elemente in einem bestimmten Bucket dieses Containers zurück.  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>Parameter  
 `_Bucket`  
 Der Bucket zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Anzahl der Buckets in diesem Container.  
  
##  <a name="a-nameunsafecbegina-unsafecbegin"></a><a name="unsafe_cbegin"></a>unsafe_cbegin 

 Gibt einen Iterator zurück, auf das erste Element in diesem Container für einen bestimmten Bucket.  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Bucket`  
 Der Bucket-Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf den Anfang des Buckets zeigt.  
  
##  <a name="a-nameunsafecenda-unsafecend"></a><a name="unsafe_cend"></a>unsafe_cend 

 Gibt einen Iterator zurück, um den Speicherort adressiert, das letzte Element in einem bestimmten Bucket.  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Bucket`  
 Der Bucket-Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf den Anfang des Buckets zeigt.  
  
##  <a name="a-nameunsafeenda-unsafeend"></a><a name="unsafe_end"></a>unsafe_end 

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
  
##  <a name="a-nameunsafeerasea-unsafeerase"></a><a name="unsafe_erase"></a>unsafe_erase 

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
 Die Position des ersten Elements außerhalb des Bereichs von Elementen, die gelöscht werden.  
  
 `KVal`  
 Der Schlüsselwert, der gelöscht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die ersten beiden Memberfunktionen geben einen Iterator zurück, der das erste Element festlegt, das länger als alle anderen entfernten Elementen verbleibt, oder er gibt `concurrent_unordered_map::end`() zurück, wenn kein solches Element vorhanden ist. Die dritte Memberfunktion gibt die Anzahl von Elementen zurück, die sie entfernt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion entfernt das Element der kontrollierten Sequenz verweist `_Where`. Die zweite Memberfunktion entfernt die Elemente im Bereich [ `_Begin`, `_End`).  
  
 Die dritte Memberfunktion entfernt die Elemente im Bereich von `concurrent_unordered_map::equal_range`(KVal).  
  
##  <a name="a-nameunsafemaxbucketcounta-unsafemaxbucketcount"></a><a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count 

 Gibt die maximale Anzahl der Buckets in diesem Container zurück.  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl der Buckets in diesem Container.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)




