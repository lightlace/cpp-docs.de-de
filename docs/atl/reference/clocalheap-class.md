---
title: CLocalHeap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
ms.openlocfilehash: 53288bea8a50f62437eab4dd81d5d816abf78f44
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283084"
---
# <a name="clocalheap-class"></a>CLocalHeap-Klasse

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Funktionen lokalen Heap befindet.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CLocalHeap : public IAtlMemMgr
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CLocalHeap::Allocate](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|
|[CLocalHeap::Free](#free)|Rufen Sie diese Methode, um einen Block von diesem Speicher-Manager zugeordneten Arbeitsspeicher freizugeben.|
|[CLocalHeap::GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von diesem Speicher-Manager zugeordnet.|
|[CLocalHeap::Reallocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|

## <a name="remarks"></a>Hinweise

`CLocalHeap` implementiert die genutzten speicherzuweisungsfunktionen mithilfe der Win32-Funktionen lokalen Heap befindet.

> [!NOTE]
>  Der lokale Heapfunktionen sind langsamer als die anderen Speicherverwaltungsfunktionen und bieten keine so viele Features. Neue Anwendungen sollten daher verwenden die [Heapfunktionen](/windows/desktop/Memory/heap-functions). Diese stehen in der [CWin32Heap](../../atl/reference/cwin32heap-class.md) Klasse.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IAtlMemMgr`

`CLocalHeap`

## <a name="requirements"></a>Anforderungen

**Header:** atlmem.h

##  <a name="allocate"></a>  Clocalheap:: Allocate

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

Rufen Sie [clocalheap:: Free](#free) oder [clocalheap:: ReAllocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Mithilfe von implementiert [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc) mit einem Flag-Parameter von LMEM_FIXED.

##  <a name="free"></a>  Clocalheap:: Free

Rufen Sie diese Methode, um einen Block von diesem Speicher-Manager zugeordneten Arbeitsspeicher freizugeben.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert und hat keine Auswirkungen.

### <a name="remarks"></a>Hinweise

Mithilfe von implementiert [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree).

##  <a name="getsize"></a>  CLocalHeap::GetSize

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

Mithilfe von implementiert [LocalSize](/windows/desktop/api/winbase/nf-winbase-localsize).

##  <a name="reallocate"></a>  Clocalheap:: ReAllocate

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

Rufen Sie [clocalheap:: Free](#free) um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Mithilfe von implementiert [LocalReAlloc](/windows/desktop/api/winbase/nf-winbase-localrealloc).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[CComHeap-Klasse](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)<br/>
[CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)<br/>
[CComHeap-Klasse](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)
