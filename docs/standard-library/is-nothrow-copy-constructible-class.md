---
title: is_nothrow_copy_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_constructible
helpviewer_keywords:
- is_nothrow_copy_constructible
ms.assetid: f13a0bea-63b1-492a-9a45-d445df35c282
ms.openlocfilehash: 7682ce8fd8f127ac20a20fb0918e69d8c2d76947
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413670"
---
# <a name="isnothrowcopyconstructible-class"></a>is_nothrow_copy_constructible-Klasse

Testet, ob der Typ einen **nothrow**-Kopierkonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_nothrow_copy_constructible;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* verfügt über einen Nothrow Kopierkonstruktor, andernfalls er false enthält.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
