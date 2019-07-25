---
title: is_nothrow_move_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
ms.openlocfilehash: 7f1ccdba11f62fcbeaf54162f80f0717feaa2fa1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455860"
---
# <a name="isnothrowmoveconstructible-class"></a>is_nothrow_move_constructible-Klasse

Testet, ob der Typ einen **nothrow**-Bewegungskonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_nothrow_move_constructible;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true",  wenn die typentität einen nothrow-bewegungskonstruktor aufweist; andernfalls "false".

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
