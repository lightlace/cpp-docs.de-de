---
title: is_move_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: c83ed4365fd0e73a7daa8b9894c5e85f20387a79
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456114"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible-Klasse

Testet, ob der Typ einen Bewegungskonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der auszuwertende Typ.

## <a name="remarks"></a>Hinweise

Ein typprädikat, das zu true ausgewertet wird, wenn der Typ *T* mit einem Verschiebungs Vorgang erstellt werden kann. Dieses Prädikat entspricht `is_constructible<T, T&&>`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
