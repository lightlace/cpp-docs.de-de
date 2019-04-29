---
title: allocator_newdel-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- stdext::allocators::allocator_newdel
helpviewer_keywords:
- stdext::allocators [C++], allocator_newdel
- stdext::allocator_newdel
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
ms.openlocfilehash: eac2fb993eb3e9aab5d043debe6402576d7b49b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411018"
---
# <a name="allocatornewdel-class"></a>allocator_newdel-Klasse

Implementiert einen Allocator, der verwendet **Delete-Operator** um einen Speicherblock freizugeben Block und **new-Operator** auf einen Speicherblock zuzuweisen.

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class allocator_newdel;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Type*|Der Elementtyp, die durch die Zuweisung zugeordnet wird.|

## <a name="remarks"></a>Hinweise

Die [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) Makro übergibt diese Klasse als die *Namen* Parameter in der folgenden Anweisung: `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)<br/>
