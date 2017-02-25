---
title: "unordered_set-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.unordered_set"
  - "std::tr1::unordered_set"
  - "unordered_set/std::tr1::unordered_set"
  - "tr1::unordered_set"
  - "unordered_set"
  - "tr1.unordered_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_set-Klasse"
  - "unordered_set-Klasse [TR1]"
ms.assetid: ac08084e-05a7-48c0-9ae4-d40c529922dd
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# unordered_set-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge vom Typ `const Key` steuert.  Die Sequenz wird grob durch eine Hashfunktion sortiert, die die Sequenz in eine geordnete Gruppe von Untersequenzen, so genannte Buckets, unterteilt.  Innerhalb jedes Buckets bestimmt eine Vergleichsfunktion, ob ein Elementpaar eine entsprechende Reihenfolge hat.  Jedes Element dient sowohl als Sortierschlüssel als auch als Wert.  Die Sequenz wird so dargestellt, dass die Suche, das Einfügen und das Entfernen eines beliebigen Elements mit einer Reihen von Vorgängen möglich ist, die unabhängig von der Anzahl von Elementen in der Sequenz \(konstante Zeit\) sein können, zumindest, wenn alle Buckets von ungefähr gleicher Länge sind.  Im schlimmsten Fall, d. h., wenn sich alle Elemente in einem Bucket befinden, ist die Anzahl von Vorgängen proportional zur Anzahl von Elementen in der Sequenz \(lineare Zeit\).  Darüber hinaus führt das Einfügen eines Elements nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen eines Elements werden nur solche Iteratoren ungültig, die auf das entfernte Element gezeigt haben.  
  
## Syntax  
  
