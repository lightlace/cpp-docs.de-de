---
title: is_trivially_copy_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
ms.openlocfilehash: f8c4026da424e77b57555dd4c342c9ac7a386591
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447993"
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible-Klasse

Testet, ob der Typ einen trivialen Kopierkonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true", wenn der Typ " *T* " eine Klasse ist, die einen trivialen Kopierkonstruktor aufweist; andernfalls "false".

Ein Kopierkonstruktor für eine Klasse *t* ist trivial, wenn er implizit deklariert ist, die Klasse *t* keine virtuellen Funktionen oder virtuellen Basen hat, alle direkten Basen der Klasse *t* über triviale Kopierkonstruktoren, die Klassen aller nicht statischen Datenmember. vom Klassentyp verfügen über triviale Kopierkonstruktoren, und die Klassen aller nicht statischen Datenmember des Typarray der Klasse haben triviale Kopierkonstruktoren.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
