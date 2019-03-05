---
title: CCRTAllocator-Klasse
ms.date: 11/04/2016
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
ms.openlocfilehash: c08d594e1c0f4d532f46961e266bf6ced98c51b2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287361"
---
# <a name="ccrtallocator-class"></a>CCRTAllocator-Klasse

Diese Klasse stellt Methoden zum Verwalten von Speicher mithilfe von CRT-Arbeitsspeicher-Routinen.

## <a name="syntax"></a>Syntax

```
class ATL::CCRTAllocator
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCRTAllocator::Allocate](#allocate)|(Statisch) Rufen Sie diese Methode, um Speicher zu belegen.|
|[CCRTAllocator::Free](#free)|(Statisch) Rufen Sie diese Methode, um Arbeitsspeicher freizugeben.|
|[CCRTAllocator::Reallocate](#reallocate)|(Statisch) Rufen Sie diese Methode, um Arbeitsspeicher neu zuzuordnen.|

## <a name="remarks"></a>Hinweise

Diese Klasse wird verwendet, indem [CHeapPtr](../../atl/reference/cheapptr-class.md) die CRT-Arbeitsspeicher speicherbelegungsroutinen bereitstellen kann. Die Klasse als Gegenstück [CComAllocator](../../atl/reference/ccomallocator-class.md), bietet die gleichen Methoden, die mit COM-Routinen.

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

##  <a name="allocate"></a>  Ccrtallocator:: Allocate

Rufen Sie diese statische Funktion auf, um Arbeitsspeicher zu belegen.

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*nBytes*<br/>
Die Anzahl der zu belegenden Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt einen void-Zeiger auf den belegten Speicherplatz oder NULL zurück, wenn nicht genügend Speicher verfügbar ist.

### <a name="remarks"></a>Hinweise

Belegt Arbeitsspeicher. Finden Sie unter [Malloc](../../c-runtime-library/reference/malloc.md) Weitere Details.

##  <a name="free"></a>  Ccrtallocator:: Free

Rufen Sie diese statischen Funktion um Arbeitsspeicher freizugeben.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Zeiger auf zugewiesenen Speicher.

### <a name="remarks"></a>Hinweise

Gibt den zugeordneten Arbeitsspeicher frei. Finden Sie unter [kostenlose](../../c-runtime-library/reference/free.md) Weitere Details.

##  <a name="reallocate"></a>  Ccrtallocator:: Allocate

Rufen Sie diese statischen Funktion auf, um Arbeitsspeicher neu zuzuordnen.

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Zeiger auf zugewiesenen Speicher.

*nBytes*<br/>
Die Anzahl der zuzuordnenden Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt einen void-Zeiger auf den zugeordneten Speicherplatz oder NULL zurück, wenn nicht genügend Speicher verfügbar ist.

### <a name="remarks"></a>Hinweise

Ändert die Größe des belegten Speichers. Finden Sie unter [Realloc](../../c-runtime-library/reference/realloc.md) Weitere Details.

## <a name="see-also"></a>Siehe auch

[CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)<br/>
[CComAllocator-Klasse](../../atl/reference/ccomallocator-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
