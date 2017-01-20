---
title: "unordered_map-Klasse"
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
  - "std::tr1::unordered_map"
  - "std.tr1.unordered_map"
  - "tr1.unordered_map"
  - "tr1::unordered_map"
  - "unordered_map"
  - "unordered_map/std::tr1::unordered_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_map-Klasse"
  - "unordered_map-Klasse [TR1]"
ms.assetid: 7cf7cfa1-16e7-461c-a9b2-3b8d8ec24e0d
caps.latest.revision: 20
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# unordered_map-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge vom Typ `std::pair<const Key, Ty>` steuert.  Die Sequenz wird grob durch eine Hashfunktion sortiert, die die Sequenz in eine geordnete Gruppe von Untersequenzen, so genannte Buckets, unterteilt.  Innerhalb jedes Buckets bestimmt eine Vergleichsfunktion, ob ein Elementpaar eine entsprechende Reihenfolge hat.  Jedes Element speichert zwei Objekte, einen Sortierschlüssel und einen Wert.  Die Sequenz wird so dargestellt, dass die Suche, das Einfügen und das Entfernen eines beliebigen Elements mit einer Reihen von Vorgängen möglich ist, die unabhängig von der Anzahl von Elementen in der Sequenz \(konstante Zeit\) sein können, zumindest, wenn alle Buckets von ungefähr gleicher Länge sind.  Im schlimmsten Fall, d. h., wenn sich alle Elemente in einem Bucket befinden, ist die Anzahl von Vorgängen proportional zur Anzahl von Elementen in der Sequenz \(lineare Zeit\).  Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
## Syntax  
  
