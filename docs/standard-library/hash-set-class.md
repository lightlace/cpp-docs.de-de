---
title: "hash_set-Klasse"
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
  - "hash_set/stdext::hash_set"
  - "std::hash_set"
  - "std.hash_set"
  - "stdext::hash_set"
  - "hash_set"
  - "stdext.hash_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set-Klasse"
ms.assetid: c765c06e-cbb6-48c2-93ca-d15468eb28d7
caps.latest.revision: 22
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# hash_set-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Diese API ist veraltet.  Die Alternative ist die [unordered\_set\-Klasse](../standard-library/unordered-set-class.md).  
  
 Die hash\_set\-Containerklasse ist eine Erweiterung der Standardvorlagenbibliothek \(Standard Template Library, STL\) und wird für das Speichern und schnelle Abrufen von Daten aus einer Auflistung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte fungieren.  
  
## Syntax  
  
```  
template <  
   class Key,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<Key>   
>  
class hash_set  
```  
  
#### Parameter  
 `Key`  
 Der im hash\_set\-Objekt zu speichernde Elementdatentyp.  
  
 `Traits`  
 Der Typ, der zwei Funktionsobjekte enthält: eines der Klasse „compare“, das ein binäres Prädikat ist, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um ihre relative Position zu bestimmen, und eine Hashfunktion, die ein unäres Prädikat ist, das Schlüsselwerte der Elemente zu vorzeichenlosen ganzen Zahlen des Typs **size\_t** zuordnet.  Dieses Argument ist optional, und der Standardwert ist `hash_compare`*\<Key,* **less***\<Key\> \>*.  
  
 `Allocator`  
 Der Typ, mit dem das gespeicherte allocator\-Objekt dargestellt wird, mit dem Details zum Belegen und Freigeben von Arbeitsspeicher für das hash\_set\-Element gekapselt werden.  Dieses Argument ist optional, und der Standardwert ist **allocator**Key*\<\>.*  
  
## Hinweise  
 Ein hash\_set\-Objekt ist:  
  
-   Ein assoziativer Container, der ein Container variabler Größe ist, der den effizienten Abruf von Elementwerten auf Grundlage eines zugeordneten Schlüsselwert unterstützt.  Darüber hinaus ist es ein einfacher assoziativer Container, da die Elementwerte den Schlüsselwerten entsprechen.  
  
-   Umkehrbar, da ein bidirektionaler Iterator für den Zugriff auf die Elemente bereitgestellt wird.  
  
-   Gehasht, da die Elemente auf Grundlage des Werts einer Hashfunktion, die auf die Schlüsselwerte der Elemente angewendet wird, in Buckets gruppiert werden.  
  
-   Insofern eindeutig, da jedes der Elemente einen eindeutigen Schlüssel aufweisen muss.  Da ein hash\_set\-Objekt auch ein einfacher assoziativer Container ist, sind seine Elemente ebenfalls eindeutig.  
  
