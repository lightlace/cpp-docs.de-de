---
title: is_nothrow_default_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_default_constructible
helpviewer_keywords:
- is_nothrow_default_constructible
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
ms.openlocfilehash: d635c8a06d3acc45d214dbe7cb1eb7800f56dc86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148483"
---
# <a name="isnothrowdefaultconstructible-class"></a>is_nothrow_default_constructible-Klasse

Testet, ob der Typ einen nicht auslösenden Standardkonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_nothrow_default_constructible;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* Nothrow über einen Standardkonstruktor verfügt, andernfalls er false enthält. Eine Instanz des Typprädikats entspricht `is_nothrow_constructible<Ty>`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
