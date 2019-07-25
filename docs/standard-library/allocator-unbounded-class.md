---
title: allocator_unbounded-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
ms.openlocfilehash: 38ecec3848808585ac0ed7cb1b076480a79f6d41
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448303"
---
# <a name="allocatorunbounded-class"></a>allocator_unbounded-Klasse

Beschreibt ein Objekt, das die Speicher Belegung und-Freigabe für Objekte des Typs *Type mithilfe eines* Caches vom Typ [cache_freelist](../standard-library/cache-freelist-class.md) mit einer von [Max_unbounded](../standard-library/max-unbounded-class.md)verwalteten Länge verwaltet.

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class allocator_unbounded;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Typ*|Der Elementtyp, die durch die Zuweisung zugeordnet wird.|

## <a name="remarks"></a>Hinweise

Das [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) -Makro übergibt diese Klasse als *Name* -Parameter in der folgenden Anweisung:`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)
