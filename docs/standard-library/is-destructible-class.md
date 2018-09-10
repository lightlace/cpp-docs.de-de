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
ms.openlocfilehash: bd23064123513281099fa14a690679fa046657fe
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106625"
---
# <a name="isdestructible-class"></a>is_destructible-Klasse

Testet, ob der Typ „destructible“ ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* "destructible" ist, andernfalls er false enthält. „destructible“-Typen sind Referenztypen, Objekttypen und Typen, bei denen für einige Typen `U` gleich `remove_all_extents_t<T>` der nicht ausgewertete Operand `std::declval<U&>.~U()` wohlgeformt ist. Andere Typen, z. B. unvollständige Typen **"void"**, und Funktionstypen, sind keine "destructible"-Typen.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
