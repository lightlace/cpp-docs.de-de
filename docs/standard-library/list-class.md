---
title: "list-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.list"
  - "list"
  - "std::list"
  - "list/std::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "list-Klasse"
ms.assetid: d3707f4a-10fd-444f-b856-f9ca2077c1cd
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# list-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL\-list\-Klasse ist eine Vorlagenklasse von Sequenzcontainern, die ihre Elemente in einer linearen Anordnung verwalten und das effiziente Einfügen und Löschen an jeder Stelle innerhalb der Sequenz ermöglichen.  Die Sequenz wird als bidirektionale verknüpfte Liste von Elementen gespeichert, die jeweils einen Member vom Typ *Typ* enthalten.  
  
## Syntax  
  
```cpp  
  
template <    class Type,     class Allocator=allocator<Type>  > class list  
```  
  
#### Parameter  
 *Typ*  
 Der in der Liste zu speichernde Elementdatentyp.  
  
 `Allocator`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zum Belegen und Freigeben des Arbeitsspeichers der Liste kapselt.  Dieses Argument ist optional, und der Standardwert ist **allocator**\<*Type*\>*.*  
  
## Hinweise  
 Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen.  Vektoren sollten der bevorzugte Container zum Verwalten einer Sequenz sein, wenn zufälliger Zugriff auf jedes Element unbedingt erforderlich und das Einfügen oder Löschen von Elementen nur am Ende einer Sequenz notwendig ist.  Die Leistung des deque\-Klassencontainers hat Vorrang, wenn zufälliger Zugriff erforderlich ist und Einfügungen und Löschungen sowohl am Anfang als auch am Ende einer Sequenz unbedingt notwendig sind.  
  
 Die Listen\-Memberfunktionen [merge](../Topic/list::merge.md), [reverse](../Topic/list::reverse.md), [unique](../Topic/list::unique.md), [remove](../Topic/list::remove.md) uand [remove\_if](../Topic/list::remove_if.md) wurden für die Verwendung mit Listenobjekten optimiert und bieten eine leistungsstarke Alternative zu ihren generischen Entsprechungen.  
  
 Die Neuzuordnung von Listen tritt auf, wenn Elemente der Liste von einer Memberfunktion eingefügt oder gelöscht werden müssen.  In solchen Fällen werden nur Iteratoren oder Verweise auf gelöschte Teile der gesteuerten Sequenz ungültig.  
  
 Schließen Sie den STL Standardheader \<list\> ein, um die [Container](../standard-library/stl-containers.md)\-Vorlageklassenliste und mehrere unterstützende Vorlagen zu definieren.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[list](../Topic/list::list.md)|Erstellt eine Liste einer bestimmten Größe bzw. mit Elementen eines bestimmten Werts oder mit einem bestimmten `allocator`\-Element oder als vollständige bzw. teilweise Kopie einer anderen Liste.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/list::allocator_type.md)|Ein Typ, mit dem die `allocator`\-Klasse für ein Listenobjekt dargestellt wird.|  
