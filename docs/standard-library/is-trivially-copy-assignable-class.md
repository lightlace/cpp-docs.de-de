---
title: is_trivially_copy_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
ms.openlocfilehash: 831e7c5afdd39980876a8e8284a68fec2084a4e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630983"
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable-Klasse

Testet, ob der Typ einen trivialen Kopierzuweisungsoperator aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist eine Klasse, die einen trivialen Kopierzuweisungsoperator, andernfalls er false enthält.

Ein Zuweisungskonstruktor für eine Klasse *T* ist trivial, wenn er implizit angegeben ist. die Klasse *T* verfügt über keine virtuellen Funktionen, die Klasse *T* hat keine virtuellen Basen, die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Zuweisungsoperatoren und die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Zuweisungsoperatoren.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
