---
title: "unordered_multimap-Klasse"
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
  - "unordered_map/std::tr1::unordered_multimap"
  - "tr1.unordered_multimap"
  - "unordered_multimap"
  - "std.tr1.unordered_multimap"
  - "tr1::unordered_multimap"
  - "std::tr1::unordered_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_multimap-Klasse"
  - "unordered_multimap-Klasse [TR1]"
ms.assetid: 4baead6c-5870-4b85-940f-a47d6b891c27
caps.latest.revision: 28
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# unordered_multimap-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge vom Typ `std::pair<const Key, Ty>` steuert.  Die Sequenz wird grob durch eine Hashfunktion sortiert, die die Sequenz in eine geordnete Gruppe von Untersequenzen, so genannte Buckets, unterteilt.  Innerhalb jedes Buckets bestimmt eine Vergleichsfunktion, ob ein Elementpaar eine entsprechende Reihenfolge hat.  Jedes Element speichert zwei Objekte, einen Sortierschlüssel und einen Wert.  Die Sequenz wird so dargestellt, dass die Suche, das Einfügen und das Entfernen eines beliebigen Elements mit einer Reihen von Vorgängen möglich ist, die unabhängig von der Anzahl von Elementen in der Sequenz \(konstante Zeit\) sein können, zumindest, wenn alle Buckets von ungefähr gleicher Länge sind.  Im schlimmsten Fall, d. h., wenn sich alle Elemente in einem Bucket befinden, ist die Anzahl von Vorgängen proportional zur Anzahl von Elementen in der Sequenz \(lineare Zeit\).  Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
## Syntax  
  
```  
template<class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_multimap;  
```  
  
#### Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`Key`|Der Schlüsseltyp.|  
|`Ty`|Der zugeordnete Typ.|  
|`Hash`|Der Hashfunktionsobjekttyp.|  
|`Pred`|Der Gleichheitsvergleich\-Funktionsobjekttyp.|  
|`Alloc`|Die Zuweisungsklasse.|  
  
## Member  
  
