---
title: Is_nothrow_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_assignable
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
ms.openlocfilehash: 9ee8b5f97c92b6eb378db40f93696e5e6c554205
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456023"
---
# <a name="isnothrowassignable-class"></a>Is_nothrow_assignable-Klasse

Testet *,* ob ein Wert *vom* Typ dem Typ zugewiesen werden kann und die Zuweisung bekanntermaßen nicht ausgelöst wird.

## <a name="syntax"></a>Syntax

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>Parameter

*An*\
Der Typ des Objekts, das die Zuweisung empfängt.

*Von*\
Der Typ des Objekts, das den Wert bereitstellt.

## <a name="remarks"></a>Hinweise

Der Ausdruck `declval<To>() = declval<From>()` muss wohlgeformt sein und der Compiler muss wissen, dass er nicht auslöst. Sowohl *von* als auch *bis* müssen komplette Typen, **void**oder Arrays mit unbekannter Grenze sein.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
