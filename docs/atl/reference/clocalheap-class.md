---
title: Clocalheap-Klasse
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
ms.openlocfilehash: a302ba4ea55c42ce214c8de4a24be843d6cb1b9f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496750"
---
# <a name="clocalheap-class"></a>Clocalheap-Klasse

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Funktionen für den lokalen Heap.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CLocalHeap : public IAtlMemMgr
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CLocalHeap::Allocate](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|
|[CLocalHeap::Free](#free)|Mit dieser Methode wird ein Speicherblock freigegeben, der von diesem Speicher-Manager zugeordnet wird.|
|[CLocalHeap::GetSize](#getsize)|Mit dieser Methode können Sie die zugeordnete Größe eines Speicherblocks abrufen, der von diesem Speicher-Manager zugeordnet wird.|
|[CLocalHeap::Reallocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|

## <a name="remarks"></a>Hinweise

`CLocalHeap`implementiert Speicher Belegungs Funktionen mit den lokalen Win32-Heap Funktionen.

> [!NOTE]
>  Die lokalen Heap Funktionen sind langsamer als andere Speicherverwaltungsfunktionen und bieten nicht so viele Features. Daher sollten neue Anwendungen die [Heap Funktionen](/windows/win32/Memory/heap-functions)verwenden. Diese sind in der [CWin32Heap](../../atl/reference/cwin32heap-class.md) -Klasse verfügbar.

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IAtlMemMgr`

`CLocalHeap`

## <a name="requirements"></a>Anforderungen

**Header:** atlmem. h

##  <a name="allocate"></a>Clocalheap:: zuordnen

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

Geben Sie [clocalheap:: Free](#free) oder [clocalheap:: rezuordnen](#reallocate) ein, um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Wird mithilfe von [localzuc](/windows/win32/api/winbase/nf-winbase-localalloc) mit dem Flag-Parameter LMEM_FIXED implementiert.

##  <a name="free"></a>Clocalheap:: Free

Mit dieser Methode wird ein Speicherblock freigegeben, der von diesem Speicher-Manager zugeordnet wird.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert und bewirkt nichts.

### <a name="remarks"></a>Hinweise

Implementiert mithilfe von [LocalFree](/windows/win32/api/winbase/nf-winbase-localfree).

##  <a name="getsize"></a>Clocalheap:: GetSize

Mit dieser Methode können Sie die zugeordnete Größe eines Speicherblocks abrufen, der von diesem Speicher-Manager zugeordnet wird.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.

### <a name="return-value"></a>Rückgabewert

Gibt die Größe des belegten Speicherblocks in Bytes zurück.

### <a name="remarks"></a>Hinweise

Wird mithilfe von [localsize](/windows/win32/api/winbase/nf-winbase-localsize)implementiert.

##  <a name="reallocate"></a>Clocalheap:: neu zuordnen

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

Ruft [clocalheap:: Free](#free) auf, um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Implementiert mithilfe von [localrezuweisungen](/windows/win32/api/winbase/nf-winbase-localrealloc).

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[CComHeap-Klasse](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)<br/>
[CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)<br/>
[CComHeap-Klasse](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)
