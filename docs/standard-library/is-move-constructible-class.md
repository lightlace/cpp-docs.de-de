---
title: is_move_constructible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 979e726e1374ac37844472d9e2f9ae8ddd5ddf4d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965801"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible-Klasse

Testet, ob der Typ einen Bewegungskonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parameter

*T* der auszuwertende Typ.

## <a name="remarks"></a>Hinweise

Ein typprädikat, der auf "true" den Typ ergibt *T* mithilfe eines Verschiebevorgangs konstruiert werden kann. Dieses Prädikat entspricht `is_constructible<T, T&&>`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
