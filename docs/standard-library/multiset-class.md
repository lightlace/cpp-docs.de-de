---
title: "multiset-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::multiset"
  - "set/std::multiset"
  - "std.multiset"
  - "multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multiset-Klasse"
ms.assetid: 630e8c10-0ce9-4ad9-8d79-9e91a600713f
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# multiset-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Standardvorlagenbibliothek\-Multimengenklasse wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der die Werte der enthaltenen Elemente nicht eindeutig sein müssen und in der sie als die Schlüsselwerte dienen, nach denen die Daten automatisch sortiert werden.  Der Schlüsselwert eines Elements in einer Multimenge darf nicht direkt geändert werden.  Stattdessen müssen alte Werte gelöscht und Elemente mit neuen Werten eingefügt werden.  
  
## Syntax  
  
```  
  
        template <  
   class Key,   
   class Compare=less<Key>,   
   class Allocator=allocator<Key>   
>  
class multiset  
```  
  
#### Parameter  
 *Key*  
 Der in der Multimenge zu speichernde Elementdatentyp.  
  
 *Compare*  
 Der Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in der Multimenge zu bestimmen.  Das binäre Prädikat **less**\<Key\> ist der Standardwert.  
  
 In C \+\+ 14 können Sie heterogenes Nachschlagen durch Angabe des `std::less<>` oder `std::greater<>` Prädikats, das keine Typparameter aufweist, aktivieren.  Weitere Informationen finden Sie unter [Heterogenes Nachschlagen in assoziativen Containern](../standard-library/stl-containers.md#sequence_containers)  
  
 `Allocator`  
 Der Typ, mit dem das gespeicherte Zuordnungsobjekt dargestellt wird, mit dem Details zum Belegen und Freigeben des Arbeitsspeichers der Multimenge gekapselt werden.  Der Standardwert ist **allocator***\<Key\>.*  
  
## Hinweise  
 Die STL\-Multimengenklasse ist:  
  
-   Ein assoziativer Container, der ein Container variabler Größe ist, der den effizienten Abruf von Elementwerten auf Grundlage eines zugeordneten Schlüsselwerts unterstützt.  
  
-   Umkehrbar, da bidirektionale Iteratoren für den Zugriff auf die Elemente bereitgestellt werden.  
  
-   Sortiert, da die Elemente anhand von Schlüsselwerten innerhalb des Containers mit einer angegebenen Vergleichsfunktion sortiert werden.  
  
-   Mehrfach insofern, als die Elemente keine eindeutigen Schlüssel aufweisen müssen, damit ein Schlüsselwert über viele zugeordnete Elementdatenwerte verfügen kann.  
  
-   Ein einfacher assoziativer Container, da die Elementwerte den Schlüsselwerten entsprechen.  
  
-   Eine Vorlagenklasse, da die bereitgestellten Funktionen generisch und daher unabhängig vom angegebenen Datentyp sind, der als Elemente enthalten ist.  Der zu verwendende Datentyp wird stattdessen in der Klassenvorlage zusammen mit der Vergleichsfunktion und der Zuweisung als Parameter angegeben.  
  
 Der von der Multimengenklasse bereitgestellte Iterator ist ein bidirektionaler Iterator. Die Klassenmemberfunktionen [insert](../Topic/multiset::insert.md) und [multiset](../Topic/multiset::multiset.md) weisen allerdings Versionen auf, die einen abgeschwächten Eingabeiterator als einen Vorlagenparameter akzeptieren, dessen Funktionalitätsanforderungen weniger umfangreich sind, als die von der Klasse bidirektionaler Iteratoren garantierten.  Die verschiedenen Iteratorkonzepte bilden eine Family, die durch Verfeinerungen in ihrer Funktionen verknüpft ist.  Jedes Iteratorkonzept weist einen eigenen Satz von Anforderungen auf, und die damit funktionierenden Algorithmen müssen die Annahmen hinsichtlich der von diesem Iteratortyp bereitgestellten Anforderungen begrenzen.  Es kann davon ausgegangen werden, dass ein Eingabeiterator möglicherweise so dereferenziert wird, dass er auf ein Objekt verweist und dieses möglicherweise zum folgenden Iterator in der Sequenz erhöht.  Das ist ein minimaler Funktionssatz, allerdings genügt er, um sinnvoll über einen Bereich von Iteratoren \(`First`, `Last`\) im Kontext der Klassenmemberfunktionen zu sprechen.  
  
 Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen.  Assoziative Container sind für Such\-, Einfüge\- und Entfernvorgänge optimiert.  Die Memberfunktionen, die diese Vorgänge explizit unterstützen, sind effizient und führen sie in einer Zeit aus, die zum Logarithmus der Elementanzahl im Container im Durchschnitt proportional ist.  Das Einfügen von Elementen führt nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen von Elementen werden nur solche Iteratoren ungültig, die speziell auf die entfernten Elemente gezeigt haben.  
  
 Die Multimenge sollte der ausgewählte assoziative Container sein, wenn die Bedingungen, mit denen die Werte von der Anwendung den Schlüsseln zugeordnet werden, erfüllt werden.  Die Elemente einer Multimenge können Mehrfache sein und als eigene Sortierschlüssel dienen, sodass Schlüssel nicht eindeutig sind.  Ein Modell für diesen Typ der Struktur ist eine geordnete Liste von z. B. Wörtern, in denen die Wörter möglicherweise mehrmals auftreten.  Wenn mehrfaches Vorkommen der Wörter nicht zugelassen wurde, ist eine Menge die geeignete Containerstruktur.  Wenn eindeutige Definitionen als Werte zur Liste von eindeutigen Schlüsselwörtern angefügt wurden, ist eine Zuordnung eine äquivalente Struktur, um diese Daten zu enthalten.  Wenn stattdessen die Definitionen nicht eindeutig sind, ist eine Mehrfachzuordnung der geeignete Container.  
  
 Die Multimenge sortiert die von ihr gesteuerten Elemente, indem ein gespeichertes Funktionsobjekt vom Typ `Compare` aufgerufen wird.  Bei diesem gespeicherten Objekt handelt es sich um eine Vergleichsfunktion, auf die zugegriffen werden kann, indem die [key\_comp](../Topic/multiset::key_comp.md)\-Memberfunktion aufgerufen wird.  Im Allgemeinen müssen die Elemente der Vorwärtsiteratoren etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass beliebige zwei Elemente möglicherweise als gleichwertig bestimmt werden \(in dem Sinne, dass keins geringer als das Andere ist\), oder dass eins geringer als das Andere ist.  Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.  Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht.  Bei einem binären *f*\(*x*,*y*\)\-Prädikat handelt es sich um ein Funktionsobjekt, das die zwei Argumentobjekte *x* und *y* aufweist sowie einen Rückgabewert von **true** oder **false**.  Eine Sortierung, die auf eine Multimenge angewendet wird, ist eine strenge schwache Sortierung, wenn das binäre Prädikat irreflexiv, antisymmetrisch und transitiv ist und wenn die Äquivalenz transitiv ist, wobei die beiden Objekte x und y als äquivalent definiert werden, wenn sowohl *f*\(*x,y*\) als auch *f*\(*y,x*\) "false" sind.  Wenn der stärkere Gleichheitszustand zwischen Schlüsseln die Äquivalenz ersetzt, erfolgt die Sortierung total \(d. h., alle Elemente werden zueinander sortiert\), und die verglichenen Schlüssel sind von den einander nicht mehr zu unterscheiden.  
  
 In C \+\+ 14 können Sie heterogenes Nachschlagen durch Angabe des `std::less<>` oder `std::greater<>` Prädikats, das keine Typparameter aufweist, aktivieren.  Weitere Informationen finden Sie unter [Heterogenes Nachschlagen in assoziativen Containern](../standard-library/stl-containers.md#sequence_containers).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[multiset](../Topic/multiset::multiset.md)|Erstellt ein `multiset`\-Element, das leer oder die Kopie eines ganzen angegebenen `multiset`\-Elements oder eines Teils davon ist.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/multiset::allocator_type.md)|Eine Typedef für die `allocator`\-Klasse für das `multiset`\-Objekt.|  
|[const\_iterator](../Topic/multiset::const_iterator.md)|Eine Typedef für einen bidirektionalen Iterator, der ein `const`\-Element in der `multiset` lesen kann.|  
|[const\_pointer](../Topic/multiset::const_pointer.md)|Eine Typedef für einen Zeiger auf ein `const`\-Element in einer `multiset`.|  
|[const\_reference](../Topic/multiset::const_reference.md)|Eine Typedef für einen Verweis auf ein `const`\-Element, das in einer `multiset` zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[const\_reverse\_iterator](../Topic/multiset::const_reverse_iterator.md)|Eine Typedef für einen bidirektionalen Iterator, der ein beliebiges `const`\-Element in der `multiset` lesen kann.|  
|[difference\_type](../Topic/multiset::difference_type.md)|Ein Ganzzahltyp mit Vorzeichen für die Anzahl von Elementen einer `multiset` in einem Bereich zwischen Elementen, auf die von Iteratoren gezeigt wird.|  
|[Iterator](../Topic/multiset::iterator.md)|Eine Typedef für einen bidirektionalen Iterator, der ein beliebiges Element in einer `multiset` lesen oder ändern kann.|  
|[key\_compare](../Topic/multiset::key_compare.md)|Eine Typedef für ein Funktionsobjekt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen in der `multiset` zu bestimmen.|  
|[key\_type](../Topic/multiset::key_type.md)|Eine Typedef für ein Funktionsobjekt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen in der `multiset` zu bestimmen.|  
|[pointer](../Topic/multiset::pointer.md)|Eine Typedef für einen Zeiger auf ein Element in einer `multiset`.|  
|[Verweis](../Topic/multiset::reference.md)|Eine Typedef für einen Verweis auf ein in einer `multiset` gespeichertes Element.|  
|[reverse\_iterator](../Topic/multiset::reverse_iterator.md)|Eine Typedef für einen bidirektionalen Iterator, der ein Element in einer umgekehrten `multiset` lesen oder ändern kann.|  
|[size\_type](../Topic/multiset::size_type.md)|Eine Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in `multiset` darstellen kann.|  
|[value\_compare](../Topic/multiset::value_compare.md)|Die Typedef für ein Funktionsobjekt, das zwei Elemente als Sortierschlüssel vergleichen kann, um ihre relative Position in der `multiset` zu bestimmen.|  
|[value\_type](../Topic/multiset::value_type.md)|Eine Typedef, die ein Objekt beschreibt, das als Element und `multiset` in seiner Kapazität als Wert gespeichert wird.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[begin](../Topic/multiset::begin.md)|Gibt einen Iterator zurück, der auf das erste Element in der `multiset` zeigt.|  
|[cbegin](../Topic/multiset::cbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element in der `multiset` adressiert.|  
|[cend](../Topic/multiset::cend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines `multiset`\-Elements nachfolgt.|  
|[nicht aktiviert](../Topic/multiset::clear.md)|Löscht alle Elemente einer `multiset` auf.|  
|[count](../Topic/multiset::count.md)|Gibt die Anzahl von Elementen in einer `multiset` zurück, deren Schlüssel dem als Parameter angegebenen Schlüssel entspricht.|  
|[crbegin](../Topic/multiset::crbegin.md)|Gibt einen const\-Iterator zurück, der das erste Element in einer umgekehrten Menge adressiert.|  
|[crend](../Topic/multiset::crend.md)|Gibt einen const\-Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten Menge nachfolgt.|  
|[emplace](../Topic/multiset::emplace.md)|Fügt ein Element ein, das vor Ort in ein `multiset`\-Element erstellt wird.|  
|[emplace\_hint](../Topic/multiset::emplace_hint.md)|Fügt ein Element ein, das vor Ort mit einem Platzierungshinweis in ein `multiset`\-Element erstellt wird.|  
|[Leer](../Topic/multiset::empty.md)|Testet, ob ein `multiset`\-Element leer ist.|  
|[end](../Topic/multiset::end.md)|Gibt einen Iterator zurück, der auf den Speicherort zeigt, der hinter dem letzten Element einer `multiset` liegt.|  
|[equal\_range](../Topic/multiset::equal_range.md)|Gibt ein Paar von Iteratoren zurück.  Der erste Iterator im Paar zeigt auf das erste Element in `multiset` mit einem Schlüssel, der größer ist, als ein bestimmter Schlüssel.  Der zweite Iterator im Paar zeigt auf das erste Element in der `multiset` mit einem Schlüssel, der größer oder gleich dem Schlüssel ist.|  
|[Löschen](../Topic/multiset::erase.md)|Es wird ein Element oder ein Bereich von Elementen in einem `multiset` von angegebenen Speicherorten entfernt, oder es werden die einem angegebenen Schlüssel entsprechenden Elemente entfernt.|  
|[find](../Topic/multiset::find.md)|Gibt einen Iterator zurück, der auf den ersten Speicherort eines Elements in einer `multiset` zeigt, der einen Schlüssel gleich einem angegebenen Schlüssel aufweist.|  
|[get\_allocator](../Topic/multiset::get_allocator.md)|Gibt eine Kopie des zum Erstellen der `allocator` verwendeten `multiset`\-Objekts zurück.|  
|[Einfügen](../Topic/multiset::insert.md)|Fügt ein Element oder einen Elementbereich in ein `multiset`\-Element ein.|  
|[key\_comp](../Topic/multiset::key_comp.md)|Stellt ein Funktionsobjekt bereit, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen in der `multiset` zu bestimmen.|  
|[lower\_bound](../Topic/multiset::lower_bound.md)|Gibt einen Iterator zum ersten Element in einem `multiset`\-Element mit einem Schlüssel zurück, der gleich oder größer ist, als ein angegebener Schlüssel.|  
|[max\_size](../Topic/multiset::max_size.md)|Gibt die Maximallänge der `multiset` zurück.|  
|[rbegin](../Topic/multiset::rbegin.md)|Gibt einen Iterator zurück, der auf das erste Element in einer umgekehrten `multiset` zeigt.|  
|[rend](../Topic/multiset::rend.md)|Gibt einen Iterator zurück, der auf den Speicherort zeigt, der auf das letzte Element einer umgekehrten `multiset` folgt.|  
|[size](../Topic/multiset::size.md)|Gibt die Anzahl von Elementen in einer `multiset` zurück.|  
|[swap](../Topic/multiset::swap.md)|Tauscht die Elemente zweier `multiset`n.|  
|[upper\_bound](../Topic/multiset::upper_bound.md)|Gibt einen Iterator zum ersten Element in einem `multiset`\-Element mit einem Schlüssel zurück, der größer als ein angegebener Schlüssel ist.|  
|[value\_comp](../Topic/multiset::value_comp.md)|Ruft eine Kopie des Vergleichsobjekts ab, das verwendet wird, um Elementwerte in einer `multiset` zu sortieren.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/multiset::operator=.md)|Ersetzt die Elemente eines `multiset`\-Elements durch eine Kopie eines anderen `multiset`\-Elements.|  
  
## Anforderungen  
 **Header:** \<set\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<set\> Members](assetId:///0c2d57c0-173f-4204-b579-c5f06aad8b95)   
 [Container](../cpp/containers-modern-cpp.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)