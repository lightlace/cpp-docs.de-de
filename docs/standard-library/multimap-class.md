---
title: "multimap-Klasse"
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
  - "multimap"
  - "std.multimap"
  - "map/std::multimap"
  - "std::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multimap-Klasse"
ms.assetid: 8796ae05-37c4-475a-9e61-75fde9d4a463
caps.latest.revision: 23
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# multimap-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Standardvorlagenbibliothek\-Mehrfachzuordnungsklasse wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der jedes Element ein Paar ist, das einen Datenwert und einen Sortierschlüssel hat.  Der Wert der Schlüssel muss nicht eindeutig sein und wird verwendet, um die Daten automatisch zu sortieren.  Der Wert eines Elements in einer Mehrfachzuordnung, aber nicht der zugehörige Schlüsselwert, wird möglicherweise direkt geändert.  Stattdessen müssen die Schlüsselwerte, die alten Elementen zugeordnet sind, gelöscht, und stattdessen neuen Schlüsselwerten für neue Elemente zugeordnet werden.  
  
## Syntax  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits=less<Key>,   
   class Allocator=allocator<pair <const Key, Type> >   
> class multimap;  
```  
  
#### Parameter  
 `Key`  
 Der in der Mehrfachzuordnung zu speichernde Schlüsseldatentyp.  
  
 `Type`  
 Der in der Mehrfachzuordnung zu speichernde Elementdatentyp.  
  
 `Traits`  
 Der Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in der Mehrfachzuordnung zu bestimmen.  Das binäre Prädikat `less<Key>` ist der Standardwert.  
  
 In C \+\+ 14 können Sie heterogenes Nachschlagen durch Angabe des `std::less<>` oder `std::greater<>` Prädikats, das keine Typparameter aufweist, aktivieren.  Weitere Informationen finden Sie unter [Heterogenes Nachschlagen in assoziativen Containern](../standard-library/stl-containers.md#sequence_containers)  
  
 `Allocator`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zum Belegen und Freigeben des Arbeitsspeichers der Zuordnung kapselt.  Dieses Argument ist optional, und der Standardwert ist `allocator<pair <const Key, Type> >`.  
  
## Hinweise  
 Die STL\-Mehrfachzuordnungsklasse ist  
  
-   Ein assoziativer Container, der ein Container variabler Größe ist, der den effizienten Abruf von Elementwerten auf Grundlage eines zugeordneten Schlüsselwert unterstützt.  
  
-   Umkehrbar, da bidirektionale Iteratoren für den Zugriff auf die Elemente bereitgestellt werden.  
  
-   Sortiert, da die Elemente anhand von Schlüsselwerten innerhalb des Containers mit einer angegebenen Vergleichsfunktion sortiert werden.  
  
-   Mehrfach, da die Elemente keine eindeutige Schlüssel aufweisen müssen, damit ein Schlüsselwert über viele zugeordnete Elementdatenwerte verfügen kann.  
  
-   Ein Paar assoziativer Container, da sich die Elementdatenwerte von den Schlüsselwerten unterscheiden.  
  
-   Eine Vorlagenklasse, da die bereitgestellten Funktionen generisch ist und daher unabhängig vom angegebenen Datentyp, der als Elemente oder Schlüssel enthalten ist.  Die für Elemente und Schlüssel zu verwendenden Datentypen werden stattdessen in der Klassenvorlage zusammen mit der Vergleichsfunktion und der Zuweisung als Parameter angegeben.  
  
 Der von einer Zuordnungsklasse bereitgestellte Iterator ist ein bidirektionaler Iterator. Die Klassenmemberfunktionen [insert](../Topic/multimap::insert.md) und [multimap](../Topic/multimap::multimap.md) weisen allerdings Versionen auf, die einen abgeschwächten Eingabeiterator als Vorlagenparameter akzeptieren, dessen Funktionalitätsanforderungen weniger umfangreich sind, als die von der Klasse bidirektionaler Iteratoren garantierten.  Die verschiedenen Iteratorkonzepte bilden eine Family, die durch Verfeinerungen in ihrer Funktionen verknüpft ist.  Jedes Iteratorkonzept weist einen eigenen Satz von Anforderungen auf, und die damit funktionierenden Algorithmen müssen die Annahmen hinsichtlich der von diesem Iteratortyp bereitgestellten Anforderungen begrenzen.  Es kann davon ausgegangen werden, dass ein Eingabeiterator möglicherweise so dereferenziert wird, dass er auf ein Objekt verweist und dieses möglicherweise zum folgenden Iterator in der Sequenz erhöht.  Das ist ein minimaler Funktionssatz, allerdings genügt er, um sinnvoll über einen Bereich von `[First, Last)`\-Iteratoren im Kontext der Klassenmemberfunktionen zu sprechen.  
  
 Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen.  Assoziative Container sind für Such\-, Einfüge\- und Entfernvorgänge optimiert.  Die Memberfunktionen, die diese Vorgänge explizit unterstützen, sind effizient und führen sie in einer Zeit aus, die zum Logarithmus der Elementanzahl im Container im Durchschnitt proportional ist.  Das Einfügen von Elementen führt nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen von Elementen werden nur solche Iteratoren ungültig, die speziell auf die entfernten Elemente gezeigt haben.  
  
 Die Mehrfachzuordnung sollte der ausgewählte assoziative Container sein, wenn die Bedingungen, mit denen die Werte von der Anwendung den Schlüsseln zugeordnet werden, erfüllt werden.  Ein Modell für diesen Strukturtyp ist eine sortierte Liste von Schlüsselwörtern mit zugeordneten Zeichenfolgewerten, die, sagen wir, Definitionen bereitstellen, in denen die Wörter nicht immer eindeutig definiert wurden.  Wenn die Schlüsselwörter stattdessen eindeutig definiert werden, damit die Schlüssel eindeutig sind, ist eine Zuordnung der gewählte Container.  Wenn hingegen nur die Wortliste gespeichert wurde, ist ein Satz der richtige Container.  Wenn mehrfaches Vorkommen der Wörter zugelassen wird, ist eine Multimenge die geeignete Containerstruktur.  
  
 Die Mehrfachzuordnung sortiert die von ihr gesteuerte Sequenz, indem ein gespeichertes Funktionsobjekt vom Typ [key\_compare](../Topic/multimap::key_compare.md) aufgerufen wird.  Bei diesem gespeicherten Objekt handelt es sich um eine Vergleichsfunktion, auf die zugegriffen werden kann, indem die [key\_comp](../Topic/multimap::key_comp.md)\-Memberfunktion aufgerufen wird.  Im Allgemeinen müssen die Elemente der Vorwärtsiteratoren etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass beliebige zwei Elemente möglicherweise als gleichwertig bestimmt werden \(in dem Sinne, dass keins geringer als das Andere ist\), oder dass eins geringer als das Andere ist.  Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.  Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht.  Bei einem binären `f(x,y)`\-Prädikat handelt es sich um ein Funktionsobjekt, das die zwei Argumentobjekte `x` und `y` aufweist sowie einen Rückgabewert von "true" oder "false".  Eine Sortierung, die bei einem Satz erzeugt wird, ist eine strenge schwache Sortierung, wenn das binäre Prädikat irreflexiv, antisymmetrisch und transitiv ist, und wenn die Äquivalenz transitiv ist; wobei zwei Objekte `x` und `y` so definiert werden, dass sie äquivalent sind, wenn sowohl `f(x,y)` als auch `f(y,x)` "false" ist.  Wenn der stärkere Gleichheitszustand zwischen Schlüsseln die Äquivalenz ersetzt, erfolgt die Sortierung total \(d. h., alle Elemente werden zueinander sortiert\), und die verglichenen Schlüssel sind von den einander nicht mehr zu unterscheiden.  
  
 In C \+\+ 14 können Sie heterogenes Nachschlagen durch Angabe des `std::less<>` oder `std::greater<>` Prädikats, das keine Typparameter aufweist, aktivieren.  Weitere Informationen finden Sie unter [Heterogenes Nachschlagen in assoziativen Containern](../standard-library/stl-containers.md#sequence_containers)  
  
## Mitglieder  
  
### Konstruktoren  
  
|||  
|-|-|  
|[multimap](../Topic/multimap::multimap.md)|Erstellt ein `multimap`\-Element, das leer oder die Kopie eines ganzen anderen `multimap`\-Elements oder eines Teils davon ist.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/multimap::allocator_type.md)|Ein Typ, der die `allocator`\-Klassentyp für das `multimap`\-Objekt darstellt.|  
|[const\_iterator](../Topic/multimap::const_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`\-Element ein `multimap`\-Element lesen kann.|  
|[const\_pointer](../Topic/multimap::const_pointer.md)|Ein Typ, der einen Zeiger auf ein `const`\-Element in einem `multimap`\-Element bereitstellt.|  
|[const\_reference](../Topic/multimap::const_reference.md)|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einem `multimap`\-Element zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[const\_reverse\_iterator](../Topic/multimap::const_reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`\-Element jedes `multimap`\-Element lesen kann.|  
|[difference\_type](../Topic/multimap::difference_type.md)|Ein Ganzzahltyp mit Vorzeichen, der dazu verwendet werden kann, die Anzahl von Elementen eines `multimap`\-Elements in einen Bereich zwischen Elementen darzustellen, auf die von Iteratoren gezeigt wird.|  
|[Iterator](../Topic/multimap::iterator.md)|Ein Typ, der den Unterschied zwischen zwei Iteratoren, die auf Elemente innerhalb derselben `multimap` verweisen, bereitstellt.|  
|[key\_compare](../Topic/multimap::key_compare.md)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen im `multimap`\-Element zu bestimmen.|  
|[key\_type](../Topic/multimap::key_type.md)|Ein Typ, mit dem das Sortierschlüsselobjekt beschrieben wird, das jedes Element von `multimap` bildet.|  
|[mapped\_type](../Topic/multimap::mapped_type.md)|Ein Typ, der den in einer `multimap` gespeicherten Datentyp darstellt.|  
|[pointer](../Topic/multimap::pointer.md)|Ein Typ, der einen Zeiger auf ein `const`\-Element in einem `multimap`\-Element bereitstellt.|  
|[Verweis](../Topic/multimap::reference.md)|Ein Typ, der einen Verweis auf ein in einer `multimap` gespeichertes Element bereitstellt.|  
|[reverse\_iterator](../Topic/multimap::reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein Element in einem umgekehrten `multimap`\-Element gelesen oder geändert werden kann.|  
|[size\_type](../Topic/multimap::size_type.md)|Ein ganze Zahl ohne Vorzeichen, die einen Zeiger auf ein `const`\-Element in einer `multimap` bereitstellt.|  
|[value\_type](../Topic/multimap::value_type.md)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Elemente als Sortierschlüssel vergleichen kann, um die relative Position im `multimap`\-Element zu bestimmen.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[begin](../Topic/multimap::begin.md)|Gibt ein Iterator zurück, der das erste Element im `multimap`\-Element adressiert.|  
|[cbegin](../Topic/multimap::cbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im `multimap`\-Element adressiert.|  
|[cend](../Topic/multimap::cend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines `multimap`\-Elements nachfolgt.|  
|[nicht aktiviert](../Topic/multimap::clear.md)|Löscht alle Elemente einer `multimap` auf.|  
|[count](../Topic/multimap::count.md)|Gibt die Anzahl von Elementen in einem `multimap`\-Element zurück, dessen Schlüssel dem von einem Parameter angegebenen Schlüssel entspricht.|  
|[crbegin](../Topic/multimap::crbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im umgekehrten `multimap`\-Element adressiert.|  
|[crend](../Topic/multimap::crend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `multimap`\-Elements nachfolgt.|  
|[emplace](../Topic/multimap::emplace.md)|Fügt ein Element ein, das vor Ort in ein `multimap`\-Element erstellt wird.|  
|[emplace\_hint](../Topic/multimap::emplace_hint.md)|Fügt ein Element ein, das vor Ort mit einem Platzierungshinweis in ein `multimap`\-Element erstellt wird.|  
|[Leer](../Topic/multimap::empty.md)|Testet, ob ein `multimap`\-Element leer ist.|  
|[end](../Topic/multimap::end.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einem `multimap`\-Element nachfolgt.|  
|[equal\_range](../Topic/multimap::equal_range.md)|Sucht den Bereich von Elementen, in dem der Schlüssel des Elements einem angegebenen Wert entspricht.|  
|[Löschen](../Topic/multimap::erase.md)|Es wird ein Element oder ein Bereich von Elementen in einem `multimap` von angegebenen Speicherorten entfernt, oder es werden die einem angegebenen Schlüssel entsprechenden Elemente entfernt.|  
|[find](../Topic/multimap::find.md)|Gibt einen Iterator zurück, der die erste Position eines Elements in einem `multimap`\-Element adressiert, das einen Schlüssel aufweist, der einem angegebenen Schlüssel entspricht.|  
|[get\_allocator](../Topic/multimap::get_allocator.md)|Gibt eine Kopie des zum Erstellen von `allocator` verwendeten `multimap`\-Objekts zurück.|  
|[Einfügen](../Topic/multimap::insert.md)|Fügt ein Element oder einen Elementbereich in ein `multimap`\-Element ein.|  
|[key\_comp](../Topic/multimap::key_comp.md)|Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Schlüssel in `multimap` verwendet wird.|  
|[lower\_bound](../Topic/multimap::lower_bound.md)|Gibt einen Iterator zum ersten Element in einem `multimap`\-Element mit einem Schlüssel zurück, der gleich oder größer ist als ein angegebener Schlüssel.|  
|[max\_size](../Topic/multimap::max_size.md)|Gibt die Maximallänge der `multimap` zurück.|  
|[rbegin](../Topic/multimap::rbegin.md)|Gibt einen Iterator zurück, der das erste Element in einem umgekehrten `multimap`\-Element adressiert.|  
|[rend](../Topic/multimap::rend.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `multimap`\-Elements nachfolgt.|  
|[size](../Topic/multimap::size.md)|Gibt die Anzahl von Elementen in der `multimap` zurück.|  
|[swap](../Topic/multimap::swap.md)|Tauscht die Elemente zweier `multimap`n.|  
|[upper\_bound](../Topic/multimap::upper_bound.md)|Gibt einen Iterator zum ersten Element in einem `multimap`\-Element mit einem Schlüssel zurück, der größer ist als ein angegebener Schlüssel.|  
|[value\_comp](../Topic/multimap::value_comp.md)|Die Memberfunktion gibt ein Funktionsobjekt zurück, das die Reihenfolge der Elemente in einer `multimap` bestimmt, indem ihre Schlüsselwerte verglichen werden.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/multimap::operator=.md)|Ersetzt die Elemente eines `multimap`\-Elements durch eine Kopie eines anderen `multimap`\-Elements.|  
  
## Anforderungen  
 **Header:** \<map\>  
  
 **Namespace:** std  
  
 Die Paare \(**key**, **value**\) werden in einer Multimenge als Objekte vom Typ `pair` gespeichert.  Die Paarklasse erfordert das Header\-\<Hilfsprogramm\>, das automatisch durch die \<Zuordnung\>enthalten ist.  
  
## Siehe auch  
 [\<map\>](assetId:///7e8f0bc2-6034-40f6-9d14-76d4cef86308)   
 [Container](../cpp/containers-modern-cpp.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)