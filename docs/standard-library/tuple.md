---
title: '&lt;tuple&gt;'
ms.date: 11/04/2016
f1_keywords:
- <tuple>
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
ms.openlocfilehash: ce6e005990d05676fb20752b5808d32ec88dd7b3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68241542"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

Definiert eine Vorlage `tuple`, deren Instanzen Objekte verschiedener Typen enthalten.

## <a name="requirements"></a>Anforderungen

**Header:** \<tuple>

**Namespace:** std

## <a name="members"></a>Member

### <a name="classes-and-structs"></a>Klassen und Strukturen

|||
|-|-|
|[Tupelklasse](../standard-library/tuple-class.md)|Umschließt eine Sequenz von Elementen mit fester Länge.|
|[tuple_element-Klasse](../standard-library/tuple-element-class-tuple.md)|Umschließt den Typ eines `tuple`-Elements.|
|[tuple_size-Klasse](../standard-library/tuple-size-class-tuple.md)|Umschließt die `tuple`-Elementanzahl.|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||

### <a name="objects"></a>erzwingen

|||
|-|-|
|[Typalias "tuple_element_t"](../standard-library/tuple-functions.md#tuple_element_t)||
|[tuple_size_v](../standard-library/tuple-functions.md#tuple_size_v)||

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|Vergleich von `tuple` Objekten: gleich.|
|[Operator!=](../standard-library/tuple-operators.md#op_neq)|Vergleich von `tuple` Objekten: ungleich.|
|[operator<](../standard-library/tuple-operators.md#op_lt)|Vergleich von `tuple` Objekten, kleiner als.|
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|Vergleich von `tuple` Objekten, die kleiner oder gleich.|
|[operator>](../standard-library/tuple-operators.md#op_gt)|Vergleich von `tuple` Objekten: größer als.|
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|Vergleich von `tuple` Objekte, die größer als oder gleich.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[apply](../standard-library/tuple-functions.md#apply)|Ruft eine Funktion mit einem Tupel.|
|[forward_as_tuple](../standard-library/tuple-functions.md#forward)|Erstellt ein Tupel von verweisen.|
|[get](../standard-library/tuple-functions.md#get)|Ruft ein Element aus einem `tuple`-Objekt ab.|
|[make_from_tuple](../standard-library/tuple-functions.md#make_from_tuple)|Schnelle Möglichkeit, Sie stellen eine `tuple`.|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Erstellt eine `tuple` aus Elementwerten.|
|[swap](../standard-library/tuple-functions.md#swap)||
|[tie](../standard-library/tuple-functions.md#tie)|Erstellt eine `tuple` aus Elementverweisen.|
|[tuple_cat](../standard-library/tuple-functions.md#tuple_cat)|Erstellt ein Tupelobjekt mit den Elementen des Typs.|

## <a name="see-also"></a>Siehe auch

[\<array>](../standard-library/array.md)<br/>
