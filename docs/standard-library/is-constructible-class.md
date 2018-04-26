---
title: is_constructible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b030d50861a207828b406bd683f02089070755be
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="isconstructible-class"></a>is_constructible-Klasse

Testet, ob ein Typ konstruierbar ist, wenn die angegebenen Argumenttypen verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>Parameter

`T` Der abzufragende Typ.

`Args` Die Argumenttypen entsprechend in einem Konstruktor, der `T`.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` durch die Verwendung der Argumenttypen von `Args` konstruierbar ist; andernfalls ist sie FALSE. Typ `T` ist konstruierbar, wenn die Variablendefinition `T t(std::declval<Args>()...);` wohlgeformt ist. Sowohl `T` als auch alle Typen in `Args` müssen vollständige Typen `void` sein oder Arrays mit unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
