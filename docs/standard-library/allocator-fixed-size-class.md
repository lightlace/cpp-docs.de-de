---
title: allocator_fixed_size-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_fixed_size
- allocators/stdext::allocator_fixed_size
- stdext::allocators::allocator_fixed_size
helpviewer_keywords:
- stdext::allocators [C++], allocator_fixed_size
- stdext::allocator_fixed_size
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
ms.openlocfilehash: 5ee506838ea723b82f04bba301c19c0149d986bf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450999"
---
# <a name="allocatorfixedsize-class"></a>allocator_fixed_size-Klasse

Beschreibt ein Objekt, das die Speicher Belegung und-Freigabe für Objekte des Typs *Type mithilfe eines* Caches vom Typ [cache_freelist](../standard-library/cache-freelist-class.md) mit einer von [Max_fixed_size](../standard-library/max-fixed-size-class.md)verwalteten Länge verwaltet.

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class allocator_fixed_size;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Typ*|Der Elementtyp, die durch die Zuweisung zugeordnet wird.|

## <a name="remarks"></a>Hinweise

Das [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) -Makro übergibt diese Klasse als *Name* -Parameter in der folgenden Anweisung:`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)
