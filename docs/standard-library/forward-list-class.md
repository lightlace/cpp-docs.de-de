---
title: "forward_list-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::forward_list"
  - "forward_list"
  - "forward_list/std::forward_list"
  - "std.forward_list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "forward_list-Klasse"
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# forward_list-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert.  Die Sequenz wird als einfach verknüpfte Knotenliste gespeichert, die jeweils einen Member vom Typ `Type` enthält.  
  
## Syntax  
  
```  
template<  
    class Type,   
    class Allocator = allocator<Type>   
>  
class forward_list   
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`Type`|Das in der Doppelschlange zu speichernde forward\_list\-Element.|  
|`Allocator`|Das gespeicherte Zuordnungsobjekt, das Details zum Belegen und Freigeben des Arbeitsspeichers des forward\_list\-Elements kapselt.  Dieser Parameter ist optional.  Der Standardwert ist "allocator\<`Type`\>".|  
  
## Hinweise  
 Ein `forward_list`\-Objekt nimmt für die Sequenz, die von ihm gesteuert wird, Speicherbelegungen und \-freigaben über ein gespeichertes Objekt vor, das aus der Klasse `Allocator` abgeleitet wurde, die auf der [allocator\-Klasse](../standard-library/allocator-class.md) basiert \(im Allgemeinen als `std::allocator)` bekannt\).  Weitere Informationen finden Sie unter [Allocators](../standard-library/allocators.md).  Ein Zuweisungsobjekt muss gleiche externe Schnittstelle wie ein Objekt der Vorlagenklasse `allocator` aufweisen.  
  
> [!NOTE]
>  Das gespeicherte Zuweisungsobjekt wird nicht kopiert, wenn das Containerobjekt zugewiesen wird.  
  
 Iteratoren, Zeiger und Verweise werden möglicherweise ungültig, wenn Elemente ihrer gesteuerten Sequenz von `forward_list` gelöscht werden.  Durch die von `forward_list` auf der gesteuerten Sequenz durchgeführten Einfügungen und Verbindungen werden keine Iteratoren ungültig.  
  
 Hinzufügungen zur gesteuerten Sequenz können bei Aufrufen von [forward\_list::insert\_after](../Topic/forward_list::insert_after.md) auftreten, die die einzige Memberfunktion ist, die den Konstruktor `Type(const _Type&)` aufruft.  `forward_list` ruft möglicherweise auch Verschiebekonstruktoren auf.  Wenn ein solcher Ausdruck eine Ausnahme auslöst, werden vom Containerobjekt keine neuen Elemente eingefügt, und die Ausnahme wird erneut ausgelöst.  Daher wird ein Objekt der Vorlagenklasse `forward_list` bei Auftreten solche Ausnahmen in einem bekannten Zustand belassen.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[forward\_list](../Topic/forward_list::forward_list.md)|Konstruiert ein Objekt vom Typ `forward_list`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/forward_list::allocator_type.md)|Ein Typ, mit dem die Zuweisungsklasse für ein forward list\-Objekt dargestellt wird.|  
|[const\_iterator](../Topic/forward_list::const_iterator.md)|Ein Typ, der einen konstanten Iterator für die Vorwärtsliste bereitstellt.|  
|[const\_pointer](../Topic/forward_list::const_pointer.md)|Ein Typ, der einen Zeiger auf ein `const`\-Element in einer Vorwärtsliste bereitstellt.|  
|[const\_reference](../Topic/forward_list::const_reference.md)|Ein Typ, der einen Konstantenverweis auf einer Vorwärtsliste gespeichertes Element bereitstellt.|  
|[difference\_type](../Topic/forward_list::difference_type.md)|Ein Ganzzahltyp mit Vorzeichen, der dazu verwendet werden kann, die Anzahl von Elementen einer Vorwärtsliste in einen Bereich zwischen Elementen darzustellen, auf die von Iteratoren gezeigt wird.|  
|[Iterator](../Topic/forward_list::iterator.md)|Ein Typ, der einen Iterator für die Vorwärtsliste bereitstellt.|  
|[pointer](../Topic/forward_list::pointer.md)|Ein Typ, der einen Zeiger auf ein Element in der Vorwärtsliste bereitstellt.|  
|[Verweis](../Topic/forward_list::reference.md)|Ein Typ, der einen Verweis auf ein in der Vorwärtsliste gespeichertes Element bereitstellt.|  
|[size\_type](../Topic/forward_list::size_type.md)|Ein Typ, der den Abstand ohne Vorzeichen zwischen zwei Elementen darstellt.|  
|[value\_type](../Topic/forward_list::value_type.md)|Ein Typ, der den Typ des in einer Vorwärtsliste gespeicherten Elements darstellt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[assign](../Topic/forward_list::assign.md)|Löscht Elemente aus einer Vorwärtsliste und kopiert einen neuen Satz von Elementen an eine Zielvorwärtsliste.|  
|[before\_begin](../Topic/forward_list::before_begin.md)|Gibt einen Iterator zurück, der die Position vor dem ersten Element in einer Vorwärtsliste adressiert.|  
|[begin](../Topic/forward_list::begin.md)|Gibt einen Iterator zurück, der das erste Element in einer Vorwärtsliste adressiert.|  
|[cbefore\_begin](../Topic/forward_list::cbefore_begin.md)|Gibt einen konstanten Iterator zurück, der die Position vor dem ersten Element in einer Vorwärtsliste adressiert.|  
|[cbegin](../Topic/forward_list::cbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element in einer Vorwärtsliste adressiert.|  
|[cend](../Topic/forward_list::cend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Vorwärtsliste nachfolgt.|  
|[nicht aktiviert](../Topic/forward_list::clear.md)|Löscht alle Elemente einer Vorwärtsliste auf.|  
|[emplace\_after](../Topic/forward_list::emplace_after.md)|Die Verschiebung erstellt ein neues Element nach einer angegebenen Position.|  
|[emplace\_front](../Topic/forward_list::emplace_front.md)|Fügt ein direkt konstruiertes Element am Anfang der Liste ein.|  
|[Leer](../Topic/forward_list::empty.md)|Testet, ob eine Vorwärtsliste leer ist.|  
|[end](../Topic/forward_list::end.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Vorwärtsliste nachfolgt.|  
|[erase\_after](../Topic/forward_list::erase_after.md)|Entfernt Elemente nach einer angegebenen Position aus der Vorwärtsliste.|  
|[front](../Topic/forward_list::front.md)|Gibt einen Verweis auf das erste Element in einer Vorwärtsliste zurück.|  
|[get\_allocator](../Topic/forward_list::get_allocator.md)|Gibt eine Kopie des Zuordnungsobjekts zurück, das zum Erstellen der Vorwärtsliste verwendet wird.|  
|[insert\_after](../Topic/forward_list::insert_after.md)|Fügt der Vorwärtsliste nach einer angegebenen Position Elemente hinzu.|  
|[max\_size](../Topic/forward_list::max_size.md)|Gibt die Maximallänge einer Vorwärtsliste zurück.|  
|[zusammenführen](../Topic/forward_list::merge.md)|Entfernt die Elemente aus der Argumentliste, fügt sie in die Zielvorwärtsliste ein und sortiert den neuen, kombinierten Elementsatz in aufsteigender Reihenfolge oder in einer anderen angegebenen Reihenfolge.|  
|[pop\_front](../Topic/forward_list::pop_front.md)|Löscht das Element am Anfang einer Vorwärtsliste.|  
|[push\_front](../Topic/forward_list::push_front.md)|Fügt am Anfang einer Vorwärtsliste ein Element hinzu.|  
|[Entfernen](../Topic/forward_list::remove.md)|Löscht Elemente in einer Vorwärtsliste, die einem angegebenen Wert entsprechen.|  
|[remove\_if](../Topic/forward_list::remove_if.md)|Löscht Elemente aus einer Vorwärtsliste, für die ein angegebenes Prädikat erfüllt ist.|  
|[Größe ändern](../Topic/forward_list::resize.md)|Gibt eine neue Größe für eine Vorwärtsliste an.|  
|[reverse](../Topic/forward_list::reverse.md)|Kehrt die Reihenfolge um, in der die Elemente in einer Vorwärtsliste auftreten.|  
|[sort](../Topic/forward_list::sort.md)|Ordnet die Elemente in aufsteigender Reihenfolge oder einer durch ein Prädikat angegebenen Reihenfolge.|  
|[splice\_after](../Topic/forward_list::splice_after.md)|Erneuert Links zwischen Knoten.|  
|[swap](../Topic/forward_list::swap.md)|Tauscht die Elemente zweier Vorwärtslisten aus.|  
|[unique](../Topic/forward_list::unique.md)|Entfernt benachbarte Elemente, die einen angegebenen Test bestehen.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/forward_list::operator=.md)|Ersetzt die Elemente der Vorwärtsliste durch eine Kopie einer anderen Vorwärtsliste.|  
  
## Anforderungen  
 **Header:** \<forward\_list\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<forward\_list\>](../standard-library/forward-list.md)