---
title: is_nothrow_destructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_destructible
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
ms.openlocfilehash: 366b40af45c57d058d918c4c2f21d1b2ba486d35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217325"
---
# <a name="isnothrowdestructible-class"></a>is_nothrow_destructible-Klasse

Testet, ob der Typ zerstörbar ist, und ob der Compiler weiß, dass der Destruktor nicht ausgelöst wird.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* "destructible" ist, und des Destruktors wird an den Compiler keine Ausnahmefehler auslöst. Andernfalls ist sie FALSE.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
