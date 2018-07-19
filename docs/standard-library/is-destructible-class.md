---
title: is_destructible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5b2c9237c7f17217d28e489edef4ab65863b54b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964111"
---
# <a name="isdestructible-class"></a>is_destructible-Klasse

Testet, ob der Typ „destructible“ ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>Parameter

*T* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* "destructible" ist, andernfalls er false enthält. „destructible“-Typen sind Referenztypen, Objekttypen und Typen, bei denen für einige Typen `U` gleich `remove_all_extents_t<T>` der nicht ausgewertete Operand `std::declval<U&>.~U()` wohlgeformt ist. Andere Typen, z. B. unvollständige Typen **"void"**, und Funktionstypen, sind keine "destructible"-Typen.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
