---
title: is_null_pointer-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_null_pointer
helpviewer_keywords:
- is_null_pointer
ms.assetid: f3b3601b-f162-4803-a6e9-dabf5c3876cc
ms.openlocfilehash: b306753146a51bde842b55e4f36d3c1afa82591d
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455836"
---
# <a name="isnullpointer-class"></a>is_null_pointer-Klasse

Testet, ob der Typ std::nullptr_t ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_null_pointer;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true",  wenn der `std::nullptr_t`Typ "T" ist, andernfalls "false".

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
