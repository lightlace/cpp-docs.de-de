---
title: allocator_variable_size-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_variable_size
- allocators/stdext::allocators::allocator_variable_size
- stdext::allocators::allocator_variable_size
helpviewer_keywords:
- stdext::allocator_variable_size
- stdext::allocators [C++], allocator_variable_size
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
ms.openlocfilehash: bf243089ee8f4e26930e183b007a108e38f444e3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458154"
---
# <a name="allocatorvariablesize-class"></a>allocator_variable_size-Klasse

Beschreibt ein Objekt, das die Speicher Belegung und-Freigabe für Objekte des Typs *Type mithilfe eines* Caches vom Typ [cache_freelist](../standard-library/cache-freelist-class.md) mit einer von [Max_variable_size](../standard-library/max-variable-size-class.md)verwalteten Länge verwaltet.

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class allocator_variable_size;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Typ*|Der Elementtyp, die durch die Zuweisung zugeordnet wird.|

## <a name="remarks"></a>Hinweise

Das [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) -Makro übergibt diese Klasse als *Name* -Parameter in der folgenden Anweisung:`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)