-   Eine Vorlagenklasse, da die bereitgestellte Funktionalität generisch und daher unabhängig vom speziellen Typ der Daten ist, die als Elemente oder Schlüssel enthalten sind.  Die für Elemente und Schlüssel zu verwendenden Datentypen werden stattdessen in der Klassenvorlage zusammen mit der Vergleichsfunktion und der Zuweisung als Parameter angegeben.  
  
 Der Hauptvorteil des Hashverfahrens gegenüber der Sortierung ist die größere Effizienz. Bei einem erfolgreichen Hashverfahren werden Einfüge\-, Lösch\- und Suchvorgänge, verglichen mit einer Zeit, die zum Logarithmus der Anzahl von Elementen im Container für Sortiertechniken proportional ist, in einer konstanten Durchschnittszeit durchgeführt.  Der Schlüsselwert eines Elements in einem Satz darf nicht direkt geändert werden.  Stattdessen müssen Sie alte Werte löschen und Elemente mit neuen Werten einfügen.  
  
 Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen.  Gehashte assoziative Container sind für Such\-, Einfüge\- und Entfernvorgänge optimiert.  Die Memberfunktionen, die diese Vorgänge explizit unterstützen, sind effizient, wenn sie mit einer gut entworfenen Hashfunktion verwendet werden. Dann werden sie in einer Zeit ausgeführt, die im Durchschnitt konstant und nicht von der Anzahl von Elementen im Container abhängig ist.  Eine ausgereifte Hashfunktion erzeugt eine vereinheitlichte Verteilung gehashter Werte und minimiert die Anzahl von Konflikten, bei denen ein Konflikt vorhergesagt wird, wenn unterschiedliche Schlüsselwerte dem gleichen gehashten Wert zugeordnet werden.  Im schlimmsten Fall ist die Anzahl von Vorgängen bei der schlimmstmöglichen Hashfunktion zu der Anzahl von Elementen in der Sequenz proportional \(lineare Zeit\).  
  
 Die hash\_set\-Klasse sollte der ausgewählte assoziative Container sein, wenn die Bedingungen, mit denen die Werte von der Anwendung den Schlüsseln zugeordnet werden, erfüllt werden.  Die Elemente eines hash\_set\-Objekts sind eindeutig und fungieren als ihre eigenen Sortierschlüssel.  Ein Modell für diesen Typ der Struktur ist eine geordnete Liste von z. B. Wörtern, in denen die Wörter möglicherweise nur einmal auftreten.  Wenn mehrfaches Vorkommen der Wörter zugelassen wird, ist ein hash\_multiset\-Element die geeignete Containerstruktur.  Wenn Werte an eine Liste von eindeutigen Schlüsselwörtern angefügt werden müssen, ist ein hash\_map\-Objekt eine geeignete Struktur, um diese Daten zu enthalten.  Wenn die Schlüssel dagegen nicht eindeutig sind, ist ein hash\_multimap\-Objekt der geeignete Container.  
  
 In einem hash\_set\-Objekt wird die von ihm gesteuerte Sequenz sortiert, indem ein gespeichertes Hash\-**Traits**\-Objekt des Typs [value\_compare](../Topic/hash_set::value_compare.md) aufgerufen wird.  Auf das gespeicherte Objekt wird möglicherweise zugegriffen, indem die Memberfunktion [key\_comp](../Topic/hash_set::key_comp.md) aufrufen wird.  Ein solches Funktionsobjekt muss sich wie ein Objekt der Klasse *hash\_compare\<Key, less\<Key\>\> verhalten.* Insbesondere für alle `_Key`\-Werte des Typs „Key“ ergibt der Aufruf Trait\(`_Key`\) eine Verteilung von Werten des Typs „size\_t“.  
  
 Im Allgemeinen müssen die Elemente der Vorwärtsiteratoren etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass beliebige zwei Elemente möglicherweise als gleichwertig bestimmt werden \(in dem Sinne, dass keins geringer als das Andere ist\), oder dass eins geringer als das Andere ist.  Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.  Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht.  Bei einem binären *f*\(*x*,*y*\)\-Prädikat handelt es sich um ein Funktionsobjekt, das die zwei Argumentobjekte x und y aufweist sowie einen Rückgabewert von „true“ oder „false“.  Eine Sortierung, die auf ein hash\_set\-Objekt angewendet wird, ist eine strenge schwache Sortierung, wenn das binäre Prädikat irreflexiv, antisymmetrisch und transitiv ist, und wenn die Äquivalenz transitiv ist, wobei die beiden Objekte *x* und *y* als äquivalent definiert werden, wenn sowohl *f*\(*x*,*y*\) als auch *f*\(*y*,*x*\) gleich „false“ sind.  Wenn der stärkere Gleichheitszustand zwischen Schlüsseln die Äquivalenz ersetzt, erfolgt die Sortierung total \(d. h., alle Elemente werden zueinander sortiert\), und die verglichenen Schlüssel sind von den einander nicht mehr zu unterscheiden.  
  
 Die tatsächliche Reihenfolge der Elemente in der gesteuerten Sequenz hängt von der Hashfunktion, der Sortierfunktion und der aktuellen Größe der Hashtabelle ab, die im Containerobjekt gespeichert wird.  Die aktuelle Größe der Hashtabelle kann nicht bestimmt werden. Deshalb kann die Reihenfolge der Elemente in der gesteuerten Sequenz im Allgemeinen nicht vorhergesagt werden.  Das Einfügen von Elementen führt nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen von Elementen werden nur solche Iteratoren ungültig, die speziell auf die entfernten Elemente gezeigt haben.  
  
 Der von der hash\_set\-Klasse bereitgestellte Iterator ist ein bidirektionaler Iterator. Die Klassenmemberfunktionen [insert](../Topic/hash_set::insert.md) und [hash\_set](../Topic/hash_set::hash_set.md) haben allerdings Versionen, die einen abgeschwächten Eingabeiterator als Vorlagenparameter akzeptieren, dessen Funktionalitätsanforderungen weniger umfangreich sind als diejenigen, die von der Klasse bidirektionaler Iteratoren garantiert werden.  Die verschiedenen Iteratorkonzepte bilden eine Family, die durch Verfeinerungen in ihrer Funktionen verknüpft ist.  Jedes Iteratorkonzept weist einen eigenen Satz von Anforderungen auf, und die damit funktionierenden Algorithmen müssen die Annahmen hinsichtlich der von diesem Iteratortyp bereitgestellten Anforderungen begrenzen.  Es kann davon ausgegangen werden, dass ein Eingabeiterator möglicherweise so dereferenziert wird, dass er auf ein Objekt verweist und dieses möglicherweise zum folgenden Iterator in der Sequenz erhöht.  Das ist ein minimaler Funktionssatz. Er genügt jedoch, um sinnvoll über einen Bereich von Iteratoren \[`_First`, `_Last`\] im Kontext der Klassenmemberfunktionen zu sprechen.  
  
 In Visual C\+\+ .NET 2003 sind Member der [\<hash\_map\>](../standard-library/hash-map.md) und [\<hash\_set\>](../standard-library/hash-set.md) Headerdateien nicht mehr im STD\-Namespace enthalten. Sie wurden stattdessen in den stdext\-Namespace verschoben.  Weitere Informationen finden Sie unter [Der stdext\-Namespace](../standard-library/stdext-namespace.md).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[hash\_set](../Topic/hash_set::hash_set.md)|Erstellt ein `hash_set`\-Element, das leer oder die Kopie eines ganzen anderen `hash_set`\-Elements oder eines Teils davon ist.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_set::allocator_type.md)|Ein Typ, der die `allocator`\-Klassentyp für das `hash_set`\-Objekt darstellt.|  
