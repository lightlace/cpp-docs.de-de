---
title: is_nothrow_copy_assignable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47cfa4d49dce7f7503c9e707d3a2f8787b4f53a3
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable-Klasse

Testet, ob der Typ einen Kopierzuweisungsoperator aufweist, von dem der Compiler weiß, dass er nicht auslöst.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Parameter

`T` Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist für einen verweisbaren Typ `T` da TRUE, wo `is_nothrow_assignable<T&, const T&>` TRUE ist; andernfalls ist sie FALSE.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_nothrow_assignable-Klasse](../standard-library/is-nothrow-assignable-class.md)<br/>
