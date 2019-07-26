---
title: is_trivially_default_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_default_constructible
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
ms.openlocfilehash: 19a5e8afedf3e59d5dafa937af4f7d35343eb7d9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459651"
---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible-Klasse

Testet, ob der Typ einen trivialen Standardkonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true",  wenn die typty eine Klasse ist, die einen trivialen Konstruktor aufweist; andernfalls "false".

Ein Standardkonstruktor für eine Klasse *Ty* ist in folgenden Fällen trivial:

- es ist eine implizit deklarierte Standardkonstruktor

- die Klasse *Ty* hat keine virtuellen Funktionen.

- die Klasse *Ty* hat keine virtuellen Basen.

- alle direkten Basen der Klasse *Ty* haben triviale Konstruktoren.

- die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Konstruktoren

- die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Konstruktoren

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
