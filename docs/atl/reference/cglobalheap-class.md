---
title: Cglobalheap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CGlobalHeap
- ATLMEM/ATL::CGlobalHeap
- ATLMEM/ATL::CGlobalHeap::Allocate
- ATLMEM/ATL::CGlobalHeap::Free
- ATLMEM/ATL::CGlobalHeap::GetSize
- ATLMEM/ATL::CGlobalHeap::Reallocate
helpviewer_keywords:
- CGlobalHeap class
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
ms.openlocfilehash: 2b5aa09357ddcc77b6b10de58545bea86eff2488
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496763"
---
# <a name="cglobalheap-class"></a>Cglobalheap-Klasse

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der globalen Win32-Heap Funktionen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CGlobalHeap : public IAtlMemMgr
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CGlobalHeap::Allocate](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|
|[CGlobalHeap::Free](#free)|Mit dieser Methode wird ein Speicherblock freigegeben, der von diesem Speicher-Manager zugeordnet wird.|
|[CGlobalHeap::GetSize](#getsize)|Mit dieser Methode können Sie die zugeordnete Größe eines Speicherblocks abrufen, der von diesem Speicher-Manager zugeordnet wird.|
|[CGlobalHeap::Reallocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|

## <a name="remarks"></a>Hinweise

`CGlobalHeap`implementiert Speicher Belegungs Funktionen mithilfe der globalen Win32-Heap Funktionen.

> [!NOTE]
>  Die globalen Heap Funktionen sind langsamer als andere Speicherverwaltungsfunktionen und bieten nicht so viele Features. Daher sollten neue Anwendungen die [Heap Funktionen](/windows/win32/Memory/heap-functions)verwenden. Diese sind in der [CWin32Heap](../../atl/reference/cwin32heap-class.md) -Klasse verfügbar. Globale Funktionen werden von DDE und den Zwischenablage Funktionen weiterhin verwendet.

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IAtlMemMgr`

`CGlobalHeap`

## <a name="requirements"></a>Anforderungen

**Header:** atlmem. h

##  <a name="allocate"></a>Cglobalheap:: zuordnen

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

Verwenden Sie [cglobalheap:: Free](#free) oder [cglobalheap:: rezuordnen](#reallocate) , um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Wird mithilfe von [globalzuordc](/windows/win32/api/winbase/nf-winbase-globalalloc) mit dem Flag-Parameter GMEM_FIXED implementiert.

##  <a name="free"></a>Cglobalheap:: Free

Mit dieser Methode wird ein Speicherblock freigegeben, der von diesem Speicher-Manager zugeordnet wird.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert und bewirkt nichts.

### <a name="remarks"></a>Hinweise

Implementiert mithilfe von [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree).

##  <a name="getsize"></a>Cglobalheap:: GetSize

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

Implementiert mithilfe von [globalsize](/windows/win32/api/winbase/nf-winbase-globalsize).

##  <a name="reallocate"></a>Cglobalheap:: neu zuordnen

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

Ruft [cglobalheap:: Free](#free) auf, um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Implementiert mithilfe von [globalrezuweisungen](/windows/win32/api/winbase/nf-winbase-globalrealloc).

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[CComHeap-Klasse](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap-Klasse](../../atl/reference/clocalheap-class.md)<br/>
[CComHeap-Klasse](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)
