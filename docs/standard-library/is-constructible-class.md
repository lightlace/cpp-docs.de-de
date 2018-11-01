---
title: is_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_constructible
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
ms.openlocfilehash: c921efd5b7e12873ce986952029ae39f118ad763
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658652"
---
# <a name="isconstructible-class"></a>is_constructible-Klasse

Testet, ob ein Typ konstruierbar ist, wenn die angegebenen Argumenttypen verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

*Args*<br/>
Die Argumenttypen in einem Konstruktor, der entsprechend *T*.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* konstruiert werden kann, ist die Verwendung der Argumenttypen *Args*, andernfalls ist Sie false. Typ *T* konstruierbar ist; wenn die Variablendefinition `T t(std::declval<Args>()...);` wohlgeformt ist. Beide *T* und alle Typen in *Args* müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
