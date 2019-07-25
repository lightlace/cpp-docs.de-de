---
title: is_trivially_move_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_constructible
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
ms.openlocfilehash: 279da956eaff21c39c6e5ca563f26989105f7e74
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448359"
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible-Klasse

Testet, ob der Typ einen trivialen Bewegungskonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn die *typität* eine Klasse ist, die einen trivialen bewegungskonstruktor aufweist; andernfalls false.

Ein bewegungskonstruktor für eine Klasse *Ty* ist in folgenden Fällen trivial:

Er wird implizit deklariert.

die Parametertypen entsprechen den einer impliziten Deklaration

die Klasse *Ty* hat keine virtuellen Funktionen.

die Klasse *Ty* hat keine virtuellen Basen.

die Klasse verfügt über keine flüchtigen nicht statischen Datenmember

alle direkten Basen der Klasse *Ty* verfügen über triviale bewegungskonstruktoren.

die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Bewegungskonstruktoren

die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Bewegungskonstruktoren

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
