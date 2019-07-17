---
title: '&lt;Variante&gt; Operatoren'
ms.date: 04/04/2019
f1_keywords:
- variant/std::operator!=
- variant/std::operator==
- variant/std::operatoroperator&gt;
- variant/std::operatoroperator&gt=;
- variant/std::operatoroperator&lt;
- variant/std::operatoroperator&lt;=
helpviewer_keywords:
- std::operator!= (variant)
- std::operator== (variant)
- std::operatoroperator&gt; (variant)
- std::operatoroperator&gt=; (variant)
- std::operatoroperator&lt; (variant)
- std::operatoroperator&lt;= (variant)
ms.openlocfilehash: 0c4042ca1d89f9835b32924b268ef17a56619009
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268562"
---
# <a name="ltvariantgt-operators"></a>&lt;Variante&gt; Operatoren

## <a name="op_eq_eq"></a> Operator ==

Testet, ob das Listenobjekt links vom Operator gleich dem Listenobjekt rechts vom Operator ist

```cpp
template <class... Types>
    constexpr bool operator==(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_neq"></a> Operator! =

Testet, ob das Listenobjekt links vom Operator ungleich dem Listenobjekt rechts vom Operator ist

```cpp
template <class... Types>
    constexpr bool operator!=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_lt"></a>-Operator&lt;

Testet, ob das Listenobjekt links vom Operator kleiner als das Listenobjekt auf der rechten Seite ist

```cpp
template <class... Types>
    constexpr bool operator<(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_lt_eq"></a> Operator&lt;=

Testet, ob das Listenobjekt links vom Operator kleiner als oder gleich dem Listenobjekt rechts vom Operator ist

```cpp
template <class... Types>
    constexpr bool operator<=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_gt"></a>-Operator&gt;

Testet, ob das Listenobjekt links vom Operator größer als das Listenobjekt auf der rechten Seite ist

```cpp
template <class... Types> constexpr
    bool operator>(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_gt_eq"></a> Operator&gt;=

Testet, ob das Listenobjekt links vom Operator größer als oder gleich dem Listenobjekt rechts vom Operator ist

```cpp
template <class... Types> constexpr
    bool operator>=(const variant<Types...>&, const variant<Types...>&);
```
