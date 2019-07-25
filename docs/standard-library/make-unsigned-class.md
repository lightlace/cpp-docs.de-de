---
title: make_unsigned-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 4c0224bd5fd7dc8c6589ae474bb9acb9a8f09cf6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456326"
---
# <a name="makeunsigned-class"></a>make_unsigned-Klasse

Macht den Typ oder den kleinsten Typ ohne Vorzeichen größer oder gleich dem Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*T*|Der zu ändernde Typ.|

## <a name="remarks"></a>Hinweise

Eine Instanz des typmodifizierers enthält einen geänderten Typ, der " *T* " `is_unsigned<T>` ist, wenn "true" ist. Andernfalls ist dies der kleinste Datentyp mit Vorzeichen `ST`, für den `sizeof (T) <= sizeof (ST)`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
