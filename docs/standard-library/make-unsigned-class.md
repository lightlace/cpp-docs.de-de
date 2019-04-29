---
title: make_unsigned-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 42c722c5250a4989b930d8f1e6fe52f2eccc614a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413046"
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

Eine Instanz des typmodifizierers enthält einen geänderten Typ, der *T* Wenn `is_unsigned<T>` gilt. Andernfalls ist dies der kleinste Datentyp mit Vorzeichen `ST`, für den `sizeof (T) <= sizeof (ST)`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
