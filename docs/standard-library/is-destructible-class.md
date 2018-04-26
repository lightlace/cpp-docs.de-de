---
title: is_destructible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 887946156084d962debf569fc4f23f45dea18293
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="isdestructible-class"></a>is_destructible-Klasse

Testet, ob der Typ „destructible“ ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>Parameter

`T` Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist „true“, wenn der Typ `T` vom Typ „destructible“ ist; andernfalls „false“. „destructible“-Typen sind Referenztypen, Objekttypen und Typen, bei denen für einige Typen `U` gleich `remove_all_extents_t<T>` der nicht ausgewertete Operand `std::declval<U&>.~U()` wohlgeformt ist. Andere Typen, z. B. unvollständige Typen, `void`und Funktionstypen, sind keine „destructible“-Typen.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
