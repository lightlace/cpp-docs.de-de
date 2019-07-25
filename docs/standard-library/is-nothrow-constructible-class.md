---
title: Is_nothrow_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_constructible
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
ms.openlocfilehash: 7ec4fc3ef5d9a799d5d77124870fbb337061c94c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455990"
---
# <a name="isnothrowconstructible-class"></a>Is_nothrow_constructible-Klasse

Testet, ob ein Typ konstruierbar ist, und nicht ausgelöst wird, wenn angegebene Argumenttypen verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der abzufragende Typ.

*Args*\
Die Argument Typen, die in einem Konstruktor von *T*abgeglichen werden sollen.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true", wenn der Typ *T* mit den Argument Typen in *args*konstruiert werden kann und der Konstruktor vom Compiler nicht ausgelöst werden kann. Andernfalls enthält Sie false. Der Typ *T* ist konstruierbar, wenn `T t(std::declval<Args>()...);` die Variablen Definition wohl geformt ist. Sowohl *T* als auch alle Typen in *args* müssen vollständige Typen, **void**oder Arrays mit unbekannter Grenze sein.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
