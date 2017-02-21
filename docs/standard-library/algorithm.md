---
title: "&lt;algorithm&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<algorithm>"
  - "std::<algorithm>"
  - "algorithm/std::<algorithm>"
  - "std.<algorithm>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<algorithm>-Header"
  - "algorithm-Header [C++]"
  - "C++-Standardbibliothek, Algorithmen"
ms.assetid: 19f97711-7a67-4a65-8fd1-9a2bd3ca327d
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# &lt;algorithm&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert Containervorlagenfunktionen für die Standardvorlagenbibliothek \(STL\), die Algorithmen ausführen.  
  
## Syntax  
  
```  
(see relevant links below for specific algorithm syntax)  
```  
  
## Hinweise  
 Die STL\-Algorithmen sind generisch, da sie für verschiedene Datenstrukturen ausgeführt werden können.  Die Datenstrukturen, für die sie ausgeführt werden können, umfassen nicht nur die STL\-Containerklassen wie `vector` und `list`, sondern auch programmdefinierte Datenstrukturen und Arrays von Elementen, die den Anforderungen eines bestimmten Algorithmus entsprechen.  STL\-Algorithmen erzielen dieses Maß an Allgemeingültigkeit, indem sie indirekt über Iteratoren auf die Elemente eines Containers zugreifen und diese durchlaufen.  
  
 Die Process\-Iteratorbereiche für STL\-Algorithmen, die in der Regel durch ihre Start\- oder Zielpositionen angegeben werden.  Die Bereiche, die angegeben werden, müssen in dem Sinne gültig sein, dass alle Zeiger in den Bereichen dereferenzierbar sind und innerhalb der Sequenzen der einzelnen Bereiche liegen. Die letzte Position muss außerdem von der ersten mittels Zunahme erreichbar sein.  
  
 Die STL\-Algorithmen erweitern die Aktionen, die durch die Vorgänge und die Memberfunktionen jedes STL\-Containers unterstützt werden, und lassen das gleichzeitige Arbeiten zum Beispiel mit anderen Typen von Containerobjekten zu.  Zwei Suffixe werden verwendet, um Informationen über den Zweck der Algorithmen zu übergeben.  
  
-   Das `_if`\-Suffix gibt an, dass der Algorithmus mit den Funktionsobjekten verwendet wird, die für die Werte der Elemente statt für die Elemente selbst ausgeführt werden.  Der `find_if`\-Algorithmus sucht nach Elementen, deren Werte dem Kriterium entsprechen, das durch ein Funktionsobjekt angegeben ist, und der `find`\-Algorithmus sucht nach einem bestimmten Wert.  
  
-   Das \_copy\-Suffix gibt an, dass der Algorithmus nicht nur die Werte der Elemente bearbeitet, sondern die geänderten Werte auch in einen Zielbereich kopiert.  Der `reverse`\-Algorithmus kehrt die Reihenfolge der Elemente innerhalb eines Bereichs um, und der `reverse_copy`\-Algorithmus kopiert das Ergebnis außerdem in einen Zielbereich.  
  
 STL\-Algorithmen werden häufig in Gruppen klassifiziert, die Informationen über ihren Zweck oder ihre Anforderungen angeben.  Diese schließen Änderungsalgorithmen ein, die den Wert der Elemente ändern. Im Gegensatz dazu stehen Nichtänderungsalgorithmen, die den Wert nicht ändern.  Mit Mutationsalgorithmen wird zwar die Reihenfolge von Elementen geändert, jedoch nicht die Werte ihrer Elemente.  Mit Entfernungsalgorithmen können Elemente aus einem Bereich oder aus einer Kopie eines Bereichs entfernt werden.  Sortieralgorithmen ordnen die Elemente in einem Bereich auf verschiedene Weise neu und Algorithmen für sortierte Bereiche werden nur für Algorithmen ausgeführt, deren Elemente auf bestimmte Weise sortiert wurden.  
  
 Die numerischen STL\-Algorithmen, die für die numerische Verarbeitung bereitgestellt werden, verfügen über eine eigene Headerdatei [\<numeric\>](../standard-library/numeric.md), und Funktionsobjekte und Adapter werden im Header [\<functional\>](../standard-library/functional.md) in Funktionsobjekten definiert, die als Prädikate bezeichnete boolesche Werte zurückgeben.  Das binäre Standardprädikat ist der Vergleichs\-`operator<`.  Im Allgemeinen müssen die zu sortierenden Elemente etwas weniger als vergleichbar sein, sodass für zwei Elemente bestimmt werden kann, dass sie gleichwertig sind \(in dem Sinne, dass keins geringer als das andere ist\) oder dass eins geringer als das andere ist.  Dies führt zu einer Sortierung zwischen den nicht gleichwertigen Elementen.  
  
