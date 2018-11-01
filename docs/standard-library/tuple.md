---
title: '&lt;tuple&gt;'
ms.date: 11/04/2016
f1_keywords:
- <tuple>
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
ms.openlocfilehash: 2e46b3997096c6e61f7dd6140131e3f10223b8e7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586666"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

Definiert eine Vorlage `tuple`, deren Instanzen Objekte verschiedener Typen enthalten.

## <a name="syntax"></a>Syntax

```cpp
#include <tuple>
```

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[tuple](../standard-library/tuple-class.md)|Umschließt eine Sequenz von Elementen mit fester Länge.|
|[tuple_element-Klasse](../standard-library/tuple-element-class-tuple.md)|Umschließt den Typ eines `tuple`-Elements.|
|[tuple_size-Klasse](../standard-library/tuple-size-class-tuple.md)|Umschließt die `tuple`-Elementanzahl.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|Vergleich von `tuple`-Objekten, gleich|
|[Operator!=](../standard-library/tuple-operators.md#op_neq)|Vergleich von `tuple`-Objekten, ungleich|
|[operator<](../standard-library/tuple-operators.md#op_lt)|Vergleich von `tuple`-Objekten, kleiner als|
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|Vergleich von `tuple`-Objekten, kleiner als oder gleich|
|[operator>](../standard-library/tuple-operators.md#op_gt)|Vergleich von `tuple`-Objekten, größer als|
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|Vergleich von `tuple`-Objekten, größer als oder gleich|

### <a name="functions"></a>Funktionen

|Funktion|Beschreibung|
|-|-|
|[get](../standard-library/tuple-functions.md#get)|Ruft ein Element aus einem `tuple`-Objekt ab.|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Erstellt eine `tuple` aus Elementwerten.|
|[tie](../standard-library/tuple-functions.md#tie)|Erstellt eine `tuple` aus Elementverweisen.|

## <a name="see-also"></a>Siehe auch

[\<array>](../standard-library/array.md)<br/>
