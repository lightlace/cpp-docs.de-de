---
title: is_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_constructible
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
ms.openlocfilehash: dc0596ac7a3fc2bcbcbe49f5fa4b20a971e5e445
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452863"
---
# <a name="isconstructible-class"></a>is_constructible-Klasse

Testet, ob ein Typ konstruierbar ist, wenn die angegebenen Argumenttypen verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der abzufragende Typ.

*Args*\
Die Argument Typen, die in einem Konstruktor von *T*abgeglichen werden sollen.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* mit den Argument Typen in *args*konstruiert werden kann; andernfalls false. Der Typ *T* ist konstruierbar, wenn `T t(std::declval<Args>()...);` die Variablen Definition wohl geformt ist. Sowohl *T* als auch alle Typen in *args* müssen vollständige Typen, **void**oder Arrays mit unbekannter Grenze sein.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