### Funktionen  
  
|||  
|-|-|  
|[adjacent\_find](../Topic/adjacent_find.md)|Sucht zwei benachbarte Elemente, die entweder gleich sind oder eine angegebene Bedingung erfüllen.|  
|[all\_of](../Topic/all_of.md)|Gibt `true` zurück, wenn eine Bedingung bei jedem Element im angegebenen Bereich vorhanden ist.|  
|[any\_of](../Topic/any_of.md)|Gibt `true` zurück, wenn eine Bedingung mindestens einmal im angegebenen Bereich von Elementen vorhanden ist.|  
|[binary\_search](../Topic/binary_search.md)|Testet, ob ein Element in einem sortierten Bereich einem angegebenen Wert entspricht oder ihm auf eine von einem binären Prädikat angegebene Weise gleicht.|  
|[copy](../Topic/copy.md)|Weist die Werte von Elementen aus einem Quellbereich einem Zielbereich zu, durchläuft die Quellelementsequenz und weist ihnen vorwärts neue Positionen zu.|  
|[copy\_backward](../Topic/copy_backward.md)|Weist die Werte von Elementen aus einem Quellbereich einem Zielbereich zu, durchläuft die Quellelementsequenz und weist ihnen rückwärts neue Positionen zu.|  
|[copy\_if](../Topic/copy_if.md)|Kopiert alle Elemente in einen angegebenen Bereich, der `true` für eine angegebene Bedingung testet.|  
|[copy\_n](../Topic/copy_n.md)|Kopiert eine angegebene Anzahl von Elementen.|  
|[count](../Topic/count.md)|Gibt die Anzahl von Elementen in einem Bereich zurück, dessen Werte mit einem angegebenen Wert übereinstimmen.|  
|[count\_if](../Topic/count_if.md)|Gibt die Anzahl von Elementen in einem Bereich zurück, dessen Werte mit einer angegebenen Bedingung übereinstimmen.|  
|[equal](../Topic/equal.md)|Vergleicht zwei Bereiche elementweise entweder auf Gleichheit oder Äquivalenz in dem durch ein binäres Prädikat angegebenen Sinn.|  
|[equal\_range](../Topic/equal_range.md)|Sucht ein Paar Positionen in einem sortierten Bereich, wobei die erste Position kleiner als oder gleich der Position eines bestimmten Elements und die zweite Position größer als die Position des Elements ist. Die Äquivalenz oder Sortierung zur Festlegung der Positionen in der Sequenz kann durch ein binäres Prädikat angegeben werden.|  
|[fill](../Topic/fill.md)|Weist den gleichen neuen Wert jedem Element in einem angegebenen Bereich zu.|  
|[fill\_n](../Topic/fill_n.md)|Weist einer angegebenen Anzahl von Elementen in einem Bereich, der mit einem bestimmten Element beginnt, einen neuen Wert zu.|  
|[find](../Topic/find%20\(STL\).md)|Sucht die Position des ersten Vorkommens eines Elements in einem Bereich, der einen angegebenen Wert enthält.|  
|[find\_end](../Topic/find_end.md)|Sucht in einem Bereich nach der letzten Untersequenz, die mit einer angegebenen Sequenz identisch ist oder die in durch ein binäres Prädikat angegebenen Sinne äquivalent ist.|  
|[find\_first\_of](../Topic/find_first_of.md)|Sucht das erste Vorkommen mehrerer Werte innerhalb eines Zielbereichs oder das erste Vorkommen mehrerer Elemente, die wie durch ein binäres Prädikat angegeben mit einem angegebenen Satz der Elemente äquivalent sind.|  
|[find\_if](../Topic/find_if.md)|Sucht die Position des ersten Vorkommens eines Elements in einem Bereich, der eine bestimmte Bedingung erfüllt.|  
|[find\_if\_not](../Topic/find_if_not.md)|Gibt das erste Element im angegebenen Bereich zurück, der eine Bedingung nicht erfüllt.|  
|[for\_each](../Topic/for_each.md)|Wendet ein angegebenes Funktionsobjekt auf jedes Element in einer Vorwärtsreihenfolge innerhalb eines Bereichs an und gibt das Funktionsobjekt zurück.|  
|[generate](../Topic/generate.md)|Weist die Werte, die von einem Funktionsobjekt generiert werden, jedem Element in einem Bereich zu.|  
|[generate\_n](../Topic/generate_n.md)|Weist die Werte, die von einem Funktionsobjekt generiert werden, einer angegebenen Anzahl von Elementen eines Bereichs zu und kehrt zu der Position zurück, die direkt nach dem letzten zugewiesenen Wert liegt.|  
|[includes](../Topic/includes.md)|Testet, ob ein sortierter Bereich alle Elemente enthält, die in einem zweiten sortierten Bereich enthalten sind, wobei das Sortier\- oder Äquivalenzkriterium für die Elemente durch ein binäres Prädikat angegeben werden kann.|  
|[inplace\_merge](../Topic/inplace_merge.md)|Kombiniert die Elemente von zwei aufeinander folgenden sortierten Bereichen in einen einzelnen sortierten Bereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[is\_heap](../Topic/is_heap.md)|Gibt `true` zurück, wenn die Elemente im angegebenen Bereich ein Heap bilden.|  
|[is\_heap\_until](../Topic/is_heap_until.md)|Gibt `true` zurück, wenn der angegebene Bereich ein Heap bis zum letzten Element bildet.|  
|[is\_partitioned](../Topic/is_partitioned.md)|Gibt `true` zurück, wenn alle Elemente im angegebenen Bereich, die für eine Bedingung `true` ergeben, vor allen Elementen liegen, die `false` ergeben.|  
|[is\_permutation](../Topic/is_permutation.md)|Legt fest, ob die Elemente in einem angegebenen Bereich eine gültige Permutation bilden.|  
|[is\_sorted](../Topic/is_sorted.md)|Gibt `true` zurück, wenn sich die Elemente im angegebenen Bereich in einer sortierten Reihenfolge befinden.|  
|[is\_sorted\_until](../Topic/is_sorted_until.md)|Gibt `true` zurück, wenn sich die Elemente im angegebenen Bereich in einer sortierten Reihenfolge befinden.|  
|[iter\_swap](../Topic/iter_swap.md)|Tauscht zwei Werte aus, auf die durch ein Paar angegebener Iteratoren verwiesen wird.|  
|[lexicographical\_compare](../Topic/lexicographical_compare.md)|Vergleicht zwei Sequenzen elementweise, um zu bestimmen, welche der beiden kleiner ist.|  
|[lower\_bound](../Topic/lower_bound.md)|Sucht die Position des ersten Elements in einem sortierten Bereich, der über einen Wert größer als oder gleich einem angegebenen Wert verfügt. Dabei wird das Sortierkriterium möglicherweise von einen binären Prädikat bestimmt.|  
|[make\_heap](../Topic/make_heap.md)|Konvertiert Elemente aus einem angegebenen Bereich in einen Heap, in dem das erste Element das größte ist und für den ein Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[max](../Topic/max.md)|Vergleicht zwei Objekte und gibt das größere der beiden zurück, wobei das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.|  
|[max\_element](../Topic/max_element.md)|Sucht das erste Vorkommen des größten Elements in einem angegebenen Bereich, in dem das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.|  
|[merge](../Topic/merge.md)|Kombiniert alle Elemente von zwei sortierten Quellbereichen in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[min](../Topic/min.md)|Vergleicht zwei Objekte und gibt das kleinere der beiden zurück, wobei das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.|  
|[min\_element](../Topic/min_element.md)|Sucht das erste Vorkommen des kleinsten Elements in einem angegebenen Bereich, in dem das Sortierkriterium von einem binären Prädikat angegeben werden kann.|  
|[minmax](../Topic/minmax.md)|Vergleicht zwei Eingabeparameter und gibt diese als Paar, in der Reihenfolge "kleiner zu größer", zurück.|  
|[minmax\_element](../Topic/minmax_element.md)|Führt die Aufgaben aus, die von [min\_element](../Topic/min_element.md) und [max\_element](../Topic/max_element.md) in einem Aufruf erlegt werden.|  
|[mismatch](../Topic/mismatch.md)|Vergleicht zwei Bereiche elementweise entweder auf Gleichheit oder Äquivalenz, wie von einem binären Prädikat angegeben, und sucht die erste Position, an der ein Unterschied auftritt.|  
|[verschieben](../Topic/%3Calg%3E%20move.md)|Verschiebt Elemente, die einem angegebenen Bereich zugeordnet sind.|  
|[move\_backward](../Topic/move_backward.md)|Verschiebt die Elemente eines Iterators in einen anderen.  Die Verschiebung beginnt mit dem letzten Element in einem angegebenen Bereich und endet mit dem ersten Element in diesem Bereich.|  
|[next\_permutation](../Topic/next_permutation.md)|Ordnet die Elemente in einem Bereich neu, damit die ursprüngliche Reihenfolge von der lexikografisch nächsthöheren Permutation ersetzt wird, falls vorhanden, wobei die Bedeutung von "nächsthöher" durch ein binäres Prädikat angegeben werden kann.|  
|[none\_of](../Topic/none_of.md)|Gibt `true` zurück, wenn eine Bedingung für die Elemente im angegebenen Bereich nie vorhanden ist.|  
|[nth\_element](../Topic/nth_element.md)|Partitioniert einen Bereich von Elementen und ermittelt das *n\-te* Element der Sequenz im Bereich, sodass alle Elemente davor kleiner oder gleich sind und alle Elemente, die in der Sequenz folgen, größer oder gleich sind.|  
|[partial\_sort](../Topic/partial_sort.md)|Ordnet eine bestimmte Anzahl von kleineren Elementen in einem Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird.|  
|[partial\_sort\_copy](../Topic/partial_sort_copy.md)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich, in dem die Quellelemente entweder durch kleiner als oder durch ein anderes festgelegtes binäres Prädikat sortiert werden.|  
|[partition](../Topic/partition.md)|Klassifiziert Elemente in einem Bereich in zwei zusammenhanglose Sätze, wenn diese Elemente ein unäres Prädikat erfüllen, das denen direkt vorausgeht, die es nicht erfüllen können.|  
|[partition\_copy](../Topic/partition_copy.md)|Kopiert Elemente, für die eine Bedingung `true` für ein Ziel ist, und für die die Bedingung `false` für ein anderes Ziel ist.  Die Elemente müssen von einem angegebenen Bereich stammen.|  
|[partition\_point](../Topic/partition_point.md)|Gibt das erste Element im angegebenen Bereich zurück, der die Bedingung nicht erfüllt.  Die Elemente werden so sortiert, dass die, die die Bedingung erfüllen, vor denen angeordnet werden, die die Bedingung nicht erfüllen.|  
|[pop\_heap](../Topic/pop_heap.md)|Entfernt das größte Element von der Vorderseite eines Heaps und fügt es in die vorletzte Position des Bereichs ein und bildet dann einen neuen Heap aus den übrigen Elementen.|  
|[prev\_permutation](../Topic/prev_permutation.md)|Ordnet die Elemente in einem Bereich neu, damit die ursprüngliche Reihenfolge von der lexikografisch nächsthöheren Permutation ersetzt wird, falls vorhanden, wobei die Bedeutung von "nächsthöher" durch ein binäres Prädikat angegeben werden kann.|  
|[push\_heap](../Topic/push_heap.md)|Fügt ein Element hinzu, das sich am Ende eines Bereichs in einem vorhandenen Heap befindet, der aus den vorherigen Elementen im Bereich besteht.|  
|[random\_shuffle](../Topic/random_shuffle.md)|Sortiert eine Sequenz von *N* Elementen in einem Bereich in einer von *N*\!  möglichen per Zufall ausgewählten Anordnungen neu.|  
|[remove](../Topic/remove.md)|Eliminiert einen angegebenen Wert von einem angegebenen Bereich, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Bereichs zurückzugeben, der den angegebenen Wert nicht enthält.|  
|[remove\_copy](../Topic/remove_copy.md)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich, ohne dass Elemente eines angegebenen Werts kopiert werden und ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Zielbereichs zurückzugeben.|  
|[remove\_copy\_if](../Topic/remove_copy_if.md)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich, ohne dass Elemente, die ein Prädikat erfüllen, kopiert werden und ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Zielbereichs zurückzugeben.|  
|[remove\_if](../Topic/remove_if.md)|Eliminiert Elemente, die ein Prädikat aus einem angegebenen Bereich erfüllen, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Bereichs zurückzugeben, der den angegebenen Wert nicht enthält.|  
|[replace](../Topic/replace.md)|Überprüft jedes Element in einem Bereich und ersetzt es, sofern es einem angegebenen Wert entspricht.|  
|[replace\_copy](../Topic/replace_copy.md)|Überprüft jedes Element in einem Quellbereich und ersetzt es, sofern es einem angegebenen Wert entspricht, während das Ergebnis in einen neuen Zielbereich kopiert wird.|  
|[replace\_copy\_if](../Topic/replace_copy_if.md)|Überprüft jedes Element in einem Quellbereich und ersetzt es, sofern es ein angegebenes Prädikat erfüllt, während das Ergebnis in einen neuen Zielbereich kopiert wird.|  
|[replace\_if](../Topic/replace_if.md)|Überprüft jedes Element in einem Bereich und ersetzt es, sofern es das angegebene Prädikat erfüllt.|  
|[reverse](../Topic/reverse.md)|Kehrt die Reihenfolge der Elemente innerhalb eines Bereichs um.|  
|[reverse\_copy](../Topic/reverse_copy.md)|Kehrt die Reihenfolge der Elemente in einem Quellbereich beim Kopieren in einen Zielbereich um.|  
|[rotate](../Topic/rotate.md)|Vertauscht die Elemente in zwei benachbarten Bereichen.|  
|[rotate\_copy](../Topic/rotate_copy.md)|Vertauscht die Elemente in zwei benachbarten Bereiche innerhalb eines Quellbereichs und kopiert das Ergebnis in einen Zielbereich.|  
|[search](../Topic/search.md)|Sucht das erste Vorkommen einer Sequenz in einem Zielbereich, dessen Elemente gleich den Elementen in einer bestimmten Elementsequenz sind oder dessen Elemente äquivalent sind mit den Elementen in der angegebenen Sequenz, wie durch ein binäres Prädikat festgelegt.|  
|[search\_n](../Topic/search_n.md)|Sucht nach der ersten Untersequenz in einem Bereich, der aus einer angegebenen Anzahl von Elementen besteht, die einen bestimmten Wert oder eine Beziehung zu diesem durch ein binäres Prädikat angegebenen Wert haben.|  
|[set\_difference](../Topic/set_difference.md)|Vereinigt alle Elemente, die zu dem einen, jedoch nicht zu einem anderen sortierten Quellbereich gehören, in einen einzelnen, sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[set\_intersection](../Topic/set_intersection.md)|Vereinigt alle Elemente, die zu beiden sortierten Quellbereichen gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[set\_symmetric\_difference](../Topic/set_symmetric_difference.md)|Vereinigt alle Elemente, die zu einem, jedoch nicht zu beiden sortierten Quellbereichen gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[set\_union](../Topic/set_union.md)|Vereinigt alle Elemente, die mindestens zu einem der beiden sortierten Quellbereiche gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[sort](../Topic/sort.md)|Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird.|  
|[shuffle](../Topic/std::shuffle.md)|Mischt \(sortiert\) Elemente für einen gegebenen Bereich mithilfe eines Zufallszahlengenerators.|  
|[sort\_heap](../Topic/sort_heap.md)|Konvertiert einen Heap in einen sortierten Bereich.|  
|[stable\_partition](../Topic/stable_partition.md)|Klassifiziert Elemente in einem Bereich in zwei zusammenhanglose Sätze, wobei die Elemente, die ein unäres Prädikat erfüllen, direkt den Elementen vorausgehen, die es nicht erfüllen können, und die relative Reihenfolge der äquivalenten Elemente beibehalten wird.|  
|[stable\_sort](../Topic/stable_sort.md)|Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird, und behält die relative Reihenfolge der äquivalenten Elemente bei.|  
|[swap](../Topic/swap.md)|Vertauscht die Werte der Elemente von zwei Objekttypen und weist den Inhalt des ersten Objekts dem zweiten Objekt und den Inhalt des zweiten dem ersten zu.|  
|[swap\_ranges](../Topic/swap_ranges.md)|Vertauscht die Elemente eines Bereichs mit den Elementen eines anderen gleich großen Bereichs.|  
|[Transformation](../Topic/transform.md)|Wendet ein angegebenes Funktionsobjekt auf jedes Element in einem Quellbereich oder auf ein Elementpaar aus zwei Quellbereichen an und kopiert die Rückgabewerte des Funktionsobjekts in einen Zielbereich.|  
|[unique](../Topic/unique%20\(%3Calgorithm%3E\).md)|Entfernt doppelte Elemente, die in einem angegebenen Bereich nebeneinander angeordnet sind.|  
|[unique\_copy](../Topic/unique_copy.md)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich mit Ausnahmen von doppelten Elementen, die nebeneinander angeordnet sind.|  
|[upper\_bound](../Topic/upper_bound.md)|Sucht die Position des ersten Elements in einem sortierten Bereich, der über einen Wert größer als einen angegebenen Wert verfügt. Dabei wird das Sortierkriterium möglicherweise von einen binären Prädikat bestimmt.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)