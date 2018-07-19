---
title: CGlobalHeap-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CGlobalHeap
- ATLMEM/ATL::CGlobalHeap
- ATLMEM/ATL::CGlobalHeap::Allocate
- ATLMEM/ATL::CGlobalHeap::Free
- ATLMEM/ATL::CGlobalHeap::GetSize
- ATLMEM/ATL::CGlobalHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CGlobalHeap class
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f3113cf4176c3f582a210e89e732d5e0d92b62d
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882831"
---
# <a name="cglobalheap-class"></a>CGlobalHeap-Klasse
Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Heap der globalen Funktionen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
class CGlobalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Cglobalheap:: Allocate](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|  
|[Cglobalheap:: Free](#free)|Rufen Sie diese Methode, um einen Block von diesem Speicher-Manager zugeordneten Arbeitsspeicher freizugeben.|  
|[CGlobalHeap::GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von diesem Speicher-Manager zugeordnet.|  
|[Cglobalheap:: ReAllocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 `CGlobalHeap` implementiert mithilfe der globalen Heapfunktionen Win32-speicherbelegungsfunktionen an.  
  
> [!NOTE]
>  Die globalen Heap-Funktionen sind langsamer als die anderen Speicherverwaltungsfunktionen und bieten keine so viele Features. Neue Anwendungen sollten daher verwenden die [Heapfunktionen](http://msdn.microsoft.com/library/windows/desktop/aa366711). Diese stehen in der [CWin32Heap](../../atl/reference/cwin32heap-class.md) Klasse. Globale Funktionen sind immer noch von DDE und Funktionen der Zwischenablage verwendet.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CGlobalHeap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlmem.h  
  
##  <a name="allocate"></a>  Cglobalheap:: Allocate  
 Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nBytes*  
 Die angeforderte Anzahl von Bytes im neuen Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [cglobalheap:: Free](#free) oder [cglobalheap:: ReAllocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Mithilfe von implementiert [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) mit einem Flag-Parameter von GMEM_FIXED.  
  
##  <a name="free"></a>  Cglobalheap:: Free  
 Rufen Sie diese Methode, um einen Block von diesem Speicher-Manager zugeordneten Arbeitsspeicher freizugeben.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *p*  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert und hat keine Auswirkungen.  
  
### <a name="remarks"></a>Hinweise  
 Mithilfe von implementiert [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579).  
  
##  <a name="getsize"></a>  CGlobalHeap::GetSize  
 Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von diesem Speicher-Manager zugeordnet.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *p*  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Größe des belegten Speicherblocks in Bytes zurück.  
  
### <a name="remarks"></a>Hinweise  
 Mithilfe von implementiert [GlobalSize ist](http://msdn.microsoft.com/library/windows/desktop/aa366593).  
  
##  <a name="reallocate"></a>  Cglobalheap:: ReAllocate  
 Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *p*  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
 *nBytes*  
 Die angeforderte Anzahl von Bytes im neuen Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [cglobalheap:: Free](#free) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Mithilfe von implementiert [GlobalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CComHeap-Klasse](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap-Klasse](../../atl/reference/clocalheap-class.md)   
 [Ccomheap-Klasse](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)
