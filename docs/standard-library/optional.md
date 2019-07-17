---
title: '&lt;optional&gt;'
ms.date: 11/04/2016
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: c73ad2ad94a5de29bc2c457fdf6ca8b9c783615c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268482"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Definiert die containervorlagenklasse optional und einige unterstützende Vorlagen.

## <a name="requirements"></a>Anforderungen

**Header:** \<optional >

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
> Neben relationalen vergleicht \<optional > Operatoren unterstützt auch den Vergleich mit **Nullopt** und `T`.

### <a name="functions"></a>Funktionen

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Ist ein Objekt optional.|
|[swap](../standard-library/optional-functions.md#swap)||

### <a name="classes-and-structs"></a>Klassen und Strukturen

|||
|-|-|
|[hash]()||
|[Optionale-Klasse](../standard-library/optional-class.md)|Beschreibt ein Objekt, die möglicherweise einen Wert möglicherweise nicht enthalten.|
|[Nullopt_t-Struktur](../standard-library/nullopt-t-structure.md)|Beschreibt ein Objekt, das nicht mit einem Wert.|
|[Bad_optional_access-Klasse](../standard-library/bad-optional-access-class.md)|Beschreibt ein Objekt, das als einen Zugriffsversuch auf einen Wert nicht vorhanden gemeldet Ausnahme ausgelöst.|

### <a name="objects"></a>erzwingen

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)||

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
