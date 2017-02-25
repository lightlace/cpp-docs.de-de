---
title: "hash_map-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::hash_map"
  - "hash_map/stdext::hash_map"
  - "std.hash_map"
  - "stdext.hash_map"
  - "std::hash_map"
  - "hash_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_map-Klasse"
ms.assetid: 40879dfc-51ba-4a59-9f9e-26208de568a8
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# hash_map-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Diese API ist veraltet.  Die Alternative ist die [unordered\_map\-Klasse](../standard-library/unordered-map-class.md).  
  
 Speichert Daten und ruft sie schnell aus einer Auflistung ab, in der jedes Element ein Paar ist, das einen Sortierschlüssel aufweist, dessen Wert eindeutig und ein zugeordneter Datenwert ist.  
  
## Syntax  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<pair <const Key, Type> >   
>  
class hash_map  
```  
  
#### Parameter  
 `Key`  
 Der im hash\_map\-Element zu speichernde Schlüsseldatentyp.  
  
 `Type`  
 Der im hash\_map\-Element zu speichernde Elementdatentyp.  
  
 `Traits`  
 Der Typ, der zwei Funktionsobjekte enthält. Eins der Klasse "compare", der zwei Elementwerte als Sortierschlüssel vergleichen kann, um ihre relative Position zu bestimmen, und eine Hashfunktion, die ein Zuordnungsschlüssel mit unärem Prädikat der Elemente für ganzen Zahlen ohne Vorzeichen vom Typ `size_t` ist.  Dieses Argument ist optional, und der Standardwert ist hash\_compare\<`Key`, less\<`Key`\> \>.  
  
 `Allocator`  
 Der Typ, mit dem das gespeicherte Zuordnungsobjekt darstellt wird, mit dem Details zum Belegen und Freigeben des Arbeitsspeichers des hash\_map\-Elements gekapselt werden.  Dieses Argument ist optional, und der Standardwert ist allocator\<pair \<const `Key`, `Type`\>\>.  
  
## Hinweise  
 Das hash\_map\-Element ist:  
  
-   Ein assoziativer Container, der ein Container variabler Größe ist, der den effizienten Abruf von Elementwerten auf Grundlage eines zugeordneten Schlüsselwert unterstützt.  
  
-   Umkehrbar, da ein bidirektionaler Iterator für den Zugriff auf die Elemente bereitgestellt wird.  
  
-   Gehasht, da die Elemente auf Grundlage des Werts einer Hashfunktion, die auf die Schlüsselwerte der Elemente angewendet wird, in Buckets gruppiert werden.  
  
-   Insofern eindeutig, da jedes der Elemente einen eindeutigen Schlüssel aufweisen muss.  
  
-   Ein Paar assoziativer Container, da sich die Elementdatenwerte von den Schlüsselwerten unterscheiden.  
  
-   Eine Vorlagenklasse, da die bereitgestellten Funktionen generisch ist und daher unabhängig vom angegebenen Datentyp, der als Elemente oder Schlüssel enthalten ist.  Die für Elemente und Schlüssel zu verwendenden Datentypen werden stattdessen in der Klassenvorlage zusammen mit der Vergleichsfunktion und der Zuweisung als Parameter angegeben.  
  
 Der Hauptvorteil des Hashverfahrens gegenüber der Sortierung ist die größere Effizienz. Bei einem erfolgreichen Hashverfahren werden Einfüge\-, Lösch\- und Suchvorgänge, verglichen mit einer Zeit, die zum Logarithmus der Anzahl von Elementen im Container für Sortiertechniken proportional ist, in einer konstanten Durchschnittszeit durchgeführt.  Der Wert eines Elements in einem hash\_map\-Element, aber nicht der zugehörige Schlüsselwert, werden möglicherweise direkt geändert.  Stattdessen müssen die Schlüsselwerte, die alten Elementen zugeordnet sind, gelöscht, und stattdessen neuen Schlüsselwerten für neue Elemente zugeordnet werden.  
  
 Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen.  Gehashte assoziative Container sind für Such\-, Einfüge\- und Entfernvorgänge optimiert.  Die Memberfunktionen, die diese Vorgänge explizit unterstützen, sind effizient, wenn sie mit einer gut entworfenen Hashfunktion verwendet werden. Dann werden sie in einer Zeit ausgeführt, die im Durchschnitt konstant und nicht von der Anzahl von Elementen im Container abhängig ist.  Eine ausgereifte Hashfunktion erzeugt eine vereinheitlichte Verteilung gehashter Werte und minimiert die Anzahl von Konflikten, bei denen ein Konflikt vorhergesagt wird, wenn unterschiedliche Schlüsselwerte dem gleichen gehashten Wert zugeordnet werden.  Im schlimmsten Fall ist die Anzahl von Vorgängen bei der schlimmstmöglichen Hashfunktion zu der Anzahl von Elementen in der Sequenz proportional \(lineare Zeit\).  
  
 Das hash\_map\-Element sollte der ausgewählte assoziative Container sein, wenn die Bedingungen, mit denen die Werte von der Anwendung den Schlüsseln zugeordnet werden, erfüllt werden.  Ein Modell für diesen Strukturtyp ist eine geordnete Liste eindeutig auftretender Schlüsselwörter mit zugeordneten Zeichenfolgewerten, die etwa Definitionen bereitstellen.  Wenn stattdessen die Wörter mehrere genaue Definition aufweisen, sodass die Schlüssel nicht eindeutig sind, ist ein hash\_multimap\-Element der ausgewählte Container.  Wenn hingegen nur die Wortliste gespeichert wurden, ist ein hash\_set\-Element der richtige Container.  Wenn mehrfaches Vorkommen der Wörter zugelassen wird, ist ein hash\_multiset\-Element die geeignete Containerstruktur.  
  
 Das hash\_map\-Element sortiert die gesteuerte Sequenz, indem ein gespeichertes `Traits`\-Hashobjekt der Klasse [value\_compare](../standard-library/value-compare-class.md) aufgerufen wird.  Auf das gespeicherte Objekt wird möglicherweise zugegriffen, indem die Memberfunktion [key\_comp](../Topic/hash_map::key_comp.md) aufrufen wird.  Ein solches Funktionsobjekt muss sich wie ein Objekt der Klasse [hash\_compare](../standard-library/hash-compare-class.md)\<Key, less\<Key\>\> verhalten.  Insbesondere für alle `Key`\-Werte des Typs `Key`, erreicht der `Traits`\-Aufruf \(`Key` \) eine Verteilung der Werte vom Typ `size_t`.  
  
 Im Allgemeinen müssen die Elemente der Vorwärtsiteratoren etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass beliebige zwei Elemente möglicherweise als gleichwertig bestimmt werden \(in dem Sinne, dass keins geringer als das Andere ist\), oder dass eins geringer als das Andere ist.  Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.  Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht.  Bei einem binären f\(x y\)\-\-Prädikat handelt es sich um ein Funktionsobjekt, das die zwei Argumentobjekte `x` und `y` aufweist sowie einen Rückgabewert von `true` oder `false`.  Eine Sortierung, die auf ein hash\_map\-Element angewendet wird, ist eine strenge schwache Sortierung, wenn das binäre Prädikat irreflexiv, antisymmetrisch und transitiv ist, und wenn die Äquivalenz transitiv ist, wobei die beiden Objekte x und y als äquivalent definiert werden, wenn sowohl f \(x, y\) als auch f \(x, y\) falsch sind.  Wenn der stärkere Gleichheitszustand zwischen Schlüsseln die Äquivalenz ersetzt, erfolgt die Sortierung total \(d. h., alle Elemente werden zueinander sortiert\), und die verglichenen Schlüssel sind von den einander nicht mehr zu unterscheiden.  
  
 Die tatsächliche Reihenfolge der Elemente in der gesteuerten Sequenz hängt von der Hashfunktion, der Sortierfunktion und der aktuellen Größe der Hashtabelle ab, die im Containerobjekt gespeichert wird.  Die aktuelle Größe der Hashtabelle kann nicht bestimmt werden. Deshalb kann die Reihenfolge der Elemente in der gesteuerten Sequenz im Allgemeinen nicht vorhergesagt werden.  Das Einfügen von Elementen führt nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen von Elementen werden nur solche Iteratoren ungültig, die speziell auf die entfernten Elemente gezeigt haben.  
  
 Der von einer hash\_map\-Klasse bereitgestellte Iterator ist ein bidirektionaler Iterator. Die Klassenmemberfunktionen [insert](../Topic/hash_map::insert.md) und [hash\_map](../Topic/hash_map::hash_map.md) weisen allerdings Versionen auf, einen abgeschwächten Eingabeiterator als einen Vorlagenparameter akzeptieren, dessen Funktionalitätsanforderungen weniger umfangreich sind, als die von der Klasse bidirektionaler Iteratoren garantierten.  Die verschiedenen Iteratorkonzepte bilden eine Family, die durch Verfeinerungen in ihrer Funktionen verknüpft ist.  Jedes Iteratorkonzept weist einen eigenen Satz von Anforderungen auf, und die damit funktionierenden Algorithmen müssen die Annahmen hinsichtlich der von diesem Iteratortyp bereitgestellten Anforderungen begrenzen.  Es kann davon ausgegangen werden, dass ein Eingabeiterator möglicherweise so dereferenziert wird, dass er auf ein Objekt verweist und dieses möglicherweise zum folgenden Iterator in der Sequenz erhöht.  Das ist ein minimaler Funktionssatz, allerdings genügt er, um sinnvoll über einen Bereich von `[First, Last)`\-Iteratoren im Kontext der Klassenmemberfunktionen zu sprechen.  
  
 In Visual C\+\+ .NET 2003 sind Member der [\<hash\_map\>](../standard-library/hash-map.md) und [\<hash\_set\>](../standard-library/hash-set.md) Headerdateien nicht mehr im STD\-Namespace enthalten. Sie wurden stattdessen in den stdext\-Namespace verschoben.  Weitere Informationen finden Sie unter [Der stdext\-Namespace](../standard-library/stdext-namespace.md).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[hash\_map](../Topic/hash_map::hash_map.md)|Erstellt ein `hash_map`\-Element, das leer oder die Kopie eines ganzen anderen `hash_map`\-Elements oder eines Teils davon ist.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_map::allocator_type.md)|Ein Typ, der die `allocator`\-Klassentyp für das `hash_map`\-Objekt darstellt.|  
|[const\_iterator](../Topic/hash_map::const_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`\-Element ein `hash_map`\-Element lesen kann.|  
|[const\_pointer](../Topic/hash_map::const_pointer.md)|Ein Typ, der einen Zeiger auf ein `const`\-Element in einem `hash_map`\-Element bereitstellt.|  
|[const\_reference](../Topic/hash_map::const_reference.md)|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einem `hash_map`\-Element zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[const\_reverse\_iterator](../Topic/hash_map::const_reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`\-Element jedes `hash_map`\-Element lesen kann.|  
|[difference\_type](../Topic/hash_map::difference_type.md)|Ein Ganzzahltyp mit Vorzeichen, der dazu verwendet werden kann, die Anzahl von Elementen eines `hash_map`\-Elements in einen Bereich zwischen Elementen darzustellen, auf die von Iteratoren gezeigt wird.|  
|[Iterator](../Topic/hash_map::iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes Element in einer `hash_map` gelesen oder geändert werden kann.|  
|[key\_compare](../Topic/hash_map::key_compare.md)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen im `hash_map`\-Element zu bestimmen.|  
|[key\_type](../Topic/hash_map::key_type.md)|Ein Typ beschreibt das Sortierschlüsselobjekt, das jedes Element von `hash_map` bildet.|  
|[mapped\_type](../Topic/hash_map::mapped_type.md)|Ein Typ, der den in einer `hash_map` gespeicherten Datentyp darstellt.|  
|[pointer](../Topic/hash_map::pointer.md)|Ein Typ, der einen Zeiger auf ein Element in einer `hash_map` bereitstellt.|  
|[Verweis](../Topic/hash_map::reference.md)|Ein Typ, der einen Verweis auf ein in einer `hash_map` gespeichertes Element bereitstellt.|  
|[reverse\_iterator](../Topic/hash_map::reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein Element in einem umgekehrten `hash_map`\-Element gelesen oder geändert werden kann.|  
|[size\_type](../Topic/hash_map::size_type.md)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `hash_map` darstellen kann.|  
|[value\_type](../Topic/hash_map::value_type.md)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Elemente als Sortierschlüssel vergleichen kann, um die relative Position im `hash_map`\-Element zu bestimmen.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[hash\_map::at](../Topic/hash_map::at.md)|Sucht ein Element in der `hash_map` mit einem angegebenen Schlüsselwert.|  
|[begin](../Topic/hash_map::begin.md)|Gibt ein Iterator zurück, der das erste Element im `hash_map`\-Element adressiert.|  
|[hash\_map::cbegin](../Topic/hash_map::cbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im `hash_map`\-Element adressiert.|  
|[hash\_map::cend](../Topic/hash_map::cend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines `hash_map`\-Elements nachfolgt.|  
|[nicht aktiviert](../Topic/hash_map::clear.md)|Löscht alle Elemente einer `hash_map` auf.|  
|[count](../Topic/hash_map::count.md)|Gibt die Anzahl von Elementen in einem `hash_map`\-Element zurück, dessen Schlüssel dem von einem Parameter angegebenen Schlüssel entspricht.|  
|[hash\_map::crbegin](../Topic/hash_map::crbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im umgekehrten `hash_map`\-Element adressiert.|  
|[hash\_map::crend](../Topic/hash_map::crend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `hash_map`\-Elements nachfolgt.|  
|[hash\_map::emplace](../Topic/hash_map::emplace.md)|Fügt ein Element ein, das vor Ort in ein `hash_map`\-Element erstellt wird.|  
|[hash\_map::emplace\_hint](../Topic/hash_map::emplace_hint.md)|Fügt ein Element ein, das vor Ort mit einem Platzierungshinweis in ein `hash_map`\-Element erstellt wird.|  
|[Leer](../Topic/hash_map::empty.md)|Testet, ob ein `hash_map`\-Element leer ist.|  
|[end](../Topic/hash_map::end.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einem `hash_map`\-Element nachfolgt.|  
|[equal\_range](../Topic/hash_map::equal_range.md)|Gibt ein Iteratorpaar jeweils zum ersten Element in einem `hash_map`\-Element mit einem Schlüssel zurück, der größer als ein bestimmter Schlüssel ist, bzw. zum ersten Element im `hash_map`\-Element mit einem Schlüssel, der größer oder gleich dem Schlüssel ist.|  
|[Löschen](../Topic/hash_map::erase.md)|Entfernt ein Element oder eine Reihe von Elementen in einer `hash_map` aus angegebenen Speicherorten.|  
|[find](../Topic/hash_map::find.md)|Gibt einen Iterator zurück, der die Position eines Elements in einem `hash_map`\-Element adressiert, das einen Schlüssel aufweist, der einen angegebenen Schlüssel entspricht.|  
|[get\_allocator](../Topic/hash_map::get_allocator.md)|Gibt eine Kopie des zum Erstellen von `allocator` verwendeten `hash_map`\-Objekts zurück.|  
|[Einfügen](../Topic/hash_map::insert.md)|Fügt ein Element oder einen Elementbereich in ein `hash_map`\-Element ein.|  
|[key\_comp](../Topic/hash_map::key_comp.md)|Gibt einen Iterator zum ersten Element in einem `hash_map`\-Element mit einem Schlüsselwert zurück, der gleich oder größer ist, als ein angegebener Schlüssel.|  
|[lower\_bound](../Topic/hash_map::lower_bound.md)|Gibt einen Iterator zum ersten Element in einem `hash_map`\-Element mit einem Schlüsselwert zurück, der gleich oder größer ist, als ein angegebener Schlüssel.|  
|[max\_size](../Topic/hash_map::max_size.md)|Gibt die Maximallänge der `hash_map` zurück.|  
|[rbegin](../Topic/hash_map::rbegin.md)|Gibt einen Iterator zurück, der das erste Element in einem umgekehrten `hash_map`\-Element adressiert.|  
|[rend](../Topic/hash_map::rend.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `hash_map`\-Elements nachfolgt.|  
|[size](../Topic/hash_map::size.md)|Gibt die Anzahl von Elementen in der `hash_map` zurück.|  
|[swap](../Topic/hash_map::swap.md)|Tauscht die Elemente zweier `hash_map`n.|  
|[upper\_bound](../Topic/hash_map::upper_bound.md)|Gibt einen Iterator zum ersten Element in einem `hash_map`\-Element mit einem Schlüsselwert zurück, der größer ist, als ein angegebener Schlüssel.|  
|[value\_comp](../Topic/hash_map::value_comp.md)|Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Elementwerte in `hash_map` verwendet wird.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator&#91;&#93;](../Topic/hash_map::operator.md)|Fügt ein Element in ein `hash_map`\-Element mit einem angegebenen Schlüsselwert ein.|  
|[hash\_map::operator\=](../Topic/hash_map::operator=.md)|Ersetzt die Elemente eines `hash_map`\-Elements durch eine Kopie eines anderen `hash_map`\-Elements.|  
  
## Anforderungen  
 **Header:** \<hash\_map\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)