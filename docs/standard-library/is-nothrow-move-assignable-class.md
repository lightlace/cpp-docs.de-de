---
title: is_nothrow_move_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_assignable
helpviewer_keywords:
- is_nothrow_move_assignable
ms.assetid: 000baa02-cbba-49de-9870-af730033348e
ms.openlocfilehash: 8273be92a9c7e60e446b3c2b561a6020e70fb2f2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455897"
---
# <a name="isnothrowmoveassignable-class"></a>is_nothrow_move_assignable-Klasse

Testet, ob der Typ einen **nothrow**-Bewegungszuweisungsoperator aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true",  wenn die typty einen nothrow-Verschiebungs Zuweisungs Operator aufweist; andernfalls "false".

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
