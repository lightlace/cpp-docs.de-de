---
title: is_nothrow_destructible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee35bd9fd138dce5e9163fe1712083f5671caaa1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964322"
---
# <a name="isnothrowdestructible-class"></a>is_nothrow_destructible-Klasse

Testet, ob der Typ zerstörbar ist, und ob der Compiler weiß, dass der Destruktor nicht ausgelöst wird.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>Parameter

*T* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* "destructible" ist, und des Destruktors wird an den Compiler keine Ausnahmefehler auslöst. Andernfalls ist sie FALSE.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
