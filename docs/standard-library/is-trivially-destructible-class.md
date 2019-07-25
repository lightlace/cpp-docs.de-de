---
title: is_trivially_destructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_destructible
helpviewer_keywords:
- is_trivially_destructible
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
ms.openlocfilehash: 6a978b7cc32e6de3d4b1d811b9aa6f52cf0370d7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459636"
---
# <a name="istriviallydestructible-class"></a>is_trivially_destructible-Klasse

Testet, ob der Typ trivial zerstörbar ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivially_destructible;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ein deerbarer Typ ist, und der Dekonstruktor dem Compiler bekannt ist, dass keine nicht trivialen Vorgänge verwendet werden. Andernfalls ist sie FALSE.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
