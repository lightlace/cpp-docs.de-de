---
title: is_nothrow_copy_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
ms.openlocfilehash: bb3aca47b61bdcc5b28eeedc1a6b4edefc303c4e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383593"
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable-Klasse

Testet, ob der Typ einen Kopierzuweisungsoperator aufweist, von dem der Compiler weiß, dass er nicht auslöst.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats enthält "true" für einen referenzierbare *T* , in denen `is_nothrow_assignable<T&, const T&>` enthält true ist; andernfalls ist Sie false.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_nothrow_assignable-Klasse](../standard-library/is-nothrow-assignable-class.md)<br/>
