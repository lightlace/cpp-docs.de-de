---
title: is_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_assignable
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
ms.openlocfilehash: b1357bf8c5ad4dfd5035855e34a8fd6a7ed73d15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391009"
---
# <a name="isassignable-class"></a>is_assignable-Klasse

Testet, ob ein Wert des `From`-Typs einem `To`-Typ zugewiesen werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Parameter

*Aktion*<br/>
Der Typ des Objekts, das die Zuweisung empfängt.

*From*<br/>
Der Typ des Objekts, das den Wert bereitstellt.

## <a name="remarks"></a>Hinweise

Der ausgewertete Ausdruck `declval<To>() = declval<From>()` muss wohlgeformt sein. Beide `From` und `To` müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
