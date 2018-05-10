---
title: '&lt;tuple&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <tuple>
dev_langs:
- C++
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ba25328b86a51e34cba60bd55b63ce2eab696d6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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
|[operator!=](../standard-library/tuple-operators.md#op_neq)|Vergleich von `tuple`-Objekten, ungleich|
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
