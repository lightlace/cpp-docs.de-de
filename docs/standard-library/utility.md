---
title: '&lt;utility&gt;'
ms.date: 11/04/2016
f1_keywords:
- <utility>
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
ms.openlocfilehash: 76b04c3c26f6ec49f1d816feaeec7e21312d79a9
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246281"
---
# <a name="ltutilitygt"></a>&lt;utility&gt;

Definiert Typen, Funktionen und Operatoren einer C++-Standardbibliothek, mit denen Paare von Objekten erstellt und verwaltet werden können. Solche Paare von Objekten sind immer dann nützlich, wenn zwei Objekte so behandelt werden müssen, als wären sie ein Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** \<utility>

**Namespace:** std

## <a name="remarks"></a>Hinweise

Paare werden häufig in der C++-Standardbibliothek verwendet. Sie sind sowohl als Argumente als auch als Rückgabewerte für verschiedene Funktionen sowie als Elementtypen für Container wie [map-Klasse](../standard-library/map-class.md) und [multimap-Klasse](../standard-library/multimap-class.md) erforderlich. Der \<utility>-Header wird automatisch von \<map> eingefügt, damit deren Typelemente für Schlüssel/Wert-Paare einfacher zu verwalten sind.

> [!NOTE]
> Die \<Utility >-Header verwendet die Anweisung `#include <initializer_list>`. Er bezieht sich auch auf `class tuple` gemäß \<Tupel >.

## <a name="members"></a>Member

### <a name="classes"></a>Klassen

|||
|-|-|
|[chars_format](../standard-library/chars-format-class.md)|Gleitkommaformat für primitive numerische Konvertierung.|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Eine Klasse, die den Typ eines `pair`-Elements umschließt.|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Eine Klasse, die eine `pair`-Elementanzahl umschließt.|

### <a name="objects"></a>erzwingen

|||
|-|-|
|[index_sequence](../standard-library/utility-functions.md#index_sequence)||
|[index_sequence_for](../standard-library/utility-functions.md#index_sequence_for)||
|[make_index_sequence](../standard-library/utility-functions.md#make_index_sequence)||
|[make_integer_sequence](../standard-library/utility-functions.md#make_integer_sequence)||

### <a name="functions"></a>Funktionen

|||
|-|-|
|[as_const](../standard-library/utility-functions.md#asconst)|Gibt den Typ.|
|[declval](../standard-library/utility-functions.md#declval)|Kurzform der ausdrucksauswertung.|
|[exchange](../standard-library/utility-functions.md#exchange)|Weist einen neuen Wert auf ein Objekt und seinen alten Wert.|
|[forward](../standard-library/utility-functions.md#forward)|Verhindert durch perfektes Weiterleiten, dass der Referenztyp (entweder `lvalue` oder `rvalue`) des Arguments verdeckt wird.|
|[from_chars](../standard-library/utility-functions.md#from_chars)||
|[get](../standard-library/utility-functions.md#get)|Eine Funktion, die ein Element aus einem `pair`-Objekt abruft.|
|[make_pair](../standard-library/utility-functions.md#make_pair)|Eine Vorlagenhilfsfunktion, die zum Erstellen von Objekten des Typs `pair` verwendet wird, wobei die Komponententypen auf den Datentypen basieren, die als Parameter übergeben werden.|
|[move](../standard-library/utility-functions.md#move)|Gibt das als Eingabe übergebene Argument als einen `rvalue`-Verweis zurück.|
|[move_if_noexcept](../standard-library/utility-functions.md#moveif)||
|[swap](../standard-library/utility-functions.md#swap)|Tauscht die Elemente zweier `pair`-Objekte.|
|[to_chars](../standard-library/utility-functions.md#to_chars)|Wert in eine Zeichenfolge konvertiert.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator!=](../standard-library/utility-operators.md#op_neq)|Testet, ob das pair-Objekt links vom Operator ungleich dem pair-Objekt rechts vom Operator ist.|
|[operator==](../standard-library/utility-operators.md#op_eq_eq)|Testet, ob das pair-Objekt links vom Operator gleich dem pair-Objekt rechts vom Operator ist.|
|[operator\<](../standard-library/utility-operators.md#op_lt)|Testet, ob das pair-Objekt links vom Operator kleiner als das pair-Objekt rechts vom Operator ist.|
|[operator\<=](../standard-library/utility-operators.md#op_gt_eq)|Testet, ob das pair-Objekt links vom Operator kleiner gleich dem pair-Objekt rechts vom Operator ist.|
|[operator>](../standard-library/utility-operators.md#op_gt)|Testet, ob das pair-Objekt links vom Operator größer als das pair-Objekt rechts vom Operator ist.|
|[operator>=](../standard-library/utility-operators.md#op_gt_eq)|Testet, ob das pair-Objekt links vom Operator größer gleich dem pair-Objekt rechts vom Operator ist.|

### <a name="structs"></a>Strukturen

|||
|-|-|
|[from_chars_result](../standard-library/from-chars-result-structure.md)|Eine Struktur zum `from_chars`.|
|[identity](../standard-library/identity-structure.md)|Eine Struktur, die eine Typdefinition als den Vorlagenparameter bereitstellt.|
|[von in_place_t](../standard-library/in-place-t-struct.md)|Enthält auch Strukturen `in_place_type_t` und `in_place_index_t`.|
|["integer_sequence"](../standard-library/integer-sequence-class.md)|Stellt eine Ganzzahlsequenz dar.|
|[pair](../standard-library/pair-structure.md)|Ein Typ, der die Möglichkeit bietet, zwei Objekte als ein einzelnes Objekt zu behandeln.|
|[piecewise_construct_t](../standard-library/piecewise-construct-t-structure.md)|Ein Typ verwendet, um separate Konstruktor und beim Überladen von Funktionen zu erhalten.|
|[to_chars_result](../standard-library/to-chars-result-structure.md)|Eine Struktur zum `to_chars`.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
