---
title: Is_trivially_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: c83bea8be5c88876ffa25337464caa62b998ab45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413475"
---
# <a name="istriviallyconstructible-class"></a>Is_trivially_constructible-Klasse

Testet, ob ein Typ trivial konstruierbar ist, wenn die angegebenen Argumenttypen verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

*Args*<br/>
Die Argumenttypen in einem Konstruktor, der entsprechend *T*.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* Trivial konstruierbar ist mit den Argumenttypen in *Args*, andernfalls ist Sie false. Typ *T* Trivial konstruierbar ist; wenn die Variablendefinition `T t(std::declval<Args>()...);` wohlgeformt ist, und ist bekannt, dass keine nicht trivialen Operationen aufruft. Beide *T* und alle Typen in *Args* müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
