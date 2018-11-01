---
title: '&lt;Iterator&gt;'
ms.date: 11/04/2016
f1_keywords:
- <iterator>
- iterator/std::<iterator>
helpviewer_keywords:
- iterator header
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
ms.openlocfilehash: 1582f6167d8aae3a9d5a318726cc7404c7e1ea62
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640361"
---
# <a name="ltiteratorgt"></a>&lt;Iterator&gt;

Definiert die primitiven Elemente von Iteratoren, vordefinierte Iteratoren sowie Stream-Iteratoren sowie einige unterstützende Vorlagen. Die vordefinierten Iteratoren beinhalten Insert- und Reverse-Adapter. Es gibt drei Klassen von Insert-Adaptern für Iteratoren: Front, Back und General. Sie bieten Einfügesemantik anstelle der Semantik zum Überschreiben, die von Iteratoren der Memberfunktion des Containers bereitgestellt wird.

## <a name="syntax"></a>Syntax

```cpp
#include <iterator>

```

## <a name="remarks"></a>Hinweise

Iteratoren sind eine Verallgemeinerung von Zeigern. Die Anforderungen werden so abstrahiert, dass ein C++-Programm mit unterschiedlichen Datenstrukturen einheitlich arbeiten kann. Iteratoren dienen als Vermittler zwischen Containern und allgemeinen Algorithmen. Algorithmen sind nicht für bestimmte Datentypen definiert, sondern für Bereiche, die durch den Iterator-Typ festgelegt sind. Der Algorithmus funktioniert dann für jede Datenstruktur, die den Anforderungen des Iterators entspricht. Es wird zwischen fünf Typen oder Kategorien von Iteratoren mit jeweils eigenen Anforderungen und Funktionen unterschieden:

- Output: Kann vorwärts bewegt werden, Werte speichern, aber nicht abrufen, und wird von ostream und inserter bereitgestellt.

- Input: Kann vorwärts bewegt werden, Werte abrufen, aber nicht speichern, und wird von istream bereitgestellt.

- Forward: Kann vorwärts bewegt werden und Werte speichern sowie abrufen.

- Bidirektional: Kann vorwärts und rückwärts bewegt werden, Werte speichern und abrufen, und wird durch List, Set, Multiset, Map und Multimap bereitgestellt.

- Random-Access: Auf Elemente wird in beliebiger Reihenfolge zugegriffen, Werte können gespeichert und abgerufen werden, wird durch Vector, Deque, String und Array bereitgestellt.

Iteratoren mit höheren Anforderungen und besserem Zugriff auf Elemente können anstelle von Iteratoren mit geringeren Anforderungen verwendet werden. Wird beispielsweise ein Forward-Iterator aufgerufen, kann stattdessen auch ein Random-Access-Iterator verwendet werden.

Visual Studio besitzt zusätzliche Erweiterungen für C++-Standardbibliotheksiteratoren, um eine Vielzahl von Debugmodussituationen für aktivierte und nicht aktivierte Iteratoren zu unterstützen. Weitere Informationen finden Sie unter [Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md).

### <a name="functions"></a>Funktionen

