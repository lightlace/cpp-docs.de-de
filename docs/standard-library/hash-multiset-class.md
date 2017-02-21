---
title: "hash_multiset-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext.hash_multiset"
  - "std::hash_multiset"
  - "stdext::hash_multiset"
  - "hash_multiset"
  - "std.hash_multiset"
  - "hash_set/stdext::hash_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_multiset-Klasse"
ms.assetid: 0580397a-a76e-40ad-aea2-5c6f3a9d0a21
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# hash_multiset-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Diese API ist veraltet.  Die Alternative ist die [unordered\_multiset\-Klasse](../standard-library/unordered-multiset-class.md).  
  
 Die hash\_multiset\-Containerklasse ist eine Erweiterung der Standardvorlagenbibliothek und wird für das Speichern und schnelle Abrufen von Daten aus einer Auflistung verwendet, in der die Werte der enthaltenen Elemente als Schlüsselwerte fungieren und nicht eindeutig sein müssen.  
  
## Syntax  
  
```  
  
        template <  
   class Key,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<Key>   
>  
class hash_multiset  
```  
  
#### Parameter  
 *Key*  
 Der im hash\_multiset\-Objekt zu speichernde Elementdatentyp.  
  
 `Traits`  
 Der Typ, der zwei Funktionsobjekte enthält: eines der Klasse "compare" ist ein binäres Prädikat, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um ihre relative Position zu bestimmen. Eines ist eine Hashfunktion, ein unäres Prädikat, das den Schlüsselwerten der Elemente vorzeichenlose ganze Zahlen vom Typ **size\_t** zuordnet.  Dieses Argument ist optional, und der Standardwert ist `hash_compare`*\<Key,* **less***\<Key\> \>* .  
  
 `Allocator`  
 Der Typ, der das gespeicherte Zuweisungsobjekt darstellt, mit dem Details zur Belegung und Freigabe von Arbeitsspeicher für das hash\_multiset\-Objekt gekapselt werden.  Dieses Argument ist optional, und der Standardwert ist **allocator**Key*\<\>.*  
  
## Hinweise  
 Ein hash\_multiset\-Objekt ist:  
  
-   Ein assoziativer Container, der ein Container variabler Größe ist, der den effizienten Abruf von Elementwerten auf Grundlage eines zugeordneten Schlüsselwert unterstützt.  Darüber hinaus ist es ein einfacher assoziativer Container, da die Elementwerte den Schlüsselwerten entsprechen.  
  
-   Umkehrbar, da ein bidirektionaler Iterator für den Zugriff auf die Elemente bereitgestellt wird.  
  
-   Gehasht, da die Elemente auf Grundlage des Werts einer Hashfunktion, die auf die Schlüsselwerte der Elemente angewendet wird, in Buckets gruppiert werden.  
  
-   Insofern eindeutig, da jedes der Elemente einen eindeutigen Schlüssel aufweisen muss.  Da ein hash\_multiset\-Objekt auch ein einfacher assoziativer Container ist, sind seine Elemente ebenfalls eindeutig.  
  
