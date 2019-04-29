---
title: is_move_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_assignable
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
ms.openlocfilehash: da4734507bac14ecf0278117deb7668518305be0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351065"
---
# <a name="ismoveassignable-class"></a>is_move_assignable-Klasse

Prüft, ob dem Typ eine Verschiebung zugewiesen werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Einem Typ kann eine Verschiebung zugewiesen werden, wenn ein rvalue-Verweis auf den Typ einem Verweis auf den Typ zugewiesen werden kann. Das Typprädikat entspricht `is_assignable<T&, T&&>`. Verschieben von zuweisbaren Typen beinhaltet verweisbare skalare Typen und Klassentypen, die entweder vom Compiler generierte oder benutzerdefinierte Bewegungszuweisungsoperatoren haben.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
