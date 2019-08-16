---
title: CComHeap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
ms.openlocfilehash: 1ded73047b895a44a22bdd5730886f7fc088c77a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497350"
---
# <a name="ccomheap-class"></a>CComHeap-Klasse

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der com-Speicher Belegungs Funktionen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CComHeap : public IAtlMemMgr
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComHeap:: zuordnen](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|
|[CComHeap::Free](#free)|Mit dieser Methode wird ein Speicherblock freigegeben, der von diesem Speicher-Manager zugeordnet wird.|
|[CComHeap::GetSize](#getsize)|Mit dieser Methode können Sie die zugeordnete Größe eines Speicherblocks abrufen, der von diesem Speicher-Manager zugeordnet wird.|
|[CComHeap::Reallocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|

## <a name="remarks"></a>Hinweise

`CComHeap`implementiert Speicher Belegungs Funktionen mithilfe der com-Zuordnungs Funktionen, einschließlich " [CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)", " [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)", " [IMalloc:: GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize)" und " [CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)". Die maximale Menge an Arbeitsspeicher, die zugeordnet werden kann, ist gleich INT_MAX (2147483647) Bytes.

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IAtlMemMgr`

`CComHeap`

## <a name="requirements"></a>Anforderungen

**Header:** ATLComMem.h

##  <a name="allocate"></a>CComHeap:: zuordnen

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

Rufen Sie [CComHeap:: Free](#free) oder [CComHeap:: rezuordnung](#reallocate) auf, um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Implementiert mit [cotaskmemzuweisung](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc).

##  <a name="free"></a>CComHeap:: Free

Mit dieser Methode wird ein Speicherblock freigegeben, der von diesem Speicher-Manager zugeordnet wird.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert und bewirkt nichts.

### <a name="remarks"></a>Hinweise

Implementiert mit [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree).

##  <a name="getsize"></a>CComHeap:: GetSize

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

Implementiert mithilfe von [imzuzuordnungs:: GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize).

##  <a name="reallocate"></a>CComHeap:: Neuzuordnen

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

Rufen Sie [CComHeap:: Free](#free) auf, um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Implementiert mit [cotaskmemrezuweisungen](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc).

## <a name="see-also"></a>Siehe auch

[DynamicConsumer-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap-Klasse](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)<br/>
[CComHeap-Klasse](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)