|[const\_iterator](../Topic/hash_set::const_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`\-Element ein `hash_set`\-Element lesen kann.|  
|[const\_pointer](../Topic/hash_set::const_pointer.md)|Ein Typ, der einen Zeiger auf ein `const`\-Element in einem `hash_set`\-Element bereitstellt.|  
|[const\_reference](../Topic/hash_set::const_reference.md)|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einem `hash_set`\-Element zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[const\_reverse\_iterator](../Topic/hash_set::const_reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der im `const`\-Element jedes `hash_set`\-Element lesen kann.|  
|[difference\_type](../Topic/hash_set::difference_type.md)|Ein Ganzzahltyp mit Vorzeichen, der dazu verwendet werden kann, die Anzahl von Elementen eines `hash_set`\-Elements in einen Bereich zwischen Elementen darzustellen, auf die von Iteratoren gezeigt wird.|  
|[Iterator](../Topic/hash_set::iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes Element in einer `hash_set` gelesen oder geändert werden kann.|  
|[key\_compare](../Topic/hash_set::key_compare.md)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen im `hash_set`\-Element zu bestimmen.|  
|[key\_type](../Topic/hash_set::key_type.md)|Ein Typ, der ein Objekt beschreibt, das als Element eines `hash_set`\-Objekts in seiner Kapazität als Sortierschlüssel gespeichert wird.|  
|[pointer](../Topic/hash_set::pointer.md)|Ein Typ, der einen Zeiger auf ein Element in einer `hash_set` bereitstellt.|  
|[Verweis](../Topic/hash_set::reference.md)|Ein Typ, der einen Verweis auf ein in einer `hash_set` gespeichertes Element bereitstellt.|  
|[reverse\_iterator](../Topic/hash_set::reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein Element in einem umgekehrten `hash_set`\-Element gelesen oder geändert werden kann.|  
|[size\_type](../Topic/hash_set::size_type.md)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `hash_set` darstellen kann.|  
|[value\_compare](../Topic/hash_set::value_compare.md)|Ein Typ, der Folgendes bereitstellt: zwei Funktionsobjekte, ein binäres Prädikat der compare\-Klasse, das zwei Elementwerte eines `hash_set`\-Objekts vergleichen kann, um deren relative Reihenfolge zu bestimmen, und ein unäres Prädikat, das die Hashwerte der Elemente ermittelt.|  
|[value\_type](../Topic/hash_set::value_type.md)|Ein Typ, der ein Objekt beschreibt, das als Element eines `hash_set`\-Objekts in seiner Kapazität als Wert gespeichert wird.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[begin](../Topic/hash_set::begin.md)|Gibt einen Iterator zurück, der auf das erste Element im `hash_set`\-Objekt verweist.|  
|[hash\_set::cbegin](../Topic/hash_set::cbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im `hash_set`\-Element adressiert.|  
|[hash\_set::cend](../Topic/hash_set::cend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines `hash_set`\-Elements nachfolgt.|  
|[nicht aktiviert](../Topic/hash_set::clear.md)|Löscht alle Elemente einer `hash_set` auf.|  
|[count](../Topic/hash_set::count.md)|Gibt die Anzahl von Elementen in einem `hash_set`\-Element zurück, dessen Schlüssel dem von einem Parameter angegebenen Schlüssel entspricht.|  
|[hash\_set::crbegin](../Topic/hash_set::crbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im umgekehrten `hash_set`\-Element adressiert.|  
|[hash\_set::crend](../Topic/hash_set::crend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `hash_set`\-Elements nachfolgt.|  
|[hash\_set::emplace](../Topic/hash_set::emplace.md)|Fügt ein Element ein, das vor Ort in ein `hash_set`\-Element erstellt wird.|  
|[hash\_set::emplace\_hint](../Topic/hash_set::emplace_hint.md)|Fügt ein Element ein, das vor Ort mit einem Platzierungshinweis in ein `hash_set`\-Element erstellt wird.|  
|[Leer](../Topic/hash_set::empty.md)|Testet, ob ein `hash_set`\-Element leer ist.|  
|[end](../Topic/hash_set::end.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einem `hash_set`\-Element nachfolgt.|  
|[equal\_range](../Topic/hash_set::equal_range.md)|Gibt ein Iteratorpaar jeweils bezogen auf das erste Element in einem `hash_set`\-Objekt mit einem Schlüssel zurück, der größer als ein bestimmter Schlüssel ist, bzw. bezogen auf das erste Element im `hash_set`\-Objekt mit einem Schlüssel, der größer oder gleich dem Schlüssel ist.|  
|[Löschen](../Topic/hash_set::erase.md)|Es wird ein Element oder ein Bereich von Elementen in einem `hash_set` von angegebenen Speicherorten entfernt, oder es werden die einem angegebenen Schlüssel entsprechenden Elemente entfernt.|  
|[find](../Topic/hash_set::find.md)|Gibt einen Iterator zurück, der die Position eines Elements in einem `hash_set`\-Element adressiert, das einen Schlüssel aufweist, der einen angegebenen Schlüssel entspricht.|  
|[get\_allocator](../Topic/hash_set::get_allocator.md)|Gibt eine Kopie des zum Erstellen von `allocator` verwendeten `hash_set`\-Objekts zurück.|  
|[Einfügen](../Topic/hash_set::insert.md)|Fügt ein Element oder einen Elementbereich in ein `hash_set`\-Element ein.|  
|[key\_comp](../Topic/hash_set::key_comp.md)|Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Schlüssel in `hash_set` verwendet wird.|  
|[lower\_bound](../Topic/hash_set::lower_bound.md)|Gibt einen Iterator zum ersten Element in einem `hash_set`\-Element mit einem Schlüssel zurück, der gleich oder größer ist, als ein angegebener Schlüssel.|  
|[max\_size](../Topic/hash_set::max_size.md)|Gibt die Maximallänge der `hash_set` zurück.|  
|[rbegin](../Topic/hash_set::rbegin.md)|Gibt einen Iterator zurück, der das erste Element in einem umgekehrten `hash_set`\-Element adressiert.|  
|[rend](../Topic/hash_set::rend.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten `hash_set`\-Elements nachfolgt.|  
|[size](../Topic/hash_set::size.md)|Gibt die Anzahl von Elementen in der `hash_set` zurück.|  
|[swap](../Topic/hash_set::swap.md)|Tauscht die Elemente zweier `hash_set`n.|  
|[upper\_bound](../Topic/hash_set::upper_bound.md)|Gibt einen Iterator zum ersten Element in einem `hash_set`\-Element mit einem Schlüssel zurück, der gleich oder größer ist als ein angegebener Schlüssel.|  
|[value\_comp](../Topic/hash_set::value_comp.md)|Ruft eine Kopie des hash\-traits\-Objekts ab, das dazu verwendet wird, Elementschlüsselwerte in einem `hash_set`\-Objekt zu hashen und zu sortieren.|  
  
### Operatoren  
  
|||  
|-|-|  
|[hash\_set::operator\=](../Topic/hash_set::operator=.md)|Ersetzt die Elemente eines `hash_set`\-Elements durch eine Kopie eines anderen `hash_set`\-Elements.|  
  
## Anforderungen  
 **Header:** \<hash\_set\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)