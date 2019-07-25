---
title: is_nothrow_default_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_default_constructible
helpviewer_keywords:
- is_nothrow_default_constructible
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
ms.openlocfilehash: 76b58800a454f42f6b5b6fcea23df161c37564b2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455934"
---
# <a name="isnothrowdefaultconstructible-class"></a>is_nothrow_default_constructible-Klasse

Testet, ob der Typ einen nicht auslösenden Standardkonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_nothrow_default_constructible;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true",  wenn die typentität einen nothrow-Standardkonstruktor aufweist; andernfalls "false". Eine Instanz des Typprädikats entspricht `is_nothrow_constructible<Ty>`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
