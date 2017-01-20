---
title: "unordered_multiset-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "tr1::unordered_multiset"
  - "std::tr1::unordered_multiset"
  - "unordered_multiset"
  - "std.tr1.unordered_multiset"
  - "unordered_set/std::tr1::unordered_multiset"
  - "tr1.unordered_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_multiset-Klasse"
  - "unordered_multiset-Klasse [TR1]"
ms.assetid: 70c8dfc5-492a-4af2-84f5-1aa9cb04b71c
caps.latest.revision: 24
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# unordered_multiset-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge vom Typ `const Key` steuert.  Die Sequenz wird grob durch eine Hashfunktion sortiert, die die Sequenz in eine geordnete Gruppe von Untersequenzen, so genannte Buckets, unterteilt.  Innerhalb jedes Buckets bestimmt eine Vergleichsfunktion, ob ein Elementpaar eine entsprechende Reihenfolge hat.  Jedes Element dient sowohl als Sortierschlüssel als auch als Wert.  Die Sequenz wird so dargestellt, dass die Suche, das Einfügen und das Entfernen eines beliebigen Elements mit einer Reihen von Vorgängen möglich ist, die unabhängig von der Anzahl von Elementen in der Sequenz \(konstante Zeit\) sein können, zumindest, wenn alle Buckets von ungefähr gleicher Länge sind.  Im schlimmsten Fall, d. h., wenn sich alle Elemente in einem Bucket befinden, ist die Anzahl von Vorgängen proportional zur Anzahl von Elementen in der Sequenz \(lineare Zeit\).  Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
## Syntax  
  
```  
template<class Key,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_multiset;  
```  
  
#### Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`Key`|Der Schlüsseltyp.|  
|`Hash`|Der Hashfunktionsobjekttyp.|  
|`Pred`|Der Gleichheitsvergleich\-Funktionsobjekttyp.|  
|`Alloc`|Die Zuweisungsklasse.|  
  
## Member  
  