```  
template<class Key,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_set;  
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
|[unordered\_set::allocator\_type](../Topic/unordered_set::allocator_type.md)|Der Typ einer Zuweisung für die Speicherverwaltung.|  
|[unordered\_set::const\_iterator](../Topic/unordered_set::const_iterator.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[unordered\_set::const\_local\_iterator](../Topic/unordered_set::const_local_iterator.md)|Der Typ eines konstanten Bucketiterators für die gesteuerte Sequenz.|  
|[unordered\_set::const\_pointer](../Topic/unordered_set::const_pointer.md)|Der Typ eines konstanten Zeigers auf ein Element.|  
|[unordered\_set::const\_reference](../Topic/unordered_set::const_reference.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[unordered\_set::difference\_type](../Topic/unordered_set::difference_type.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[unordered\_set::hasher](../Topic/unordered_set::hasher.md)|Der Typ der Hashfunktion.|  
|[unordered\_set::iterator](../Topic/unordered_set::iterator.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[unordered\_set::key\_equal](../Topic/unordered_set::key_equal.md)|Der Typ der Vergleichsfunktion.|  
|[unordered\_set::key\_type](../Topic/unordered_set::key_type.md)|Der Typ eines Sortierschlüssels.|  
|[unordered\_set::local\_iterator](../Topic/unordered_set::local_iterator.md)|Der Typ eines Bucketiterators für die gesteuerte Sequenz.|  
|[unordered\_set::pointer](../Topic/unordered_set::pointer.md)|Der Typ eines Zeigers auf ein Element.|  
|[unordered\_set::reference](../Topic/unordered_set::reference.md)|Der Typ eines Verweises auf ein Element.|  
|[unordered\_set::size\_type](../Topic/unordered_set::size_type.md)|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|[unordered\_set::value\_type](../Topic/unordered_set::value_type.md)|Der Typ eines Elements.|  
  
|||  
|-|-|  
|Memberfunktion|Beschreibung|  
|[unordered\_set::begin](../Topic/unordered_set::begin.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[unordered\_set::bucket](../Topic/unordered_set::bucket.md)|Ruft die Bucketnummer für einen Schlüsselwert ab.|  
|[unordered\_set::bucket\_count](../Topic/unordered_set::bucket_count.md)|Ruft die Anzahl von Buckets ab.|  
|[unordered\_set::bucket\_size](../Topic/unordered_set::bucket_size.md)|Ruft die Größe eines Buckets ab.|  
|[unordered\_set::cbegin](../Topic/unordered_set::cbegin.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[unordered\_set::cend](../Topic/unordered_set::cend.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[unordered\_set::clear](../Topic/unordered_set::clear.md)|Entfernt alle Elemente.|  
|[unordered\_set::count](../Topic/unordered_set::count.md)|Sucht die Anzahl von Elementen, die einem angegebenen Schlüssel entsprechen.|  
|[unordered\_set::emplace](../Topic/unordered_set::emplace.md)|Fügt ein Element hinzu, das direkt erstellt wird.|  
|[unordered\_set::emplace\_hint](../Topic/unordered_set::emplace_hint.md)|Fügt ein Element hinzu, das direkt mit Hinweis erstellt wird.|  
|[unordered\_set::empty](../Topic/unordered_set::empty.md)|Testet, ob keine Elemente vorhanden sind.|  
|[unordered\_set::end](../Topic/unordered_set::end.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[unordered\_set::equal\_range](../Topic/unordered_set::equal_range.md)|Sucht den Bereich, der einem angegebenen Schlüssel entspricht.|  
|[unordered\_set::erase](../Topic/unordered_set::erase.md)|Entfernt Elemente an den angegebenen Positionen.|  
|[unordered\_set::find](../Topic/unordered_set::find.md)|Sucht ein Element, das einem angegebenen Schlüssel entspricht.|  
|[unordered\_set::get\_allocator](../Topic/unordered_set::get_allocator.md)|Ruft das gespeicherte Zuweisungsobjekt ab.|  
|[unordered\_set::hash\_function](../Topic/unordered_set::hash_function.md)|Ruft das gespeicherte Hashfunktionsobjekt ab.|  
|[unordered\_set::insert](../Topic/unordered_set::insert.md)|Fügt Elemente hinzu.|  
|[unordered\_set::key\_eq](../Topic/unordered_set::key_eq.md)|Ruft das gespeicherte Vergleichsfunktionsobjekt ab.|  
|[unordered\_set::load\_factor](../Topic/unordered_set::load_factor.md)|Zählt die durchschnittliche Anzahl von Elementen pro Bucket.|  
|[unordered\_set::max\_bucket\_count](../Topic/unordered_set::max_bucket_count.md)|Ruft die maximale Anzahl von Buckets ab.|  
|[unordered\_set::max\_load\_factor](../Topic/unordered_set::max_load_factor.md)|Ruft die maximale Anzahl von Elementen pro Bucket ab oder legt sie fest.|  
|[unordered\_set::max\_size](../Topic/unordered_set::max_size.md)|Ruft die maximale Größe der gesteuerten Sequenz ab.|  
|[unordered\_set::rehash](../Topic/unordered_set::rehash.md)|Erstellt die Hashtabelle neu.|  
|[unordered\_set::size](../Topic/unordered_set::size.md)|Ermittelt die Anzahl von Elementen.|  
|[unordered\_set::swap](../Topic/unordered_set::swap.md)|Vertauscht den Inhalt von zwei Containern.|  
|[unordered\_set::unordered\_set](../Topic/unordered_set::unordered_set.md)|Erstellt ein container\-Objekt.|  
  
|||  
|-|-|  
|Operators|Beschreibung|  
|[unordered\_set::operator\=](../Topic/unordered_set::operator=.md)|Kopiert eine Hashtabelle.|  
  
## Hinweise  
 Das Objekt sortiert die Sequenz, die es steuert, indem es zwei gespeicherte Objekte aufruft, ein Vergleichsfunktionsobjekt des Typs [unordered\_set::key\_equal](../Topic/unordered_set::key_equal.md) und ein Hashfunktionsobjekt des Typs [unordered\_set::hasher](../Topic/unordered_set::hasher.md).  Sie greifen auf das zuerst gespeicherte Objekt zu, indem Sie die Memberfunktion [unordered\_set::key\_eq](../Topic/unordered_set::key_eq.md) aufrufen`()`. Auf das zweite gespeicherte Objekt greifen Sie zu, indem Sie die Memberfunktion [unordered\_set::hash\_function](../Topic/unordered_set::hash_function.md)`()` aufrufen.  Insbesondere für alle Werte `X` und `Y` vom Typ `Key` gibt der Aufruf von `key_eq()(X, Y)` nur "true" zurück, wenn die beiden Argumentwerte die entsprechende Reihenfolge aufweisen. Der Aufruf von `hash_function()(keyval)` ergibt eine Verteilung von Werten des Typs `size_t`.  Im Gegensatz zur Vorlagenklasse [unordered\_multiset\-Klasse](../standard-library/unordered-multiset-class.md) stellt ein Objekt der Vorlagenklasse `unordered_set` sicher, dass `key_eq()(X, Y)` für zwei Elemente der gesteuerten Sequenz immer "false" ist. \(Schlüssel sind eindeutig.\)  
  
 Das Objekt speichert auch einen Höchstlastfaktor, der die maximal erwünschte durchschnittliche Anzahl von Elementen pro Bucket angibt.  Wenn durch Einfügen eines Elements der Wert [unordered\_set::load\_factor](../Topic/unordered_set::load_factor.md)`()` den Höchstlastfaktor überschreitet, erhöht der Container die Anzahl von Buckets und erstellt die Hashtabelle nach Bedarf neu.  
  
 Die tatsächliche Reihenfolge der Elemente in der gesteuerten Sequenz hängt von der Hashfunktion, von der Vergleichsfunktion, von der Einfügereihenfolge, vom Höchstlastfaktor und von der aktuellen Anzahl von Buckets ab.  Sie können die Reihenfolge der Elemente in der gesteuerten Sequenz im Allgemeinen nicht vorhersagen.  Sie können allerdings sicher sein, dass jede Teilmenge von Elementen, die die entsprechende Reihenfolge aufweisen, in der gesteuerten Sequenz benachbart sind.  
  
 Das Objekt belegt Speicher und gibt Speicher für die gesteuerte Sequenz durch ein gespeichertes Zuweisungsobjekt des Typs [unordered\_set::allocator\_type](../Topic/unordered_set::allocator_type.md) frei.  Ein solches Zuweisungsobjekt muss die gleiche externe Schnittstelle wie ein Objekt der Vorlagenklasse `allocator` aufweisen.  Beachten Sie, dass das gespeicherte Zuweisungsobjekt nicht kopiert wird, wenn das Containerobjekt zugewiesen wird.  
  
## Anforderungen  
 **Header:** \<unordered\_set\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<unordered\_set\>](../standard-library/unordered-set.md)   
 [Container](../cpp/containers-modern-cpp.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)