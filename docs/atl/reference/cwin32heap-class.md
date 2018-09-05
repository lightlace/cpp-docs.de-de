---
title: CWin32Heap-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c8081b5a85b09f513152861cb09758b61df8d9b
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763252"
---
# <a name="cwin32heap-class"></a>CWin32Heap-Klasse

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Heapreservierungsfunktionen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CWin32Heap : public IAtlMemMgr
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CWin32Heap::CWin32Heap](#cwin32heap)|Der Konstruktor.|
|[CWin32Heap:: ~ CWin32Heap](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWin32Heap:: Allocate](#allocate)|Führt eine Belegung eines Speicherblocks vom Heapobjekt durch.|
|[CWin32Heap:: Attach](#attach)|Fügt die heapobjekt an einem vorhandenen Heap befindet.|
|[CWin32Heap::Detach](#detach)|Trennt das heapobjekt aus einem vorhandenen Heap befindet.|
|[CWin32Heap:: Free](#free)|Zuvor vom Heap zugewiesenen Speicher frei.|
|[CWin32Heap::GetSize](#getsize)|Gibt die Größe eines Speicherblocks vom heapobjekt zugeordnet.|
|[CWin32Heap:: ReAllocate](#reallocate)|Führt eine Neubelegung eines Speicherblocks vom Heapobjekt durch.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|Ein Flag, das verwendet, um die aktuellen Besitzer des Heap-Handles zu bestimmen.|
|[CWin32Heap::m_hHeap](#m_hheap)|Handle für das heapobjekt.|

## <a name="remarks"></a>Hinweise

`CWin32Heap` implementiert mithilfe der Win32-Heapreservierungsfunktionen, einschließlich Speicher-Zuordnungsmethoden [HeapAlloc](/windows/desktop/api/heapapi/nf-heapapi-heapalloc) und [HeapFree](/windows/desktop/api/heapapi/nf-heapapi-heapfree). Im Gegensatz zu anderen Klassen Heap `CWin32Heap` muss einem gültigen Heaphandle bereitgestellt werden, bevor der Speicher zugeordnet wird: der andere Klassen standardmäßig den Prozessheap. Das Handle kann angegeben werden, an den Konstruktor oder auf die [CWin32Heap:: Attach](#attach) Methode. Finden Sie unter den [CWin32Heap::CWin32Heap](#cwin32heap) Methode für die weitere Details.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>Anforderungen

**Header:** atlmem.h

##  <a name="allocate"></a>  CWin32Heap:: Allocate

Führt eine Belegung eines Speicherblocks vom Heapobjekt durch.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*nBytes*  
Die angeforderte Anzahl von Bytes im neuen Speicherblock.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den neu belegten Speicherblock zurück.

### <a name="remarks"></a>Hinweise

Rufen Sie [CWin32Heap:: Free](#free) oder [CWin32Heap:: ReAllocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Mithilfe von implementiert [HeapAlloc](/windows/desktop/api/heapapi/nf-heapapi-heapalloc).

##  <a name="attach"></a>  CWin32Heap:: Attach

Fügt die heapobjekt an einem vorhandenen Heap befindet.

```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>Parameter

*hHeap*  
Ein vorhandenes Heaphandle.

*bTakeOwnership*  
Ein Flag, der angibt, wenn die `CWin32Heap` Objekt ist, den Besitz der Ressourcen den Heap übernehmen.

### <a name="remarks"></a>Hinweise

Wenn *bTakeOwnership* ist "true", die `CWin32Heap` Objekt ist verantwortlich für das Löschen der Heap-Handles.

##  <a name="cwin32heap"></a>  CWin32Heap::CWin32Heap

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

*hHeap*  
Ein vorhandenes Heapobjekt.

*dwFlags*  
Bei der Erstellung des Heaps verwendete Flags.

*nInitialSize*  
Die Anfangsgröße des Heaps.

*nMaxSize*  
Die maximale Größe des Heaps.

### <a name="remarks"></a>Hinweise

Vor dem Zuordnen von Speicher muss das `CWin32Heap`-Objekt mit einem gültigen Heaphandle bereitgestellt werden. Das geht am einfachsten mit dem Prozessheap:

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

Es ist auch möglich, ein vorhandenes Heaphandle an den Konstruktor auszugeben; in diesem Fall übernimmt das neue Objekt nicht Besitz des Heaps. Wenn das `CWin32Heap`-Objekt gelöscht wird, ist das ursprüngliche Heaphandle weiterhin gültig.

Ein vorhandenes Heap kann auch angefügt werden, auf das neue Objekt, um mithilfe [CWin32Heap:: Attach](#attach).

Wenn ein Heap erforderlich ist, in dem alle Operationen von einem einzigen Thread ausgeführt werden, empfiehlt es sich, das Objekt folgendermaßen zu erstellen:

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

Der Parameter HEAP_NO_SERIALIZE gibt an, dass es sich bei gegenseitiger Ausschluss nicht verwendet wird, wenn die Heapfunktionen reservieren und Freigeben von Arbeitsspeicher, die einen entsprechenden Zunahme der Leistung.

Der dritte Parameter beträgt standardmäßig 0; dadurch kann das Heap nach Bedarf vergrößert werden. Finden Sie unter [HeapCreate](/windows/desktop/api/heapapi/nf-heapapi-heapcreate) eine Erläuterung der Arbeitsspeichergrößen und Kennzeichen.

##  <a name="dtor"></a>  CWin32Heap:: ~ CWin32Heap

Der Destruktor.

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>Hinweise

Der Heap-Handles zerstört, wenn die `CWin32Heap` Objekt hat den Besitz des Heaps.

##  <a name="detach"></a>  CWin32Heap::Detach

Trennt das heapobjekt aus einem vorhandenen Heap befindet.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Handle zurück, auf dem Heap, den das Objekt bereits vorher angefügt wurde.

##  <a name="free"></a>  CWin32Heap:: Free

Gibt aus dem Heap von zuvor zugewiesenen Arbeitsspeicher frei, [CWin32Heap:: Allocate](#allocate) oder [CWin32Heap:: ReAllocate](#reallocate).

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*  
Zeiger auf den Speicherblock freizugeben. NULL ist ein gültiger Wert und hat keine Auswirkungen.

##  <a name="getsize"></a>  CWin32Heap::GetSize

Gibt die Größe eines Speicherblocks vom heapobjekt zugeordnet.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*  
Zeiger zum Speicherblock, deren Größe, die die Methode erhält. Dies ist ein Zeiger, der vom [CWin32Heap:: Allocate](#allocate) oder [CWin32Heap:: ReAllocate](#reallocate).

### <a name="return-value"></a>Rückgabewert

Gibt die Größe des belegten Speicherblocks in Bytes zurück.

##  <a name="m_bownheap"></a>  CWin32Heap::m_bOwnHeap

Ein Flag, das zum Bestimmen der aktuellen Besitzer der Heap-Handles, die in gespeicherten [M_hHeap](#m_hheap).

```
bool m_bOwnHeap;
```

##  <a name="m_hheap"></a>  CWin32Heap::m_hHeap

Handle für das heapobjekt.

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>Hinweise

Eine Variable verwendet, um ein Handle für das heapobjekt zu speichern.

##  <a name="reallocate"></a>  CWin32Heap:: ReAllocate

Führt eine Neubelegung eines Speicherblocks vom Heapobjekt durch.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*p*  
Zeiger auf den neu zu belegenden Speicherblock.

*nBytes*  
Die neue Größe des belegten Blocks in Bytes. Der Block kann größer oder kleiner gemacht werden.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den neu belegten Speicherblock zurück.

### <a name="remarks"></a>Hinweise

Wenn *p* NULL ist, es wird davon ausgegangen, dass der Speicherblock noch nicht belegt wurde und [CWin32Heap:: Allocate](#allocate) aufgerufen wird, mit dem Argument *nBytes*.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)   
[IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)   
[CLocalHeap-Klasse](../../atl/reference/clocalheap-class.md)   
[CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)   
[Ccomheap-Klasse](../../atl/reference/ccrtheap-class.md)   
[CComHeap-Klasse](../../atl/reference/ccomheap-class.md)