|||  
|-|-|  
|Typdefinition|Beschreibung|  
|[unordered\_multiset::allocator\_type](../Topic/unordered_multiset::allocator_type.md)|Der Typ einer Zuweisung für die Speicherverwaltung.|  
|[unordered\_multiset::const\_iterator](../Topic/unordered_multiset::const_iterator.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[unordered\_multiset::const\_local\_iterator](../Topic/unordered_multiset::const_local_iterator.md)|Der Typ eines konstanten Bucketiterators für die gesteuerte Sequenz.|  
|[unordered\_multiset::const\_pointer](../Topic/unordered_multiset::const_pointer.md)|Der Typ eines konstanten Zeigers auf ein Element.|  
|[unordered\_multiset::const\_reference](../Topic/unordered_multiset::const_reference.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[unordered\_multiset::difference\_type](../Topic/unordered_multiset::difference_type.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[unordered\_multiset::hasher](../Topic/unordered_multiset::hasher.md)|Der Typ der Hashfunktion.|  
|[unordered\_multiset::iterator](../Topic/unordered_multiset::iterator.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[unordered\_multiset::key\_equal](../Topic/unordered_multiset::key_equal.md)|Der Typ der Vergleichsfunktion.|  
|[unordered\_multiset::key\_type](../Topic/unordered_multiset::key_type.md)|Der Typ eines Sortierschlüssels.|  
|[unordered\_multiset::local\_iterator](../Topic/unordered_multiset::local_iterator.md)|Der Typ eines Bucketiterators für die gesteuerte Sequenz.|  
|[unordered\_multiset::pointer](../Topic/unordered_multiset::pointer.md)|Der Typ eines Zeigers auf ein Element.|  
|[unordered\_multiset::reference](../Topic/unordered_multiset::reference.md)|Der Typ eines Verweises auf ein Element.|  
|[unordered\_multiset::size\_type](../Topic/unordered_multiset::size_type.md)|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|[unordered\_multiset::value\_type](../Topic/unordered_multiset::value_type.md)|Der Typ eines Elements.|  
  
|||  
|-|-|  
|Memberfunktion|Beschreibung|  
|[unordered\_multiset::begin](../Topic/unordered_multiset::begin.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[unordered\_multiset::bucket](../Topic/unordered_multiset::bucket.md)|Ruft die Bucketnummer für einen Schlüsselwert ab.|  
|[unordered\_multiset::bucket\_count](../Topic/unordered_multiset::bucket_count.md)|Ruft die Anzahl von Buckets ab.|  
|[unordered\_multiset::bucket\_size](../Topic/unordered_multiset::bucket_size.md)|Ruft die Größe eines Buckets ab.|  
|[unordered\_multiset::cbegin](../Topic/unordered_multiset::cbegin.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[unordered\_multiset::cend](../Topic/unordered_multiset::cend.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[unordered\_multiset::clear](../Topic/unordered_multiset::clear.md)|Entfernt alle Elemente.|  
|[unordered\_multiset::count](../Topic/unordered_multiset::count.md)|Sucht die Anzahl von Elementen, die einem angegebenen Schlüssel entsprechen.|  
|[unordered\_multiset::emplace](../Topic/unordered_multiset::emplace.md)|Fügt ein Element hinzu, das direkt erstellt wird.|  
|[unordered\_multiset::emplace\_hint](../Topic/unordered_multiset::emplace_hint.md)|Fügt ein Element hinzu, das direkt mit Hinweis erstellt wird.|  
|[unordered\_multiset::empty](../Topic/unordered_multiset::empty.md)|Testet, ob keine Elemente vorhanden sind.|  
|[unordered\_multiset::end](../Topic/unordered_multiset::end.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[unordered\_multiset::equal\_range](../Topic/unordered_multiset::equal_range.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[unordered\_multiset::erase](../Topic/unordered_multiset::erase.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[unordered\_multiset::find](../Topic/unordered_multiset::find.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[unordered\_multiset::get\_allocator](../Topic/unordered_multiset::get_allocator.md)|Ruft das gespeicherte Zuweisungsobjekt ab.|  
|[unordered\_multiset::hash\_function](../Topic/unordered_multiset::hash_function.md)|Ruft das gespeicherte Hashfunktionsobjekt ab.|  
|[unordered\_multiset::insert](../Topic/unordered_multiset::insert.md)|Fügt Elemente hinzu.|  
|[unordered\_multiset::key\_eq](../Topic/unordered_multiset::key_eq.md)|Ruft das gespeicherte Vergleichsfunktionsobjekt ab.|  
|[unordered\_multiset::load\_factor](../Topic/unordered_multiset::load_factor.md)|Zählt die durchschnittliche Anzahl von Elementen pro Bucket.|  
|[unordered\_multiset::max\_bucket\_count](../Topic/unordered_multiset::max_bucket_count.md)|Ruft die maximale Anzahl von Buckets ab.|  
|[unordered\_multiset::max\_load\_factor](../Topic/unordered_multiset::max_load_factor.md)|Ruft die maximale Anzahl von Elementen pro Bucket ab oder legt sie fest.|  
|[unordered\_multiset::max\_size](../Topic/unordered_multiset::max_size.md)|Ruft die maximale Größe der gesteuerten Sequenz ab.|  
|[unordered\_multiset::rehash](../Topic/unordered_multiset::rehash.md)|Erstellt die Hashtabelle neu.|  
|[unordered\_multiset::size](../Topic/unordered_multiset::size.md)|Ermittelt die Anzahl von Elementen.|  
|[unordered\_multiset::swap](../Topic/unordered_multiset::swap.md)|Vertauscht den Inhalt von zwei Containern.|  
|[unordered\_multiset::unordered\_multiset](../Topic/unordered_multiset::unordered_multiset.md)|Erstellt ein container\-Objekt.|  
  
|||  
|-|-|  
|Operator|Beschreibung|  
|[unordered\_multiset::operator\=](../Topic/unordered_multiset::operator=.md)|Kopiert eine Hashtabelle.|  
  
## Hinweise  
 Das Objekt sortiert die Sequenz, die es steuert, indem es zwei gespeicherte Objekte aufruft, ein Vergleichsfunktionsobjekt des Typs [unordered\_multiset::key\_equal](../Topic/unordered_multiset::key_equal.md) und ein Hashfunktionsobjekt des Typs [unordered\_multiset::hasher](../Topic/unordered_multiset::hasher.md).  Sie greifen auf das zuerst gespeicherte Objekt zu, indem Sie die Memberfunktion [unordered\_multiset::key\_eq](../Topic/unordered_multiset::key_eq.md) aufrufen`()`. Auf das zweite gespeicherte Objekt greifen Sie zu, indem Sie die Memberfunktion [unordered\_multiset::hash\_function](../Topic/unordered_multiset::hash_function.md)`()` aufrufen.  Insbesondere für alle Werte `X` und `Y` vom Typ `Key` gibt der Aufruf von `key_eq()(X, Y)` nur "true" zurück, wenn die beiden Argumentwerte die entsprechende Reihenfolge aufweisen. Der Aufruf von `hash_function()(keyval)` ergibt eine Verteilung von Werten des Typs `size_t`.  Im Gegensatz zur Vorlagenklasse [unordered\_set\-Klasse](../standard-library/unordered-set-class.md) stellt ein Objekt der Vorlagenklasse `unordered_multiset` nicht sicher, dass `key_eq()(X, Y)` für zwei Elemente der gesteuerten Sequenz immer "false" ist. \(Die Schlüssel müssen nicht eindeutig sein.\)  
  
 Das Objekt speichert auch einen Höchstlastfaktor, der die maximal erwünschte durchschnittliche Anzahl von Elementen pro Bucket angibt.  Wenn durch Einfügen eines Elements der Wert [unordered\_multiset::load\_factor](../Topic/unordered_multiset::load_factor.md)`()` den Höchstlastfaktor überschreitet, erhöht der Container die Anzahl von Buckets und erstellt die Hashtabelle nach Bedarf neu.  
  
 Die tatsächliche Reihenfolge der Elemente in der gesteuerten Sequenz hängt von der Hashfunktion, von der Vergleichsfunktion, von der Einfügereihenfolge, vom Höchstlastfaktor und von der aktuellen Anzahl von Buckets ab.  Sie können die Reihenfolge der Elemente in der gesteuerten Sequenz im Allgemeinen nicht vorhersagen.  Sie können allerdings sicher sein, dass jede Teilmenge von Elementen, die die entsprechende Reihenfolge aufweisen, in der gesteuerten Sequenz benachbart sind.  
  
 Das Objekt belegt Speicher und gibt Speicher für die gesteuerte Sequenz durch ein gespeichertes Zuweisungsobjekt des Typs [unordered\_multiset::allocator\_type](../Topic/unordered_multiset::allocator_type.md) frei.  Ein solches Zuweisungsobjekt muss die gleiche externe Schnittstelle wie ein Objekt der Vorlagenklasse `allocator` aufweisen.  Beachten Sie, dass das gespeicherte Zuweisungsobjekt nicht kopiert wird, wenn das Containerobjekt zugewiesen wird.  
  
## Anforderungen  
 **Header:** \<unordered\_set\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<unordered\_set\>](../standard-library/unordered-set.md)   
 [Container](../cpp/containers-modern-cpp.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)