-   Eine Vorlagenklasse, da die von ihr bereitgestellte Funktionalität generisch und daher unabhängig vom jeweiligen Typ der Daten ist, die als Elemente oder Schlüssel enthalten sind.  Die für Elemente und Schlüssel zu verwendenden Datentypen werden stattdessen in der Klassenvorlage zusammen mit der Vergleichsfunktion und der Zuweisung als Parameter angegeben.  
  
 Der Hauptvorteil des Hashverfahrens gegenüber der Sortierung ist die größere Effizienz: Bei einem erfolgreichen Hashverfahren werden Einfüge\-, Lösch\- und Suchvorgänge in einer konstanten Durchschnittszeit durchgeführt, während die Zeit bei Sortiertechniken proportional zum Logarithmus der Anzahl von Elementen im Container ist.  Der Schlüsselwert eines Elements in einem Satz darf nicht direkt geändert werden.  Stattdessen müssen Sie alte Werte löschen und Elemente mit neuen Werten einfügen.  
  
 Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen.  Gehashte assoziative Container sind für Such\-, Einfüge\- und Entfernvorgänge optimiert.  Die Memberfunktionen, die diese Vorgänge explizit unterstützen, sind effizient, wenn sie mit einer gut entworfenen Hashfunktion verwendet werden. Dann werden sie in einer Zeit ausgeführt, die im Durchschnitt konstant und nicht von der Anzahl von Elementen im Container abhängig ist.  Eine ausgereifte Hashfunktion erzeugt eine vereinheitlichte Verteilung gehashter Werte und minimiert die Anzahl von Konflikten, bei denen ein Konflikt vorhergesagt wird, wenn unterschiedliche Schlüsselwerte dem gleichen gehashten Wert zugeordnet werden.  Im schlimmsten Fall ist die Anzahl von Vorgängen bei der schlimmstmöglichen Hashfunktion zu der Anzahl von Elementen in der Sequenz proportional \(lineare Zeit\).  
  
 Ein hash\_multiset\-Objekt sollte der assoziative Container der Wahl sein, wenn die Bedingungen, mit denen die Werte den Schlüsseln zugeordnet werden, von der Anwendung erfüllt werden.  Die Elemente eines hash\_multiset\-Objekts können Mehrfache sein und als eigene Sortierschlüssel dienen, sodass Schlüssel nicht eindeutig sind.  Ein Modell für diesen Typ der Struktur ist eine geordnete Liste von z. B. Wörtern, in denen die Wörter möglicherweise mehrmals auftreten.  Wenn mehrfaches Vorkommen der Wörter nicht zugelassen wurde, ist ein hash\_set\-Objekt die geeignete Containerstruktur.  Wenn eindeutige Definitionen als Werte an die Liste von eindeutigen Schlüsselwörtern angefügt wurden, ist ein hash\_map\-Objekt eine äquivalente Struktur, um diese Daten zu enthalten.  Wenn die Definitionen dagegen nicht eindeutig sind, ist ein hash\_multimap\-Objekt der geeignete Container.  
  
 Das hash\_multiset\-Objekt sortiert die gesteuerte Sequenz, indem ein gespeichertes Hashmerkmalsobjekt vom Typ [value\_compare](../Topic/hash_multiset::value_compare.md) aufgerufen wird.  Auf das gespeicherte Objekt wird möglicherweise zugegriffen, indem die Memberfunktion [key\_comp](../Topic/hash_multiset::key_comp.md) aufrufen wird.  Ein solches Funktionsobjekt sich wie ein Objekt der Klasse `hash_compare`*\<Key,* **less***\<Key\> \>* verhalten. Insbesondere für alle *Key*\-Werte vom Typ **Key** erreicht der Aufruf **Trait**\(*Key*\) eine Verteilung der Werte vom Typ **size\_t**.  
  
 Im Allgemeinen müssen die Elemente der Vorwärtsiteratoren etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass beliebige zwei Elemente möglicherweise als gleichwertig bestimmt werden \(in dem Sinne, dass keins geringer als das Andere ist\), oder dass eins geringer als das Andere ist.  Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.  Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht.  Bei einem binären *f*\(*x*,*y*\)\-Prädikat handelt es sich um ein Funktionsobjekt, das die zwei Argumentobjekte x und y aufweist sowie einen Rückgabewert von "true" oder "false".  Eine Sortierung, die auf ein hash\_multiset\-Objekt angewendet wird, ist eine strenge schwache Sortierung, wenn das binäre Prädikat irreflexiv, antisymmetrisch und transitiv und wenn die Äquivalenz transitiv ist, wobei die beiden Objekte x und y als äquivalent definiert sind, wenn sowohl *f*\(*x*,*y*\) als auch *f*\(*y*,*x*\) gleich "false" sind.  Wenn der stärkere Gleichheitszustand zwischen Schlüsseln die Äquivalenz ersetzt, erfolgt die Sortierung total \(d. h., alle Elemente werden zueinander sortiert\), und die verglichenen Schlüssel sind von den einander nicht mehr zu unterscheiden.  
  
 Die tatsächliche Reihenfolge der Elemente in der gesteuerten Sequenz hängt von der Hashfunktion, der Sortierfunktion und der aktuellen Größe der Hashtabelle ab, die im Containerobjekt gespeichert wird.  Die aktuelle Größe der Hashtabelle kann nicht bestimmt werden. Deshalb kann die Reihenfolge der Elemente in der gesteuerten Sequenz im Allgemeinen nicht vorhergesagt werden.  Das Einfügen von Elementen führt nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen von Elementen werden nur solche Iteratoren ungültig, die speziell auf die entfernten Elemente gezeigt haben.  
  
 Der von der hash\_multiset\-Klasse bereitgestellte Iterator ist ein bidirektionaler Iterator. Die Klassenmemberfunktionen [insert](../Topic/set::insert.md) und [hash\_multimap](../Topic/set::set.md) weisen allerdings Versionen auf, die als Vorlagenparameter einen abgeschwächten Eingabeiterator akzeptieren, dessen Funktionalitätsanforderungen weniger umfangreich sind als die von der Klasse bidirektionaler Iteratoren garantierten.  Die verschiedenen Iteratorkonzepte bilden eine Family, die durch Verfeinerungen in ihrer Funktionen verknüpft ist.  Jedes Iteratorkonzept hat sein eigenes hash\_multiset\-Objekt von Anforderungen, und die Annahmen der verwendenden Algorithmen müssen sich auf die von diesem Iteratortyp erfüllten Anforderungen beschränken.  Es kann davon ausgegangen werden, dass ein Eingabeiterator möglicherweise so dereferenziert wird, dass er auf ein Objekt verweist und dieses möglicherweise zum folgenden Iterator in der Sequenz erhöht.  Dies ist hinsichtlich der Funktionalität ein minimales hash\_multiset\-Objekt, allerdings genügt es, um sinnvoll über einen Bereich von Iteratoren \[`_First`, `_Last`\] im Kontext der Klassenmemberfunktionen zu sprechen.  
  
 In Visual C\+\+ .NET 2003 sind Member der [\<hash\_map\>](../standard-library/hash-map.md) und [\<hash\_set\>](../standard-library/hash-set.md) Headerdateien nicht mehr im STD\-Namespace enthalten. Sie wurden stattdessen in den stdext\-Namespace verschoben.  Weitere Informationen finden Sie unter [Der stdext\-Namespace](../standard-library/stdext-namespace.md).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[hash\_multiset](../Topic/hash_multiset::hash_multiset.md)|Erstellt ein `hash_multiset`\-Element, das leer oder die Kopie eines ganzen anderen `hash_multiset`\-Elements oder eines Teils davon ist.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_multiset::allocator_type.md)|Ein Typ, der die `allocator`\-Klassentyp für das `hash_multiset`\-Objekt darstellt.|  
