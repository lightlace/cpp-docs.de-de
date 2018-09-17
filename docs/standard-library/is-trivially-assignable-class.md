---
title: is_trivially_assignable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd0a8bbffd3a6e0f03635b659dd3743e12c9f077
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700764"
---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable-Klasse

Testet, ob ein Wert des `From`-Typs einem `To`-Typ trivial zugewiesen werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>Parameter

*Aktion*<br/>
Der Typ des Objekts, das die Zuweisung empfängt.

*From*<br/>
Der Typ des Objekts, das den Wert bereitstellt.

## <a name="remarks"></a>Hinweise

Der Ausdruck `declval<To>() = declval<From>()` muss wohlgeformt sein, und es muss für den Compiler bekannt sein, dass er keine nicht trivialen Vorgänge benötigt. Beide `From` und `To` müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
