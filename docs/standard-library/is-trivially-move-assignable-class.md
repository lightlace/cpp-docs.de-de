---
title: is_trivially_move_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_assignable
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
ms.openlocfilehash: b25d16658def4e3cf620ab707d2dabacb2620f33
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435538"
---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable-Klasse

Testet, ob der Typ einen trivialen Verschiebezuweisungsoperator aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist eine Klasse, die einen trivialen verschiebezuweisungsoperator, andernfalls er false enthält.

Ein bewegungszuweisungsoperator für eine Klasse *Ty* ist trivial wenn:

Er wird impliziert bereitgestellt

die Klasse *Ty* verfügt über keine virtuellen Funktionen

die Klasse *Ty* hat keine virtuellen Basen

Die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Verschiebungszuweisungsoperatoren

Die Klassen aller nicht statischen Datenmember des Typarrays der Klasse haben triviale Verschiebungszuweisungsoperatoren

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
