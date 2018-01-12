---
title: "Clocalheap – Klasse | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
dev_langs: C++
helpviewer_keywords: CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5307e0e6e8925bcbbfa7a03d0140c3a5a08baff9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clocalheap-class"></a>Clocalheap – Klasse
Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der lokalen Heap Win32-Funktionen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CLocalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Clocalheap:: Allocate](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|  
|[Clocalheap:: Free](#free)|Rufen Sie diese Methode, um einen Speicherblock, der von diesem Speicher-Manager frei.|  
|[CLocalHeap::GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von diesem Speicher-Manager zugeordnet.|  
|[Clocalheap:: ReAllocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 `CLocalHeap`implementiert die Speicherverwaltungsfunktionen, die mit der lokalen Heap Win32-Funktionen.  
  
> [!NOTE]
>  Die lokalen Heap-Funktionen sind langsamer als die anderen Speicherverwaltungsfunktionen und bieten keine so viele Funktionen. Neue Anwendungen sollten daher verwenden die [heap Funktionen](http://msdn.microsoft.com/library/windows/desktop/aa366711). Diese Seiten sind verfügbar, in der [CWin32Heap](../../atl/reference/cwin32heap-class.md) Klasse.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CLocalHeap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlmem.h  
  
##  <a name="allocate"></a>Clocalheap:: Allocate  
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
 Rufen Sie [clocalheap:: Free](#free) oder [clocalheap:: ReAllocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Implementiert mit [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) mit einem Flag-Parameter der **LMEM_FIXED**.  
  
##  <a name="free"></a>Clocalheap:: Free  
 Rufen Sie diese Methode, um einen Speicherblock, der von diesem Speicher-Manager frei.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert, und es wird keine Aktion ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert mit [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366730).  
  
##  <a name="getsize"></a>CLocalHeap::GetSize  
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
 Implementiert mit [LocalSize](http://msdn.microsoft.com/library/windows/desktop/aa366745).  
  
##  <a name="reallocate"></a>Clocalheap:: ReAllocate  
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
 Rufen Sie [clocalheap:: Free](#free) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Implementiert mit [LocalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366742).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [CComHeap-Klasse](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap-Klasse](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)
