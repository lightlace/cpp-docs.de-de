---
title: is_trivially_constructible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f73559503ad427c9b7eb513d4164d3348c652948
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954746"
---
# <a name="istriviallyconstructible-class"></a>Is_trivially_constructible-Klasse

Testet, ob ein Typ trivial konstruierbar ist, wenn die angegebenen Argumenttypen verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Parameter

*T* der abzufragende Typ.

*Args* den Argumenttypen in einem Konstruktor, der entsprechend *T*.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* Trivial konstruierbar ist mit den Argumenttypen in *Args*, andernfalls ist Sie false. Typ *T* Trivial konstruierbar ist; wenn die Variablendefinition `T t(std::declval<Args>()...);` wohlgeformt ist, und ist bekannt, dass keine nicht trivialen Operationen aufruft. Beide *T* und alle Typen in *Args* müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
