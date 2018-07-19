---
title: allocator_fixed_size-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocators::allocator_fixed_size
- allocators/stdext::allocator_fixed_size
- stdext::allocators::allocator_fixed_size
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocators [C++], allocator_fixed_size
- stdext::allocator_fixed_size
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94207895eb88e0d799289e2c730f99668ca32cef
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963195"
---
# <a name="allocatorfixedsize-class"></a>allocator_fixed_size-Klasse

Beschreibt ein Objekt, das speicherbelegung und-Freigabe für Objekte des Typs verwaltet *Typ* mithilfe eines Caches vom Typ [Cache_freelist](../standard-library/cache-freelist-class.md) mit einer Länge von verwalteten [Max_fixed_size](../standard-library/max-fixed-size-class.md).

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class allocator_fixed_size;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Type*|Der Elementtyp, die durch die Zuweisung zugeordnet wird.|

## <a name="remarks"></a>Hinweise

Die [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) Makro übergibt diese Klasse als die *Namen* Parameter in der folgenden Anweisung: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)<br/>
