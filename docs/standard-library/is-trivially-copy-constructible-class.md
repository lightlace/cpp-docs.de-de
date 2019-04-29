---
title: is_trivially_copy_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
ms.openlocfilehash: aa6d6b19ae2bd5d6967c57db61c5697c0c6153e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413436"
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible-Klasse

Testet, ob der Typ einen trivialen Kopierkonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist eine Klasse, die einen trivialen Kopierkonstruktor, andernfalls er false enthält.

Ein Kopierkonstruktor für eine Klasse *T* ist trivial, wenn er implizit deklariert, die Klasse *T* verfügt über keine virtuellen Funktionen oder Basen und alle direkten Basen der Klasse *T* haben triviale Kopierkonstruktoren, die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Kopierkonstruktoren, und die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Kopierkonstruktoren.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