|[const\_iterator](../Topic/hash_multiset::const_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`\-Element ein `hash_multiset`\-Element lesen kann.|  
|[const\_pointer](../Topic/hash_multiset::const_pointer.md)|Ein Typ, der einen Zeiger auf ein `const`\-Element in einem `hash_multiset`\-Element bereitstellt.|  
|[const\_reference](../Topic/hash_multiset::const_reference.md)|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einem `hash_multiset`\-Element zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[const\_reverse\_iterator](../Topic/hash_multiset::const_reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`\-Element jedes `hash_multiset`\-Element lesen kann.|  
|[difference\_type](../Topic/hash_multiset::difference_type.md)|Ein ganzzahliger Typ mit Vorzeichen, der den Unterschied zwischen zwei Iteratoren bereitstellt, die auf Elemente im selben `hash_multiset`\-Objekt verweisen.|  
|[Iterator](../Topic/hash_multiset::iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes Element in einer `hash_multiset` gelesen oder geändert werden kann.|  
|[key\_compare](../Topic/hash_multiset::key_compare.md)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen im `hash_multiset`\-Element zu bestimmen.|  
|[key\_type](../Topic/hash_multiset::key_type.md)|Ein Typ, der ein Objekt beschreibt, das als Element eines `hash_set`\-Objekts in seiner Kapazität als Sortierschlüssel gespeichert wird.|  
|[pointer](../Topic/hash_multiset::pointer.md)|Ein Typ, der einen Zeiger auf ein Element in einer `hash_multiset` bereitstellt.|  
|[Verweis](../Topic/hash_multiset::reference.md)|Ein Typ, der einen Verweis auf ein in einer `hash_multiset` gespeichertes Element bereitstellt.|  
|[reverse\_iterator](../Topic/hash_multiset::reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein Element in einem umgekehrten `hash_multiset`\-Element gelesen oder geändert werden kann.|  
|[size\_type](../Topic/hash_multiset::size_type.md)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `hash_multiset` darstellen kann.|  
|[value\_compare](../Topic/hash_multiset::value_compare.md)|Ein Typ, der zwei Funktionsobjekte bereitstellt: ein binäres Prädikat der compare\-Klasse, das zwei Elementwerte eines `hash_multiset`\-Objekts vergleichen kann, um deren relative Reihenfolge zu bestimmen, und ein unäres Prädikat, das die Hashwerte der Elemente ermittelt.|  
|[value\_type](../Topic/hash_multiset::value_type.md)|Ein Typ, der ein Objekt beschreibt, das als Element eines `hash_multiset`\-Objekts in seiner Kapazität als Wert gespeichert wird.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[begin](../Topic/hash_multiset::begin.md)|Gibt einen Iterator zurück, der das erste Element im `hash_multiset` adressiert.|  
|[hash\_multiset::cbegin](../Topic/hash_multiset::cbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im `hash_multiset`\-Element adressiert.|  
|[hash\_multiset::cend](../Topic/hash_multiset::cend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines `hash_multiset`\-Elements nachfolgt.|  
|[nicht aktiviert](../Topic/hash_multiset::clear.md)|Löscht alle Elemente einer `hash_multiset` auf.|  
|[count](../Topic/hash_multiset::count.md)|Gibt die Anzahl von Elementen in einem `hash_multiset`\-Objekt zurück, dessen Schlüssel dem von einem Parameter angegebenen Schlüssel entspricht.|  
|[hash\_multiset::crbegin](../Topic/hash_multiset::crbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im umgekehrten `hash_multiset`\-Element adressiert.|  
|[hash\_multiset::crend](../Topic/hash_multiset::crend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `hash_multiset`\-Elements nachfolgt.|  
|[hash\_multiset::emplace](../Topic/hash_multiset::emplace.md)|Fügt ein Element ein, das vor Ort in ein `hash_multiset`\-Element erstellt wird.|  
|[hash\_multiset::emplace\_hint](../Topic/hash_multiset::emplace_hint.md)|Fügt ein Element ein, das vor Ort mit einem Platzierungshinweis in ein `hash_multiset`\-Element erstellt wird.|  
|[Leer](../Topic/hash_multiset::empty.md)|Testet, ob ein `hash_multiset`\-Element leer ist.|  
|[end](../Topic/hash_multiset::end.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einem `hash_multiset`\-Element nachfolgt.|  
|[equal\_range](../Topic/hash_multiset::equal_range.md)|Gibt ein Iteratorpaar jeweils zum ersten Element in einem `hash_multiset`\-Objekt mit einem Schlüssel zurück, der größer als ein bestimmter Schlüssel ist, bzw. zum ersten Element im `hash_multiset`\-Objekt mit einem Schlüssel, der größer oder gleich dem Schlüssel ist.|  
|[Löschen](../Topic/hash_multiset::erase.md)|Es wird ein Element oder ein Bereich von Elementen in einem `hash_multiset` von angegebenen Speicherorten entfernt, oder es werden die einem angegebenen Schlüssel entsprechenden Elemente entfernt.|  
|[find](../Topic/hash_multiset::find.md)|Gibt einen Iterator zurück, der die Position eines Elements in einem `hash_multiset`\-Element adressiert, das einen Schlüssel aufweist, der einen angegebenen Schlüssel entspricht.|  
|[get\_allocator](../Topic/hash_multiset::get_allocator.md)|Gibt eine Kopie des zum Erstellen von `allocator` verwendeten `hash_multiset`\-Objekts zurück.|  
|[Einfügen](../Topic/hash_multiset::insert.md)|Fügt ein Element oder einen Elementbereich in ein `hash_multiset`\-Element ein.|  
|[key\_comp](../Topic/hash_multiset::key_compare.md)|Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Schlüssel in `hash_multiset` verwendet wird.|  
|[lower\_bound](../Topic/hash_multiset::lower_bound.md)|Gibt einen Iterator zum ersten Element in einem `hash_multiset`\-Element mit einem Schlüssel zurück, der gleich oder größer ist, als ein angegebener Schlüssel.|  
|[max\_size](../Topic/hash_multiset::max_size.md)|Gibt die Maximallänge der `hash_multiset` zurück.|  
|[rbegin](../Topic/hash_multiset::rbegin.md)|Gibt einen Iterator zurück, der das erste Element in einem umgekehrten `hash_multiset`\-Element adressiert.|  
|[rend](../Topic/hash_multiset::rend.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `hash_multiset`\-Elements nachfolgt.|  
|[size](../Topic/hash_multiset::size.md)|Gibt die Anzahl von Elementen in der `hash_multiset` zurück.|  
|[swap](../Topic/hash_multiset::swap.md)|Tauscht die Elemente zweier `hash_multiset`n.|  
|[upper\_bound](../Topic/hash_multiset::upper_bound.md)|Gibt einen Iterator zum ersten Element in einem `hash_multiset`\-Element mit einem Schlüssel zurück, der gleich oder größer ist als ein angegebener Schlüssel.|  
|[value\_comp](../Topic/hash_multiset::value_comp.md)|Ruft eine Kopie des Hashmerkmalsobjekts ab, mit dem Elementschlüsselwerte in einem `hash_multiset`\-Element gehasht und sortiert wurden.|  
  
### Operatoren  
  
|||  
|-|-|  
|[hash\_multiset::operator\=](../Topic/hash_multiset::operator=.md)|Ersetzt die Elemente des \-Objekts durch eine Kopie eine anderen \-Objekts.|  
  
## Anforderungen  
 **Header:** \<hash\_set\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)