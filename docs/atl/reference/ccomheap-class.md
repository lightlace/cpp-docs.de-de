---
title: CComHeap-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75bd4ad2f182d2a9f62e82b78f9ee9d0db44fa00
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359862"
---
# <a name="ccomheap-class"></a>CComHeap-Klasse
Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mit COM-Speicherverwaltungsfunktionen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComHeap::Allocate](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|  
|[Ccomheap:: Free](#free)|Rufen Sie diese Methode, um einen Speicherblock, der von diesem Speicher-Manager frei.|  
|[CComHeap::GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von diesem Speicher-Manager zugeordnet.|  
|[Ccomheap:: ReAllocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 `CComHeap` implementiert die Speicherverwaltungsfunktionen, die mit der COM-Zuordnungsfunktionen, einschließlich [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226), und [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280). Die Höchstmenge an Arbeitsspeicher an, die zugeordnet werden kann, ist gleich **INT_MAX** (2.147.483.647) Bytes.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ATLComMem.h  
  
##  <a name="allocate"></a>  CComHeap::Allocate  
 Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Die angeforderte Anzahl von Bytes im neuen Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [ccomheap:: Free](#free) oder [ccomheap:: ReAllocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Implementiert mit [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727).  
  
##  <a name="free"></a>  Ccomheap:: Free  
 Rufen Sie diese Methode, um einen Speicherblock, der von diesem Speicher-Manager frei.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert, und es wird keine Aktion ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert mit [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722).  
  
##  <a name="getsize"></a>  CComHeap::GetSize  
 Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von diesem Speicher-Manager zugeordnet.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Größe des belegten Speicherblocks in Bytes zurück.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert mit [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226).  
  
##  <a name="reallocate"></a>  Ccomheap:: ReAllocate  
 Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
 `nBytes`  
 Die angeforderte Anzahl von Bytes im neuen Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [ccomheap:: Free](#free) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Implementiert mit [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280).  
  
## <a name="see-also"></a>Siehe auch  
 [-Beispiel-Beispiel](../../visual-cpp-samples.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)   
 [Clocalheap – Klasse](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap-Klasse](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)
