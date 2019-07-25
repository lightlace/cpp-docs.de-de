---
title: is_aggregate-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_aggregate
helpviewer_keywords:
- is_aggregate
ms.openlocfilehash: 89749e2b4c0e6aaf00de074718cfb598333bc739
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456694"
---
# <a name="isaggregate-class"></a>is_aggregate-Klasse

Testet, ob der Typ ein als `aggregate` markierter Klassentyp ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_aggregate;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ein als markierter `aggregate`Klassentyp ist; andernfalls false. Wenn *T* ein Klassentyp ist, muss es sich um einen kompletten Typ handeln.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
