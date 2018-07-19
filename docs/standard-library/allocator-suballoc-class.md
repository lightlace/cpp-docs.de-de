---
title: allocator_suballoc-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocators::allocator_suballoc
- allocators/stdext::allocator_suballoc
dev_langs:
- C++
helpviewer_keywords:
- allocator_suballoc class
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6238aeada530a8fc33fc98b79cba969353796ae
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953087"
---
# <a name="allocatorsuballoc-class"></a>allocator_suballoc-Klasse

Beschreibt ein Objekt, das speicherbelegung und-Freigabe für Objekte des Typs verwaltet *Typ* mithilfe eines Caches vom Typ [Cache_suballoc](../standard-library/cache-suballoc-class.md).

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class allocator_suballoc;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Type*|Der Elementtyp, die durch die Zuweisung zugeordnet wird.|

## <a name="remarks"></a>Hinweise

Die [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) Makro übergibt diese Klasse als die *Namen* Parameter in der folgenden Anweisung: `ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)<br/>
