---
title: is_rvalue_reference-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_rvalue_reference
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
ms.openlocfilehash: 58cbf5709eda4f41d2edab7ddac1e0a04a9c74cf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455669"
---
# <a name="isrvaluereference-class"></a>is_rvalue_reference-Klasse

Testet, ob es sich beim Typ um einen „rvalue“-Verweis handelt.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_rvalue_reference;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz dieses typprädikats ist true, wenn die *typität* ein [rvalue-Verweis](../cpp/rvalue-reference-declarator-amp-amp.md)ist.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)
