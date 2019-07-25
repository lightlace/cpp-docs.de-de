---
title: make_signed-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_signed
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
ms.openlocfilehash: c3c35e28dec3270299329c0186273e324effc2bb
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453687"
---
# <a name="makesigned-class"></a>make_signed-Klasse

Macht den Typ oder den kleinsten Typ mit Vorzeichen größer oder gleich dem Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typmodifizierers enthält einen geänderten Typ, der " *T* " `is_signed<T>` ist, wenn "true" ist. Andernfalls ist der kleinste Datentyp mit Vorzeichen `UT`, für den `sizeof (T) <= sizeof (UT)`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
