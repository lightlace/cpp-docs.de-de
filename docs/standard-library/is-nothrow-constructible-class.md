---
title: Is_nothrow_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_constructible
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
ms.openlocfilehash: 9ea11d54d49bf8f6ae6416f9663c2593cc66ea3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383606"
---
# <a name="isnothrowconstructible-class"></a>Is_nothrow_constructible-Klasse

Testet, ob ein Typ konstruierbar ist, und nicht ausgelöst wird, wenn angegebene Argumenttypen verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

*Args*<br/>
Die Argumenttypen in einem Konstruktor, der entsprechend *T*.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* konstruiert werden kann, ist die Verwendung der Argumenttypen *Args*, und der Konstruktor ist der Compiler löst bekannt; andernfalls ist Sie false. Typ *T* konstruierbar ist; wenn die Variablendefinition `T t(std::declval<Args>()...);` wohlgeformt ist. Beide *T* und alle Typen in *Args* müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
