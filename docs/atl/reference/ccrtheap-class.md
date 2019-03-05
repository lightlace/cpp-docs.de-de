---
title: Ccomheap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
ms.openlocfilehash: 3c5030b9cfbfd636a783d27bcc8f9469f8348acb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276272"
---
# <a name="ccrtheap-class"></a>Ccomheap-Klasse

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Funktionen der CRT-Heap.

## <a name="syntax"></a>Syntax

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCRTHeap::Allocate](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|
|[CCRTHeap::Free](#free)|Rufen Sie diese Methode, um einen Block von diesem Speicher-Manager zugeordneten Arbeitsspeicher freizugeben.|
|[CCRTHeap::GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von diesem Speicher-Manager zugeordnet.|
|[CCRTHeap::Reallocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|

## <a name="remarks"></a>Hinweise

`CCRTHeap` Memory heap Zuordnungsfunktionen, die Verwendung der CRT-Funktionen, einschließlich implementiert [Malloc](../../c-runtime-library/reference/malloc.md), [kostenlose](../../c-runtime-library/reference/free.md), [Realloc](../../c-runtime-library/reference/realloc.md), und [_msize](../../c-runtime-library/reference/msize.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>Anforderungen

**Header:** atlmem.h

##  <a name="allocate"></a>  Ccrtheap:: Allocate

Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*nBytes*<br/>
Die angeforderte Anzahl von Bytes im neuen Speicherblock.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.

### <a name="remarks"></a>Hinweise

Rufen Sie [ccrtheap:: Free](#free) oder [ccrtheap:: ReAllocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Mithilfe von implementiert [Malloc](../../c-runtime-library/reference/malloc.md).

##  <a name="free"></a>  Ccrtheap:: Free

Rufen Sie diese Methode, um einen Block von diesem Speicher-Manager zugeordneten Arbeitsspeicher freizugeben.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert und hat keine Auswirkungen.

### <a name="remarks"></a>Hinweise

Mithilfe von implementiert [kostenlose](../../c-runtime-library/reference/free.md).

##  <a name="getsize"></a>  CCRTHeap::GetSize

Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von diesem Speicher-Manager zugeordnet.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.

### <a name="return-value"></a>Rückgabewert

Gibt die Größe des belegten Speicherblocks in Bytes zurück.

### <a name="remarks"></a>Hinweise

Mithilfe von implementiert [_msize](../../c-runtime-library/reference/msize.md).

##  <a name="reallocate"></a>  Ccrtheap:: ReAllocate

Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.

*nBytes*<br/>
Die angeforderte Anzahl von Bytes im neuen Speicherblock.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.

### <a name="remarks"></a>Hinweise

Rufen Sie [ccrtheap:: Free](#free) um den von dieser Methode belegten Arbeitsspeicher freizugeben. Mithilfe von implementiert [Realloc](../../c-runtime-library/reference/realloc.md).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[CComHeap-Klasse](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap-Klasse](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)<br/>
[IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)
