---
title: Klasse CCRTHeap | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CCRTHeap
- ATL.CCRTHeap
- CCRTHeap
dev_langs:
- C++
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 1b4df6949794981867051437835d043196613afa
ms.lasthandoff: 02/24/2017

---
# <a name="ccrtheap-class"></a>CCRTHeap-Klasse
Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der CRT-Heapfunktionen.  
  
## <a name="syntax"></a>Syntax  
  
```
class CCRTHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCRTHeap::Allocate](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|  
|[CCRTHeap::Free](#free)|Rufen Sie diese Methode, um einen Speicherblock, der von dieser Speicher-Manager frei.|  
|[CCRTHeap::GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von dieser Speicher-Manager.|  
|[CCRTHeap::Reallocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 `CCRTHeap`implementiert Zuordnungsfunktionen, die die Verwendung der CRT-heap Funktionen, einschließlich Speicher [Malloc](../../c-runtime-library/reference/malloc.md), [freien](../../c-runtime-library/reference/free.md), [Realloc](../../c-runtime-library/reference/realloc.md), und [_msize](../../c-runtime-library/reference/msize.md).  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlmem.h  
  
##  <a name="a-nameallocatea--ccrtheapallocate"></a><a name="allocate"></a>CCRTHeap::Allocate  
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
 Rufen Sie [CCRTHeap::Free](#free) oder [CCRTHeap::Reallocate](#reallocate) , die von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Implementiert mit [Malloc](../../c-runtime-library/reference/malloc.md).  
  
##  <a name="a-namefreea--ccrtheapfree"></a><a name="free"></a>CCRTHeap::Free  
 Rufen Sie diese Methode, um einen Speicherblock, der von dieser Speicher-Manager frei.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert, und es wird keine Aktion ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert mit [kostenlose](../../c-runtime-library/reference/free.md).  
  
##  <a name="a-namegetsizea--ccrtheapgetsize"></a><a name="getsize"></a>CCRTHeap::GetSize  
 Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von dieser Speicher-Manager.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Größe des belegten Speicherblocks in Bytes zurück.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert mit [_msize](../../c-runtime-library/reference/msize.md).  
  
##  <a name="a-namereallocatea--ccrtheapreallocate"></a><a name="reallocate"></a>CCRTHeap::Reallocate  
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
 Rufen Sie [CCRTHeap::Free](#free) , die von dieser Methode belegten Arbeitsspeicher freizugeben. Implementiert mit [Realloc](../../c-runtime-library/reference/realloc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CComHeap-Klasse](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap-Klasse](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)   
 [IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)

