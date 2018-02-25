---
title: unordered_set-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- unordered_set/std::unordered_set
- unordered_set/std::unordered_set::allocator_type
- unordered_set/std::unordered_set::const_iterator
- unordered_set/std::unordered_set::const_local_iterator
- unordered_set/std::unordered_set::const_pointer
- unordered_set/std::unordered_set::const_reference
- unordered_set/std::unordered_set::difference_type
- unordered_set/std::unordered_set::hasher
- unordered_set/std::unordered_set::iterator
- unordered_set/std::unordered_set::key_equal
- unordered_set/std::unordered_set::key_type
- unordered_set/std::unordered_set::local_iterator
- unordered_set/std::unordered_set::pointer
- unordered_set/std::unordered_set::reference
- unordered_set/std::unordered_set::size_type
- unordered_set/std::unordered_set::value_type
- unordered_set/std::unordered_set::begin
- unordered_set/std::unordered_set::bucket
- unordered_set/std::unordered_set::bucket_count
- unordered_set/std::unordered_set::bucket_size
- unordered_set/std::unordered_set::cbegin
- unordered_set/std::unordered_set::cend
- unordered_set/std::unordered_set::clear
- unordered_set/std::unordered_set::count
- unordered_set/std::unordered_set::emplace
- unordered_set/std::unordered_set::emplace_hint
- unordered_set/std::unordered_set::empty
- unordered_set/std::unordered_set::end
- unordered_set/std::unordered_set::equal_range
- unordered_set/std::unordered_set::erase
- unordered_set/std::unordered_set::find
- unordered_set/std::unordered_set::get_allocator
- unordered_set/std::unordered_set::hash
- unordered_set/std::unordered_set::insert
- unordered_set/std::unordered_set::key_eq
- unordered_set/std::unordered_set::load_factor
- unordered_set/std::unordered_set::max_bucket_count
- unordered_set/std::unordered_set::max_load_factor
- unordered_set/std::unordered_set::max_size
- unordered_set/std::unordered_set::rehash
- unordered_set/std::unordered_set::size
- unordered_set/std::unordered_set::swap
- unordered_set/std::unordered_set::unordered_set
- unordered_set/std::unordered_set::operator=
- unordered_set/std::unordered_set::hash_function
dev_langs:
- C++
helpviewer_keywords:
- std::unordered_set
- std::unordered_set::allocator_type
- std::unordered_set::const_iterator
- std::unordered_set::const_local_iterator
- std::unordered_set::const_pointer
- std::unordered_set::const_reference
- std::unordered_set::difference_type
- std::unordered_set::hasher
- std::unordered_set::iterator
- std::unordered_set::key_equal
- std::unordered_set::key_type
- std::unordered_set::local_iterator
- std::unordered_set::pointer
- std::unordered_set::reference
- std::unordered_set::size_type
- std::unordered_set::value_type
- std::unordered_set::begin
- std::unordered_set::bucket
- std::unordered_set::bucket_count
- std::unordered_set::bucket_size
- std::unordered_set::cbegin
- std::unordered_set::cend
- std::unordered_set::clear
- std::unordered_set::count
- std::unordered_set::emplace
- std::unordered_set::emplace_hint
- std::unordered_set::empty
- std::unordered_set::end
- std::unordered_set::equal_range
- std::unordered_set::erase
- std::unordered_set::find
- std::unordered_set::get_allocator
- std::unordered_set::hash
- std::unordered_set::insert
- std::unordered_set::key_eq
- std::unordered_set::load_factor
- std::unordered_set::max_bucket_count
- std::unordered_set::max_load_factor
- std::unordered_set::max_size
- std::unordered_set::rehash
- std::unordered_set::size
- std::unordered_set::swap
- std::unordered_set::unordered_set
- std::unordered_set::operator=
- std::unordered_set::allocator_type
- std::unordered_set::const_iterator
- std::unordered_set::const_local_iterator
- std::unordered_set::const_pointer
- std::unordered_set::const_reference
- std::unordered_set::difference_type
- std::unordered_set::hasher
- std::unordered_set::iterator
- std::unordered_set::key_equal
- std::unordered_set::key_type
- std::unordered_set::local_iterator
- std::unordered_set::pointer
- std::unordered_set::reference
- std::unordered_set::size_type
- std::unordered_set::value_type
- std::unordered_set::begin
- std::unordered_set::bucket
- std::unordered_set::bucket_count
- std::unordered_set::bucket_size
- std::unordered_set::cbegin
- std::unordered_set::cend
- std::unordered_set::clear
- std::unordered_set::count
- std::unordered_set::emplace
- std::unordered_set::emplace_hint
- std::unordered_set::empty
- std::unordered_set::end
- std::unordered_set::equal_range
- std::unordered_set::erase
- std::unordered_set::find
- std::unordered_set::get_allocator
- std::unordered_set::hash_function
- std::unordered_set::insert
- std::unordered_set::key_eq
- std::unordered_set::load_factor
- std::unordered_set::max_bucket_count
- std::unordered_set::max_load_factor
- std::unordered_set::max_size
- std::unordered_set::rehash
- std::unordered_set::size
- std::unordered_set::swap
ms.assetid: ac08084e-05a7-48c0-9ae4-d40c529922dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70b9f8541601cc2d91cf2e43fbb66110302488be
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="unorderedset-class"></a>unordered_set-Klasse
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge vom Typ `const Key` steuert. Die Sequenz wird grob durch eine Hashfunktion sortiert, die die Sequenz in eine geordnete Gruppe von Untersequenzen, so genannte Buckets, unterteilt. Innerhalb jedes Buckets bestimmt eine Vergleichsfunktion, ob ein Elementpaar eine entsprechende Reihenfolge hat. Jedes Element dient sowohl als Sortierschlüssel als auch als Wert. Die Sequenz wird so dargestellt, dass die Suche, das Einfügen und das Entfernen eines beliebigen Elements mit einer Reihen von Vorgängen möglich ist, die unabhängig von der Anzahl von Elementen in der Sequenz (konstante Zeit) sein können, zumindest, wenn alle Buckets von ungefähr gleicher Länge sind. Im schlimmsten Fall, d. h., wenn sich alle Elemente in einem Bucket befinden, ist die Anzahl von Vorgängen proportional zur Anzahl von Elementen in der Sequenz (lineare Zeit). Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <
   class Key,  
   class Hash = std::hash<Key>,  
   class Pred = std::equal_to<Key>,  
   class Alloc = std::allocator<Key>>  
