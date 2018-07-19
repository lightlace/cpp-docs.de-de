---
title: is_null_pointer-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_null_pointer
dev_langs:
- C++
helpviewer_keywords:
- is_null_pointer
ms.assetid: f3b3601b-f162-4803-a6e9-dabf5c3876cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6de5d24c0763e731b3123778e74b22c20798b729
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966536"
---
# <a name="isnullpointer-class"></a>is_null_pointer-Klasse

Testet, ob der Typ std::nullptr_t ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_null_pointer;
```

### <a name="parameters"></a>Parameter

*T* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist `std::nullptr_t`, andernfalls ist Sie false.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
