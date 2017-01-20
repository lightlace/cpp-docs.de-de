---
title: "algorithm (STL/CLR)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "<cliext/algorithm>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<algorithm>-Header [STL/CLR]"
  - "<cliext/algorithm>-Header [STL/CLR]"
  - "Algorithmusfunktionen [STL/CLR]"
ms.assetid: ee2718dc-a98d-40b8-8341-593fe7d2ac15
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# algorithm (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert STL\/CLR\-Containervorlagenfunktionen, die Algorithmen ausführen.  
  
## Syntax  
  
```  
#include <cliext/algorithm>  
```  
  
## Funktionen  
  
|Funktion|**Beschreibung**|  
|--------------|----------------------|  
|[adjacent\_find](../dotnet/adjacent-find-stl-clr.md)|Sucht zwei benachbarten Elemente, die gleich sind.|  
|[binary\_search](../dotnet/binary-search-stl-clr.md)|Testet, ob einer Sortierreihenfolge einem angegebenen Wert enthält.|  
|[copy](../dotnet/copy-stl-clr.md)|Kopienwerte von einem Quellbereich einem Zielbereich, vorwärts durchlaufend.|  
|[copy\_backward](../dotnet/copy-backward-stl-clr.md)|Kopienwerte von einem Quellbereich einem Zielbereich, der durchlaufend.|  
|[count](../dotnet/count-stl-clr.md)|Gibt die Anzahl der Elemente in einem Bereich zurück, dessen Werte einen angegebenen Wert übereinstimmen.|  
|[count\_if](../dotnet/count-if-stl-clr.md)|Gibt die Anzahl der Elemente in einem Bereich zurück, dessen Werte einer angegebenen Bedingung entsprechen.|  
|[equal](../dotnet/equal-stl-clr.md)|Vergleicht zwei Bereiche, Element durch Element.|  
|[equal\_range](../dotnet/equal-range-stl-clr.md)|Sucht eine geordnete Sequenz von Werten und gibt zwei Positionen zurück, die eine Untersequenz von Werten begrenzen, die gleich ein angegebenes Element sind.|  
|[Füllung](../dotnet/fill-stl-clr.md)|Weist den gleichen neue Wert für jedes Element in einem angegebenen Bereich zu.|  
|[fill\_n](../dotnet/fill-n-stl-clr.md)|Weist einer angegebenen Anzahl von Elementen in einem Bereich, der mit einem bestimmten Element beginnt, einen neuen Wert zu.|  
|[Suchen](../dotnet/find-stl-clr.md)|Gibt die Position des ersten Vorkommens eines angegebenen Werts zurück.|  
|[find\_end](../dotnet/find-end-stl-clr.md)|Gibt die letzten Untersequenz in einem Bereich zurück, der einer bestimmten Sequenz identisch ist.|  
|[find\_first\_of](../dotnet/find-first-of-stl-clr.md)|Sucht einen Bereich für das erste Vorkommen beliebiger eines bestimmten Bereichs der Elemente.|  
|[find\_if](../dotnet/find-if-stl-clr.md)|Gibt die Position des ersten Elements in eine Sequenz von Werten zurück, wobei das Element eine angegebene Bedingung erfüllt.|  
|[for\_each](../dotnet/for-each-stl-clr.md)|Wendet ein angegebenes Funktionsobjekt an jedem Element in einer Sequenz von Werten und gibt dem Funktionsobjekt zurück.|  
|[Generieren](../dotnet/generate-stl-clr.md)|Weist die Werte, die von ein Funktionsobjekt an jedem Element in einer Sequenz von Werten generiert werden.|  
|[generate\_n](../dotnet/generate-n-stl-clr.md)|Weist die Werte, die von ein Funktionsobjekt an einer angegebenen Anzahl Elemente generiert werden.|  
|[includes](../dotnet/includes-stl-clr.md)|Testet, ob ein Bereich sortierter den gesamten Bereich der sortierten Elemente sofort enthält.|  
|[inplace\_merge](../dotnet/inplace-merge-stl-clr.md)|Kombiniert die Elemente von zwei aufeinander sortierten Bereichen in einen einzelnen Bereich sortieren.|  
|[iter\_swap](../dotnet/iter-swap-stl-clr.md)|Austauschen zwei Werte sprachen durch ein Paar angegebene Iteratoren an.|  
|[lexicographical\_compare](../dotnet/lexicographical-compare-stl-clr.md)|Vergleicht zwei Sequenzen, Element durch das Element und identifiziert, das der Sequenz das kleiner zwei ist.|  
|[lower\_bound](../dotnet/lower-bound-stl-clr.md)|Sucht die Position des ersten Elements in einer geordneten Sequenz von Werten, die einen Wert größer oder gleich einem angegebenen Wert enthält.|  
|[make\_heap](../dotnet/make-heap-stl-clr.md)|Konvertiert Elemente von einem angegebenen Bereichs in einen Heap, in dem das erste Element auf dem Heap der größte ist.|  
|[max](../dotnet/max-stl-clr.md)|Vergleicht zwei Objekte und gibt das größere der beiden zurück.|  
|[max\_element](../dotnet/max-element-stl-clr.md)|Sucht das größte Element in einer angegebenen Sequenz von Werten.|  
|[zusammenführen](../dotnet/merge-stl-clr.md)|Kombiniert alle Elemente zweier sortierten Quellbereichen in einem einzelnen, sortierten Zielbereich.|  
|[min](../dotnet/min-stl-clr.md)|Vergleicht zwei Objekte und gibt die kleinere der beiden zurück.|  
|[min\_element](../dotnet/min-element-stl-clr.md)|Sucht das kleinste Element in einer angegebenen Sequenz von Werten.|  
|[mismatch](../dotnet/mismatch-stl-clr.md)|Vergleicht das Element mit zwei Bereichen durch Element und gibt der ersten Position zurück, in der ein Unterschied auftritt.|  
|[next\_permutation](../dotnet/next-permutation-stl-clr.md)|Ordnet die Elemente in einem Bereich neu damit die ursprüngliche Reihenfolge von der lexikografisch nächsthöhere Permutation ersetzt wird, falls vorhanden.|  
|[nth\_element](../dotnet/nth-element-stl-clr.md)|Partitioniert eine Sequenz von Elementen und korrekt ermittelt `n` das Element der Sequenz, sodass alle Elemente vor das kleiner oder gleich sie sind und alle Elemente, die sie ausführen, größer oder gleich sie sind.|  
|[partial\_sort](../dotnet/partial-sort-stl-clr.md)|Ordnet eine angegebene Anzahl kleinerer Elemente in einem Bereich in nondescending Reihenfolge.|  
|[partial\_sort\_copy](../dotnet/partial-sort-copy-stl-clr.md)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich, sodass die Elemente vom Quellbereich sortiert werden.|  
|[partition](../dotnet/partition-stl-clr.md)|Ordnet Elemente in einem Bereich so an, dass diese Elemente, die kein unäres Prädikat erfüllen, denen befinden, die es nicht erfüllen können.|  
|[pop\_heap](../dotnet/pop-heap-stl-clr.md)|Verschiebt das größte Element der Vorderseite eines Heaps auf das Ende und bildet dann einen neuen Heap von den übrigen Elemente.|  
|[prev\_permutation](../dotnet/prev-permutation-stl-clr.md)|Ordnet eine Sequenz von Elementen neu damit die ursprüngliche Reihenfolge von der lexikografisch vorherige größere Permutation ersetzt wird, falls vorhanden.|  
|[push\_heap](../dotnet/push-heap-stl-clr.md)|Fügt ein Element hinzu, das am Ende eines Bereichs in einen vorhandenen Heap befindet, der aus den vorherigen Elementen im Bereich besteht.|  
|[random\_shuffle](../dotnet/random-shuffle-stl-clr.md)|Ordnet eine Sequenz von `N`\-Elementen in einem Bereich in einen von `N` neu an\! beliebige Anordnungen zufällig ausgewählt.|  
|[Entfernen](../dotnet/remove-stl-clr.md)|Löscht einen angegebenen Wert von einem angegebenen Bereich, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und gibt das Ende eines neuen Bereichs zurück, der aus dem angegebenen Wert frei ist.|  
|[remove\_copy](../dotnet/remove-copy-stl-clr.md)|Kopiert Elemente aus einem Quellbereich einem Zielbereich, dass Elemente eines angegebenen Werts werden kopiert, nicht, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen.|  
|[remove\_copy\_if](../dotnet/remove-copy-if-stl-clr.md)|Kopiert Elemente aus einem Quellbereich einem Zielbereich, außer, die ein Prädikat erfüllen, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen.|  
|[remove\_if](../dotnet/remove-if-stl-clr.md)|Löscht Elemente, die ein Prädikat aus einem angegebenen Bereich erfüllen, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen. .|  
|[Ersetzen](../dotnet/replace-stl-clr.md)|Ersetzt Elemente in einem Bereich, die einen angegebenen Wert mit einem neuen Wert übereinstimmen.|  
|[replace\_copy](../dotnet/replace-copy-stl-clr.md)|Kopiert Elemente aus einem Quellbereich einem Zielbereich und ersetzt Elemente, die einen angegebenen Wert mit einem neuen Wert übereinstimmen.|  
|[replace\_copy\_if](../dotnet/replace-copy-if-stl-clr.md)|Überprüft jedes Element in einem Quellbereich und ersetzt, sofern eines angegebenen Prädikat beim Kopieren des Ergebnisses in einen neuen Zielbereich erfüllt.|  
|[replace\_if](../dotnet/replace-if-stl-clr.md)|Überprüft jedes Element in einem Bereich und ersetzt, sofern das angegebene Prädikat erfüllt.|  
|[reverse](../dotnet/reverse-stl-clr.md)|Kehrt die Reihenfolge der Elemente in einem Bereich um.|  
|[reverse\_copy](../dotnet/reverse-copy-stl-clr.md)|Kehrt die Reihenfolge der Elemente in einem Quellbereichs beim Kopieren in einen Zielbereich um.|  
|[rotate](../dotnet/rotate-stl-clr.md)|Vertauscht die Elemente in zwei aufeinander Bereiche aus.|  
|[rotate\_copy](../dotnet/rotate-copy-stl-clr.md)|Vertauscht die Elemente in zwei aufeinander Bereiche innerhalb eines Quellbereichs aus und kopiert das Ergebnis in einen Zielbereich.|  
|[search](../dotnet/search-stl-clr.md)|Sucht das erste Vorkommen einer Sequenz in eines Zielbereichs, dessen Elemente gleich der in einer bestimmten Sequenz von Elementen sind, und dessen Elemente auf eine Weise angegeben durch ein binäres Prädikat an Elemente in der angegebenen Sequenz entsprechendes sind.|  
|[search\_n](../dotnet/search-n-stl-clr.md)|Suchen nach der ersten Untersequenz in einem Bereich der aus einer angegebenen Anzahl Elemente, die einen bestimmten Wert oder eine Beziehung in diesen Wert aufweisen, z binäres durch ein Prädikat angegeben.|  
|[set\_difference](../dotnet/set-difference-stl-clr.md)|Vereinigt alle Elemente, die ein Quellbereich sortierten gehören, jedoch keiner Sekunde sortierte Quellbereich, in einem einzelnen, sortierten Zielbereich, wobei Sortierkriterium möglicherweise durch ein binäres Prädikat angegeben wird.|  
|[set\_intersection](../dotnet/set-intersection-stl-clr.md)|Vereinigt alle Elemente, die beiden Quellbereichen sortierten in einen einzelnen gehören, sortierten Zielbereich, wobei Sortierkriterium möglicherweise durch ein binäres Prädikat angegeben wird.|  
|[set\_symmetric\_difference](../dotnet/set-symmetric-difference-stl-clr.md)|Vereinigt alle Elemente, die bis eins gehören, jedoch nicht beide, der sortierten Quellbereiche in ein einzelnes, sortierten Zielbereich, wobei Sortierkriterium möglicherweise durch ein binäres Prädikat angegeben wird.|  
|[set\_union](../dotnet/set-union-stl-clr.md)|Vereinigt alle Elemente, die von mindestens einen von zwei Quellbereichen sortierten in einen einzelnen gehören, sortierten Zielbereich, wobei Sortierkriterium möglicherweise durch ein binäres Prädikat angegeben wird.|  
|[Sortieren](../dotnet/sort-stl-clr.md)|Ordnet die Elemente in einem angegebenen Gültigkeitsbereich in eine nondescending Reihenfolge oder entsprechend einem Sortierkriterium an, das durch ein binäres Prädikat angegeben wird.|  
|[sort\_heap](../dotnet/sort-heap-stl-clr.md)|Konvertiert einen Heap in sortierter einen Bereich.|  
|[stable\_partition](../dotnet/stable-partition-stl-clr.md)|Klassifiziert Elemente in einem Bereich in disjunkte zwei Sätze, wenn diese Elemente kein unäres Prädikat erfüllen, das die direkt vorausgeht, die es nicht erfüllen können und behält die relative Position von entsprechenden Arbeitsaufgaben beibehalten.|  
|[stable\_sort](../dotnet/stable-sort-stl-clr.md)|Ordnet die Elemente in einem angegebenen Gültigkeitsbereich in eine nondescending Reihenfolge oder entsprechend einem Sortierkriterium an, das durch ein binäres Prädikat angegeben wird und behält die relative Position von entsprechenden Arbeitsaufgaben beibehalten.|  
|[swap](../dotnet/swap-stl-clr.md)|Vertauscht die Werte der Elemente zwischen zwei Typen Objekte aus und weist den Inhalt des ersten Objekts bis des zweiten Objekts und den Inhalt des zweiten zum ersten zu.|  
|[swap\_ranges](../dotnet/swap-ranges-stl-clr.md)|Vertauscht die Elemente eines Bereichs mit den Elementen von anderen, \- groß Bereich gleicher aus.|  
|[transform](../dotnet/transform-stl-clr.md)|Wendet ein angegebenes Funktionsobjekt an jedes Element in einem Quellbereich oder einem Paar Elemente von zwei Quellbereichen und kopiert die Rückgabewerte des Funktionsobjekts in einen Zielbereich.|  
|[Eindeutig](../dotnet/unique-stl-clr.md)|Entfernt doppelte Elemente nebeneinander, die in einem angegebenen Gültigkeitsbereich.|  
|[unique\_copy](../dotnet/unique-copy-stl-clr.md)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich außer, die doppelte Elemente nebeneinander angeordnet sind.|  
|[upper\_bound](../dotnet/upper-bound-stl-clr.md)|Sucht die Position des ersten Elements in einem sortierten Bereich, der über einen Wert größer als einen angegebenen Wert verfügt. Dabei wird das Sortierkriterium möglicherweise von einen binären Prädikat bestimmt.|  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)