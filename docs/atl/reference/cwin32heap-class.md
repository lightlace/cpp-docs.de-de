---
title: CWin32Heap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CWin32Heap
- ATLMEM/ATL::CWin32Heap
- ATLMEM/ATL::CWin32Heap::CWin32Heap
- ATLMEM/ATL::CWin32Heap::Allocate
- ATLMEM/ATL::CWin32Heap::Attach
- ATLMEM/ATL::CWin32Heap::Detach
- ATLMEM/ATL::CWin32Heap::Free
- ATLMEM/ATL::CWin32Heap::GetSize
- ATLMEM/ATL::CWin32Heap::Reallocate
- ATLMEM/ATL::CWin32Heap::m_bOwnHeap
- ATLMEM/ATL::CWin32Heap::m_hHeap
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
ms.openlocfilehash: ce3585310198ee3e2d7b2b8b829f4202b1021284
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496203"
---
# <a name="cwin32heap-class"></a>CWin32Heap-Klasse

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Heap Zuordnungs Funktionen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CWin32Heap : public IAtlMemMgr
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CWin32Heap:: CWin32Heap](#cwin32heap)|Der Konstruktor.|
|[CWin32Heap:: ~ CWin32Heap](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWin32Heap:: zuordnen](#allocate)|Führt eine Belegung eines Speicherblocks vom Heapobjekt durch.|
|[CWin32Heap:: Attach](#attach)|Fügt das Heap Objekt an einen vorhandenen Heap an.|
|[CWin32Heap::Detach](#detach)|Trennt das Heap Objekt von einem vorhandenen Heap.|
|[CWin32Heap:: Free](#free)|Gibt Arbeitsspeicher frei, der zuvor vom Heap belegt wurde.|
|[CWin32Heap::GetSize](#getsize)|Gibt die Größe eines Speicherblocks zurück, der dem Heap Objekt zugewiesen ist.|
|[CWin32Heap::Reallocate](#reallocate)|Führt eine Neubelegung eines Speicherblocks vom Heapobjekt durch.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|Ein Flag, mit dem der aktuelle Besitz des Heap Handles bestimmt wird.|
|[CWin32Heap::m_hHeap](#m_hheap)|Handle für das Heap Objekt.|

## <a name="remarks"></a>Hinweise

`CWin32Heap`implementiert Speicher Belegungs Methoden mithilfe der Win32-Heap Zuordnungs Funktionen, einschließlich [HeapAlloc](/windows/win32/api/heapapi/nf-heapapi-heapalloc) und [HeapFree](/windows/win32/api/heapapi/nf-heapapi-heapfree). Im Gegensatz zu anderen Heap `CWin32Heap` Klassen erfordert ein gültiges Heap handle, das vor dem Zuordnen des Speichers bereitgestellt wird: bei den anderen Klassen wird standardmäßig der Prozess Heap verwendet. Das Handle kann dem Konstruktor oder der [CWin32Heap:: Attach](#attach) -Methode bereitgestellt werden. Weitere Informationen finden Sie unter der [CWin32Heap:: CWin32Heap](#cwin32heap) -Methode.

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>Anforderungen

**Header:** atlmem. h

##  <a name="allocate"></a>CWin32Heap:: zuordnen

Führt eine Belegung eines Speicherblocks vom Heapobjekt durch.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*nBytes*<br/>
Die angeforderte Anzahl von Bytes im neuen Speicherblock.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den neu belegten Speicherblock zurück.

### <a name="remarks"></a>Hinweise

Verwenden Sie [CWin32Heap:: Free](#free) oder [CWin32Heap:: rezuordnen](#reallocate) , um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Mit [Heapzuweisung](/windows/win32/api/heapapi/nf-heapapi-heapalloc)implementiert.

##  <a name="attach"></a>CWin32Heap:: Attach

Fügt das Heap Objekt an einen vorhandenen Heap an.

```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>Parameter

*hheap*<br/>
Ein vorhandenes Heap handle.

*bTakeOwnership*<br/>
Ein Flag, das angibt `CWin32Heap` , ob das Objekt den Besitz der Heap Ressourcen übernehmen soll.

### <a name="remarks"></a>Hinweise

Wenn *btakeownership* den Wert true hat `CWin32Heap` , ist das-Objekt für das Löschen des Heap Handles verantwortlich.

##  <a name="cwin32heap"></a>CWin32Heap:: CWin32Heap

Der Konstruktor.

```
CWin32Heap() throw();
CWin32Heap( HANDLE  hHeap) throw();
CWin32Heap(
    DWORD  dwFlags,
    size_t nInitialSize,
    size_t nMaxSize = 0);
```

### <a name="parameters"></a>Parameter

*hheap*<br/>
Ein vorhandenes Heapobjekt.

*dwFlags*<br/>
Bei der Erstellung des Heaps verwendete Flags.

*nInitialSize*<br/>
Die Anfangsgröße des Heaps.

*nmaxsize*<br/>
Die maximale Größe des Heaps.

### <a name="remarks"></a>Hinweise

Vor dem Zuordnen von Speicher muss das `CWin32Heap`-Objekt mit einem gültigen Heaphandle bereitgestellt werden. Das geht am einfachsten mit dem Prozessheap:

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

Es ist auch möglich, ein vorhandenes Heaphandle an den Konstruktor auszugeben; in diesem Fall übernimmt das neue Objekt nicht Besitz des Heaps. Wenn das `CWin32Heap`-Objekt gelöscht wird, ist das ursprüngliche Heaphandle weiterhin gültig.

Ein vorhandener Heap kann auch mit [CWin32Heap:: Attach](#attach)an das neue Objekt angefügt werden.

Wenn ein Heap erforderlich ist, in dem alle Operationen von einem einzigen Thread ausgeführt werden, empfiehlt es sich, das Objekt folgendermaßen zu erstellen:

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

Der HEAP_NO_SERIALIZE-Parameter gibt an, dass der gegenseitige Ausschluss nicht verwendet wird, wenn die Heap Funktionen Arbeitsspeicher zuordnen und freigeben, mit einer entsprechenden Leistungssteigerung.

Der dritte Parameter beträgt standardmäßig 0; dadurch kann das Heap nach Bedarf vergrößert werden. Eine Erläuterung der Speichergrößen und Flags finden Sie unter [HeapCreate](/windows/win32/api/heapapi/nf-heapapi-heapcreate) .

##  <a name="dtor"></a>CWin32Heap:: ~ CWin32Heap

Der Destruktor.

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>Hinweise

Zerstört das Heap handle, wenn `CWin32Heap` das Objekt den Besitz des Heaps besitzt.

##  <a name="detach"></a>CWin32Heap::D Etach

Trennt das Heap Objekt von einem vorhandenen Heap.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Handle für den Heap zurück, dem das Objekt zuvor angefügt wurde.

##  <a name="free"></a>CWin32Heap:: Free

Gibt Arbeitsspeicher frei, der zuvor aus dem Heap durch [CWin32Heap:: zuordnen](#allocate) oder [CWin32Heap:: Neuzuordnung](#reallocate)zugewiesen wurde.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Speicherblock, der freigegeben werden soll. NULL ist ein gültiger Wert und bewirkt nichts.

##  <a name="getsize"></a>CWin32Heap:: GetSize

Gibt die Größe eines Speicherblocks zurück, der dem Heap Objekt zugewiesen ist.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Zeiger auf den Speicherblock, dessen Größe die Methode erhält. Dies ist ein Zeiger, der von [CWin32Heap::](#allocate) alloor [CWin32Heap:: rezuordnen](#reallocate)zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

Gibt die Größe des belegten Speicherblocks in Bytes zurück.

##  <a name="m_bownheap"></a>CWin32Heap:: m_bOwnHeap

Ein Flag, mit dem der aktuelle Besitz des in [m_hHeap](#m_hheap)gespeicherten Heap Handles bestimmt wird.

```
bool m_bOwnHeap;
```

##  <a name="m_hheap"></a>CWin32Heap:: m_hHeap

Handle für das Heap Objekt.

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>Hinweise

Eine Variable, die zum Speichern eines Handles für das Heap Objekt verwendet wird.

##  <a name="reallocate"></a>CWin32Heap:: Neuzuordnen

Führt eine Neubelegung eines Speicherblocks vom Heapobjekt durch.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Zeiger auf den neu zu belegenden Speicherblock.

*nBytes*<br/>
Die neue Größe des belegten Blocks in Bytes. Der Block kann größer oder kleiner gemacht werden.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den neu belegten Speicherblock zurück.

### <a name="remarks"></a>Hinweise

Wenn *p* NULL ist, wird davon ausgegangen, dass der Speicherblock noch nicht zugeordnet wurde und dass [CWin32Heap:: zuordnen](#allocate) mit einem Argument von *nbytes*aufgerufen wird.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)<br/>
[CLocalHeap-Klasse](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)<br/>
[CComHeap-Klasse](../../atl/reference/ccrtheap-class.md)<br/>
[CComHeap-Klasse](../../atl/reference/ccomheap-class.md)
