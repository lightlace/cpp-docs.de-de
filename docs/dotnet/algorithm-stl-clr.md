---
title: Algorithmus (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/algorithm>
- cliext::adjacent_find
- cliext::binary_search
- cliext::copy
- cliext::copy_backward
- cliext::count
- cliext::count_if
- cliext::equal
- cliext::equal_range
- cliext::fill
- cliext::fill_n
- cliext::find
- cliext::find_end
- cliext::find_first_of
- cliext::find_if
- cliext::for_each
- cliext::generate
- cliext::generate_n
- cliext::includes
- cliext::inplace_merge
- cliext::iter_swap
- cliext::lexicographical_compare
- cliext::lower_bound
- cliext::make_heap
- cliext::max
- cliext::max_element
- cliext::merge
- cliext::min
- cliext::min_element
- cliext::mismatch
- cliext::next_permutation
- cliext::nth_element
- cliext::partial_sort
- cliext::partial_sort_copy
- cliext::partition
- cliext::pop_heap
- cliext::prev_permutation
- cliext::push_heap
- cliext::random_shuffle
- cliext::remove
- cliext::remove_copy
- cliext::remove_copy_if
- cliext::remove_if
- cliext::replace
- cliext::replace_copy
- cliext::replace_copy_if
- cliext::replace_if
- cliext::reverse
- cliext::reverse_copy
- cliext::rotate
- cliext::rotate_copy
- cliext::search
- cliext::search_n
- cliext::set_difference
- cliext::set_intersection
- cliext::set_symmetric_difference
- cliext::set_union
- cliext::sort
- cliext::sort_heap
- cliext::stable_partition
- cliext::stable_sort
- cliext::swap
- cliext::swap_ranges
- cliext::transform
- cliext::unique
- cliext::unique_copy
- cliext::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- algorithm functions [STL/CLR]
- <algorithm> header [STL/CLR]
- <cliext/algorithm> header [STL/CLR]
- adjacent_find function
- binary_search function [STL/CLR]
- copy function [STL/CLR]
- copy_backward function [STL/CLR]
- count function [STL/CLR]
- count_if function [STL/CLR]
- equal function [STL/CLR]
- equal_range function [STL/CLR]
- fill function
- fill_n function
- find function [STL/CLR]
- find_end function [STL/CLR]
- find_first_of function [STL/CLR]
- find_if function [STL/CLR]
- for_each function [STL/CLR]
- generate function [STL/CLR]
- generate_n function [STL/CLR]
- includes function [STL/CLR]
- inplace_merge function [STL/CLR]
- iter_swap function [STL/CLR]
- lexicographical_compare function [STL/CLR]
- lower_bound function [STL/CLR]
- make_heap function [STL/CLR]
- max function [STL/CLR]
- max_element function [STL/CLR]
- merge function [STL/CLR]
- min function [STL/CLR]
- min_element function [STL/CLR]
- mismatch function [STL/CLR]
- next_permutation function [STL/CLR]
- nth_element function [STL/CLR]
- partial_sort function [STL/CLR]
- partial_sort_copy function [STL/CLR]
- partition function [STL/CLR]
- pop_heap function [STL/CLR]
- prev_permutation function [STL/CLR]
- push_heap function [STL/CLR]
- random_shuffle function [STL/CLR]
- remove function [STL/CLR]
- remove_copy function [STL/CLR]
- remove_copy_if function [STL/CLR]
- remove_if function [STL/CLR]
- replace function [STL/CLR]
- replace_copy function [STL/CLR]
- replace_copy_if function [STL/CLR]
- replace_if function [STL/CLR]
- reverse function [STL/CLR]
- reverse_copy function [STL/CLR]
- rotate function [STL/CLR]
- rotate_copy function [STL/CLR]
- search function [STL/CLR]
- search_n function [STL/CLR]
- set_difference function [STL/CLR]
- set_intersection function [STL/CLR]
- set_symmetric_difference function [STL/CLR]
- set_union function [STL/CLR]
- sort function [STL/CLR]
- sort_heap function [STL/CLR]
- stable_partition function [STL/CLR]
- stable_sort function [STL/CLR]
- swap function [STL/CLR]
- swap_ranges function [STL/CLR]
- transform function [STL/CLR]
- unique function [STL/CLR]
- unique_copy function [STL/CLR]
- upper_bound function [STL/CLR]
ms.assetid: ee2718dc-a98d-40b8-8341-593fe7d2ac15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 71399d254b2b47b33959695a00227e316c04a008
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "36305799"
---
# <a name="algorithm-stlclr"></a>algorithm (STL/CLR)
Definiert die STL/CLR-containervorlagenfunktionen, die Algorithmen ausführen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <cliext/algorithm>  
```  

## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
    
## <a name="functions"></a>Funktionen  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[adjacent_find (STL/CLR)](#adjacent_find)|Sucht zwei benachbarte Elemente, die gleich sind.|  
|[binary_search (STL/CLR)](#binary_search)|Testet, ob eine sortierte Sequenz über einen bestimmten Wert enthält.|  
|[copy (STL/CLR)](#copy)|Kopiert die Werte aus einem Quellbereich in einen Zielbereich, in dem vorwärts durchlaufen.|  
|[copy_backward (STL/CLR)](#copy_backward)|Kopiert die Werte aus einem Quellbereich einem Zielbereich, in der rückwärts durchlaufen.|  
|[count (STL/CLR)](#count)|Gibt die Anzahl von Elementen in einem Bereich zurück, dessen Werte mit einem angegebenen Wert übereinstimmen.|  
|[count_if (STL/CLR)](#count_if)|Gibt die Anzahl von Elementen in einem Bereich zurück, dessen Werte mit einer angegebenen Bedingung übereinstimmen.|  
|[equal (STL/CLR)](#equal)|Vergleicht zwei Bereiche elementweise an.|  
|[equal_range (STL/CLR)](#equal_range)|Sucht eine geordnete Sequenz von Werten und gibt zwei Positionen, die eine Untersequenz von Werten zu begrenzen, die alle auf ein angegebenes Element gleich sind.|  
|[fill (STL/CLR)](#fill)|Weist den gleichen neuen Wert jedem Element in einem angegebenen Bereich zu.|  
|[fill_n (STL/CLR)](#fill_n)|Weist einer angegebenen Anzahl von Elementen in einem Bereich, der mit einem bestimmten Element beginnt, einen neuen Wert zu.|  
|[find (STL/CLR)](#find)|Gibt die Position des ersten Vorkommens eines angegebenen Werts zurück.|  
|[find_end (STL/CLR)](#find_end)|Gibt zurück, die letzte Untersequenz in einem Bereich, der mit einer angegebenen Sequenz identisch ist.|  
|[find_first_of (STL/CLR)](#find_first_of)|Durchsucht einen Bereich für das erste Vorkommen eines von einem angegebenen Bereich von Elementen an.|  
|[find_if (STL/CLR)](#find_if)|Gibt die Position des ersten Elements in einer Sequenz von Werten zurück, in dem das Element eine angegebene Bedingung erfüllt.|  
|[for_each (STL/CLR)](#for_each)|Wendet ein angegebenes Funktionsobjekt auf jedes Element in einer Sequenz von Werten und gibt das Funktionsobjekt zurück.|  
|[generate (STL/CLR)](#generate)|Weist die Werte durch ein Funktionsobjekt auf jedes Element in einer Sequenz von Werten generiert.|  
|[generate_n (STL/CLR)](#generate_n)|Weist die Werte durch ein Funktionsobjekt, das eine angegebene Anzahl von Elementen generiert.|  
|[includes (STL/CLR)](#includes)|Testet, ob ein sortierter Bereich alle Elemente in einem zweiten sortierten Bereich enthält.|  
|[inplace_merge (STL/CLR)](#inplace_merge)|Kombiniert die Elemente von zwei aufeinander folgenden sortierten Bereichen in einen einzelnen sortierten Bereich.|  
|[iter_swap (STL/CLR)](#iter_swap)|Tauscht zwei Werte aus, auf die durch ein Paar angegebener Iteratoren verwiesen wird.|  
|[lexicographical_compare (STL/CLR)](#lexicographical_compare)|Vergleicht zwei Sequenzen elementweise, identifizieren, welche Sequenz die kleinere der beiden ist.|  
|[lower_bound (STL/CLR)](#lower_bound)|Sucht die Position des ersten Elements in eine geordnete Sequenz von Werten, die einen Wert größer als oder gleich einem angegebenen Wert aufweist.|  
|[make_heap (STL/CLR)](#make_heap)|Konvertiert Elemente aus einem angegebenen Bereich in einen Heap, in dem das erste Element im Heap an das größte ist.|  
|[Max (STL/CLR)](#max))|Vergleicht zwei Objekte und gibt das größere der beiden zurück.|  
|[max_element (STL/CLR)](#max_element)|Sucht nach dem größten Element in einer angegebenen Sequenz von Werten aus.|  
|[Merge (STL/CLR)](#merge))|Kombiniert alle Elemente von zwei sortierten Quellbereichen in einen einzelnen, sortierten Zielbereich.|  
|[min (STL/CLR)](#min)|Vergleicht zwei Objekte und gibt das kleinere der beiden zurück.|  
|[min_element (STL/CLR)](#min_element)|Sucht das kleinste Element in einer angegebenen Sequenz von Werten an.|  
|[mismatch (STL/CLR)](#mismatch)|Vergleicht zwei Bereiche elementweise und gibt die erste Position, an der ein Unterschied auftritt.|  
|[next_permutation (STL/CLR)](#next_permutation)|Ordnet die Elemente in einem Bereich neu, damit, dass die ursprüngliche Reihenfolge von der lexikografisch nächsthöheren Permutation ersetzt wird, falls es vorhanden ist.|  
|[nth_element (STL/CLR)](#nth_element)|Partitionen eine Sequenz von Elementen und ermittelt die `n`th-Element der Sequenz, damit alle Elemente davor kleiner oder gleich ist, werden und alle Elemente, die er diesem Link folgen, größer als oder gleich werden.|  
|[partial_sort (STL/CLR)](#partial_sort)|Ordnet eine angegebene Anzahl von kleineren Elementen in einem Bereich in einer aufsteigenden Reihenfolge an.|  
|[partial_sort_copy (STL/CLR)](#partial_sort_copy)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich, dass die Elemente aus der Quellbereich sortiert werden.|  
|[partition (STL/CLR)](#partition)|Ordnet die Elemente in einem Bereich, dass diese Elemente, die ein unäres Prädikat erfüllen die vorangehen, bei denen es nicht erfüllen.|  
|[pop_heap (STL/CLR)](#pop_heap)|Das größte Element von der Vorderseite eines Heaps an das Ende verschoben und bildet dann einen neuen Heap aus den übrigen Elementen.|  
|[prev_permutation (STL/CLR)](#prev_permutation)|Sortiert eine Sequenz von Elementen an, damit, dass die ursprüngliche Reihenfolge von der lexikografisch vorherigen größer Permutation ersetzt wird, falls es vorhanden ist.|  
|[push_heap (STL/CLR)](#push_heap)|Fügt ein Element hinzu, das sich am Ende eines Bereichs in einem vorhandenen Heap befindet, der aus den vorherigen Elementen im Bereich besteht.|  
|[random_shuffle (STL/CLR)](#random_shuffle)|Sortiert eine Sequenz von `N` Elemente in einem Bereich in einer der `N`! möglichen per Zufall ausgewählten Anordnungen neu.|  
|[remove (STL/CLR)](#remove)|Löscht einen angegebenen Wert aus einem angegebenen Bereich, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen, und gibt das Ende eines neuen Bereichs des angegebenen Werts zurück.|  
|[remove_copy (STL/CLR)](#remove_copy)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich, ohne dass Elemente eines angegebenen Werts nicht kopiert werden, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen.|  
|[remove_copy_if (STL/CLR)](#remove_copy_if)|Kopiert Elemente aus einem Quellbereich einem Zielbereich zu, mit Ausnahme derjenigen, die ein Prädikat erfüllen, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen.|  
|[remove_if (STL/CLR)](#remove_if)|Löscht die Elemente, die ein Prädikat aus einem angegebenen Bereich erfüllen, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen. sein.|  
|[replace (STL/CLR)](#replace)|Ersetzt die Elemente in einem Bereich, die einem angegebenen Wert durch einen neuen Wert übereinstimmen.|  
|[replace_copy (STL/CLR)](#replace_copy)|Kopiert Elemente aus einem Quellbereich einem Zielbereich, ersetzen Elemente, die einem angegebenen Wert durch einen neuen Wert übereinstimmen.|  
|[replace_copy_if (STL/CLR)](#replace_copy_if)|Überprüft jedes Element in einem Quellbereich und ersetzt es, sofern es ein angegebenes Prädikat erfüllt, während das Ergebnis in einen neuen Zielbereich kopiert wird.|  
|[replace_if (STL/CLR)](#replace_if)|Überprüft jedes Element in einem Bereich und ersetzt es, sofern es das angegebene Prädikat erfüllt.|  
|[reverse (STL/CLR)](#reverse)|Kehrt die Reihenfolge der Elemente innerhalb eines Bereichs um.|  
|[reverse_copy (STL/CLR)](#reverse_copy)|Kehrt die Reihenfolge der Elemente in einem Quellbereich beim Kopieren in einen Zielbereich.|  
|[rotate (STL/CLR)](#rotate)|Vertauscht die Elemente in zwei benachbarten Bereichen.|  
|[rotate_copy (STL/CLR)](#rotate_copy)|Vertauscht die Elemente in zwei benachbarten Bereiche innerhalb eines Quellbereichs und kopiert das Ergebnis in einen Zielbereich.|  
|[search (STL/CLR)](#search_)|Sucht das erste Vorkommen einer Sequenz in einem Zielbereich, dessen Elemente gleich den Elementen in einer bestimmten Elementsequenz sind oder dessen Elemente äquivalent sind mit den Elementen in der angegebenen Sequenz, wie durch ein binäres Prädikat festgelegt.|  
|[search_n (STL/CLR)](#search_n)|Sucht nach der ersten Untersequenz in einem Bereich, der aus einer angegebenen Anzahl von Elementen besteht, die einen bestimmten Wert oder eine Beziehung zu diesem durch ein binäres Prädikat angegebenen Wert haben.|  
|[set_difference (STL/CLR)](#set_difference)|Vereinigt alle Elemente, die zu dem einen, jedoch nicht zu einem anderen sortierten Quellbereich gehören, in einen einzelnen, sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[set_intersection (STL/CLR)](#set_intersection)|Vereinigt alle Elemente, die zu beiden sortierten Quellbereichen gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[set_symmetric_difference (STL/CLR)](#set_symmetric_difference)|Vereinigt alle Elemente, die zu einem, jedoch nicht zu beiden sortierten Quellbereichen gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[Set_union (STL/CLR)](#set_union))|Vereinigt alle Elemente, die mindestens zu einem der beiden sortierten Quellbereiche gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.|  
|[sort (STL/CLR)](#sort)|Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird.|  
|[sort_heap (STL/CLR)](#sort_heap)|Konvertiert einen Heap in einen sortierten Bereich.|  
|[stable_partition (STL/CLR)](#stable_partition)|Klassifiziert Elemente in einem Bereich in zwei zusammenhanglose Sätze, wobei die Elemente, die ein unäres Prädikat erfüllen, direkt den Elementen vorausgehen, die es nicht erfüllen können. Die relative Reihenfolge der äquivalenten Elemente wird dabei beibehalten.|  
|[stable_sort (STL/CLR)](#stable_sort)|Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird, und behält die relative Reihenfolge der äquivalenten Elemente bei.|  
|[swap (STL/CLR)](#swap)|Vertauscht die Werte der Elemente von zwei Objekttypen und weist den Inhalt des ersten Objekts dem zweiten Objekt und den Inhalt des zweiten dem ersten zu.|  
|[swap_ranges (STL/CLR)](#swap_ranges)|Vertauscht die Elemente eines Bereichs mit den Elementen eines anderen gleich großen Bereichs.|  
|[transform (STL/CLR)](#transform)|Wendet ein angegebenes Funktionsobjekt auf jedes Element in einem Quellbereich oder auf ein Elementpaar aus zwei Quellbereichen an und kopiert die Rückgabewerte des Funktionsobjekts in einen Zielbereich.|  
|[unique (STL/CLR)](#unique)|Entfernt doppelte Elemente, die in einem angegebenen Bereich nebeneinander angeordnet sind.|  
|[unique_copy (STL/CLR)](#unique_copy)|Kopiert Elemente aus einem Quellbereich in einen Zielbereich mit Ausnahmen von doppelten Elementen, die nebeneinander angeordnet sind.|  
|[upper_bound (STL/CLR)](#upper_bound)|Sucht die Position des ersten Elements in einem sortierten Bereich, der über einen Wert größer als einen angegebenen Wert verfügt. Dabei wird das Sortierkriterium möglicherweise von einen binären Prädikat bestimmt.|  
 

## <a name="adjacent_find"></a> Adjacent_find (STL/CLR)
Sucht zwei benachbarte Elemente, die entweder gleich sind oder eine angegebene Bedingung erfüllen.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt> inline  
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `adjacent_find`. Weitere Informationen finden Sie unter [Adjacent_find](../standard-library/algorithm-functions.md#adjacent_find).

## <a name="binary_search"></a> Binary_search (STL/CLR)
Testet, ob ein Element in einem sortierten Bereich einem angegebenen Wert entspricht oder ihm auf eine von einem binären Prädikat angegebene Weise gleicht.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _Ty> inline  
    bool binary_search(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    bool binary_search(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `binary_search`. Weitere Informationen finden Sie unter [Binary_search](../standard-library/algorithm-functions.md#binary_search).  
  
## <a name="copy"></a> Kopieren Sie (STL/CLR)
Weist die Werte von Elementen aus einem Quellbereich einem Zielbereich zu, durchläuft die Quellelementsequenz und weist ihnen vorwärts neue Positionen zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt copy(_InIt _First, _InIt _Last, _OutIt _Dest);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `copy`. Weitere Informationen finden Sie unter [Kopie](http://msdn.microsoft.com/Library/f1fec7da-e01b-40f1-b5bd-6b81e304cae1). 

## <a name="copy_backward"></a> Copy_backward (STL/CLR)
Weist die Werte von Elementen aus einem Quellbereich einem Zielbereich zu, durchläuft die Quellelementsequenz und weist ihnen rückwärts neue Positionen zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt1, class _BidIt2> inline  
    _BidIt2 copy_backward(_BidIt1 _First, _BidIt1 _Last,  
        _BidIt2 _Dest);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `copy_backward`. Weitere Informationen finden Sie unter [Copy_backward](../standard-library/algorithm-functions.md#copy_backward).  

## <a name="count"></a> Count (STL/CLR)
Gibt die Anzahl von Elementen in einem Bereich zurück, dessen Werte mit einem angegebenen Wert übereinstimmen.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _Ty> inline  
    typename iterator_traits<_InIt>::difference_type  
        count(_InIt _First, _InIt _Last, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `count`. Weitere Informationen finden Sie unter [Anzahl](../standard-library/algorithm-functions.md#count). 

## <a name="count_if"></a> Count_if (STL/CLR)
Gibt die Anzahl von Elementen in einem Bereich zurück, dessen Werte mit einer angegebenen Bedingung übereinstimmen.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _Pr> inline  
    typename iterator_traits<_InIt>::difference_type  
        count_if(_InIt _First, _InIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `count_if`. Weitere Informationen finden Sie unter [Count_if](../standard-library/algorithm-functions.md#count_if).  
  
## <a name="equal"></a> gleich (STL/CLR)
Vergleicht zwei Bereiche elementweise entweder auf Gleichheit oder Äquivalenz in dem durch ein binäres Prädikat angegebenen Sinn.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `equal`. Weitere Informationen finden Sie unter [gleich](../standard-library/algorithm-functions.md#equal).  

## <a name="equal_range"></a> Equal_range (STL/CLR)
Sucht ein Paar Positionen in einem sortierten Bereich, wobei die erste Position kleiner als oder gleich der Position eines bestimmten Elements und die zweite Position größer als die Position des Elements ist. Die Äquivalenz oder Sortierung zur Festlegung der Positionen in der Sequenz kann durch ein binäres Prädikat angegeben werden.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _Ty> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `equal_range`. Weitere Informationen finden Sie unter [Equal_range](../standard-library/algorithm-functions.md#equal_range).  

## <a name="fill"></a> ausfüllen (STL/CLR)
Weist den gleichen neuen Wert jedem Element in einem angegebenen Bereich zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _Ty> inline  
    void fill(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `fill`. Weitere Informationen finden Sie unter [Füllung](../standard-library/algorithm-functions.md#fill). 

## <a name="fill_n"></a> Fill_n (STL/CLR)
Weist einer angegebenen Anzahl von Elementen in einem Bereich, der mit einem bestimmten Element beginnt, einen neuen Wert zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _OutIt, class _Diff, class _Ty> inline  
    void fill_n(_OutIt _First, _Diff _Count, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `fill_n`. Weitere Informationen finden Sie unter [Fill_n](../standard-library/algorithm-functions.md#fill_n).  

## <a name="find"></a> Find (STL/CLR)
Sucht die Position des ersten Vorkommens eines Elements in einem Bereich, der einen angegebenen Wert enthält.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _Ty> inline  
    _InIt find(_InIt _First, _InIt _Last, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `find`. Weitere Informationen finden Sie unter [suchen](../standard-library/algorithm-functions.md#find). 

## <a name="find_end"></a> Find_end (STL/CLR)
Sucht in einem Bereich nach der letzten Untersequenz, die mit einer angegebenen Sequenz identisch ist oder die in durch ein binäres Prädikat angegebenen Sinne äquivalent ist.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt1 find_end(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2);  
template<class _FwdIt1, class _FwdIt2, class _Pr> inline  
    _FwdIt1 find_end(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `find_end`. Weitere Informationen finden Sie unter [Find_end](../standard-library/algorithm-functions.md#find_end).  

## <a name="find_first_of"></a> Find_first_of (STL/CLR)
Sucht das erste Vorkommen mehrerer Werte innerhalb eines Zielbereichs oder das erste Vorkommen mehrerer Elemente, die wie durch ein binäres Prädikat angegeben mit einem angegebenen Satz der Elemente äquivalent sind.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2);  
template<class _FwdIt1, class _FwdIt2, class _Pr> inline  
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `find_first_of`. Weitere Informationen finden Sie unter [Find_first_of](../standard-library/algorithm-functions.md#find_first_of).  

## <a name="find_if"></a> Find_if (STL/CLR)
Sucht die Position des ersten Vorkommens eines Elements in einem Bereich, der eine bestimmte Bedingung erfüllt.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _Pr> inline  
    _InIt find_if(_InIt _First, _InIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `find_if`. Weitere Informationen finden Sie unter [für "find_if"](../standard-library/algorithm-functions.md#find_if). 

## <a name="for_each"></a> For_each (STL/CLR)
Wendet ein angegebenes Funktionsobjekt auf jedes Element in einer Vorwärtsreihenfolge innerhalb eines Bereichs an und gibt das Funktionsobjekt zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _Fn1> inline  
    _Fn1 for_each(_InIt _First, _InIt _Last, _Fn1 _Func);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `for_each`. Weitere Informationen finden Sie unter [For_each](../standard-library/algorithm-functions.md#for_each).  

## <a name="generate"></a> Generieren von (STL/CLR)
Weist die Werte, die von einem Funktionsobjekt generiert werden, jedem Element in einem Bereich zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _Fn0> inline  
    void generate(_FwdIt _First, _FwdIt _Last, _Fn0 _Func);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `generate`. Weitere Informationen finden Sie unter [generieren](../standard-library/algorithm-functions.md#generate).  

## <a name="generate_n"></a> Generate_n (STL/CLR)
Weist die Werte, die von einem Funktionsobjekt generiert werden, einer angegebenen Anzahl von Elementen eines Bereichs zu und kehrt zu der Position zurück, die direkt nach dem letzten zugewiesenen Wert liegt.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _OutIt, class _Diff, class _Fn0> inline  
    void generate_n(_OutIt _Dest, _Diff _Count, _Fn0 _Func);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `generate_n`. Weitere Informationen finden Sie unter [Generate_n](../standard-library/algorithm-functions.md#generate_n).  
 
## <a name="includes"></a> enthält (STL/CLR)
Testet, ob ein sortierter Bereich alle Elemente enthält, die in einem zweiten sortierten Bereich enthalten sind, wobei das Sortier- oder Äquivalenzkriterium für die Elemente durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `includes`. Weitere Informationen finden Sie unter [enthält](../standard-library/algorithm-functions.md#includes).  

## <a name="inplace_merge"></a> Inplace_merge (STL/CLR)
Kombiniert die Elemente von zwei aufeinander folgenden sortierten Bereichen in einen einzelnen sortierten Bereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `inplace_merge` Weitere Informationen finden Sie unter [Inplace_merge](../standard-library/algorithm-functions.md#inplace_merge).  
  
## <a name="iter_swap"></a> Iter_swap (STL/CLR)
Tauscht zwei Werte aus, auf die durch ein Paar angegebener Iteratoren verwiesen wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    void iter_swap(_FwdIt1 _Left, _FwdIt2 _Right);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `iter_swap`. Weitere Informationen finden Sie unter [Iter_swap](../standard-library/algorithm-functions.md#iter_swap).  

## <a name="lexicographical_compare"></a> Lexicographical_compare (STL/CLR)
Vergleicht zwei Sequenzen elementweise, um zu bestimmen, welche der beiden kleiner ist.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `lexicographical_compare`. Weitere Informationen finden Sie unter [Lexicographical_compare](../standard-library/algorithm-functions.md#lexicographical_compare).  

## <a name="lower_bound"></a> Lower_bound (STL/CLR)
Sucht die Position des ersten Elements in einem sortierten Bereich, dessen Wert kleiner als oder gleich einem angegebenen Wert, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _Ty> inline  
    _FwdIt lower_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _FwdIt lower_bound(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `lower_bound`. Weitere Informationen finden Sie unter [Lower_bound](../standard-library/algorithm-functions.md#lower_bound).  

## <a name="make_heap"></a> Make_heap (STL/CLR)
Konvertiert Elemente aus einem angegebenen Bereich in einen Heap, in dem das erste Element das größte ist und für den ein Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void make_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void make_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `make_heap`. Weitere Informationen finden Sie unter [Make_heap](../standard-library/algorithm-functions.md#make_heap).  
  
## <a name="max"></a> Max (STL/CLR)
Vergleicht zwei Objekte und gibt das größere der beiden zurück, wobei das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _Ty> inline  
    const _Ty max(const _Ty% _Left, const _Ty% _Right);  
template<class _Ty, class _Pr> inline  
    const _Ty max(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `max`. Weitere Informationen finden Sie unter [max](../standard-library/algorithm-functions.md#max).  

## <a name="max_element"></a> Max_element (STL/CLR)
Sucht das erste Vorkommen des größten Elements in einem angegebenen Bereich, in dem das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `max_element`. Weitere Informationen finden Sie unter [Max_element](../standard-library/algorithm-functions.md#max_element).  

## <a name="merge"></a> Merge (STL/CLR)
Kombiniert alle Elemente von zwei sortierten Quellbereichen in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt merge(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt merge(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `merge`. Weitere Informationen finden Sie unter [Merge](../standard-library/algorithm-functions.md#merge).  

## <a name="min"></a> Min (STL/CLR)
Vergleicht zwei Objekte und gibt das kleinere der beiden zurück, wobei das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _Ty> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right);  
template<class _Ty, class _Pr> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `min`. Weitere Informationen finden Sie unter [min](../standard-library/algorithm-functions.md#min).  

## <a name="min_element"></a> Min_element (STL/CLR)
Sucht das erste Vorkommen des kleinsten Elements in einem angegebenen Bereich, in dem das Sortierkriterium von einem binären Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt> inline  
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `min_element`. Weitere Informationen finden Sie unter [Min_element](../standard-library/algorithm-functions.md#min_element).  
  
## <a name="mismatch"></a> Typenkonflikt (STL/CLR)
Vergleicht zwei Bereiche elementweise entweder auf Gleichheit oder Äquivalenz, wie von einem binären Prädikat angegeben, und sucht die erste Position, an der ein Unterschied auftritt.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2> inline  
    _PAIR_TYPE(_InIt1)  
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    _PAIR_TYPE(_InIt1)  
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
            _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `mismatch`. Weitere Informationen finden Sie unter [Konflikt](../standard-library/algorithm-functions.md#mismatch).  

## <a name="next_permutation"></a> Next_permutation (STL/CLR)
Ordnet die Elemente in einem Bereich neu, damit die ursprüngliche Reihenfolge von der lexikografisch nächsthöheren Permutation ersetzt wird, falls vorhanden, wobei die Bedeutung von „nächsthöher“ durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `next_permutation`. Weitere Informationen finden Sie unter [Next_permutation](../standard-library/algorithm-functions.md#next_permutation).  
  
## <a name="nth_element"></a> Nth_element (STL/CLR)
Partitioniert einen Bereich von Elementen und ermittelt die `n`th-Element der Sequenz im Bereich sind so, dass alle Elemente davor kleiner oder gleich und alle Elemente, die in der Sequenz folgen, größer als oder gleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `nth_element`. Weitere Informationen finden Sie unter [Nth_element](../standard-library/algorithm-functions.md#nth_element).  

## <a name="partial_sort"></a> Partial_sort (STL/CLR)
Ordnet eine bestimmte Anzahl von kleineren Elementen in einem Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void partial_sort(_RanIt _First, _RanIt _Mid, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void partial_sort(_RanIt _First, _RanIt _Mid, _RanIt _Last,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `partial_sort`. Weitere Informationen finden Sie unter [Partial_sort](../standard-library/algorithm-functions.md#partial_sort). 

## <a name="partial_sort_copy"></a> Partial_sort_copy (STL/CLR)
Kopiert Elemente aus einem Quellbereich in einen Zielbereich, in dem die Quellelemente entweder durch kleiner als oder durch ein anderes festgelegtes binäres Prädikat sortiert werden.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _RanIt> inline  
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,  
        _RanIt _First2, _RanIt _Last2);  
template<class _InIt, class _RanIt, class _Pr> inline  
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,  
        _RanIt _First2, _RanIt _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `partial_sort_copy`. Weitere Informationen finden Sie unter [Partial_sort_copy](../standard-library/algorithm-functions.md#partial_sort_copy).  
  
## <a name="partition"></a> Partition (STL/CLR)
Klassifiziert Elemente in einem Bereich in zwei zusammenhanglose Sätze, wenn diese Elemente ein unäres Prädikat erfüllen, das denen direkt vorausgeht, die es nicht erfüllen können.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt, class _Pr> inline  
    _BidIt partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `partition`. Weitere Informationen finden Sie unter [Partition](../standard-library/algorithm-functions.md#partition).  

## <a name="pop_heap"></a> Pop_heap (STL/CLR)
Entfernt das größte Element von der Vorderseite eines Heaps und fügt es in die vorletzte Position des Bereichs ein und bildet dann einen neuen Heap aus den übrigen Elementen.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void pop_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void pop_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `pop_heap`. Weitere Informationen finden Sie unter [Pop_heap](../standard-library/algorithm-functions.md#pop_heap).  

## <a name="prev_permutation"></a> Prev_permutation (STL/CLR)
Ordnet die Elemente in einem Bereich neu, damit die ursprüngliche Reihenfolge von der lexikografisch nächsthöheren Permutation ersetzt wird, falls vorhanden, wobei die Bedeutung von „nächsthöher“ durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `prev_permutation`. Weitere Informationen finden Sie unter [Prev_permutation](../standard-library/algorithm-functions.md#prev_permutation).  

## <a name="push_heap"></a> Push_heap (STL/CLR)
Fügt ein Element hinzu, das sich am Ende eines Bereichs in einem vorhandenen Heap befindet, der aus den vorherigen Elementen im Bereich besteht.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void push_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void push_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `push_heap`. Weitere Informationen finden Sie unter [Push_heap](../standard-library/algorithm-functions.md#push_heap).  

## <a name="random_shuffle"></a> Random_shuffle (STL/CLR)
Sortiert eine Sequenz von `N` Elemente in einem Bereich in einer der `N`! möglichen per Zufall ausgewählten Anordnungen neu.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void random_shuffle(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Fn1> inline  
    void random_shuffle(_RanIt _First, _RanIt _Last, _Fn1% _Func);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `random_shuffle`. Weitere Informationen finden Sie unter [Random_shuffle](../standard-library/algorithm-functions.md#random_shuffle). 

## <a name="remove"></a> Entfernen Sie (STL/CLR)
Eliminiert einen angegebenen Wert von einem angegebenen Bereich, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Bereichs zurückzugeben, der den angegebenen Wert nicht enthält.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _Ty> inline  
    _FwdIt remove(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `remove`. Weitere Informationen finden Sie unter [entfernen](http://msdn.microsoft.com/Library/77e2585c-441e-448d-bd1d-c893d1356ed8).  

## <a name="remove_copy"></a> Remove_copy (STL/CLR)
Kopiert Elemente aus einem Quellbereich in einen Zielbereich, ohne dass Elemente eines angegebenen Werts kopiert werden und ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Zielbereichs zurückzugeben.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt remove_copy(_InIt _First, _InIt _Last,  
        _OutIt _Dest, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `remove_copy`. Weitere Informationen finden Sie unter [Remove_copy](../standard-library/algorithm-functions.md#remove_copy).  

## <a name="remove_copy_if"></a> Remove_copy_if (STL/CLR)
Kopiert Elemente aus einem Quellbereich in einen Zielbereich, ohne dass Elemente, die ein Prädikat erfüllen, kopiert werden und ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Zielbereichs zurückzugeben.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt remove_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `remove_copy_if`. Weitere Informationen finden Sie unter [Remove_copy_if](../standard-library/algorithm-functions.md#remove_copy_if).  
  
## <a name="remove_if"></a> Remove_if (STL/CLR)
Eliminiert Elemente, die ein Prädikat aus einem angegebenen Bereich erfüllen, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und das Ende eines neuen Bereichs zurückzugeben, der den angegebenen Wert nicht enthält.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _Pr> inline  
    _FwdIt remove_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `remove_if`. Weitere Informationen finden Sie unter [Remove_if](../standard-library/algorithm-functions.md#remove_if).  
  
## <a name="replace"></a> Replace (STL/CLR)
Überprüft jedes Element in einem Bereich und ersetzt es, sofern es einem angegebenen Wert entspricht.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _Ty> inline  
    void replace(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Oldval, const _Ty% _Newval);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `replace`. Weitere Informationen finden Sie unter [ersetzen](../standard-library/algorithm-functions.md#replace).

## <a name="replace_copy"></a> Replace_copy (STL/CLR)
Überprüft jedes Element in einem Quellbereich und ersetzt es, sofern es einem angegebenen Wert entspricht, während das Ergebnis in einen neuen Zielbereich kopiert wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt replace_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        const _Ty% _Oldval, const _Ty% _Newval);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `replace_copy`. Weitere Informationen finden Sie unter [Replace_copy](../standard-library/algorithm-functions.md#replace_copy).  

## <a name="replace_copy_if"></a> Replace_copy_if (STL/CLR)
Überprüft jedes Element in einem Quellbereich und ersetzt es, sofern es ein angegebenes Prädikat erfüllt, während das Ergebnis in einen neuen Zielbereich kopiert wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _OutIt, class _Pr, class _Ty> inline  
    _OutIt replace_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred, const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `replace_copy_if`. Weitere Informationen finden Sie unter [Replace_copy_if](../standard-library/algorithm-functions.md#replace_copy_if).  
  
## <a name="replace_if"></a> Replace_if (STL/CLR)
Überprüft jedes Element in einem Bereich und ersetzt es, sofern es das angegebene Prädikat erfüllt.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _Pr, class _Ty> inline  
    void replace_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred,  
        const _Ty% _Val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `replace_if`. Weitere Informationen finden Sie unter [Replace_if](../standard-library/algorithm-functions.md#replace_if).  

## <a name="reverse"></a> Reverse (STL/CLR)
Kehrt die Reihenfolge der Elemente innerhalb eines Bereichs um.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt> inline  
    void reverse(_BidIt _First, _BidIt _Last);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `reverse`. Weitere Informationen finden Sie unter [reverse](../standard-library/algorithm-functions.md#reverse).  

## <a name="reverse_copy"></a> Reverse_copy (STL/CLR)
Kehrt die Reihenfolge der Elemente in einem Quellbereich beim Kopieren in einen Zielbereich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt, class _OutIt> inline  
    _OutIt reverse_copy(_BidIt _First, _BidIt _Last, _OutIt _Dest);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `reverse_copy`. Weitere Informationen finden Sie unter [Reverse_copy](../standard-library/algorithm-functions.md#reverse_copy).  
  
## <a name="rotate"></a> Drehen Sie (STL/CLR)
Vertauscht die Elemente in zwei benachbarten Bereichen.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt> inline  
    void rotate(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `rotate`. Weitere Informationen finden Sie unter [Drehen](../standard-library/algorithm-functions.md#rotate).  

## <a name="rotate_copy"></a> Rotate_copy (STL/CLR)
Vertauscht die Elemente in zwei benachbarten Bereiche innerhalb eines Quellbereichs und kopiert das Ergebnis in einen Zielbereich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _OutIt> inline  
    _OutIt rotate_copy(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last,  
        _OutIt _Dest);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `rotate_copy`. Weitere Informationen finden Sie unter [Rotate_copy](../standard-library/algorithm-functions.md#rotate_copy).  
  
## <a name="search_"></a> Suche (STL/CLR)
Sucht das erste Vorkommen einer Sequenz in einem Zielbereich, dessen Elemente gleich den Elementen in einer bestimmten Elementsequenz sind oder dessen Elemente äquivalent sind mit den Elementen in der angegebenen Sequenz, wie durch ein binäres Prädikat festgelegt.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2);  
template<class _FwdIt1, class _FwdIt2, class _Pr> inline  
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `search`. Weitere Informationen finden Sie unter [Suche](../standard-library/algorithm-functions.md#search).  

## <a name="search_n"></a> Search_n (STL/CLR)
Sucht nach der ersten Untersequenz in einem Bereich, der aus einer angegebenen Anzahl von Elementen besteht, die einen bestimmten Wert oder eine Beziehung zu diesem durch ein binäres Prädikat angegebenen Wert haben.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt1, class _Diff2, class _Ty> inline  
    _FwdIt1 search_n(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _Diff2 _Count, const _Ty& _Val);  
template<class _FwdIt1, class _Diff2, class _Ty, class _Pr> inline  
    _FwdIt1 search_n(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _Diff2 _Count, const _Ty& _Val, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `search_n`. Weitere Informationen finden Sie unter [Search_n](../standard-library/algorithm-functions.md#search_n).  

## <a name="set_difference"></a> Set_difference (STL/CLR)
Vereinigt alle Elemente, die zu dem einen, jedoch nicht zu einem anderen sortierten Quellbereich gehören, in einen einzelnen, sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2,_OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `set_difference`. Weitere Informationen finden Sie unter [Set_difference](../standard-library/algorithm-functions.md#set_difference).

## <a name="set_intersection"></a> Set_intersection (STL/CLR)
Vereinigt alle Elemente, die zu beiden sortierten Quellbereichen gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `set_intersection`. Weitere Informationen finden Sie unter [Set_intersection](../standard-library/algorithm-functions.md#set_intersection). 

## <a name="set_symmetric_difference"></a> Set_symmetric_difference (STL/CLR)
Vereinigt alle Elemente, die zu einem, jedoch nicht zu beiden sortierten Quellbereichen gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_symmetric_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_symmetric_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `set_symmetric_difference`. Weitere Informationen finden Sie unter [Set_symmetric_difference](../standard-library/algorithm-functions.md#set_symmetric_difference).  

## <a name="set_union"></a> Set_union (STL/CLR)
Vereinigt alle Elemente, die mindestens zu einem der beiden sortierten Quellbereiche gehören, in einen einzelnen sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_union(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_union(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `set_union`. Weitere Informationen finden Sie unter [Set_union](../standard-library/algorithm-functions.md#set_union).  

## <a name="sort"></a> Sort (STL/CLR)
Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void sort(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void sort(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `sort`. Weitere Informationen finden Sie unter [sortieren](../mfc/reference/cmfclistctrl-class.md#sort).  

## <a name="sort_heap"></a> Sort_heap (STL/CLR)
Konvertiert einen Heap in einen sortierten Bereich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void sort_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void sort_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `sort_heap`. Weitere Informationen finden Sie unter [Sort_heap](../standard-library/algorithm-functions.md#sort_heap).  

## <a name="stable_partition"></a> Stable_partition (STL/CLR)
Klassifiziert Elemente in einem Bereich in zwei zusammenhanglose Sätze, wobei die Elemente, die ein unäres Prädikat erfüllen, direkt den Elementen vorausgehen, die es nicht erfüllen können. Die relative Reihenfolge der äquivalenten Elemente wird dabei beibehalten.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt, class _Pr> inline  
    _BidIt stable_partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `stable_partition`. Weitere Informationen finden Sie unter [Stable_partition](../standard-library/algorithm-functions.md#stable_partition).  

## <a name="stable_sort"></a> Stable_sort (STL/CLR)
Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat angegeben wird, und behält die relative Reihenfolge der äquivalenten Elemente bei.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt> inline  
    void stable_sort(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void stable_sort(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `stable_sort`. Weitere Informationen finden Sie unter [Stable_sort](../standard-library/algorithm-functions.md#stable_sort).  
  
## <a name="swap"></a> Swap (STL/CLR)
Vertauscht die Werte der Elemente von zwei Objekttypen und weist den Inhalt des ersten Objekts dem zweiten Objekt und den Inhalt des zweiten dem ersten zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
<class _Ty> inline  
    void swap(_Ty% _Left, _Ty% _Right);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `swap`. Weitere Informationen finden Sie unter [Swap](http://msdn.microsoft.com/Library/b471a2de-035e-4aff-b1c7-345d85d93972).  

## <a name="swap_ranges"></a> Swap_ranges (STL/CLR)
Vertauscht die Elemente eines Bereichs mit den Elementen eines anderen gleich großen Bereichs.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt2 swap_ranges(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `swap_ranges`. Weitere Informationen finden Sie unter [Swap_ranges](../standard-library/algorithm-functions.md#swap_ranges).  

## <a name="transform"></a> Transformieren Sie (STL/CLR)
Wendet ein angegebenes Funktionsobjekt auf jedes Element in einem Quellbereich oder auf ein Elementpaar aus zwei Quellbereichen an und kopiert die Rückgabewerte des Funktionsobjekts in einen Zielbereich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _OutIt, class _Fn1> inline  
    _OutIt transform(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Fn1 _Func);  
template<class _InIt1, class _InIt2, class _OutIt, class _Fn2> inline  
    _OutIt transform(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `transform`. Weitere Informationen finden Sie unter [transformieren](../standard-library/algorithm-functions.md#transform).  

## <a name="unique"></a> eindeutige (STL/CLR)
Entfernt doppelte Elemente, die in einem angegebenen Bereich nebeneinander angeordnet sind.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `unique`. Weitere Informationen finden Sie unter [eindeutige](../standard-library/algorithm-functions.md#unique).  
  
## <a name="unique_copy"></a> Unique_copy (STL/CLR)
Kopiert Elemente aus einem Quellbereich in einen Zielbereich mit Ausnahmen von doppelten Elementen, die nebeneinander angeordnet sind.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `unique_copy`. Weitere Informationen finden Sie unter [Unique_copy](../standard-library/algorithm-functions.md#unique_copy).  

## <a name="upper_bound"></a> Upper_bound (STL/CLR)
Sucht die Position des ersten Elements in einem sortierten Bereich, der über einen Wert größer als einen angegebenen Wert verfügt. Dabei wird das Sortierkriterium möglicherweise von einen binären Prädikat bestimmt.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt, class _Ty> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `upper_bound`. Weitere Informationen finden Sie unter [Upper_bound](../standard-library/algorithm-functions.md#upper_bound). 
