---
title: '&lt;optional&gt;'
ms.date: 11/04/2016
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: 83a0ad52735f92d731dafb32ad1be5a8278776b4
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447184"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Definiert die Container Vorlagen Klasse optional und einige unterstützende Vorlagen.

## <a name="requirements"></a>Anforderungen

**Header:** \<optionale >

**Namespace:** std

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|Testet, ob das `optional`-Objekt links vom Operator gleich dem `optional`-Objekt rechts vom Operator ist.|
|[Operator!=](../standard-library/optional-operators.md#op_neq)|Testet, ob das `optional`-Objekt links vom Operator ungleich dem `optional`-Objekt rechts vom Operator ist.|
|[operator<](../standard-library/optional-operators.md#op_lt)|Testet, ob das `optional`-Objekt links vom Operator kleiner als das `optional`-Objekt auf der rechten Seite ist.|
|[operator<=](../standard-library/optional-operators.md#op_lt_eq)|Testet, ob das `optional`-Objekt links vom Operator kleiner oder gleich dem `optional`-Objekt auf der rechten Seite ist.|
|[operator>](../standard-library/optional-operators.md#op_gt)|Testet, ob das `optional`-Objekt links vom Operator größer als das `optional`-Objekt auf der rechten Seite ist.|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|Testet, ob das `optional`-Objekt links vom Operator größer oder gleich dem `optional`-Objekt auf der rechten Seite ist.|

> [!NOTE]
> Neben relationalen vergleichen \<unterstützen optionale >-Operatoren auch Vergleiche mit **nullopt** und. `T`

### <a name="functions"></a>Funktionen

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Macht ein-Objekt optional.|
|[swap](../standard-library/optional-functions.md#swap)||

### <a name="classes-and-structs"></a>Klassen und Strukturen

|||
|-|-|
|[hash]()||
|[optionale Klasse](../standard-library/optional-class.md)|Beschreibt ein Objekt, das einen Wert enthalten kann.|
|[nullopt_t-Struktur](../standard-library/nullopt-t-structure.md)|Beschreibt ein Objekt, das keinen Wert enthält.|
|[bad_optional_access-Klasse](../standard-library/bad-optional-access-class.md)|Beschreibt ein Objekt, das als Ausnahme ausgelöst wurde, um einen Versuch, auf einen Wert zuzugreifen, zu melden.|

### <a name="objects"></a>erzwingen

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)||

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
