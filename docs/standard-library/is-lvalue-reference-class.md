---
title: is_lvalue_reference-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_lvalue_reference
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
ms.openlocfilehash: 5bcd5c8333f011475cb11a452759c8986ab22215
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456206"
---
# <a name="islvaluereference-class"></a>is_lvalue_reference-Klasse

Testet, ob es sich beim Typ um einen lvalue-Verweis handelt.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz dieses typprädikats ist "true",  wenn die typität ein Verweis auf ein Objekt oder eine Funktion ist; andernfalls "false". Beachten Sie, dass *Ty* möglicherweise kein rvalue-Verweis ist. Weitere Informationen zu „rvalues“ finden Sie unter [Rvalue Reference Declarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md) (Rvalue-Verweisdeklarator: &&).

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)
