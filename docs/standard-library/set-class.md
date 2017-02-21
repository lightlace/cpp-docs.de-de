---
title: "set-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::set"
  - "set"
  - "set/std::set"
  - "std.set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set-Klasse"
ms.assetid: 8991f9aa-5509-4440-adc1-371512d32018
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# set-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der STL\-Containerklassensatz wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte dienen, nach denen die Daten automatisch sortiert werden.  Der Schlüsselwert eines Elements in einem Satz darf nicht direkt geändert werden.  Stattdessen müssen Sie alte Werte löschen und Elemente mit neuen Werten einfügen.  
  
## Syntax  
  
```  
template <  
    class Key,   
    class Traits=less<Key>,   
    class Allocator=allocator<Key>   
>  
class set  
```  
  
#### Parameter  
 `Key`  
 Der in dem Satz zu speichernde Elementdatentyp.  
  
 `Traits`  
 Der Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in dem Satz zu bestimmen.  Dieses Argument ist optional, und das binäre Prädikat **less***\<Key\>* ist der Standardwert.  
  
 In C \+\+ 14 können Sie heterogenes Nachschlagen durch Angabe des `std::less<>` oder `std::greater<>` Prädikats, das keine Typparameter aufweist, aktivieren.  Weitere Informationen finden Sie unter [Heterogenes Nachschlagen in assoziativen Containern](../standard-library/stl-containers.md#sequence_containers)  
  
 `Allocator`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zum Belegen und Freigeben des Arbeitsspeichers des Satzes kapselt.  Dieses Argument ist optional, und der Standardwert ist **allocator**Key*\<\>.*  
  
## Hinweise  
 Ein STL\-Satz ist:  
  
-   Ein assoziativer Container, der ein Container variabler Größe ist, der den effizienten Abruf von Elementwerten auf Grundlage eines zugeordneten Schlüsselwert unterstützt.  Darüber hinaus ist es ein einfacher assoziativer Container, da die Elementwerte den Schlüsselwerten entsprechen.  
  
-   Umkehrbar, da ein bidirektionaler Iterator für den Zugriff auf die Elemente bereitgestellt wird.  
  
-   Sortiert, da die Elemente anhand von Schlüsselwerten innerhalb des Containers mit einer angegebenen Vergleichsfunktion sortiert werden.  
  
-   Insofern eindeutig, da jedes der Elemente einen eindeutigen Schlüssel aufweisen muss.  Da der Satz auch ein einfacher assoziativer Container ist, sind seine Elemente ebenfalls eindeutig.  
  
 Ein Satz wird auch als Vorlagenklasse beschrieben, da die bereitgestellten Funktionen generisch sind und daher unabhängig vom angegebenen Datentyp, der als Elemente enthalten ist.  Der zu verwendende Datentyp wird stattdessen in der Klassenvorlage zusammen mit der Vergleichsfunktion und der Zuweisung als Parameter angegeben.  
  
 Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen.  Assoziative Container sind für Such\-, Einfüge\- und Entfernvorgänge optimiert.  Die Memberfunktionen, die diese Vorgänge explizit unterstützen, sind effizient und führen sie in einer Zeit aus, die zum Logarithmus der Elementanzahl im Container im Durchschnitt proportional ist.  Das Einfügen von Elementen führt nicht dazu, dass Iteratoren ungültig werden, und durch das Entfernen von Elementen werden nur solche Iteratoren ungültig, die speziell auf die entfernten Elemente gezeigt haben.  
  
 Der Satz sollte der ausgewählte assoziative Container sein, wenn die Bedingungen, mit denen die Werte von der Anwendung den Schlüsseln zugeordnet werden, erfüllt werden.  Die Elemente eines Satzes sind eindeutig und dienen als eigene Sortierschlüssel.  Ein Modell für diesen Typ der Struktur ist eine geordnete Liste von z. B. Wörtern, in denen die Wörter möglicherweise nur einmal auftreten.  Wenn mehrfaches Vorkommen der Wörter zugelassen wird, ist eine Multimenge die geeignete Containerstruktur.  Wenn Werte einer Liste von eindeutigen Schlüsselwörtern hinzugefügt werden müssen, ist eine Zuordnung eine äquivalente Struktur, um diese Daten zu enthalten.  Wenn stattdessen die Schlüssel nicht eindeutig sind, ist eine Mehrfachzuordnung der geeignete Container.  
  
 Der Satz sortiert die von ihm gesteuerte Sequenz, indem ein gespeichertes Funktionsobjekt vom Typ [key\_compare](../Topic/set::key_compare.md) aufgerufen wird.  Bei diesem gespeicherten Objekt handelt es sich um eine Vergleichsfunktion, auf die zugegriffen werden kann, indem die [key\_comp](../Topic/set::key_comp.md)\-Memberfunktion aufgerufen wird.  Im Allgemeinen müssen die Elemente etwas weniger als vergleichbar sein, um diese Sortierung zu erstellen, sodass für zwei Elemente bestimmt werden kann, dass sie gleichwertig sind \(in dem Sinne, dass keins geringer als das andere ist\) oder dass eins geringer als das andere ist.  Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.  Etwas technischer betrachtet ist die Vergleichsfunktion ein binäres Prädikat, das eine strenge schwache Sortierung im mathematischen Sinn verursacht.  Bei einem binären *f*\(*x,y*\)\-Prädikat handelt es sich um ein Funktionsobjekt, das die zwei Argumentobjekte *x* und *y* aufweist sowie einen Rückgabewert von **true** oder **false**.  Eine Sortierung, die auf eine Multimenge angewendet wird, ist eine strenge schwache Sortierung, wenn das binäre Prädikat irreflexiv, antisymmetrisch und transitiv ist und wenn die Äquivalenz transitiv ist, wobei die beiden Objekte *x* und *y* als äquivalent definiert werden, wenn sowohl *f*\(*x,y*\) als auch *f*\(*y,x*\) "false" sind.  Wenn der stärkere Gleichheitszustand zwischen Schlüsseln die Äquivalenz ersetzt, erfolgt die Sortierung total \(d. h., alle Elemente werden zueinander sortiert\), und die verglichenen Schlüssel sind von den einander nicht mehr zu unterscheiden.  
  
 In C \+\+ 14 können Sie heterogenes Nachschlagen durch Angabe des `std::less<>` oder `std::greater<>` Prädikats, das keine Typparameter aufweist, aktivieren.  Weitere Informationen finden Sie unter [Heterogenes Nachschlagen in assoziativen Containern](../standard-library/stl-containers.md#sequence_containers)  
  
 Der von einer Set\-Klasse bereitgestellte Iterator ist ein bidirektionaler Iterator. Die Klassenmemberfunktionen [insert](../Topic/set::insert.md) und [set](../Topic/set::set.md) weisen allerdings Versionen auf, einen abgeschwächten Eingabeiterator als einen Vorlagenparameter akzeptieren, dessen Funktionalitätsanforderungen weniger umfangreich sind, als die von der Klasse bidirektionaler Iteratoren garantierten.  Die verschiedenen Iteratorkonzepte bilden eine Family, die durch Verfeinerungen in ihrer Funktionen verknüpft ist.  Jedes Iteratorkonzept weist einen eigenen Satz von Anforderungen auf, und die damit funktionierenden Algorithmen müssen die Annahmen hinsichtlich der von diesem Iteratortyp bereitgestellten Anforderungen begrenzen.  Es kann davon ausgegangen werden, dass ein Eingabeiterator möglicherweise so dereferenziert wird, dass er auf ein Objekt verweist und dieses möglicherweise zum folgenden Iterator in der Sequenz erhöht.  Das ist ein minimaler Funktionssatz, allerdings genügt er, um sinnvoll über einen Bereich von Iteratoren \(`First`, `Last`\) im Kontext der Klassenmemberfunktionen zu sprechen.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[Festlegen](../Topic/set::set.md)|Erstellt einen Satz, der leer oder die Kopie eines ganzen anderen Satzes oder eines Teils davon ist.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/set::allocator_type.md)|Ein Typ, der die `allocator`\-Klasse für das Set\-Objekt darstellt.|  
|[const\_iterator](../Topic/set::const_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, der ein `const`\-Element im Satz lesen kann.|  
|[const\_pointer](../Topic/set::const_pointer.md)|Ein Typ, der einen Zeiger auf ein `const`\-Element in einem Satz bereitstellt.|  
|[const\_reference](../Topic/set::const_reference.md)|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einem Satz zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[const\_reverse\_iterator](../Topic/set::const_reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes `const`\-Element im Satz gelesen werden kann.|  
|[difference\_type](../Topic/set::difference_type.md)|Ein Ganzzahltyp mit Vorzeichen, der dazu verwendet werden kann, die Anzahl von Elementen eines Satzes in einem Bereich zwischen Elementen darzustellen, auf die von Iteratoren gezeigt wird.|  
|[Iterator](../Topic/set::iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem jedes Element in einem Satz gelesen oder geändert werden kann.|  
|[key\_compare](../Topic/set::key_compare.md)|Eine Typ, der ein Funktionsobjekt bereitstellt, das zwei Sortierschlüssel vergleichen kann, um die relative Position von zwei Elementen im Satz zu bestimmen.|  
|[key\_type](../Topic/set::key_type.md)|Der Typ beschreibt ein Objekt, das als Element eines Satzes in seiner Kapazität als Sortierschlüssel gespeichert wird.|  
|[pointer](../Topic/set::pointer.md)|Ein Typ, der einen Zeiger auf ein Element in einem Satz bereitstellt.|  
|[Verweis](../Topic/set::reference.md)|Ein Typ, der einen Verweis auf ein in einem Satz gespeichertes Element bereitstellt.|  
|[reverse\_iterator](../Topic/set::reverse_iterator.md)|Ein Typ, der einen bidirektionalen Iterator bereitstellt, mit dem ein Element in einem umgekehrten Satz gelesen oder geändert werden kann.|  
|[size\_type](../Topic/set::size_type.md)|Ein Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen in einem Satz darstellen kann.|  
|[value\_compare](../Topic/set::value_compare.md)|Der Typ, der ein Funktionsobjekt bereitstellt, das zwei Elemente vergleichen kann, um die relative Position im Satz zu bestimmen.|  
|[value\_type](../Topic/set::value_type.md)|Der Typ beschreibt ein Objekt, das als Element eines Satzes in seiner Kapazität als Wert gespeichert wird.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[begin](../Topic/set::begin.md)|Gibt einen Iterator zurück, der das erste Element im Satz adressiert.|  
|[cbegin](../Topic/set::cbegin.md)|Gibt einen konstanten Iterator zurück, der das erste Element im Satz adressiert.|  
|[cend](../Topic/set::cend.md)|Gibt einen konstanten Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines Satzes nachfolgt.|  
|[nicht aktiviert](../Topic/set::clear.md)|Löscht alle Elemente eines Satzes.|  
|[count](../Topic/set::count.md)|Gibt die Anzahl von Elementen in einem Satz zurück, dessen Schlüssel dem von einem Parameter angegebenen Schlüssel entspricht.|  
|[crbegin](../Topic/set::rbegin.md)|Gibt einen const\-Iterator zurück, der das erste Element in einer umgekehrten Menge adressiert.|  
|[crend](../Topic/set::rend.md)|Gibt einen const\-Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten Menge nachfolgt.|  
|[emplace](../Topic/set::emplace.md)|Fügt ein Element, das vor Ort erstellt wird, in einen Satz ein.|  
|[emplace\_hint](../Topic/set::emplace_hint.md)|Fügt ein Element, das vor Ort erstellt wird, mit einem Platzierungshinweis in einen Satz ein.|  
|[Leer](../Topic/set::empty.md)|Testet, ob ein Satz leer ist.|  
|[end](../Topic/set::end.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines Satzes nachfolgt.|  
|[equal\_range](../Topic/set::equal_range.md)|Gibt ein Iteratorpaar jeweils zum ersten Element in einem Satz mit einem Schlüssel zurück, der größer als ein bestimmter Schlüssel ist, bzw. zum ersten Element im Satz mit einem Schlüssel, der größer oder gleich dem Schlüssel ist.|  
|[Löschen](../Topic/set::erase.md)|Es wird ein Element oder ein Bereich von Elementen in einem Satz von angegebenen Speicherorten entfernt, oder es werden die einem angegebenen Schlüssel entsprechenden Elemente entfernt.|  
|[find](../Topic/set::find.md)|Gibt einen Iterator zurück, der die Position eines Elements in einem Satz adressiert, das einen Schlüssel aufweist, der einem angegebenen Schlüssel entspricht.|  
|[get\_allocator](../Topic/set::get_allocator.md)|Gibt eine Kopie des zum Erstellen des Satzes verwendeten `allocator`\-Objekts zurück.|  
|[Einfügen](../Topic/set::insert.md)|Fügt ein Element oder einen Elementbereich in einen Satz ein.|  
|[key\_comp](../Topic/set::key_comp.md)|Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Schlüssel in einem Satz verwendet wird.|  
|[lower\_bound](../Topic/set::lower_bound.md)|Gibt einen Iterator zum ersten Element in einem Satz mit einem Schlüssel zurück, der gleich oder größer als ein angegebener Schlüssel ist.|  
|[max\_size](../Topic/set::max_size.md)|Gibt die Maximallänge des Satzes zurück.|  
|[rbegin](../Topic/set::rbegin.md)|Gibt einen Iterator zurück, der das erste Element in einem umgekehrten Satz adressiert.|  
|[rend](../Topic/set::rend.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines umgekehrten Satzes nachfolgt.|  
|[size](../Topic/set::size.md)|Gibt die Anzahl der Elemente im Satz zurück.|  
|[swap](../Topic/set::swap.md)|Tauscht die Elemente zweier Sätze aus.|  
|[upper\_bound](../Topic/set::upper_bound.md)|Gibt einen Iterator zum ersten Element in einem Satz mit einem Schlüssel zurück, der größer als ein angegebener Schlüssel ist.|  
|[value\_comp](../Topic/set::value_comp.md)|Ruft eine Kopie des Vergleichsobjekts ab, das zum Sortieren der Elementwerte in einem Satz verwendet wird.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/set::operator=.md)|Ersetzt die Elemente eines Satzes durch eine Kopie eines anderen Satzes.|  
  
## Anforderungen  
 **Header:** \<set\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<set\>](../standard-library/set.md)   
 [Container](../cpp/containers-modern-cpp.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)