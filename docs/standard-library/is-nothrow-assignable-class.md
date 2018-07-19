---
title: is_nothrow_assignable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 424fcf5b960182326dc1192d8d60f168ead59d98
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965414"
---
# <a name="isnothrowassignable-class"></a>Is_nothrow_assignable-Klasse

Testet, ob der Wert *aus* Typ zugewiesen werden kann, um *zu* Typ und die Zuweisung ist bekanntermaßen nicht auslösen.

## <a name="syntax"></a>Syntax

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>Parameter

*Um* den Typ des Objekts, das die Zuweisung empfängt.

*Von* den Typ des Objekts, das den Wert bereitstellt.

## <a name="remarks"></a>Hinweise

Der Ausdruck `declval<To>() = declval<From>()` muss wohlgeformt sein und der Compiler muss wissen, dass er nicht auslöst. Beide *aus* und *zu* müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
