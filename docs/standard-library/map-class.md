---
title: "map-Klasse"
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
  - "std::map"
  - "map/std::map"
  - "map"
  - "std.map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "map-Klasse"
ms.assetid: 7876f4c9-ebb4-4878-af1e-09364c43af0a
caps.latest.revision: 27
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# map-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird zum Speichern und Abrufen von Daten aus einer Auflistung verwendet, in der jedes Element ein Paar ist, das einen Datenwert und einen Sortierschlüssel aufweist.  Der Wert des Schlüssels ist eindeutig und wird verwendet, zum automatischen Sortieren der Daten verwendet.  
  
 Der Wert eines Elements in einer Zuordnung kann direkt geändert werden.  Der Schlüsselwert ist eine Konstante und kann nicht geändert werden.  Stattdessen müssen die Schlüsselwerte, die alten Elementen zugeordnet sind, gelöscht und neue Schlüsselwerte für neue Elemente eingefügt werden.  
  
## Syntax  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits = less<Key>,   
   class Allocator=allocator<pair <const Key, Type> >   
> class map;  
```  
  
#### Parameter  
 `Key`  
 Der in der Zuordnung zu speichernde Schlüsseldatentyp.  
  
 `Type`  
 Der in der Zuordnung zu speichernde Elementdatentyp.  
  
 `Traits`  
 Der Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in der Zuordnung zu bestimmen.  Dieses Argument ist optional, und das binäre Prädikat `less<``Key``>` ist der Standardwert.  
  
 In C \+\+ 14 können Sie heterogenes Nachschlagen durch Angabe des std::less\<\>\-Prädikats aktivieren, das keine Typparameter aufweist.  Weitere Informationen finden Sie unter [Heterogenes Nachschlagen in assoziativen Containern](../standard-library/stl-containers.md#sequence_containers).  
  
 `Allocator`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zum Belegen und Freigeben des Arbeitsspeichers der Zuordnung kapselt.  Dieses Argument ist optional, und der Standardwert ist `allocator<pair` `<const``Key`*,* `Type``> >`.  
  
## Hinweise  
 Die Zuordnungsklasse der Standardvorlagenbibliothek \(STK\) ist:  
  
-   Ein Container variabler Größe, der Elementwerte effizient auf Grundlage zugeordneter Schlüsselwerte abruft.  
  
-   Umkehrbar, da bidirektionale Iteratoren für den Zugriff auf die Elemente bereitgestellt werden.  
  
-   Sortiert, da die Elemente entsprechend einer angegebenen Vergleichsfunktion nach Schlüsselwerten sortiert werden.  
  
-   Eindeutig.  Eindeutig, da jedes der Elemente einen eindeutigen Schlüssel aufweisen muss.  
  
-   Ein Paar\-assoziativer Container, da sich die Elementdatenwerte von den Schlüsselwerten unterscheiden.  
  
-   Eine Vorlagenklasse, da die bereitgestellten Funktionen generisch und vom Element\- oder Schlüsseltyp unabhängig sind.  Die für Elemente und Schlüssel verwendeten Datentypen werden in der Klassenvorlage zusammen mit der Vergleichsfunktion und der Zuweisung als Parameter angegeben.  
  
 Der der von einer Zuordnungsklasse bereitgestellte Iterator ist ein bidirektionaler Iterator. Die Klassenmemberfunktionen [insert](../Topic/map::insert.md) und [map](../Topic/map::map.md) weisen allerdings Versionen auf, einen abgeschwächten Eingabeiterator als einen Vorlagenparameter akzeptieren, dessen Funktionalitätsanforderungen weniger umfangreich sind, als die von der Klasse bidirektionaler Iteratoren garantierten.  Die verschiedenen Iteratorkonzepte sind durch Verfeinerungen in ihrer Funktionen verknüpft.  Jedes Iteratorkonzept weist einen eigenen Satz von Anforderungen auf, und damit einhergehenden Algorithmen müssen durch diese Anforderungen beschränkt werden.  Ein Eingabeiterator kann dereferenziert werden, um auf ein Objekt zu verweisen und wird zum folgenden Iterator in der Sequenz erhöht.  
  
 Es wird empfohlen, dass Sie die Auswahl des Containertyps auf Grundlage der für die Anwendung erforderlichen Such\- und Einfügeweise treffen.  Assoziative Container sind auf Such\-, Einfüge\- und Entfernvorgänge optimiert.  Die Memberfunktionen, die diese Vorgänge explizit unterstützen, führen sie in einer Zeit für den schlimmsten Fall aus, die zum Logarithmus der Elementanzahl im Container proportional ist.  Das Einfügen von Elementen führt nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen von Elementen werden nur solche Iteratoren ungültig, die speziell auf die entfernten Elemente gezeigt haben.  
  
 Es wird empfohlen, die Zuordnung der ausgewählten assoziativen Container zu erstellen, wenn die Bedingungen zur Zuordnung der Werte mit Schlüssel von der Anwendung erfüllt werden.  Ein Modell dieser Art von Struktur ist eine geordnete Liste eindeutig auftretender Schlüsselwörter, die Zeichenfolgewerte zugeordnet aufweisen, die Definitionen bereitstellen.  Wenn ein Wort über mehrere genaue Definition verfügt, sodass der Schlüssel nicht eindeutig ist, ist eine Mehrfachzuordnung der ausgewählte Container.  Wenn nur die Wortliste gespeichert wird, ist ein Satz der geeignete Container.  Wenn mehrfaches Vorkommen der Wörter zulässig ist, ist eine Multimenge geeignet.  
  
 Die Zuordnung sortiert die von ihr gesteuerten Elemente, indem ein gespeichertes Funktionsobjekt vom Typ [key\_compare](../Topic/map::key_compare.md) aufgerufen wird.  Bei diesem gespeicherten Objekt handelt es sich um eine Vergleichsfunktion, auf die zugegriffen wird, indem die [key\_comp](../Topic/map::key_comp.md)\-Methode aufgerufen wird.  Im Allgemeinen werden beliebige zwei angegebene Elemente verglichen, um zu bestimmen, ob eins kleiner als das andere ist, oder ob sie sich entsprechen.  Obwohl alle Elemente verglichen werden, wird eine sortierte Sequenz antivalenter Elementen erstellt.  
  
> [!NOTE]
>  Die Vergleichsfunktion ist ein binäres Prädikat, das eine strenge schwache Sortierung im üblichen mathematischen Sinn erzeugt.  Bei einem binären f\(x,y\)\-Prädikat handelt es sich um ein Funktionsobjekt, das zwei x und y\-Argumentobjekte aufweist sowie einen Rückgabewert von `true` oder `false`.  Eine Sortierung, die bei einem Satz erzeugt wird, ist eine strenge schwache Sortierung, wenn das binäre Prädikat irreflexiv, antisymmetrisch und transitiv ist, und wenn die Äquivalenz transitiv ist; wobei zwei Objekte x und y so definiert werden, dass sie äquivalent sind, wenn sowohl f\(x,y\) ``  als auch f\(y,x\)`false` sind.  Wenn der stärkere Gleichheitszustand zwischen Schlüsseln die Äquivalenz ersetzt, erfolgt die Sortierung total \(d. h., alle Elemente werden zueinander sortiert\), und die verglichenen Schlüssel sind von den einander nicht mehr zu unterscheiden.  
>   
>  In C \+\+ 14 können Sie heterogenes Nachschlagen durch Angabe des `std::less<>` oder `std::greater<>` Prädikats, das keine Typparameter aufweist, aktivieren.  Weitere Informationen finden Sie unter [Heterogenes Nachschlagen in assoziativen Containern](../standard-library/stl-containers.md#sequence_containers).  
  
## Mitglieder  
  
### Konstruktoren  
  
|||  
|-|-|  
|[Zuordnung](../Topic/map::map.md)|Erstellt eine Liste einer bestimmten Größe bzw. mit Elementen eines bestimmten Werts oder mit einem bestimmten `allocator`\-Element oder als vollständige bzw. teilweise Kopie einer anderen Zuordnung.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/map::allocator_type.md)|Eine Typdefinition für die `allocator`\-Klasse für das Zuordnungsobjekt.|  
|[const\_iterator](../Topic/map::const_iterator.md)|Eine Typdefinition für einen bidirektionalen Iterator, der ein `const`\-Element in der Zuordnung lesen kann.|  
|[const\_pointer](../Topic/map::const_pointer.md)|Eine Typdefinition für einen Zeiger auf ein `const`\-Element in einer Zuordnung.|  
|[const\_reference](../Topic/map::const_reference.md)|Eine Typedef für einen Verweis auf ein `const`\-Element bereitstellt, das in einer Zuordnung zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[const\_reverse\_iterator](../Topic/map::const_reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes `const`\-Element in der Zuordnung gelesen werden kann.|  
|[difference\_type](../Topic/map::difference_type.md)|Ein Ganzzahltyp mit Vorzeichen für die Anzahl von Elementen einer Zuordnung in einem Bereich zwischen Elementen, auf die von Iteratoren gezeigt wird.|  
|[Iterator](../Topic/map::iterator.md)|Eine Typedef für einen bidirektionalen Iterator, der ein beliebiges Element in einer Zuordnung lesen oder ändern kann.|  
|[key\_compare](../Topic/map::key_compare.md)|Eine Typedef für ein Funktionsobjekt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen in der Zuordnung zu bestimmen.|  
|[key\_type](../Topic/map::key_type.md)|Eine Typedef für den in jedem Element der Zuordnung gespeicherten Sortierschlüssel.|  
|[mapped\_type](../Topic/map::mapped_type.md)|Eine Typedef für die in jedem Element einer Zuordnung gespeicherten Daten.|  
|[pointer](../Topic/map::pointer.md)|Eine Typdefinition für einen Zeiger auf ein `const`\-Element in einer Zuordnung.|  
|[Verweis](../Topic/map::reference.md)|Eine Typedef für einen Verweis auf ein in einer Zuordnung gespeichertes Element.|  
|[reverse\_iterator](../Topic/map::reverse_iterator.md)|Eine Typdefinition für einen bidirektionalen Iterator, der ein beliebiges Element in einer reservierten Zuordnung lesen oder ändern kann.|  
|[size\_type](../Topic/map::size_type.md)|Eine Ganzzahltypedef ohne Vorzeichen für die Anzahl von Elementen in einer Zuordnung.|  
|[value\_type](../Topic/map::value_type.md)|Eine Typedef für den Typ des Objekts, der als Element in einer Zuordnung gespeichert wird.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[bei](../Topic/map::at.md)|Sucht ein Element mit einem angegebenen Schlüsselwert.|  
|[begin](../Topic/map::begin.md)|Gibt einen Iterator zurück, der auf das erste Element in der Zuordnung zeigt.|  
|[cbegin](../Topic/map::cbegin.md)|Gibt einen konstanten Iterator zurück, der auf das erste Element in der Zuordnung zeigt.|  
|[cend](../Topic/map::cend.md)|Gibt einen konstanten "past\-the\-end"\-Iterator zurück.|  
|[nicht aktiviert](../Topic/map::clear.md)|Löscht alle Elemente einer Zuordnung auf.|  
|[count](../Topic/map::count.md)|Gibt die Anzahl von Elementen in einer Zuordnung zurück, deren Schlüssel dem in einem Parameter angegebenen Schlüssel entspricht.|  
|[crbegin](../Topic/map::crbegin.md)|Gibt einen konstanten Iterator zurück, der auf das erste Element in einer umgekehrten Zuordnung zeigt.|  
|[crend](../Topic/map::crend.md)|Gibt einen konstanten Iterator zurück, der auf den Speicherort zeigt, der hinter dem letzten Element einer umgekehrten Zuordnung liegt.|  
|[emplace](../Topic/map::emplace.md)|Fügt ein Element ein, das vor Ort in die Zuordnung erstellt wird.|  
|[emplace\_hint](../Topic/map::emplace_hint.md)|Fügt ein Element ein, das vor Ort mit einem Platzierungshinweis in die Zuordnung erstellt wird.|  
|[Leer](../Topic/map::empty.md)|Gibt `true` zurück, wenn eine Zuordnung leer ist.|  
|[end](../Topic/map::end.md)|Gibt den "past\-the\-end"\-Iterator zurück.|  
|[equal\_range](../Topic/map::equal_range.md)|Gibt ein Paar von Iteratoren zurück.  Der erste Iterator im Paar zeigt auf das erste Element in `map` mit einem Schlüssel, der größer ist, als ein bestimmter Schlüssel.  Der zweite Iterator im Paar zeigt auf das erste Element in `map` mit einem Schlüssel, die größer oder gleich dem Schlüssel ist.|  
|[Löschen](../Topic/map::erase.md)|Entfernt ein Element oder eine Reihe von Elementen in einer Zuordnung aus den angegebenen Positionen.|  
|[find](../Topic/map::find.md)|Gibt einen Iterator zurück, der auf den Speicherort eines Elements in einer Zuordnung zeigt, der einen Schlüssel gleich einem angegebenen Schlüssel aufweist.|  
|[get\_allocator](../Topic/map::get_allocator.md)|Gibt eine Kopie des zum Erstellen der Zuordnung verwendeten `allocator`\-Objekts zurück.|  
|[Einfügen](../Topic/map::insert.md)|Fügt ein Element oder einen Reihe von Elementen an einer angegebenen Position in die Zuordnung ein.|  
|[key\_comp](../Topic/map::key_comp.md)|Gibt eine Kopie des Vergleichsobjekts zurück, das verwendet wird, um die Schlüssel in einer Zuordnung zu sortieren.|  
|[lower\_bound](../Topic/map::lower_bound.md)|Gibt einen Iterator zum ersten Element in einer Zuordnung zurück, die einen Schlüsselwert aufweist, der gleich oder größer ist als ein angegebener Schlüssel.|  
|[max\_size](../Topic/map::max_size.md)|Gibt die Maximallänge der Zuordnung zurück.|  
|[rbegin](../Topic/map::rbegin.md)|Gibt einen Iterator zurück, der auf das erste Element in einer umgekehrten Zuordnung zeigt.|  
|[rend](../Topic/map::rend.md)|Gibt einen Iterator zurück, der auf den Speicherort zeigt, der hinter dem letzten Element einer umgekehrten Zuordnung liegt.|  
|[size](../Topic/map::size.md)|Gibt die Anzahl von Elementen in der Zuordnung zurück.|  
|[swap](../Topic/map::swap.md)|Tauscht die Elemente zweier Zuordnungen aus.|  
|[upper\_bound](../Topic/map::upper_bound.md)|Gibt einen Iterator zum ersten Element in einer Zuordnung zurück, die einen Schlüsselwert aufweist, der größer ist als ein angegebener Schlüssel.|  
|[value\_comp](../Topic/map::value_comp.md)|Ruft eine Kopie des Vergleichsobjekts ab, das verwendet wird, um Elementwerte in einer Zuordnung zu sortieren.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator&#91;&#93;](../Topic/map::operator[].md)|Fügt ein Element in eine Zuordnung mit einem angegebenen Schlüsselwert ein.|  
|[operator \=](../Topic/map::operator=.md)|Ersetzt die Elemente einer Zuordnung durch einer Kopie einer anderen Zuordnung.|  
  
## Anforderungen  
 **Header:** \<map\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<map\> Members](assetId:///7e8f0bc2-6034-40f6-9d14-76d4cef86308)   
 [Container](../cpp/containers-modern-cpp.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)