|[const\_iterator](../Topic/list::const_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein `const`\-Element in einer Liste gelesen werden kann.|  
|[const\_pointer](../Topic/list::const_pointer.md)|Ein Typ, der einen Zeiger auf ein `const`\-Element in einer Liste bereitstellt.|  
|[const\_reference](../Topic/list::const_reference.md)|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einer Liste zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[const\_reverse\_iterator](../Topic/list::const_reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes beliebige `const`\-Element in einer Liste gelesen werden kann.|  
|[difference\_type](../Topic/list::difference_type.md)|Ein Typ, der den Unterschied zwischen zwei Iteratoren, die auf Elemente innerhalb derselben Liste verweisen, bereitstellt.|  
|[Iterator](../Topic/list::iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes Element in einer Liste gelesen oder geändert werden kann.|  
|[pointer](../Topic/list::pointer.md)|Ein Typ, der einen Zeiger auf ein Element in einer Liste bereitstellt.|  
|[Verweis](../Topic/list::reference.md)|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einer Liste zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[reverse\_iterator](../Topic/list::reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein Element in einer umgekehrten Liste gelesen oder geändert werden kann.|  
|[size\_type](../Topic/list::size_type.md)|Ein Typ, der die Anzahl von Elementen in einer Liste zählt.|  
|[value\_type](../Topic/list::value_type.md)|Ein Typ, der den in einer Liste gespeicherten Datentyp darstellt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[assign](../Topic/list::assign.md)|Löscht Elemente aus einer Liste und kopiert einen neuen Satz von Elementen in die Zielliste.|  
|[back](../Topic/list::back.md)|Gibt einen Verweis auf das letzte Element einer Liste zurück.|  
|[begin](../Topic/list::begin.md)|Gibt einen Iterator zurück, der das erste Element in einer Liste adressiert.|  
|[list::cbegin](../Topic/list::cbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element in einer Liste adressiert.|  
|[list::cend](../Topic/list::cend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Liste nachfolgt.|  
|[list::clear](../Topic/list::clear.md)|Löscht alle Elemente einer Liste.|  
|[list::crbegin](../Topic/list::crbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element in einer umgekehrten Liste adressiert.|  
|[list::crend](../Topic/list::crend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten Listenelements nachfolgt.|  
|[list::emplace](../Topic/list::emplace.md)|Fügt ein direkt konstruiertes Element an einer angegebenen Position in die Liste ein.|  
|[list::emplace\_back](../Topic/list::emplace_back.md)|Fügt ein direkt konstruiertes Element am Ende einer Liste ein.|  
|[list::emplace\_front](../Topic/list::emplace_front.md)|Fügt ein direkt konstruiertes Element am Anfang einer Liste ein.|  
|[empty](../Topic/list::empty.md)|Testet, ob eine Liste leer ist.|  
|[end](../Topic/list::end.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Liste nachfolgt.|  
|[Löschen](../Topic/list::erase.md)|Entfernt ein Element oder eine Reihe von Elementen in einer Liste aus angegebenen Speicherorten.|  
|[front](../Topic/list::front.md)|Gibt einen Verweis auf das erste Element in einer Liste zurück.|  
|[get\_allocator](../Topic/list::get_allocator.md)|Gibt eine Kopie des `allocator`\-Objekts zurück, das zum Erstellen einer Liste verwendet wird.|  
|[Einfügen](../Topic/list::insert.md)|Fügt ein Element oder mehrere Elemente oder ein Reihe von Elementen an einer bestimmten Position in die Liste ein.|  
|[max\_size](../Topic/list::max_size.md)|Gibt die Maximallänge einer Liste zurück.|  
|[merge](../Topic/list::merge.md)|Entfernt die Elemente aus der Argumentliste, fügt sie in die Zielliste ein und sortiert den neuen, kombinierten Elementsatz in aufsteigender Reihenfolge oder in einer anderen angegebenen Reihenfolge.|  
|[pop\_back](../Topic/list::pop_back.md)|Löscht das Element am Ende einer Liste.|  
|[pop\_front](../Topic/list::pop_front.md)|Löscht das Element am Anfang einer Liste.|  
|[push\_back](../Topic/list::push_back.md)|Fügt am Ende einer Liste ein Element hinzu.|  
|[push\_front](../Topic/list::push_front.md)|Fügt am Anfang einer Liste ein Element hinzu.|  
|[rbegin](../Topic/list::rbegin.md)|Gibt einen Iterator zurück, der das erste Element in einer umgekehrten Liste adressiert.|  
|[remove](../Topic/list::remove.md)|Löscht Elemente in einer Liste, die einen angegebenen Wert entsprechen.|  
|[remove\_if](../Topic/list::remove_if.md)|Löscht Elemente aus der Liste, für die ein angegebenes Prädikat erfüllt ist.|  
|[rend](../Topic/list::rend.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten Liste nachfolgt.|  
|[resize](../Topic/list::resize.md)|Gibt eine neue Größe für eine Liste an.|  
|[reverse](../Topic/list::reverse.md)|Kehrt die Reihenfolge um, in der die Elemente in einer Liste auftreten.|  
|[size](../Topic/list::size.md)|Gibt die Anzahl von Elementen in einer Liste zurück.|  
|[sort](../Topic/list::sort.md)|Ordnet die Elemente einer Liste in aufsteigender Reihenfolge oder in Bezug auf eine andere Reihenfolgebeziehung.|  
|[splice](../Topic/list::splice.md)|Entfernt Elemente aus der Argumentliste und fügt sie in die Zielliste ein.|  
|[swap](../Topic/list::swap.md)|Tauscht die Elemente zweier Listen aus.|  
|[unique](../Topic/list::unique.md)|Entfernt benachbarte doppelte Elemente oder benachbarte Elemente, die einige andere binäre Prädikate aus der Liste erfüllen.|  
  
### Operatoren  
  
|||  
|-|-|  
|[list::operator\=](../Topic/list::operator=.md)|Ersetzt die Elemente der Liste mit einer Kopie einer anderen Liste.|  
  
## Anforderungen  
 **Header:** \<list\>  
  
## Siehe auch  
 [\<list\>](../standard-library/list.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)