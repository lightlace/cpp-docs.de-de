---
title: is_nothrow_copy_assignable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e540d6fe4c00772af01b187d24efae18fd62357f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957557"
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable-Klasse

Testet, ob der Typ einen Kopierzuweisungsoperator aufweist, von dem der Compiler weiß, dass er nicht auslöst.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Parameter

*T* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats enthält "true" für einen referenzierbare *T* , in denen `is_nothrow_assignable<T&, const T&>` enthält true ist; andernfalls ist Sie false.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_nothrow_assignable-Klasse](../standard-library/is-nothrow-assignable-class.md)<br/>
