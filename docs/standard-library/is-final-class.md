---
title: is_final-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_final
helpviewer_keywords:
- is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
ms.openlocfilehash: f605b160f6ed71aaafcc7c391e17180e4b243444
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446538"
---
# <a name="isfinal-class"></a>is_final-Klasse

Testet, ob der Typ ein als `final` markierter Klassentyp ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_final;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist ein Klassentyp gekennzeichnet `final`, andernfalls ist Sie false. Wenn *T* ist ein Klassentyp, es muss ein vollständiger Typ sein.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[final-Bezeichner](../cpp/final-specifier.md)<br/>