|Funktion|Beschreibung|
|-|-|
|[advance](../standard-library/iterator-functions.md#advance)|Damit kann ein Iterator um eine bestimmte Anzahl von Positionen vorwärts verschoben werden.|
|[back_inserter](../standard-library/iterator-functions.md#back_inserter)|Damit wird ein Iterator erstellt, mit dem Elemente an das Ende eines bestimmten Containers eingefügt werden können.|
|[begin](../standard-library/iterator-functions.md#begin)|Ruft einen Iterator für das erste Element in einem angegebenen Container ab.|
|[cbegin](../standard-library/iterator-functions.md#cbegin)|Ruft einen konstanten Iterator für das erste Element in einem angegebenen Container ab.|
|[cend](../standard-library/iterator-functions.md#cend)|Ruft einen konstanten Iterator für das Element ab, das auf das letzte Element im angegebenen Container folgt.|
|[distance](../standard-library/iterator-functions.md#distance)|Bestimmt die Anzahl von Inkrementen zwischen den durch zwei Iteratoren festgelegten Positionen.|
|[end](../standard-library/iterator-functions.md#end)|Ruft einen Iterator für das Element ab, das auf das letzte Element im angegebenen Container folgt.|
|[front_inserter](../standard-library/iterator-functions.md#front_inserter)|Damit wird ein Iterator erstellt, mit dem Elemente an den Anfang eines bestimmten Containers eingefügt werden können.|
|[inserter](../standard-library/iterator-functions.md#inserter)|Ein Iterator-Adapter, mit dem einem Container an einem bestimmten Punkt ein neues Element hinzugefügt wird.|
|[make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator)|Erstellt ein [checked_array_iterator](../standard-library/checked-array-iterator-class.md)-Objekt, das von anderen Algorithmen verwendet werden kann. **Hinweis:** Bei dieser Funktion handelt es sich um eine Microsoft-Erweiterung der C++-Standardbibliothek. Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C++-Standardbuildumgebungen übertragbar, die die Microsoft-Erweiterung nicht unterstützen.|
|[make_move_iterator](../standard-library/iterator-functions.md#make_move_iterator)|Gibt einen Move-Iterator zurück, der den bereitgestellten Iterator als gespeicherten Basis-Iterator enthält.|
|[make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator)|Erstellt ein [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md)-Objekt, das von anderen Algorithmen verwendet werden kann. **Hinweis:** Bei dieser Funktion handelt es sich um eine Microsoft-Erweiterung der C++-Standardbibliothek. Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C++-Standardbuildumgebungen übertragbar, die die Microsoft-Erweiterung nicht unterstützen.|
|[next](../standard-library/iterator-functions.md#next)|Führt eine bestimmte Anzahl von Iterationen aus und gibt die neue Position des Iterators zurück.|
|[prev](../standard-library/iterator-functions.md#prev)|Führt eine bestimmte Anzahl von Iterationen rückwärts aus und gibt die neue Position des Iterators zurück.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[Operator!=](../standard-library/iterator-operators.md#op_neq)|Testet, ob das Iterator-Objekt links vom Operator ungleich dem Iterator-Objekt rechts vom Operator ist.|
|[operator==](../standard-library/iterator-operators.md#op_eq_eq)|Testet, ob das Iterator-Objekt links vom Operator gleich dem Iterator-Objekt rechts vom Operator ist.|
|[operator<](../standard-library/iterator-operators.md#op_lt)|Testet, ob das Iterator-Objekt links vom Operator kleiner ist als das Iterator-Objekt rechts vom Operator.|
|[operator\<=](../standard-library/iterator-operators.md#op_gt_eq)|Testet, ob das Iterator-Objekt links vom Operator kleiner als oder gleich dem Iterator-Objekt rechts vom Operator ist.|
|[operator>](../standard-library/iterator-operators.md#op_gt)|Testet, ob das Iterator-Objekt links vom Operator größer als das Iterator-Objekt rechts vom Operator ist.|
|[operator>=](../standard-library/iterator-operators.md#op_gt_eq)|Testet, ob das Iterator-Objekt links vom Operator größer als oder gleich dem Iterator-Objekt rechts vom Operator ist.|
|[operator+](../standard-library/iterator-operators.md#op_add)|Fügt einen Offset zu einem Iterator hinzu und gibt den neuen `reverse_iterator` zurück, der auf das eingefügte Element an der neuen Offsetposition zeigt.|
|[operator-](../standard-library/iterator-operators.md#operator-)|Subtrahiert einen Iterator von einem anderen und gibt die Differenz zurück.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[back_insert_iterator](../standard-library/back-insert-iterator-class.md)|Die Vorlagenklasse beschreibt einen Output-Iterator. Er fügt Elemente an, in einen Container des Typs `Container`, der Zugriff erfolgt über das geschützte `pointer` -Objekt namens Container.|
|[bidirectional_iterator_tag](../standard-library/bidirectional-iterator-tag-struct.md)|Eine Klasse, die einen Rückgabetyp für eine eine `iterator_category` -Funktion, die einen bidirektionalen Iterator darstellt.|
|[checked_array_iterator](../standard-library/checked-array-iterator-class.md)|Eine Klasse, die auf ein Array mit einem Iterator vom Typ "Random-Access, Checked" zugreift. **Hinweis:** Bei dieser Klasse handelt es sich um eine Microsoft-Erweiterung der C++-Standardbibliothek. Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C++-Standardbuildumgebungen übertragbar, die die Microsoft-Erweiterung nicht unterstützen.|
|[forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)|Eine Klasse, die einen Rückgabetyp für eine eine `iterator_category` -Funktion, die einen forward-Iterator darstellt.|
|[front_insert_iterator](../standard-library/front-insert-iterator-class.md)|Die Vorlagenklasse beschreibt einen Output-Iterator. Er fügt Elemente an, in einen Container des Typs `Container`, der Zugriff erfolgt über das geschützte `pointer` -Objekt namens Container.|
|[input_iterator_tag](../standard-library/input-iterator-tag-struct.md)|Eine Klasse, die einen Rückgabetyp für eine eine `iterator_category` -Funktion, die einen eingabeiterator darstellt.|
|[insert_iterator](../standard-library/insert-iterator-class.md)|Die Vorlagenklasse beschreibt einen Output-Iterator. Er fügt Elemente an, in einen Container des Typs `Container`, der Zugriff erfolgt über das geschützte `pointer` -Objekt namens Container. Außerdem speichert er die geschützte `iterator` -Objekt der Klasse `Container::iterator`namens `iter`.|
|[istream_iterator](../standard-library/istream-iterator-class.md)|Die Vorlagenklasse beschreibt einen Input-Iterator. Anschließend extrahiert Sie Objekte der Klasse `Ty` aus einem Eingabedatenstrom, der Zugriff über ein Objekt gespeichert erfolgt, ein Zeiger auf `basic_istream` \< **Elem**, **Tr**>.|
|[istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)|Die Vorlagenklasse beschreibt einen Input-Iterator. Es fügt die Elemente der Klasse `Elem` in einen Datenstrom-Ausgabepuffer, der Zugriff darauf erfolgt durch ein Objekt es speichert, des Typs `pointer` zu `basic_streambuf` \< **Elem**, **Tr** >.|
|[Iterator](../standard-library/iterator-struct.md)|Die Vorlagenklasse wird als Basistyp für alle Iteratoren verwendet.|
|[iterator_traits](../standard-library/iterator-traits-struct.md)|Eine Hilfsklasse für Vorlagen, die wichtige Typen bereitstellt, die mit verschiedenen Iterator-Typen verknüpft sind, damit die Verweise auf dieselbe Weise funktionieren.|
|[move_iterator](../standard-library/move-iterator-class.md)|Ein `move_iterator`-Objekt speichert einen Random-Access-Iterator des Typs `RandomIterator`. Es verhält sich wie ein Rand-Access-Iterator, außer bei einer Dereferenzierung. Das Ergebnis von `operator*` wird implizit umgewandelt in `value_type&&:`, um `rvalue reference` zu erhalten.|
|[ostream_iterator](../standard-library/ostream-iterator-class.md)|Die Vorlagenklasse beschreibt einen Output-Iterator. Er fügt Objekte der Klasse `Type` in einen Ausgabestream, der Zugriff darauf erfolgt durch ein Objekt es speichert, des Typs `pointer` zu `basic_ostream` \< **Elem**, **Tr**>.|
|[ostreambuf_iterator Class](../standard-library/ostreambuf-iterator-class.md)|Die Vorlagenklasse beschreibt einen Output-Iterator. Es fügt die Elemente der Klasse `Elem` in einem Datenstrom-Ausgabepuffer, der Zugriff über ein Objekt gespeichert erfolgt, ein Zeiger auf `basic_streambuf` \< **Elem**, **Tr**>.|
|[output_iterator_tag](../standard-library/output-iterator-tag-struct.md)|Eine Klasse, die einen Rückgabetyp für eine `iterator_category` -Funktion, die einen Ausgabeiterator darstellt.|
|[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)|Eine Klasse, die einen Rückgabetyp für eine `iterator_category` -Funktion, die einen random-Access-Iterator darstellt.|
|[reverse_iterator](../standard-library/reverse-iterator-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das sich wie ein Random-Access-Iterator verhält, nur in umgekehrter Reihenfolge.|
|[unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md)|Eine Klasse, die auf ein Array mit einem Iterator vom Typ "Random-Access, Unchecked" zugreift. **Hinweis:** Bei dieser Klasse handelt es sich um eine Microsoft-Erweiterung der C++-Standardbibliothek. Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C++-Standardbuildumgebungen übertragbar, die die Microsoft-Erweiterung nicht unterstützen.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
