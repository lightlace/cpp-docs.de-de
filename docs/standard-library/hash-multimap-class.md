---
title: "hash_multimap-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::hash_multimap"
  - "stdext.hash_multimap"
  - "hash_map/stdext::hash_multimap"
  - "hash_multimap"
  - "std::hash_multimap"
  - "std.hash_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_multimap-Klasse"
ms.assetid: f41a6db9-67aa-43a3-a3c5-dbfe9ec3ae7d
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# hash_multimap-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Diese API ist veraltet.  Die Alternative ist die [unordered\_multimap\-Klasse](../standard-library/unordered-multimap-class.md).  
  
 Die hash\_multimap\-Containerklasse ist eine Erweiterung der Standardvorlagenbibliothek und wird für das Speichern und schnelle Abrufen von Daten aus einer Auflistung verwendet, in der jedes Element ein Paar mit einem Sortierschlüssel ist, dessen Wert nicht eindeutig sein muss, und einem zugeordneten Datenwert.  
  
## Syntax  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<pair <const Key, Type> >   
>  
class hash_multimap  
```  
  
#### Parameter  
 `Key`  
 Der im hash\_multimap\-Element zu speichernde Schlüsseldatentyp.  
  
 `Type`  
 Der im hash\_multimap\-Element zu speichernde Elementdatentyp.  
  
 `Traits`  
 Der Typ, der zwei Funktionsobjekte enthält. Einer der Klasse `Traits`, der zwei Elementwerte als Sortierschlüssel vergleichen kann, um ihre relative Position zu bestimmen und eine Hashfunktion, die ein Zuordnungsschlüssel mit unärem Prädikat der Elemente für ganzen Zahlen ohne Vorzeichen vom Typ **size\_t** ist.  Dieses Argument ist optional, und `hash_compare``<Key, less<Key> >` ist der Standardwert.  
  
 `Allocator`  
 Der Typ, mit dem das gespeicherte Zuordnungsobjekt darstellt wird, mit dem Details zum Belegen und Freigeben des Arbeitsspeichers des hash\_multimap\-Elements gekapselt werden.  Dieses Argument ist optional, und der Standardwert ist `allocator<pair <const Key, Type> >`.  
  
## Hinweise  
 Das hash\_multimap\-Element ist:  
  
-   Ein assoziativer Container, der ein Container variabler Größe ist, der den effizienten Abruf von Elementwerten auf Grundlage eines zugeordneten Schlüsselwert unterstützt.  
  
-   Umkehrbar, da ein bidirektionaler Iterator für den Zugriff auf die Elemente bereitgestellt wird.  
  
-   Gehasht, da die Elemente auf Grundlage des Werts einer Hashfunktion, die auf die Schlüsselwerte der Elemente angewendet wird, in Buckets gruppiert werden.  
  
-   Mehrfach, da die Elemente keine eindeutige Schlüssel aufweisen müssen, damit ein Schlüsselwert über viele zugeordnete Elementdatenwerte verfügen kann.  
  
-   Ein Paar assoziativer Container, da sich die Elementwerte von den Schlüsselwerten unterscheiden.  
  
-   Eine Vorlagenklasse, da die bereitgestellten Funktionen generisch ist und daher unabhängig vom angegebenen Datentyp, der als Elemente oder Schlüssel enthalten ist.  Die für Elemente und Schlüssel zu verwendenden Datentypen werden stattdessen in der Klassenvorlage zusammen mit der Vergleichsfunktion und der Zuweisung als Parameter angegeben.  
  
 Der Hauptvorteil des Hashverfahrens gegenüber der Sortierung ist die größere Effizienz. Bei einem erfolgreichen Hashverfahren werden Einfüge\-, Lösch\- und Suchvorgänge, verglichen mit einer Zeit, die zum Logarithmus der Anzahl von Elementen im Container für Sortiertechniken proportional ist, in einer konstanten Durchschnittszeit durchgeführt.  Der Wert eines Elements in einem hash\_multimap\-Element, aber nicht der zugehörige Schlüsselwert, werden möglicherweise direkt geändert.  Stattdessen müssen die Schlüsselwerte, die alten Elementen zugeordnet sind, gelöscht, und stattdessen neuen Schlüsselwerten für neue Elemente zugeordnet werden.  
  
 Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen.  Gehashte assoziative Container sind für Such\-, Einfüge\- und Entfernvorgänge optimiert.  Die Memberfunktionen, die diese Vorgänge explizit unterstützen, sind effizient, wenn sie mit einer gut entworfenen Hashfunktion verwendet werden. Dann werden sie in einer Zeit ausgeführt, die im Durchschnitt konstant und nicht von der Anzahl von Elementen im Container abhängig ist.  Eine ausgereifte Hashfunktion erzeugt eine vereinheitlichte Verteilung gehashter Werte und minimiert die Anzahl von Konflikten, bei denen ein Konflikt vorhergesagt wird, wenn unterschiedliche Schlüsselwerte dem gleichen gehashten Wert zugeordnet werden.  Im schlimmsten Fall ist die Anzahl von Vorgängen bei der schlimmstmöglichen Hashfunktion zu der Anzahl von Elementen in der Sequenz proportional \(lineare Zeit\).  
  
 Das hash\_multimap\-Element sollte der ausgewählte assoziative Container sein, wenn die Bedingungen, mit denen die Werte von der Anwendung den Schlüsseln zugeordnet werden, erfüllt werden.  Ein Modell für diesen Strukturtyp ist eine sortierte Liste von Schlüsselwörtern mit zugeordneten Zeichenfolgewerten, die, sagen wir, Definitionen bereitstellen, in denen die Wörter nicht immer eindeutig definiert wurden.  Wenn die Schlüsselwörter stattdessen eindeutig definiert werden, damit die Schlüssel eindeutig sind, ist ein hash\_map\-Element der gewählte Container.  Wenn hingegen nur die Wortliste gespeichert wurden, ist ein hash\_set\-Element der richtige Container.  Wenn mehrfaches Vorkommen der Wörter zugelassen wird, ist ein hash\_multiset\-Element die geeignete Containerstruktur.  
  
 Das hash\_multimap\-Element sortiert die gesteuerte Sequenz, indem ein gespeichertes `Traits`\-Hashobjekt des Objekts [value\_compare](../standard-library/value-compare-class.md) aufgerufen wird.  Auf das gespeicherte Objekt wird möglicherweise zugegriffen, indem die Memberfunktion [key\_comp](../Topic/hash_map::key_comp.md) aufrufen wird.  Ein solches Funktionsobjekt muss dasselbe Verhalten haben wie ein aus der Klasse [hash\_compare](../standard-library/hash-compare-class.md)`<Key,  less<Key> >` abgeleitetes Objekt.  Insbesondere für alle `Key`\-Werte des Typs `Key`, erreicht der `Traits (Key)`\-Aufruf eine Verteilung der Werte vom Typ `size_t`.  
  
 Im Allgemeinen müssen die Elemente der Vorwärtsiteratoren etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass beliebige zwei Elemente möglicherweise als gleichwertig bestimmt werden \(in dem Sinne, dass keins geringer als das Andere ist\), oder dass eins geringer als das Andere ist.  Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.  Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht.  Bei einem binären f\(x, y\)\-\-Prädikat handelt es sich um ein Funktionsobjekt, das die zwei Argumentobjekte `x` und `y` aufweist sowie einen Rückgabewert von `true` oder `false`.  Eine Sortierung, die auf ein hash\_multimap\-Element angewendet wird, ist eine strenge schwache Sortierung, wenn das binäre Prädikat irreflexiv, antisymmetrisch und transitiv ist, und wenn die Äquivalenz transitiv ist, wobei die beiden Objekte `x` und `y` als äquivalent definiert werden, wenn sowohl f \(x, y\) als auch f \(x, y\) `false` sind.  Wenn der stärkere Gleichheitszustand zwischen Schlüsseln die Äquivalenz ersetzt, erfolgt die Sortierung total \(d. h., alle Elemente werden zueinander sortiert\), und die verglichenen Schlüssel sind von den einander nicht mehr zu unterscheiden.  
  
 Die tatsächliche Reihenfolge der Elemente in der gesteuerten Sequenz hängt von der Hashfunktion, der Sortierfunktion und der aktuellen Größe der Hashtabelle ab, die im Containerobjekt gespeichert wird.  Die aktuelle Größe der Hashtabelle kann nicht bestimmt werden. Deshalb kann die Reihenfolge der Elemente in der gesteuerten Sequenz im Allgemeinen nicht vorhergesagt werden.  Das Einfügen von Elementen führt nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen von Elementen werden nur solche Iteratoren ungültig, die speziell auf die entfernten Elemente gezeigt haben.  
  
 Der von einer hash\_multimap\-Klasse bereitgestellte Iterator ist ein bidirektionaler Iterator. Die Klassenmemberfunktionen [insert](../Topic/hash_multimap::insert.md) und [hash\_multimap](../Topic/hash_multimap::hash_multimap.md) weisen allerdings Versionen auf, einen abgeschwächten Eingabeiterator als einen Vorlagenparameter akzeptieren, dessen Funktionalitätsanforderungen weniger umfangreich sind, als die von der Klasse bidirektionaler Iteratoren garantierten.  Die verschiedenen Iteratorkonzepte bilden eine Family, die durch Verfeinerungen in ihrer Funktionen verknüpft ist.  Jedes Iteratorkonzept weist einen eigenes hash\_multimap\-Element von Anforderungen auf, und die damit funktionierenden Algorithmen müssen die Annahmen hinsichtlich der von diesem Iteratortyp bereitgestellten Anforderungen begrenzen.  Es kann davon ausgegangen werden, dass ein Eingabeiterator möglicherweise so dereferenziert wird, dass er auf ein Objekt verweist und dieses möglicherweise zum folgenden Iterator in der Sequenz erhöht.  Das ist eine minimaler hash\_multimap\-Funktion, allerdings genügt sie, um sinnvoll über einen Bereich von `[First, Last)`\-Iteratoren im Kontext der Klassenmemberfunktionen zu sprechen.  
  
 In Visual C\+\+ .NET 2003 sind Member der [\<hash\_map\>](../standard-library/hash-map.md) und [\<hash\_set\>](../standard-library/hash-set.md) Headerdateien nicht mehr im STD\-Namespace enthalten. Sie wurden stattdessen in den stdext\-Namespace verschoben.  Weitere Informationen finden Sie unter [Der stdext\-Namespace](../standard-library/stdext-namespace.md).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[hash\_multimap](../Topic/hash_multimap::hash_multimap.md)|Erstellt eine Liste einer bestimmten Größe bzw. mit Elementen eines bestimmten Werts oder mit einem bestimmten `allocator`\-Element oder als vollständige bzw. teilweise Kopie eines anderen `hash_multimap`\-Elements.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_multimap::allocator_type.md)|Ein Typ, der die `allocator`\-Klassentyp für das `hash_multimap`\-Objekt darstellt.|  
|[const\_iterator](../Topic/hash_multimap::const_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`\-Element ein `hash_multimap`\-Element lesen kann.|  
|[const\_pointer](../Topic/hash_multimap::const_pointer.md)|Ein Typ, der einen Zeiger auf ein `const`\-Element in einem `hash_multimap`\-Element bereitstellt.|  
|[const\_reference](../Topic/hash_multimap::const_reference.md)|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einem `hash_multimap`\-Element zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[const\_reverse\_iterator](../Topic/hash_multimap::const_reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`\-Element jedes `hash_multimap`\-Element lesen kann.|  
|[difference\_type](../Topic/hash_multimap::difference_type.md)|Ein Ganzzahltyp mit Vorzeichen, der dazu verwendet werden kann, die Anzahl von Elementen eines `hash_multimap`\-Elements in einen Bereich zwischen Elementen darzustellen, auf die von Iteratoren gezeigt wird.|  
|[Iterator](../Topic/hash_multimap::iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes Element in einer `hash_multimap` gelesen oder geändert werden kann.|  
|[key\_compare](../Topic/hash_multimap::key_compare.md)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen im `hash_multimap`\-Element zu bestimmen.|  
|[key\_type](../Topic/hash_multimap::key_type.md)|Ein Typ, mit dem das Sortierschlüsselobjekt beschrieben wird, das jedes Element von `hash_multimap` bildet.|  
|[mapped\_type](../Topic/hash_multimap::mapped_type.md)|Ein Typ, der den in einer `hash_multimap` gespeicherten Datentyp darstellt.|  
|[pointer](../Topic/hash_multimap::pointer.md)|Ein Typ, der einen Zeiger auf ein Element in einer `hash_multimap` bereitstellt.|  
|[Verweis](../Topic/hash_multimap::reference.md)|Ein Typ, der einen Verweis auf ein in einer `hash_multimap` gespeichertes Element bereitstellt.|  
|[reverse\_iterator](../Topic/hash_multimap::reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein Element in einem umgekehrten `hash_multimap`\-Element gelesen oder geändert werden kann.|  
|[size\_type](../Topic/hash_multimap::size_type.md)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `hash_multimap` darstellen kann.|  
|[value\_type](../Topic/hash_multimap::value_type.md)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Elemente als Sortierschlüssel vergleichen kann, um die relative Position im `hash_multimap`\-Element zu bestimmen.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[begin](../Topic/hash_multimap::begin.md)|Gibt ein Iterator zurück, der das erste Element im `hash_multimap`\-Element adressiert.|  
|[hash\_multimap::cbegin](../Topic/hash_multimap::cbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im `hash_multimap`\-Element adressiert.|  
|[hash\_multimap::cend](../Topic/hash_multimap::cend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines `hash_multimap`\-Elements nachfolgt.|  
|[nicht aktiviert](../Topic/hash_multimap::clear.md)|Löscht alle Elemente einer `hash_multimap` auf.|  
|[count](../Topic/hash_multimap::count.md)|Gibt die Anzahl von Elementen in einem `hash_multimap`\-Element zurück, dessen Schlüssel dem von einem Parameter angegebenen Schlüssel entspricht.|  
|[hash\_multimap::crbegin](../Topic/hash_multimap::crbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im umgekehrten `hash_multimap`\-Element adressiert.|  
|[hash\_multimap::crend](../Topic/hash_multimap::crend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `hash_multimap`\-Elements nachfolgt.|  
|[hash\_multimap::emplace](../Topic/hash_multimap::emplace.md)|Fügt ein Element ein, das vor Ort in ein `hash_multimap`\-Element erstellt wird.|  
|[hash\_multimap::emplace\_hint](../Topic/hash_multimap::emplace_hint.md)|Fügt ein Element ein, das vor Ort mit einem Platzierungshinweis in ein `hash_multimap`\-Element erstellt wird.|  
|[Leer](../Topic/hash_multimap::empty.md)|Testet, ob ein `hash_multimap`\-Element leer ist.|  
|[end](../Topic/hash_multimap::end.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einem `hash_multimap`\-Element nachfolgt.|  
|[equal\_range](../Topic/hash_multimap::equal_range.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einem `hash_multimap`\-Element nachfolgt.|  
|[Löschen](../Topic/hash_multimap::erase.md)|Entfernt ein Element oder eine Reihe von Elementen in einer `hash_multimap` aus angegebenen Speicherorten.|  
|[find](../Topic/hash_multimap::find.md)|Gibt einen Iterator zurück, der die Position eines Elements in einem `hash_multimap`\-Element adressiert, das einen Schlüssel aufweist, der einen angegebenen Schlüssel entspricht.|  
|[get\_allocator](../Topic/hash_multimap::get_allocator.md)|Gibt eine Kopie des zum Erstellen von `allocator` verwendeten `hash_multimap`\-Objekts zurück.|  
|[Einfügen](../Topic/hash_multimap::insert.md)|Fügt ein Element oder einen Elementbereich an einer angegebenen Position in das `hash_multimap`\-Element ein.|  
|[key\_comp](../Topic/hash_multimap::key_comp.md)|Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Schlüssel in `hash_multimap` verwendet wird.|  
|[lower\_bound](../Topic/hash_multimap::lower_bound.md)|Gibt einen Iterator zum ersten Element in einem `hash_multimap`\-Element mit einem Schlüsselwert zurück, der gleich oder größer ist, als ein angegebener Schlüssel.|  
|[max\_size](../Topic/hash_multimap::max_size.md)|Gibt die Maximallänge der `hash_multimap` zurück.|  
|[rbegin](../Topic/hash_multimap::rbegin.md)|Gibt einen Iterator zurück, der das erste Element in einem umgekehrten `hash_multimap`\-Element adressiert.|  
|[rend](../Topic/hash_multimap::rend.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `hash_multimap`\-Elements nachfolgt.|  
|[size](../Topic/hash_multimap::size.md)|Gibt eine neue Größe für eine `hash_multimap` an.|  
|[swap](../Topic/hash_multimap::swap.md)|Tauscht die Elemente zweier `hash_multimap`n.|  
|[upper\_bound](../Topic/hash_multimap::upper_bound.md)|Gibt einen Iterator zum ersten Element in einem `hash_multimap`\-Element mit einem Schlüsselwert zurück, der größer ist, als ein angegebener Schlüssel.|  
|[value\_comp](../Topic/hash_multimap::value_comp.md)|Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Elementwerte in `hash_multimap` verwendet wird.|  
  
### Operatoren  
  
|||  
|-|-|  
|[hash\_multimap::operator\=](../Topic/hash_multimap::operator=.md)|Ersetzt die Elemente eines `hash_multimap`\-Elements durch eine Kopie eines anderen `hash_multimap`\-Elements.|  
  
## Anforderungen  
 **Header:** \<hash\_map\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)