---
title: '&lt;Variant&gt;'
ms.date: 04/04/2019
f1_keywords:
- <variant>
helpviewer_keywords:
- <variant>
ms.openlocfilehash: 7a812ccc3c8cb2a660c01ad2b17ea75b5d5c9542
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268442"
---
# <a name="ltvariantgt"></a>&lt;Variant&gt;

Variant-Objekts enthält, und verwaltet einen Wert. Wenn die Variante einen Wert, der Typ des Werts der Argumenttypen Vorlage übergeben, um Variant-Wert sein enthält. Diese Argumente werden als alternativen bezeichnet.

## <a name="requirements"></a>Anforderungen

**Header:** \<Variant-Wert >

**Namespace:** std

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator==](../standard-library/forward-list-operators.md#op_eq_eq)|Testet, ob der Variante-Objekt links vom Operator gleich der variant-Objekts auf der rechten Seite ist.|
|[Operator!=](../standard-library/forward-list-operators.md#op_neq)|Testet, ob der variant-Objekts auf der linken Seite des Operators ungleich dem variant-Objekts auf der rechten Seite ist.|
|[operator<](../standard-library/forward-list-operators.md#op_lt)|Testet, ob der Variante-Objekt links vom Operator kleiner als der variant-Objekts auf der rechten Seite ist.|
|[operator<=](../standard-library/forward-list-operators.md#op_lt_eq)|Testet, ob die Variante auf der linken Seite des Operators ist kleiner als oder gleich der variant-Objekts auf der rechten Seite.|
|[operator>](../standard-library/forward-list-operators.md#op_gt)|Testet, ob der Variante-Objekt links vom Operator größer als der variant-Objekts auf der rechten Seite ist.|
|[operator>=](../standard-library/forward-list-operators.md#op_lt_eq)|Testet, ob der Variante-Objekt links vom Operator größer als oder gleich der variant-Objekts auf der rechten Seite ist.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[get](../standard-library/variant-functions.md#get)|Ruft die Variante eines Objekts ab.|
|[get_if](../standard-library/variant-functions.md#get_if)|Ruft die Variante eines Objekts ab, falls vorhanden.|
|[holds_alternative](../standard-library/variant-functions.md#holds_alternative)|Zurückgeben **"true"** Wenn eine Variante vorhanden ist.|
|[swap](../standard-library/variant-functions.md#swap)|Tauscht eine **Variante**.|
|[Besuch](../standard-library/variant-functions.md#visit)|Wechselt zur nächsten **Variante**.|

### <a name="classes"></a>Klassen

|||
|-|-|
|[bad_variant_access](../standard-library/bad-variant-access-class.md)|Objekte, die zum Bericht ungültig Zugriffe auf den Wert eines variant-Objekts ausgelöst werden.|
|[Variant](../standard-library/variant.md)|Ein Objekt entweder enthalten einen Wert von mindestens einem der anderen Typen keinen Wert.|

### <a name="structs"></a>Strukturen

|||
|-|-|
|[hash](../standard-library/hash-structure.md)||
|[monostate](../standard-library/monostate-structure.md)|Ein alternativer Typ für eine Variante zu variant-Typ standardmäßig konstruiert werden kann.|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||
|[variant_alternative](../standard-library/variant-alternative-structure.md)|Unterstützt die Varianten-Objekten.|
|[variant_size](../standard-library/variant-size-structure.md)|Unterstützt die Varianten-Objekten.|

### <a name="objects"></a>erzwingen

|||
|-|-|
|[variant_npos](../standard-library/variant-functions.md#variant_npos)||

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
