---
title: is_nothrow_copy_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
ms.openlocfilehash: 330c97cd945e161d2bf47deb377dd732bf53b3c9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455976"
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable-Klasse

Testet, ob der Typ einen Kopierzuweisungsoperator aufweist, von dem der Compiler weiß, dass er nicht auslöst.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true für einen referenzierbaren  Typ T `is_nothrow_assignable<T&, const T&>` , wobei true ist; andernfalls false.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[Is_nothrow_assignable-Klasse](../standard-library/is-nothrow-assignable-class.md)