```  
template<class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<std::pair<const Key, Ty> > >  
    class unordered_map;  
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
|[unordered\_map::allocator\_type](../Topic/unordered_map::allocator_type.md)|Der Typ einer Zuweisung für die Speicherverwaltung.|  
|[unordered\_map::const\_iterator](../Topic/unordered_map::const_iterator.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[unordered\_map::const\_local\_iterator](../Topic/unordered_map::const_local_iterator.md)|Der Typ eines konstanten Bucketiterators für die gesteuerte Sequenz.|  
|[unordered\_map::const\_pointer](../Topic/unordered_map::const_pointer.md)|Der Typ eines konstanten Zeigers auf ein Element.|  
|[unordered\_map::const\_reference](../Topic/unordered_map::const_reference.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[unordered\_map::difference\_type](../Topic/unordered_map::difference_type.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[unordered\_map::hasher](../Topic/unordered_map::hasher.md)|Der Typ der Hashfunktion.|  
|[unordered\_map::iterator](../Topic/unordered_map::iterator.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[unordered\_map::key\_equal](../Topic/unordered_map::key_equal.md)|Der Typ der Vergleichsfunktion.|  
|[unordered\_map::key\_type](../Topic/unordered_map::key_type.md)|Der Typ eines Sortierschlüssels.|  
|[unordered\_map::local\_iterator](../Topic/unordered_map::local_iterator.md)|Der Typ eines Bucketiterators für die gesteuerte Sequenz.|  
|[unordered\_map::mapped\_type](../Topic/unordered_map::mapped_type.md)|Der Typ eines zugeordneten Werts, der jedem Schlüssel zugeordnet ist.|  
|[unordered\_map::pointer](../Topic/unordered_map::pointer.md)|Der Typ eines Zeigers auf ein Element.|  
|[unordered\_map::reference](../Topic/unordered_map::reference.md)|Der Typ eines Verweises auf ein Element.|  
|[unordered\_map::size\_type](../Topic/unordered_map::size_type.md)|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|[unordered\_map::value\_type](../Topic/unordered_map::value_type.md)|Der Typ eines Elements.|  
  
|||  
|-|-|  
|Memberfunktion|Beschreibung|  
|[unordered\_map::at](../Topic/unordered_map::at.md)|Sucht ein Element mit dem angegebenen Schlüssel.|  
|[unordered\_map::begin](../Topic/unordered_map::begin.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[unordered\_map::bucket](../Topic/unordered_map::bucket.md)|Ruft die Bucketnummer für einen Schlüsselwert ab.|  
|[unordered\_map::bucket\_count](../Topic/unordered_map::bucket_count.md)|Ruft die Anzahl von Buckets ab.|  
|[unordered\_map::bucket\_size](../Topic/unordered_map::bucket_size.md)|Ruft die Größe eines Buckets ab.|  
|[unordered\_map::cbegin](../Topic/unordered_map::cbegin.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[unordered\_map::cend](../Topic/unordered_map::cend.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[unordered\_map::clear](../Topic/unordered_map::clear.md)|Entfernt alle Elemente.|  
|[unordered\_map::count](../Topic/unordered_map::count.md)|Sucht die Anzahl von Elementen, die einem angegebenen Schlüssel entsprechen.|  
|[unordered\_map::emplace](../Topic/unordered_map::emplace.md)|Fügt ein Element hinzu, das direkt erstellt wird.|  
|[unordered\_map::emplace\_hint](../Topic/unordered_map::emplace_hint.md)|Fügt ein Element hinzu, das direkt mit Hinweis erstellt wird.|  
|[unordered\_map::empty](../Topic/unordered_map::empty.md)|Testet, ob keine Elemente vorhanden sind.|  
|[unordered\_map::end](../Topic/unordered_map::end.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[unordered\_map::equal\_range](../Topic/unordered_map::equal_range.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[unordered\_map::erase](../Topic/unordered_map::erase.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[unordered\_map::find](../Topic/unordered_map::find.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[unordered\_map::get\_allocator](../Topic/unordered_map::get_allocator.md)|Ruft das gespeicherte Zuweisungsobjekt ab.|  
|[unordered\_map::hash\_function](../Topic/unordered_map::hash_function.md)|Ruft das gespeicherte Hashfunktionsobjekt ab.|  
|[unordered\_map::insert](../Topic/unordered_map::insert.md)|Fügt Elemente hinzu.|  
|[unordered\_map::key\_eq](../Topic/unordered_map::key_eq.md)|Ruft das gespeicherte Vergleichsfunktionsobjekt ab.|  
|[unordered\_map::load\_factor](../Topic/unordered_map::load_factor.md)|Zählt die durchschnittliche Anzahl von Elementen pro Bucket.|  
|[unordered\_map::max\_bucket\_count](../Topic/unordered_map::max_bucket_count.md)|Ruft die maximale Anzahl von Buckets ab.|  
|[unordered\_map::max\_load\_factor](../Topic/unordered_map::max_load_factor.md)|Ruft die maximale Anzahl von Elementen pro Bucket ab oder legt sie fest.|  
|[unordered\_map::max\_size](../Topic/unordered_map::max_size.md)|Ruft die maximale Größe der gesteuerten Sequenz ab.|  
|[unordered\_map::rehash](../Topic/unordered_map::rehash.md)|Erstellt die Hashtabelle neu.|  
|[unordered\_map::size](../Topic/unordered_map::size.md)|Ermittelt die Anzahl von Elementen.|  
|[unordered\_map::swap](../Topic/unordered_map::swap.md)|Vertauscht den Inhalt von zwei Containern.|  
|[unordered\_map::unordered\_map](../Topic/unordered_map::unordered_map.md)|Erstellt ein container\-Objekt.|  
  
|||  
|-|-|  
|Operator|Beschreibung|  
|[unordered\_map::operator](../Topic/unordered_map::operator.md)|Sucht ein Element mit dem angegebenen Schlüssel oder fügt es ein.|  
|[unordered\_map::operator\=](../Topic/unordered_map::operator=.md)|Kopiert eine Hashtabelle.|  
  
## Hinweise  
 Das Objekt sortiert die Sequenz, die es steuert, indem es zwei gespeicherte Objekte aufruft, ein Vergleichsfunktionsobjekt des Typs [unordered\_map::key\_equal](../Topic/unordered_map::key_equal.md) und ein Hashfunktionsobjekt des Typs [unordered\_map::hasher](../Topic/unordered_map::hasher.md).  Sie greifen auf das zuerst gespeicherte Objekt zu, indem Sie die Memberfunktion [unordered\_map::key\_eq](../Topic/unordered_map::key_eq.md) aufrufen`()`. Auf das zweite gespeicherte Objekt greifen Sie zu, indem Sie die Memberfunktion [unordered\_map::hash\_function](../Topic/unordered_map::hash_function.md)`()` aufrufen.  Insbesondere für alle Werte `X` und `Y` vom Typ `Key` gibt der Aufruf von `key_eq()(X, Y)` nur "true" zurück, wenn die beiden Argumentwerte die entsprechende Reihenfolge aufweisen. Der Aufruf von `hash_function()(keyval)` ergibt eine Verteilung von Werten des Typs `size_t`.  Im Gegensatz zur Vorlagenklasse [unordered\_multimap\-Klasse](../standard-library/unordered-multimap-class.md) stellt ein Objekt der Vorlagenklasse `unordered_map` sicher, dass `key_eq()(X, Y)` für zwei Elemente der gesteuerten Sequenz immer "false" ist. \(Schlüssel sind eindeutig.\)  
  
 Das Objekt speichert auch einen Höchstlastfaktor, der die maximal erwünschte durchschnittliche Anzahl von Elementen pro Bucket angibt.  Wenn durch Einfügen eines Elements der Wert [unordered\_map::load\_factor](../Topic/unordered_map::load_factor.md)`()` den Höchstlastfaktor überschreitet, erhöht der Container die Anzahl von Buckets und erstellt die Hashtabelle nach Bedarf neu.  
  
 Die tatsächliche Reihenfolge der Elemente in der gesteuerten Sequenz hängt von der Hashfunktion, von der Vergleichsfunktion, von der Einfügereihenfolge, vom Höchstlastfaktor und von der aktuellen Anzahl von Buckets ab.  Sie können die Reihenfolge der Elemente in der gesteuerten Sequenz im Allgemeinen nicht vorhersagen.  Sie können allerdings sicher sein, dass jede Teilmenge von Elementen, die die entsprechende Reihenfolge aufweisen, in der gesteuerten Sequenz benachbart sind.  
  
 Das Objekt belegt Speicher und gibt Speicher für die gesteuerte Sequenz durch ein gespeichertes Zuweisungsobjekt des Typs [unordered\_map::allocator\_type](../Topic/unordered_map::allocator_type.md) frei.  Ein solches Zuweisungsobjekt muss die gleiche externe Schnittstelle wie ein Objekt der Vorlagenklasse `allocator` aufweisen.  Beachten Sie, dass das gespeicherte Zuweisungsobjekt nicht kopiert wird, wenn das Containerobjekt zugewiesen wird.  
  
## Anforderungen  
 **Header:** \<unordered\_map\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [Container](../cpp/containers-modern-cpp.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)