class unordered_set;  
```  
  
#### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`Key`|Der Schlüsseltyp.|  
|`Hash`|Der Hashfunktionsobjekttyp.|  
|`Pred`|Der Gleichheitsvergleich-Funktionsobjekttyp.|  
|`Alloc`|Die Zuweisungsklasse.|  
  
## <a name="members"></a>Member  
  
|||  
|-|-|  
|Typdefinition|Beschreibung|  
|[allocator_type](#allocator_type)|Der Typ einer Zuweisung für die Speicherverwaltung.|  
|[const_iterator](#const_iterator)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[const_local_iterator](#const_local_iterator)|Der Typ eines konstanten Bucketiterators für die gesteuerte Sequenz.|  
|[const_pointer](#const_pointer)|Der Typ eines konstanten Zeigers auf ein Element.|  
|[const_reference](#const_reference)|Der Typ eines konstanten Verweises auf ein Element.|  
|[difference_type](#difference_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[hasher](#hasher)|Der Typ der Hashfunktion.|  
|[Iterator](#iterator)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[key_equal](#key_equal)|Der Typ der Vergleichsfunktion.|  
|[key_type](#key_type)|Der Typ eines Sortierschlüssels.|  
|[local_iterator](#local_iterator)|Der Typ eines Bucketiterators für die gesteuerte Sequenz.|  
|[Zeiger](#pointer)|Der Typ eines Zeigers auf ein Element.|  
|[Verweis](#reference)|Der Typ eines Verweises auf ein Element.|  
|[size_type](#size_type)|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|[value_type](#value_type)|Der Typ eines Elements.|  
  
|||  
|-|-|  
|Memberfunktion|Beschreibung|  
|[begin](#begin)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[bucket](#bucket)|Ruft die Bucketnummer für einen Schlüsselwert ab.|  
|[bucket_count](#bucket_count)|Ruft die Anzahl von Buckets ab.|  
|[bucket_size](#bucket_size)|Ruft die Größe eines Buckets ab.|  
|[cbegin](#cbegin)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[cend](#cend)|Legt das Ende der kontrollierten Sequenz fest.|  
|[clear](#clear)|Entfernt alle Elemente.|  
|[count](#count)|Sucht die Anzahl von Elementen, die einem angegebenen Schlüssel entsprechen.|  
|[emplace](#emplace)|Fügt ein Element hinzu, das direkt erstellt wird.|  
|[emplace_hint](#emplace_hint)|Fügt ein Element hinzu, das direkt mit Hinweis erstellt wird.|  
|[empty](#empty)|Testet, ob keine Elemente vorhanden sind.|  
|[end](#end)|Legt das Ende der kontrollierten Sequenz fest.|  
|[equal_range](#equal_range)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[erase](#erase)|Entfernt Elemente an den angegebenen Positionen.|  
|[find](#find)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[get_allocator](#get_allocator)|Ruft das gespeicherte Zuweisungsobjekt ab.|  
|[hash_function](#hash)|Ruft das gespeicherte Hashfunktionsobjekt ab.|  
|[insert](#insert)|Fügt Elemente hinzu.|  
|[key_eq](#key_eq)|Ruft das gespeicherte Vergleichsfunktionsobjekt ab.|  
|[load_factor](#load_factor)|Zählt die durchschnittliche Anzahl von Elementen pro Bucket.|  
|[max_bucket_count](#max_bucket_count)|Ruft die maximale Anzahl von Buckets ab.|  
|[max_load_factor](#max_load_factor)|Ruft die maximale Anzahl von Elementen pro Bucket ab oder legt sie fest.|  
|[max_size](#max_size)|Ruft die maximale Größe der gesteuerten Sequenz ab.|  
|[rehash](#rehash)|Erstellt die Hashtabelle neu.|  
|[size](#size)|Ermittelt die Anzahl von Elementen.|  
|[swap](#swap)|Vertauscht den Inhalt von zwei Containern.|  
|[unordered_set](#unordered_set)|Erstellt ein container-Objekt.|  
  
|||  
|-|-|  
|Operatoren|Beschreibung|  
|[unordered_set::operator=](#op_eq)|Kopiert eine Hashtabelle.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt sortiert die Sequenz, die es steuert, indem es zwei gespeicherte Objekte aufruft, ein Vergleichsfunktionsobjekt des Typs [unordered_set::key_equal](#key_equal) und ein Hashfunktionsobjekt des Typs [unordered_set::hasher](#hasher). Sie greifen auf das zuerst gespeicherte Objekt zu, indem Sie die Memberfunktion [unordered_set::key_eq](#key_eq)`()` aufrufen. Auf das zweite gespeicherte Objekt greifen Sie zu, indem Sie die Memberfunktion [unordered_set::hash_function](#hash)`()` aufrufen. Insbesondere für alle Werte `X` und `Y` vom Typ `Key` gibt der Aufruf von `key_eq()(X, Y)` nur "true" zurück, wenn die beiden Argumentwerte die entsprechende Reihenfolge aufweisen. Der Aufruf von `hash_function()(keyval)` ergibt eine Verteilung von Werten des Typs `size_t`. Im Gegensatz zur Vorlagenklasse[Unordered_multiset-Klasse](../standard-library/unordered-multiset-class.md), ein Objekt der Vorlagenklasse `unordered_set` wird sichergestellt, dass `key_eq()(X, Y)` ist immer "false" für beliebige zwei Elemente der gesteuerten Sequenz. (Schlüssel sind eindeutig.)  
  
 Das Objekt speichert auch einen Höchstlastfaktor, der die maximal erwünschte durchschnittliche Anzahl von Elementen pro Bucket angibt. Wenn durch Einfügen eines Elements der Wert [unordered_set::load_factor](#load_factor)`()` den Höchstlastfaktor überschreitet, erhöht der Container die Anzahl von Buckets und erstellt die Hashtabelle nach Bedarf neu.  
  
 Die tatsächliche Reihenfolge der Elemente in der gesteuerten Sequenz hängt von der Hashfunktion, von der Vergleichsfunktion, von der Einfügereihenfolge, vom Höchstlastfaktor und von der aktuellen Anzahl von Buckets ab. Sie können die Reihenfolge der Elemente in der gesteuerten Sequenz im Allgemeinen nicht vorhersagen. Sie können allerdings sicher sein, dass jede Teilmenge von Elementen, die die entsprechende Reihenfolge aufweisen, in der gesteuerten Sequenz benachbart sind.  
  
 Das Objekt belegt Speicher und gibt Speicher für die gesteuerte Sequenz durch ein gespeichertes Zuweisungsobjekt des Typs [unordered_set::allocator_type](#allocator_type) frei. Ein solches Zuweisungsobjekt muss die gleiche externe Schnittstelle wie ein Objekt der Vorlagenklasse `allocator` aufweisen. Beachten Sie, dass das gespeicherte Zuweisungsobjekt nicht kopiert wird, wenn das Containerobjekt zugewiesen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<unordered_set>  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a> unordered_set::allocator_type  
 Der Typ einer Zuweisung für die Speicherverwaltung.  
  
```  
typedef Alloc allocator_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_allocator_type.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
typedef std::allocator<std::pair<const char, int> > Myalloc;  
int main()  
{  
    Myset c1;  
      
    Myset::allocator_type al = c1.get_allocator();  
    std::cout << "al == std::allocator() is "  
    << std::boolalpha << (al == Myalloc()) << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
al == std::allocator() is true  
```  
  
##  <a name="begin"></a> unordered_set::begin  
 Kennzeichnet den Anfang der kontrollierten Sequenz oder eines Buckets.  
  
```  
iterator begin();

const_iterator begin() const;
 
local_iterator begin(size_type nbucket);

const_local_iterator begin(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`nbucket`|Die Bucketnummer.|  
  
### <a name="remarks"></a>Hinweise  
 Die beiden ersten Memberfunktionen geben einen Vorwärtsiterator zurück, der auf das erste Element der Sequenz zeigt (bzw. unmittelbar hinter das Ende einer leeren Sequenz). Die beiden letzten Memberfunktionen geben einen Vorwärtsiterator zurück, der auf das erste Element des Buckets `nbucket` zeigt (bzw. unmittelbar hinter das Ende eines leeren Buckets).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// unordered_set_begin.cpp  
// compile using: cl.exe /EHsc /nologo /W4 /MTd  
#include <unordered_set>  
#include <iostream>  
  
using namespace std;  
  
typedef unordered_set<char> MySet;  
  
int main()  
{  
    MySet c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents using range-based for  
    for (auto it : c1) {  
    cout << " [" << it << "]";  
    }  
      
    cout << endl;  
      
    // display contents using explicit for  
    for (MySet::const_iterator it = c1.begin(); it != c1.end(); ++it) {  
        cout << " [" << *it << "]";  
    }  
      
    cout << std::endl;  
      
    // display first two items  
    MySet::iterator it2 = c1.begin();  
    cout << " [" << *it2 << "]";  
    ++it2;  
    cout << " [" << *it2 << "]";  
    cout << endl;  
      
    // display bucket containing 'a'  
    MySet::const_local_iterator lit = c1.begin(c1.bucket('a'));  
    cout << " [" << *lit << "]";  
      
    return (0);  
}  
```  
  
```Output  
 [a] [b] [c]                                   
 [a] [b] [c]                                  
 [a] [b]                                   
 [a]  
```  
  
##  <a name="bucket"></a> unordered_set::bucket  
 Ruft die Bucketnummer für einen Schlüsselwert ab.  
  
```  
size_type bucket(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parameter  
 `keyval`  
 Der zuzuordnende Schlüsselwert.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Bucketnummer zurück, die derzeit dem Schlüsselwert `keyval`entspricht.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_bucket.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // display buckets for keys  
    Myset::size_type bs = c1.bucket('a');  
    std::cout << "bucket('a') == " << bs << std::endl;  
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)  
    << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
bucket('a') == 7  
bucket_size(7) == 1  
```  
  
##  <a name="bucket_count"></a> unordered_set::bucket_count  
 Ruft die Anzahl von Buckets ab.  
  
```  
size_type bucket_count() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die aktuelle Anzahl von Buckets zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_bucket_count.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // inspect current parameters  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    // change max_load_factor and redisplay  
    c1.max_load_factor(0.10f);  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    // rehash and redisplay  
    c1.rehash(100);  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
```  
  
##  <a name="bucket_size"></a> unordered_set::bucket_size  
 Ruft die Größe eines Buckets ab.  
  
```  
size_type bucket_size(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Parameter  
 `nbucket`  
 Die Bucketnummer.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Größe von Bucket Nummer `nbucket`zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_bucket_size.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // display buckets for keys  
    Myset::size_type bs = c1.bucket('a');  
    std::cout << "bucket('a') == " << bs << std::endl;  
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)  
    << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
bucket('a') == 7  
bucket_size(7) == 1  
```  
  
##  <a name="cbegin"></a> unordered_set::cbegin  
 Gibt einen `const`-Iterator zurück, mit dem das erste Element im Bereich behandelt wird.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `const`-Forward-Access-Iterator, der auf das erste Element des Bereichs zeigt oder die Position direkt hinter dem Ende eines leeren Bereichs (für einen leeren Bereich gilt `cbegin() == cend()`).  
  
### <a name="remarks"></a>Hinweise  
 Bei dem Rückgabewert `cbegin` können die Elemente im Bereich nicht geändert werden.  
  
 Sie können diese Memberfunktion anstelle der `begin()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. Normalerweise wird sie zusammen mit dem Typableitungs-Schlüsselwort [auto](../cpp/auto-cpp.md) verwendet, wie im folgenden Beispiel gezeigt. Im folgenden Beispiel ist `Container` ein beliebiger änderbarer (Nicht-`const`-)Container, der `begin()` und `cbegin()` unterstützt.  
  
```cpp  
auto i1 = Container.begin();
// i1 isContainer<T>::iterator  
auto i2 = Container.cbegin();

// i2 isContainer<T>::const_iterator  
```  
  
##  <a name="cend"></a> unordered_set::cend  
 Gibt einen `const`-Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines Bereichs unmittelbar nachfolgt.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen `const`-Forward-Access-Iterator zurück, der auf eine Position unmittelbar nach dem Ende des Bereichs verweist.  
  
### <a name="remarks"></a>Hinweise  
 `cend` wird verwendet, um zu testen, ob ein Iterator das Ende seines Bereichs übergeben hat.  
  
 Sie können diese Memberfunktion anstelle der `end()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. Normalerweise wird sie zusammen mit dem Typableitungs-Schlüsselwort [auto](../cpp/auto-cpp.md) verwendet, wie im folgenden Beispiel gezeigt. Im folgenden Beispiel ist `Container` ein beliebiger änderbarer (Nicht-`const`-)Container, der `end()` und `cend()` unterstützt.  
  
```cpp  
auto i1 = Container.end();
// i1 isContainer<T>::iterator  
auto i2 = Container.cend();

// i2 isContainer<T>::const_iterator  
```  
  
 Der von `cend` zurückgegebene Wert darf nicht dereferenziert werden.  
  
##  <a name="clear"></a> unordered_set::clear  
 Entfernt alle Elemente.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion ruft [unordered_set::erase](#erase)`(` [unordered_set::begin](#begin)`(),` [unordered_set::end](#end)`())` auf.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_clear.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // clear the container and reinspect  
    c1.clear();  
    std::cout << "size == " << c1.size() << std::endl;  
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
    std::cout << std::endl;  
      
    c1.insert('d');  
    c1.insert('e');  
      
    // display contents " [e] [d]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    std::cout << "size == " << c1.size() << std::endl;  
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
size == 0  
empty() == true  
 [e] [d]  
size == 2  
empty() == false  
```  
  
##  <a name="const_iterator"></a> unordered_set::const_iterator  
 Der Typ eines konstanten Iterators für die gesteuerte Sequenz.  
  
```  
typedef T1 const_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt, das als konstanter Forward-Iterator für die gesteuerte Sequenz fungieren kann. Er wird hier als Synonym für einen durch Implementierung definierten `T1`-Typ beschrieben.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_const_iterator.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
    std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
```  
  
##  <a name="const_local_iterator"></a> unordered_set::const_local_iterator  
 Der Typ eines konstanten Bucketiterators für die gesteuerte Sequenz.  
  
```  
typedef T5 const_local_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt, das als konstanter Vorwärtsiterator für ein Bucket dienen kann. Er wird hier als Synonym für einen durch Implementierung definierten `T5`-Typ beschrieben.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_const_local_iterator.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // inspect bucket containing 'a'  
    Myset::const_local_iterator lit = c1.begin(c1.bucket('a'));  
    std::cout << " [" << *lit << "]";  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
 [a]  
```  
  
##  <a name="const_pointer"></a> unordered_set::const_pointer  
 Der Typ eines konstanten Zeigers auf ein Element.  
  
```  
typedef Alloc::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt, das als konstanter Zeiger für ein Element der gesteuerten Sequenz fungieren kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_const_pointer.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
    {  
        Myset::const_pointer p = &*it;  
        std::cout << " [" << *p << "]";  
    }  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
```  
  
##  <a name="const_reference"></a> unordered_set::const_reference  
 Der Typ eines konstanten Verweises auf ein Element.  
  
```  
typedef Alloc::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt, das als Konstantenverweis für ein Element der gesteuerten Sequenz fungieren kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_const_reference.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
    {  
        Myset::const_reference ref = *it;  
        std::cout << " [" << ref << "]";  
    }  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
```  
  
##  <a name="count"></a> unordered_set::count  
 Sucht die Anzahl von Elementen, die einem angegebenen Schlüssel entsprechen.  
  
```  
size_type count(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parameter  
 `keyval`  
 Der zu suchende Schlüsselwert.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Anzahl von Elementen zurück, die sich in dem Bereich befinden, der durch [unordered_set::equal_range](#equal_range)`(keyval)` begrenzt ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_count.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    std::cout << "count('A') == " << c1.count('A') << std::endl;  
    std::cout << "count('b') == " << c1.count('b') << std::endl;  
    std::cout << "count('C') == " << c1.count('C') << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
count('A') == 0  
count('b') == 1  
count('C') == 0  
```  
  
##  <a name="difference_type"></a> unordered_set::difference_type  
 Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.  
  
```  
typedef T3 difference_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Ganzzahltyp mit Vorzeichen beschreibt ein Objekt, das die Differenz zwischen den Adressen von zwei beliebigen Elementen in der gesteuerten Sequenz darstellen kann. Er wird hier als Synonym für einen durch Implementierung definierten `T3`-Typ beschrieben.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_difference_type.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // compute positive difference  
    Myset::difference_type diff = 0;  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        ++diff;  
    std::cout << "end()-begin() == " << diff << std::endl;  
      
    // compute negative difference  
    diff = 0;  
    for (Myset::const_iterator it = c1.end(); it != c1.begin(); --it)  
        --diff;  
    std::cout << "begin()-end() == " << diff << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
end()-begin() == 3  
begin()-end() == -3  
```  
  
##  <a name="emplace"></a> unordered_set::emplace  
 Es wird ein Element eingefügt, das vor Ort konstruiert wird (keine Kopieren- oder Verschiebevorgänge werden ausgeführt).  
  
```  
template <class... Args>  
pair<iterator, bool>  
emplace(
Args&&... args);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`args`|Die Argumente, die zum Erstellen eines in das unordered_set-Element einzufügenden Elements weitergeleitet werden, es sei denn, es ist bereits ein Element enthalten, dessen Wert gleichwertig sortiert wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `pair`-Element, dessen `bool`-Komponente "true" zurückgibt, wenn eine Einfügung erfolgt ist und "false", wenn `unordered_set` bereits ein Element enthält, dessen Schlüssel einen entsprechenden Wert in der Reihenfolge aufweist und dessen Iteratorkomponente die Adresse zurückgibt, an der ein neues Element eingefügt wurde oder, an der das Element bereits gefunden wurde.  
  
 Um auf die Iteratorkomponente eines `pr`-Paares zuzugreifen, das von dieser Memberfunktion zurückgegeben wird, verwenden Sie `pr.first` und `*(pr.first)`, um es zu dereferenzieren. Um auf die `bool`-Komponente eines `pr`-Paares zuzugreifen, das von dieser Memberfunktion zurückgegeben wird, verwenden Sie `pr.second`.  
  
### <a name="remarks"></a>Hinweise  
 Durch diese Funktion werden keine Iteratoren oder Verweise ungültig.  
  
 Wird bei der Einfügung eine Ausnahme ausgelöst, die aber in der Hashfunktion des Containers nicht auftritt, wird der Container nicht geändert. Wenn die Ausnahme in der Hashfunktion ausgelöst wird, ist das Ergebnis nicht definiert.  
  
 Ein Codebeispiel finden Sie unter [set::emplace](../standard-library/set-class.md#emplace).  
  
##  <a name="emplace_hint"></a> unordered_set::emplace_hint  
 Fügt ein Element mit einem Platzierungshinweis ein, das vor Ort erstellt wird (Es werden keine Kopier- oder Verschiebevorgänge ausgeführt).  
  
```  
template <class... Args>  
iterator emplace_hint(
const_iteratorwhere,  
Args&&... args);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`args`|Die Argumente, die weitergeleitet werden, um ein Element zu erstellen, das in das unordered_set-Element eingefügt werden soll, es sei denn, das unordened_set-Element erhält bereits das Element, oder allgemeiner: ein Element, dessen Schlüssel gleichwertig sortiert wird, ist bereits erhalten.|  
|`where`|Ein Hinweis bezüglich des Platzes, an dem mit der Suche nach dem richtigen Einfügepunkt begonnen wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator zum neu eingefügten Element.  
  
 Wenn die Einfügung fehlerhaft war, da das Element bereits vorhanden ist, wird ein Iterator an das vorhandene Element zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Durch diese Funktion werden keine Iteratoren oder Verweise ungültig.  
  
 Wird bei der Einfügung eine Ausnahme ausgelöst, die aber in der Hashfunktion des Containers nicht auftritt, wird der Container nicht geändert. Wenn die Ausnahme in der Hashfunktion ausgelöst wird, ist das Ergebnis nicht definiert.  
  
 Ein Codebeispiel finden Sie unter [set::emplace_hint](../standard-library/set-class.md#emplace_hint).  
  
##  <a name="empty"></a> unordered_set::empty  
 Testet, ob keine Elemente vorhanden sind.  
  
```  
bool empty() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt „true“ für eine leere gesteuerte Sequenz zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_empty.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // clear the container and reinspect  
    c1.clear();  
    std::cout << "size == " << c1.size() << std::endl;  
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
    std::cout << std::endl;  
      
    c1.insert('d');  
    c1.insert('e');  
      
    // display contents " [e] [d]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    std::cout << "size == " << c1.size() << std::endl;  
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
size == 0  
empty() == true  
 [e] [d]  
size == 2  
empty() == false  
```  
  
##  <a name="end"></a> unordered_set::end  
 Legt das Ende der kontrollierten Sequenz fest.  
  
```  
iterator end();  
  
const_iterator end() const;  
  
local_iterator end(size_type nbucket);  
  
const_local_iterator end(size_type nbucket) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`nbucket`|Die Bucketnummer.|  
  
### <a name="remarks"></a>Hinweise  
 Die ersten beiden Memberfunktionen geben einen Vorwärtsiterator zurück, der direkt hinter das Ende der Sequenz verweist. Die letzten beiden Memberfunktionen geben einen Vorwärtsiterator zurück, der direkt hinter von Bucket `nbucket` verweist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_end.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // inspect last two items " [a] [b]"  
    Myset::iterator it2 = c1.end();  
    --it2;  
    std::cout << " [" << *it2 << "]";  
    --it2;  
    std::cout << " [" << *it2 << "]";  
    std::cout << std::endl;  
      
    // inspect bucket containing 'a'  
    Myset::const_local_iterator lit = c1.end(c1.bucket('a'));  
    --lit;  
    std::cout << " [" << *lit << "]";  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
 [a] [b]  
 [a]  
```  
  
##  <a name="equal_range"></a> unordered_set::equal_range  
 Sucht den Bereich, der einem angegebenen Schlüssel entspricht.  
  
```  
std::pair<iterator, iterator>  
equal_range(const Key& keyval);

std::pair<const_iterator, const_iterator>  
equal_range(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parameter  
 `keyval`  
 Der zu suchende Schlüsselwert.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt ein Paar von Iteratoren `X` so, dass`[X.first, X.second)` nur die Elemente der gesteuerten Sequenz, die über entsprechende Sortierung mit begrenzt `keyval`. Wenn keine solchen Elemente vorhanden sind, sind beide Iteratoren `end()`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_equal_range.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // display results of failed search  
    std::pair<Myset::iterator, Myset::iterator> pair1 =  
    c1.equal_range('x');  
    std::cout << "equal_range('x'):";  
    for (; pair1.first != pair1.second; ++pair1.first)  
        std::cout << " [" << *pair1.first << "]";  
    std::cout << std::endl;  
      
    // display results of successful search  
    pair1 = c1.equal_range('b');  
    std::cout << "equal_range('b'):";  
    for (; pair1.first != pair1.second; ++pair1.first)  
        std::cout << " [" << *pair1.first << "]";  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
equal_range('x'):  
equal_range('b'): [b]  
```  
  
##  <a name="erase"></a> unordered_set::erase  
 Es wird ein Element oder ein Bereich von Elementen in einem unordered_set-Element von angegebenen Speicherorten entfernt oder es werden die einem angegebenen Schlüssel entsprechenden Elemente entfernt.  
  
```  
iterator erase(const_iterator Where);

iterator erase(const_iterator First, const_iterator Last);

size_type erase(const key_type& Key);
```  
  
### <a name="parameters"></a>Parameter  
 `Where`  
 Die Position des zu entfernenden Elements.  
  
 `First`  
 Die Position des ersten zu entfernenden Elements.  
  
 `Last`  
 Die Position direkt hinter dem letzten zu entfernenden Element.  
  
 `Key`  
 Der Schlüsselwert der zu entfernenden Elemente.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei den ersten beiden Memberfunktionen ist es ein bidirektionaler Iterator, der das erste über die entfernten Elemente hinaus verbliebe Element festlegt, oder ein Element, das das Ende des unordered_set-Elements darstellt, wenn kein solches Element vorhanden ist.  
  
 Für die dritte Memberfunktion wird die Anzahl der aus dem unordered_set-Element entfernten Elemente zurück gegeben.  
  
### <a name="remarks"></a>Hinweise  
 Ein Codebeispiel finden Sie unter [set::erase](../standard-library/set-class.md#erase).  
  
##  <a name="find"></a> unordered_set::find  
 Sucht ein Element, das einem angegebenen Schlüssel entspricht.  
  
```  
const_iterator find(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Parameter  
 `keyval`  
 Der zu suchende Schlüsselwert.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [unordered_set::equal_range](#equal_range)`(keyval).first` zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_find.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // try to find and fail  
    std::cout << "find('A') == "  
    << std::boolalpha << (c1.find('A') != c1.end()) << std::endl;  
      
    // try to find and succeed  
    Myset::iterator it = c1.find('b');  
    std::cout << "find('b') == "  
    << std::boolalpha << (it != c1.end())  
    << ": [" << *it << "]" << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
find('A') == false  
find('b') == true: [b]  
```  
  
##  <a name="get_allocator"></a> unordered_set::get_allocator  
 Ruft das gespeicherte Zuweisungsobjekt ab.  
  
```  
Alloc get_allocator() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt das gespeicherte Zuweisungsobjekt zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_get_allocator.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
typedef std::allocator<std::pair<const char, int> > Myalloc;  
int main()  
{  
    Myset c1;  
      
    Myset::allocator_type al = c1.get_allocator();  
    std::cout << "al == std::allocator() is "  
    << std::boolalpha << (al == Myalloc()) << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
al == std::allocator() is true  
```  
  
##  <a name="hash"></a> unordered_set::hash_function  
 Ruft das gespeicherte Hashfunktionsobjekt ab.  
  
```  
Hash hash_function() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt das gespeicherte Hashfunktionsobjekt zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_hash_function.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    Myset::hasher hfn = c1.hash_function();  
    std::cout << "hfn('a') == " << hfn('a') << std::endl;  
    std::cout << "hfn('b') == " << hfn('b') << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
hfn('a') == 1630279  
hfn('b') == 1647086  
```  
  
##  <a name="hasher"></a> unordered_set::hasher  
 Der Typ der Hashfunktion.  
  
```  
typedef Hash hasher;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Hash` dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_hasher.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    Myset::hasher hfn = c1.hash_function();  
    std::cout << "hfn('a') == " << hfn('a') << std::endl;  
    std::cout << "hfn('b') == " << hfn('b') << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
hfn('a') == 1630279  
hfn('b') == 1647086  
```  
  
##  <a name="insert"></a> unordered_set::insert  
 Fügt ein Element oder einen Bereich von Elementen in ein unordered_set-Element ein.  
  
```  
// (1) single element  
pair<iterator, bool> insert(const value_type& Val);
  
// (2) single element, perfect forwarded  
template <class ValTy>  
pair<iterator, bool> insert(ValTy&& Val);
 
// (3) single element with hint  
iterator insert(const_iterator Where, const value_type& Val);
 
// (4) single element, perfect forwarded, with hint  
template <class ValTy>  
iterator insert(const_iterator Where, ValTy&& Val);
 
// (5) range  
template <class InputIterator>  
void insert(InputIterator First, InputIterator Last);
 
// (6) initializer list  
void insert(initializer_list<value_type> IList);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`Val`|Der Wert eines in das unordered_set-Element einzufügenden Elements, es sei denn, es ist bereits ein Element enthalten, dessen Schlüssel gleichwertig sortiert wird.|  
|`Where`|Die Position, an dem mit der Suche nach dem richtigen Einfügepunkt begonnen wird.|  
|`ValTy`|Vorlagenparameter, der den Argumenttyp angegeben wird, das unordered_set-Element verwendet werden können, so erstellen Sie ein Element von[Value_type](../standard-library/map-class.md#value_type), und perfekt `Val` als Argument.|  
|`First`|Die Position des ersten zu kopierenden Elements.|  
|`Last`|Die Position direkt über den letzten zu kopierenden Elements.|  
|`InputIterator`|Das Vorlagenfunktionsargument, das den Anforderungen eines [Eingabeiterators](../standard-library/input-iterator-tag-struct.md) erfüllt, der auf Elemente eines Typs zeigt, der zum Erstellen von [value_type](../standard-library/map-class.md#value_type)-Objekten verwendet werden kann.|  
|`IList`|Ein [initializer_list](../standard-library/initializer-list.md)-Element, aus dem die Elemente kopiert werden sollen.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Einzelelement-Memberfunktionen (1) und (2), Zurückgeben einer[Paar](../standard-library/pair-structure.md) , deren `bool` Komponente ist "true", wenn eine Einfügung erfolgte und "false", wenn das unordered_set-Element bereits ein Element enthalten, dessen Schlüssel einen entsprechenden Wert in der Sortierung. Die Iteratorkomponente des Rückgabewertpaars zeigt auf das neu eingefügten Element, wenn die `bool`-Komponente "true" lautet, oder auf das vorhandene Element, wenn die `bool`-Komponente "false" lautet.  
  
 Die Einzelelement-Memberfunktionen mit Hinweis (3) und (4) geben einen Iterator zurück, der auf die Position zeigt, an der das neue Element in das unordered_set-Element eingefügt wurde, oder, falls ein Element mit einem entsprechenden Schlüssel bereits vorhanden ist, auf das vorhandene Element.  
  
### <a name="remarks"></a>Hinweise  
 Durch diese Funktion werden keine Iteratoren, Zeiger oder Verweise ungültig.  
  
 Wird beim Einfügen von nur einem Element eine Ausnahme ausgelöst, die jedoch nicht in der Hashfunktion des Containers auftritt, wird der Zustand des Containers nicht geändert. Wenn die Ausnahme in der Hashfunktion ausgelöst wird, ist das Ergebnis nicht definiert. Wird beim Einfügen mehrerer Elementen eine Ausnahme ausgelöst, wird der Container in einem nicht angegebenen doch gültigen Zustand belassen.  
  
 Die iteratorkomponente des Zugriff auf eine `pair` `pr` , die von den Einzelelement-Memberfunktionen zurückgegeben wird, verwenden Sie `pr.first`; um den Iterator im zurückgegebenen Paar zu dereferenzieren, verwenden`*pr.first`, erhalten Sie ein Element. Um auf die `bool`-Komponente zuzugreifen, verwenden Sie `pr.second`. Eine Beispiel finden Sie unter Beispielcode weiter unten in diesem Artikel.  
  
 Die[Value_type](../standard-library/map-class.md#value_type) eines Containers ist eine Typedef, die dem Container, und beim Satz angehört `unordered_set<V>::value_type` Typ `const V`.  
  
 Die Bereichsmemberfunktion (5) fügt die Sequenz von Elementwerten in ein unordered_set-Element ein, das jedem Element entspricht, das von einem Iterator im Bereich `[First, Last)` adressiert wird. Daher wird `Last` nicht eingefügt. Die Containermemberfunktion `end()` bezieht sich auf die Position direkt hinter dem letzten Element im Container. Z. B versucht die Anweisung `s.insert(v.begin(), v.end());` alle Elemente von `v` in `s` einzufügen. Nur Elemente, die eindeutige Werte im Bereich aufweisen werden eingefügt. Duplikate werden ignoriert. Um zu betrachten welche Elemente abgelehnt werden, verwenden Sie die Einzelelementversionen von `insert`.  
  
 Die Memberfunktion für die Initialisiererliste (6) verwendet eine [initializer_list](../standard-library/initializer-list.md), um Elemente in das unordered_set-Element zu kopieren.  
  
 Zum Einfügen eines Elements, das vor Ort erstellt wird – d. h. keine kopieren- oder Verschiebevorgänge werden ausgeführt, finden Sie unter[set::emplace](../standard-library/set-class.md#emplace) und[set::emplace_hint](../standard-library/set-class.md#emplace_hint).  
  
 Ein Codebeispiel finden Sie unter [set::insert](../standard-library/set-class.md#insert).  
  
##  <a name="iterator"></a> unordered_set::iterator  
 Ein Typ, der einen konstanten [Forward-Iterator](../standard-library/forward-iterator-tag-struct.md) bereitstellt, der Elemente in einem unordered_set-Element lesen kann.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="example"></a>Beispiel  
  Im Beispiel für [begin](../standard-library/set-class.md#begin) wird verdeutlicht, wie ein **Iterator** deklariert und verwendet wird.  
  
##  <a name="key_eq"></a> unordered_set::key_eq  
 Ruft das gespeicherte Vergleichsfunktionsobjekt ab.  
  
```  
Pred key_eq() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt das gespeicherte Vergleichsfunktionsobjekt zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_key_eq.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    Myset::key_equal cmpfn = c1.key_eq();  
    std::cout << "cmpfn('a', 'a') == "  
    << std::boolalpha << cmpfn('a', 'a') << std::endl;  
    std::cout << "cmpfn('a', 'b') == "  
    << std::boolalpha << cmpfn('a', 'b') << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
cmpfn('a', 'a') == true  
cmpfn('a', 'b') == false  
```  
  
##  <a name="key_equal"></a> unordered_set::key_equal  
 Der Typ der Vergleichsfunktion.  
  
```  
typedef Pred key_equal;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Pred` dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_key_equal.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    Myset::key_equal cmpfn = c1.key_eq();  
    std::cout << "cmpfn('a', 'a') == "  
    << std::boolalpha << cmpfn('a', 'a') << std::endl;  
    std::cout << "cmpfn('a', 'b') == "  
    << std::boolalpha << cmpfn('a', 'b') << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
cmpfn('a', 'a') == true  
cmpfn('a', 'b') == false  
```  
  
##  <a name="key_type"></a> unordered_set::key_type  
 Der Typ eines Sortierschlüssels.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Key` dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_key_type.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // add a value and reinspect  
    Myset::key_type key = 'd';  
    Myset::value_type val = key;  
    c1.insert(val);  
      
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
 [d] [c] [b] [a]  
```  
  
##  <a name="load_factor"></a> unordered_set::load_factor  
 Zählt die durchschnittliche Anzahl von Elementen pro Bucket.  
  
```  
float load_factor() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt `(float)`[unordered_set::size](#size)`() / (float)`[unordered_set::bucket_count](#bucket_count)`()` zurück, also die durchschnittliche Anzahl von Elementen pro Bucket.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_load_factor.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // inspect current parameters  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    // change max_load_factor and redisplay  
    c1.max_load_factor(0.10f);  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    // rehash and redisplay  
    c1.rehash(100);  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
```  
  
##  <a name="local_iterator"></a> unordered_set::local_iterator  
 Der Typ eines Bucketiterators.  
  
```  
typedef T4 local_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt, das als ein Vorwärtsiterator für ein Bucket dienen kann. Er wird hier als Synonym für einen durch Implementierung definierten `T4`-Typ beschrieben.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_local_iterator.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // inspect bucket containing 'a'  
    Myset::local_iterator lit = c1.begin(c1.bucket('a'));  
    std::cout << " [" << *lit << "]";  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
 [a]  
```  
  
##  <a name="max_bucket_count"></a> unordered_set::max_bucket_count  
 Ruft die maximale Anzahl von Buckets ab.  
  
```  
size_type max_bucket_count() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die maximale Anzahl von Buckets zurück, die derzeit zulässig ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_max_bucket_count.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // inspect current parameters  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    // change max_load_factor and redisplay  
    c1.max_load_factor(0.10f);  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    // rehash and redisplay  
    c1.rehash(100);  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
```  
  
##  <a name="max_load_factor"></a> unordered_set::max_load_factor  
 Ruft die maximale Anzahl von Elementen pro Bucket ab oder legt sie fest.  
  
```  
float max_load_factor() const;
 
void max_load_factor(float factor);
```  
  
### <a name="parameters"></a>Parameter  
 `factor`  
 Der neue maximale Lastfaktor.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion gibt den gespeicherten maximalen Lastfaktor zurück. Die zweite Memberfunktion ersetzt den gespeicherten maximalen Lastfaktor durch `factor`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_max_load_factor.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // inspect current parameters  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    // change max_load_factor and redisplay  
    c1.max_load_factor(0.10f);  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    // rehash and redisplay  
    c1.rehash(100);  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_bucket_count() == "  
    << c1.max_bucket_count() << std::endl;  
    std::cout << "max_load_factor() == "  
    << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
```  
  
##  <a name="max_size"></a> unordered_set::max_size  
 Ruft die maximale Größe der gesteuerten Sequenz ab.  
  
```  
size_type max_size() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Länge der längsten Sequenz zurück, die das Objekt steuern kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_max_size.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    std::cout << "max_size() == " << c1.max_size() << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
max_size() == 4294967295  
```  
  
##  <a name="op_eq"></a> unordered_set::operator=  
 Kopiert eine Hashtabelle.  
  
```  
unordered_set& operator=(const unordered_set& right);

unordered_set& operator=(unordered_set&& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`right`|Die[Unordered_set](../standard-library/unordered-set-class.md) kopiert werden, in der `unordered_set`.|  
  
### <a name="remarks"></a>Hinweise  
 Nachdem ein vorhandenes Element in einem `unordered_set` gelöscht wurde, kopiert oder verschiebt `operator=` den Inhalt von `right` in den `unordered_set`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// unordered_set_operator_as.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
int main( )  
{  
    using namespace std;  
    unordered_set<int> v1, v2, v3;  
    unordered_set<int>::iterator iter;  
      
    v1.insert(10);  
      
    cout << "v1 = " ;  
    for (iter = v1.begin(); iter != v1.end(); iter++)  
        cout << *iter << " ";  
    cout << endl;  
      
    v2 = v1;  
    cout << "v2 = ";  
    for (iter = v2.begin(); iter != v2.end(); iter++)  
        cout << *iter << " ";  
    cout << endl;  
      
    // move v1 into v2  
    v2.clear();  
    v2 = move(v1);  
    cout << "v2 = ";  
    for (iter = v2.begin(); iter != v2.end(); iter++)  
        cout << *iter << " ";  
    cout << endl;  
}  
```  
  
##  <a name="pointer"></a> unordered_set::pointer  
 Der Typ eines Zeigers auf ein Element.  
  
```  
typedef Alloc::pointer pointer;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt, das als Zeiger auf ein Element der gesteuerten Sequenz fungieren kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_pointer.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
    {  
        Myset::key_type key = *it;  
        Myset::pointer p = &key;  
        std::cout << " [" << *p << "]";  
    }  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
```  
  
##  <a name="reference"></a> unordered_set::reference  
 Der Typ eines Verweises auf ein Element.  
  
```  
typedef Alloc::reference reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt, das als Verweis auf ein Element der gesteuerten Sequenz fungieren kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_reference.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)  
    {  
        Myset::key_type key = *it;  
        Myset::reference ref = key;  
        std::cout << " [" << ref << "]";  
    }  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
```  
  
##  <a name="rehash"></a> unordered_set::rehash  
 Erstellt die Hashtabelle neu.  
  
```  
void rehash(size_type nbuckets);
```  
  
### <a name="parameters"></a>Parameter  
 `nbuckets`  
 Die angeforderte Anzahl von Buckets.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion ändert die Anzahl der Buckets in mindestens `nbuckets` und erstellt ggf. die Hashtabelle neu.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_rehash.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // inspect current parameters  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    // change max_load_factor and redisplay  
    c1.max_load_factor(0.10f);  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;  
    std::cout << std::endl;  
      
    // rehash and redisplay  
    c1.rehash(100);  
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;  
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;  
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
bucket_count() == 8  
load_factor() == 0.375  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_load_factor() == 0.1  
```  
  
##  <a name="size"></a> unordered_set::size  
 Ermittelt die Anzahl von Elementen.  
  
```  
size_type size() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Länge der gesteuerten Sequenz zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_size.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // clear the container and reinspect  
    c1.clear();  
    std::cout << "size == " << c1.size() << std::endl;  
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
    std::cout << std::endl;  
      
    c1.insert('d');  
    c1.insert('e');  
      
    // display contents " [e] [d]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    std::cout << "size == " << c1.size() << std::endl;  
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
size == 0  
empty() == true  
  
 [e] [d]  
size == 2  
empty() == false  
```  
  
##  <a name="size_type"></a> unordered_set::size_type  
 Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.  
  
```  
typedef T2 size_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der unsignierte Ganzzahltyp beschreibt ein Objekt, das die Länge jeder kontrollierten Sequenz darstellen kann. Er wird hier als Synonym für einen durch Implementierung definierten `T2`-Typ beschrieben.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_size_type.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
    Myset::size_type sz = c1.size();  
      
    std::cout << "size == " << sz << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
size == 0  
```  
  
##  <a name="swap"></a> unordered_set::swap  
 Vertauscht den Inhalt von zwei Containern.  
  
```  
void swap(unordered_set& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Der Container für den Tauschvorgang.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion tauscht die kontrollierten Sequenzen zwischen `*this` und `right`aus. Wenn [unordered_set::get_allocator](#get_allocator)`() == right.get_allocator()`, sie führt dies in konstanter Zeit, sie löst eine Ausnahme nur durch Kopieren des gespeicherter merkmalobjekts vom Typ `Tr`, und sie macht keine Verweise, Zeiger, ungültig oder Iteratoren, die Elemente in den beiden kontrollierten Sequenzen bestimmen. Andernfalls führt Sie proportional zur Anzahl der Elemente in den beiden kontrollierten Sequenzen eine Reihe von Elementzuweisungen und Konstruktoraufrufe aus.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_swap.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    Myset c2;  
      
    c2.insert('d');  
    c2.insert('e');  
    c2.insert('f');  
      
    c1.swap(c2);  
      
    // display contents " [f] [e] [d]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    swap(c1, c2);  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
 [f] [e] [d]  
 [c] [b] [a]  
```  
  
##  <a name="unordered_set"></a> unordered_set::unordered_set  
 Erstellt ein container-Objekt.  
  
```  
unordered_set(const unordered_set& Right);

explicit unordered_set(
    size_typebucket_count = N0,  
    const Hash& Hash = Hash(),  
    const Comp& Comp = Comp(),  
    const Allocator& Al = Alloc());

unordered_set(unordered_set&& Right);

unordered_set(initializer_list<Type> IList);

unordered_set(initializer_list<Type> IList, size_typebucket_count);

unordered_set(
    initializer_list<Type> IList,  
    size_typebucket_count,  
    const Hash& Hash);

unordered_set(
    initializer_list<Type> IList,  
    size_typebucket_count,  
    const Hash& Hash,  
    const Comp& Comp);

unordered_set(
    initializer_list<Type> IList,  
    size_typebucket_count,  
    const Hash& Hash,  
    const Comp& Comp,  
    const Allocator& Al);

template <class InputIterator>  
unordered_set(
    InputIteratorfirst,  
    InputIteratorlast,  
    size_typebucket_count = N0,  
    const Hash& Hash = Hash(),  
    const Comp& Comp = Comp(),  
    const Allocator& Al = Alloc());
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`InputIterator`|Der Iteratortyp.|  
|`Al`|Das zu speichernde Zuweisungsobjekt.|  
|`Comp`|Das zu speichernde Vergleichsfunktionsobjekt.|  
|`Hash`|Das zu speichernde Hashfunktionsobjekt.|  
|`bucket_count`|Die Mindestanzahl von Buckets.|  
|`Right`|Der zu kopierende Container.|  
|`IList`|Das initializer_list-Element, in dem die zu kopierenden Elemente enthalten sind.|  
  
### <a name="remarks"></a>Hinweise  
 Mit dem ersten Konstruktor wird eine Kopie der Sequenz angegeben, die von `Right` gesteuert wird. Mit dem zweiten Konstruktor wird eine leere gesteuerte Sequenz angegeben. Der dritte Konstruktor gibt eine Kopie der Sequenz an, indem `Right` verschoben wird. Der vierte bis achte Konstruktor verwendet ein initializer_list-Element, um die zu kopierenden Elemente anzugeben. Mit dem neunten Konstruktor wird die Elementwertesequenz `[first, last)` eingefügt.  
  
 Alle Konstruktoren initialisieren auch einige gespeicherte Werte. Für den Kopierkonstruktor werden die Werte aus `Right` abgerufen. Andernfalls gilt:  
  
 Die Mindestbucketanzahl entspricht dem Argument `bucket_count`, falls es vorhanden ist. Andernfalls ist es ein Standardwert, der hier als der durch die Implementierung definierte Wert `N0` beschrieben wird.  
  
 Das Hashfunktionsobjekt ist das Argument `Hash`, falls es vorhanden ist. Andernfalls ist es `Hash()`.  
  
 Das Vergleichfunktionsobjekt ist das Argument `Comp`, falls es vorhanden ist. Andernfalls ist es `Comp()`.  
  
 Das Zuweisungsobjekt ist das Argument `Al`, falls es vorhanden ist. Andernfalls ist es `Alloc()`.  
  
##  <a name="value_type"></a> unordered_set::value_type  
 Der Typ eines Elements.  
  
```  
typedef Key value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Element der gesteuerten Sequenz.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__unordered_set__unordered_set_value_type.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
    Myset c1;  
      
    c1.insert('a');  
    c1.insert('b');  
    c1.insert('c');  
      
    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    // add a value and reinspect  
    Myset::key_type key = 'd';  
    Myset::value_type val = key;  
    c1.insert(val);  
      
    for (Myset::const_iterator it = c1.begin(); it != c1.end(); ++it)  
        std::cout << " [" << *it << "]";  
    std::cout << std::endl;  
      
    return (0);  
}  
```  
  
```Output  
 [c] [b] [a]  
 [d] [c] [b] [a]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [<unordered_set>](../standard-library/unordered-set.md)   
 [Containers](../cpp/containers-modern-cpp.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)

