---
title: is_move_constructible-Klasse
ms.date: 10/24/2019
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 9585a932a34a24769201aaa379525a9b4c181e41
ms.sourcegitcommit: 33a898bf976c65f998b4e88a84765a0cef4193a8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920093"
---
# <a name="is_move_constructible-class"></a>is_move_constructible-Klasse

Testet, ob der Typ mit einem Verschiebungs Vorgang erstellt werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parameter

*T* \
Der Typ, der ausgewertet werden soll.

## <a name="remarks"></a>Hinweise

Ein typprädikat, das zu **true** ausgewertet wird, wenn der Typ *T* mit einem Verschiebungs Vorgang erstellt werden kann. Dieses Prädikat entspricht `is_constructible<T, T&&>`. Ein Typ *T* , der keinen bewegungskonstruktor hat, aber einen Kopierkonstruktor hat, der ein `const T&` Argument akzeptiert, erfüllt `std::is_move_constructible`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
