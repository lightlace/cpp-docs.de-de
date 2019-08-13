---
title: '&lt;optional&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: f3b4896a3cb4774e46b36480dd9769fa131fc287
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957179"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Definiert die Containervorlagenklasse `optional` und einige unterstützende Vorlagen.

## <a name="requirements"></a>Anforderungen

**Header:** \<optionale >

**Namespace:** std

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|Testet, ob ein Objekt gleich einem anderen Objekt ist.|
|[Operator!=](../standard-library/optional-operators.md#op_neq)|Testet, ob ein Objekt ungleich einem anderen Objekt ist.|
|[operator<](../standard-library/optional-operators.md#op_lt)|Testet, ob das Objekt auf der linken Seite kleiner ist als das Objekt auf der rechten Seite.|
|[operator<=](../standard-library/optional-operators.md#op_lt_eq)|Testet, ob das-Objekt Links kleiner als oder gleich dem-Objekt auf der rechten Seite ist.|
|[operator>](../standard-library/optional-operators.md#op_gt)|Testet, ob das-Objekt auf der linken Seite größer als das-Objekt auf der rechten Seite ist.|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|Testet, ob das-Objekt auf der linken Seite größer als oder gleich dem-Objekt auf der rechten Seite ist.|

> [!NOTE]
> Neben relationalen vergleichen \<unterstützen optionale >-Operatoren auch Vergleiche mit **nullopt** und. `T`

### <a name="functions"></a>Funktionen

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Macht ein-Objekt optional.|
|[swap](../standard-library/optional-functions.md#swap)|Vertauscht die enthaltenen Werte von `optional` zwei-Objekten.|

### <a name="classes-and-structs"></a>Klassen und Strukturen

|||
|-|-|
|Hashindizes|Gibt einen Hash des enthaltenen-Objekts zurück.|
|[optionale Klasse](../standard-library/optional-class.md)|Beschreibt ein Objekt, das einen Wert enthalten kann.|
|[nullopt_t-Struktur](../standard-library/nullopt-t-structure.md)|Beschreibt ein Objekt, das keinen Wert enthält.|
|[bad_optional_access-Klasse](../standard-library/bad-optional-access-class.md)|Beschreibt ein Objekt, das als Ausnahme ausgelöst wurde, um einen Versuch, auf einen Wert zuzugreifen, zu melden.|

### <a name="objects"></a>erzwingen

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)|Eine Instanz von `nullopt_t` für Vergleiche.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
