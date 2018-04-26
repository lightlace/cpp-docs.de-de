---
title: is_trivially_constructible-Klasse | Microsoft-Dokumentation
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
- type_traits/std::is_trivially_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f564ae5970f56690f493e26cbefebbdc34cfec61
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallyconstructible-class"></a>Is_trivially_constructible-Klasse

Testet, ob ein Typ trivial konstruierbar ist, wenn die angegebenen Argumenttypen verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Parameter

`T` Der abzufragende Typ.

`Args` Die Argumenttypen entsprechend in einem Konstruktor, der `T`.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` durch die Verwendung der Argumenttypen von `Args` trivial konstruierbar ist; andernfalls ist sie FALSE. Typ `T` ist trivial konstruierbar, wenn die Variablendefinition `T t(std::declval<Args>()...);` wohlgeformt ist, und keine nicht trivialen Operationen aufruft. Sowohl `T` als auch alle Typen in `Args` müssen vollständige Typen `void` sein oder Arrays mit unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
