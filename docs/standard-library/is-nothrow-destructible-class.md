---
title: is_nothrow_destructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_destructible
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
ms.openlocfilehash: 44de1f1fae1ea542aa247c0b39f04ee6bbd6308a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455903"
---
# <a name="isnothrowdestructible-class"></a>is_nothrow_destructible-Klasse

Testet, ob der Typ zerstörbar ist, und ob der Compiler weiß, dass der Destruktor nicht ausgelöst wird.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ein deerbarer Typ ist, und der Dekonstruktor dem Compiler bekannt ist, dass er nicht ausgelöst werden soll. Andernfalls ist sie FALSE.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
