---
title: treat_as_floating_point-Struktur
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: 4cf3ac5be972d8636f1d3dbda3b195f4012517be
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459886"
---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point-Struktur

Gibt an, ob `Rep` als Gleitkommatyp behandelt werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>Hinweise

`Rep` kann nur als Gleitkommatyp behandelt werden, wenn die Spezialisierung `treat_as_floating_point<Rep>` von [true_type](../standard-library/type-traits-typedefs.md#true_type) abgeleitet wird. Die Vorlagenklasse kann für einen benutzerdefinierten Typ abgeleitet werden.

## <a name="requirements"></a>Anforderungen

**Header:** \<chrono>

**Namespace:** std::chrono

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
