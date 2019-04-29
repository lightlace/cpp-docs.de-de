---
title: Is_nothrow_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_assignable
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
ms.openlocfilehash: c59c3623f9c9548a7b7e59d0c56a2acd4d3883a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383619"
---
# <a name="isnothrowassignable-class"></a>Is_nothrow_assignable-Klasse

Testet, ob der Wert *aus* Typ zugewiesen werden kann, um *zu* Typ und die Zuweisung ist bekanntermaßen nicht auslösen.

## <a name="syntax"></a>Syntax

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>Parameter

*Aktion*<br/>
Der Typ des Objekts, das die Zuweisung empfängt.

*From*<br/>
Der Typ des Objekts, das den Wert bereitstellt.

## <a name="remarks"></a>Hinweise

Der Ausdruck `declval<To>() = declval<From>()` muss wohlgeformt sein und der Compiler muss wissen, dass er nicht auslöst. Beide *aus* und *zu* müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