|||  
|-|-|  
|Typdefinition|Beschreibung|  
|[unordered\_multimap::allocator\_type](../Topic/unordered_multimap::allocator_type.md)|Der Typ einer Zuweisung für die Speicherverwaltung.|  
|[unordered\_multimap::const\_iterator](../Topic/unordered_multimap::const_iterator.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[unordered\_multimap::const\_local\_iterator](../Topic/unordered_multimap::const_local_iterator.md)|Der Typ eines konstanten Bucketiterators für die gesteuerte Sequenz.|  
|[unordered\_multimap::const\_pointer](../Topic/unordered_multimap::const_pointer.md)|Der Typ eines konstanten Zeigers auf ein Element.|  
|[unordered\_multimap::const\_reference](../Topic/unordered_multimap::const_reference.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[unordered\_multimap::difference\_type](../Topic/unordered_multimap::difference_type.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[unordered\_multimap::hasher](../Topic/unordered_multimap::hasher.md)|Der Typ der Hashfunktion.|  
|[unordered\_multimap::iterator](../Topic/unordered_multimap::iterator.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[unordered\_multimap::key\_equal](../Topic/unordered_multimap::key_equal.md)|Der Typ der Vergleichsfunktion.|  
|[unordered\_multimap::key\_type](../Topic/unordered_multimap::key_type.md)|Der Typ eines Sortierschlüssels.|  
|[unordered\_multimap::local\_iterator](../Topic/unordered_multimap::local_iterator.md)|Der Typ eines Bucketiterators für die gesteuerte Sequenz.|  
|[unordered\_multimap::mapped\_type](../Topic/unordered_multimap::mapped_type.md)|Der Typ eines zugeordneten Werts, der jedem Schlüssel zugeordnet ist.|  
|[unordered\_multimap::pointer](../Topic/unordered_multimap::pointer.md)|Der Typ eines Zeigers auf ein Element.|  
|[unordered\_multimap::reference](../Topic/unordered_multimap::reference.md)|Der Typ eines Verweises auf ein Element.|  
|[unordered\_multimap::size\_type](../Topic/unordered_multimap::size_type.md)|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|[unordered\_multimap::value\_type](../Topic/unordered_multimap::value_type.md)|Der Typ eines Elements.|  
  
|||  
|-|-|  
|Memberfunktion|Beschreibung|  
|[unordered\_multimap::begin](../Topic/unordered_multimap::begin.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[unordered\_multimap::bucket](../Topic/unordered_multimap::bucket.md)|Ruft die Bucketnummer für einen Schlüsselwert ab.|  
|[unordered\_multimap::bucket\_count](../Topic/unordered_multimap::bucket_count.md)|Ruft die Anzahl von Buckets ab.|  
|[unordered\_multimap::bucket\_size](../Topic/unordered_multimap::bucket_size.md)|Ruft die Größe eines Buckets ab.|  
|[unordered\_multimap::cbegin](../Topic/unordered_multimap::cbegin.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[unordered\_multimap::cend](../Topic/unordered_multimap::cend.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[unordered\_multimap::clear](../Topic/unordered_multimap::clear.md)|Entfernt alle Elemente.|  
|[unordered\_multimap::count](../Topic/unordered_multimap::count.md)|Sucht die Anzahl von Elementen, die einem angegebenen Schlüssel entsprechen.|  
|[unordered\_multimap::emplace](../Topic/unordered_multimap::emplace.md)|Fügt ein Element hinzu, das direkt erstellt wird.|  
|[unordered\_multimap::emplace\_hint](../Topic/unordered_multimap::emplace_hint.md)|Fügt ein Element hinzu, das direkt mit Hinweis erstellt wird.|  
|[unordered\_multimap::empty](../Topic/unordered_multimap::empty.md)|Testet, ob keine Elemente vorhanden sind.|  
|[unordered\_multimap::end](../Topic/unordered_multimap::end.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[unordered\_multimap::equal\_range](../Topic/unordered_multimap::equal_range.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[unordered\_multimap::erase](../Topic/unordered_multimap::erase.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[unordered\_multimap::find](../Topic/unordered_multimap::find.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[unordered\_multimap::get\_allocator](../Topic/unordered_multimap::get_allocator.md)|Ruft das gespeicherte Zuweisungsobjekt ab.|  
|[unordered\_multimap::hash\_function](../Topic/unordered_multimap::hash_function.md)|Ruft das gespeicherte Hashfunktionsobjekt ab.|  
|[unordered\_multimap::insert](../Topic/unordered_multimap::insert.md)|Fügt Elemente hinzu.|  
|[unordered\_multimap::key\_eq](../Topic/unordered_multimap::key_eq.md)|Ruft das gespeicherte Vergleichsfunktionsobjekt ab.|  
|[unordered\_multimap::load\_factor](../Topic/unordered_multimap::load_factor.md)|Zählt die durchschnittliche Anzahl von Elementen pro Bucket.|  
|[unordered\_multimap::max\_bucket\_count](../Topic/unordered_multimap::max_bucket_count.md)|Ruft die maximale Anzahl von Buckets ab.|  
|[unordered\_multimap::max\_load\_factor](../Topic/unordered_multimap::max_load_factor.md)|Ruft die maximale Anzahl von Elementen pro Bucket ab oder legt sie fest.|  
|[unordered\_multimap::max\_size](../Topic/unordered_multimap::max_size.md)|Ruft die maximale Größe der gesteuerten Sequenz ab.|  
|[unordered\_multimap::rehash](../Topic/unordered_multimap::rehash.md)|Erstellt die Hashtabelle neu.|  
|[unordered\_multimap::size](../Topic/unordered_multimap::size.md)|Ermittelt die Anzahl von Elementen.|  
|[unordered\_multimap::swap](../Topic/unordered_multimap::swap.md)|Vertauscht den Inhalt von zwei Containern.|  
|[unordered\_multimap::unordered\_multimap](../Topic/unordered_multimap::unordered_multimap.md)|Erstellt ein container\-Objekt.|  
  
|||  
|-|-|  
|Operator|Beschreibung|  
|[unordered\_multimap::operator\=](../Topic/unordered_multimap::operator=.md)|Kopiert eine Hashtabelle.|  
  
## Hinweise  
 Das Objekt sortiert die Sequenz, die es steuert, indem es zwei gespeicherte Objekte aufruft, ein Vergleichsfunktionsobjekt des Typs [unordered\_multimap::key\_equal](../Topic/unordered_multimap::key_equal.md) und ein Hashfunktionsobjekt des Typs [unordered\_multimap::hasher](../Topic/unordered_multimap::hasher.md).  Sie greifen auf das zuerst gespeicherte Objekt zu, indem Sie die Memberfunktion [unordered\_multimap::key\_eq](../Topic/unordered_multimap::key_eq.md) aufrufen`()`. Auf das zweite gespeicherte Objekt greifen Sie zu, indem Sie die Memberfunktion [unordered\_multimap::hash\_function](../Topic/unordered_multimap::hash_function.md)`()` aufrufen.  Insbesondere für alle Werte `X` und `Y` vom Typ `Key` gibt der Aufruf von `key_eq()(X, Y)` nur "true" zurück, wenn die beiden Argumentwerte die entsprechende Reihenfolge aufweisen. Der Aufruf von `hash_function()(keyval)` ergibt eine Verteilung von Werten des Typs `size_t`.  Im Gegensatz zur Vorlagenklasse [unordered\_map\-Klasse](../standard-library/unordered-map-class.md) stellt ein Objekt der Vorlagenklasse `unordered_multimap` nicht sicher, dass `key_eq()(X, Y)` für zwei Elemente der gesteuerten Sequenz immer "false" ist. \(Die Schlüssel müssen nicht eindeutig sein.\)  
  
 Das Objekt speichert auch einen Höchstlastfaktor, der die maximal erwünschte durchschnittliche Anzahl von Elementen pro Bucket angibt.  Wenn durch Einfügen eines Elements der Wert [unordered\_multimap::load\_factor](../Topic/unordered_multimap::load_factor.md)`()` den Höchstlastfaktor überschreitet, erhöht der Container die Anzahl von Buckets und erstellt die Hashtabelle nach Bedarf neu.  
  
 Die tatsächliche Reihenfolge der Elemente in der gesteuerten Sequenz hängt von der Hashfunktion, von der Vergleichsfunktion, von der Einfügereihenfolge, vom Höchstlastfaktor und von der aktuellen Anzahl von Buckets ab.  Sie können die Reihenfolge der Elemente in der gesteuerten Sequenz im Allgemeinen nicht vorhersagen.  Sie können allerdings sicher sein, dass jede Teilmenge von Elementen, die die entsprechende Reihenfolge aufweisen, in der gesteuerten Sequenz benachbart sind.  
  
 Das Objekt belegt Speicher und gibt Speicher für die gesteuerte Sequenz durch ein gespeichertes Zuweisungsobjekt des Typs [unordered\_multimap::allocator\_type](../Topic/unordered_multimap::allocator_type.md) frei.  Ein solches Zuweisungsobjekt muss die gleiche externe Schnittstelle wie ein Objekt der Vorlagenklasse `allocator` aufweisen.  Beachten Sie, dass das gespeicherte Zuweisungsobjekt nicht kopiert wird, wenn das Containerobjekt zugewiesen wird.  
  
## Anforderungen  
 **Header:** \<unordered\_map\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [Container](../cpp/containers-modern-cpp.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)