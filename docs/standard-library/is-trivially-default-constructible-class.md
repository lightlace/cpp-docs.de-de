---
title: is_trivially_default_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_default_constructible
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
ms.openlocfilehash: b35458ca280285eb699c9b12b15b705660299ef2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413410"
---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible-Klasse

Testet, ob der Typ einen trivialen Standardkonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist eine Klasse, die einen trivialen Konstruktor aufweist; andernfalls ist Sie false.

Einen Standardkonstruktor für eine Klasse *Ty* ist trivial wenn:

- es ist eine implizit deklarierte Standardkonstruktor

- die Klasse *Ty* verfügt über keine virtuellen Funktionen

- die Klasse *Ty* hat keine virtuellen Basen

- alle direkten Basisklassen der Klasse *Ty* haben triviale Konstruktoren

- die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Konstruktoren

- die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Konstruktoren

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
