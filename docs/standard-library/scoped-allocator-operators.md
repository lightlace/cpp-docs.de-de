---
title: '&lt;scoped_allocator&gt;-Header'
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 7c9f2c3a2425bf3ac6e62ce7fcecfe9315c3e04e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512462"
---
# <a name="ltscopedallocatorgt-operators"></a>&lt;scoped_allocator&gt;-Header

|||
|-|-|
|[Operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Überprüft zwei `scoped_allocator_adaptor`-Objekte auf Ungleichheit.

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das linke `scoped_allocator_adaptor`-Objekt.

*right*<br/>
Das rechte `scoped_allocator_adaptor`-Objekt.

### <a name="return-value"></a>Rückgabewert

`!(left == right)`

## <a name="op_eq_eq"></a> operator==

Überprüft zwei `scoped_allocator_adaptor`-Objekte auf Gleichheit.

```cpp
template <class Outer, class... Inner>
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das linke `scoped_allocator_adaptor`-Objekt.

*right*<br/>
Das rechte `scoped_allocator_adaptor`-Objekt.

### <a name="return-value"></a>Rückgabewert

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>Siehe auch

[<scoped_allocator>](../standard-library/scoped-allocator.md)<br/>
