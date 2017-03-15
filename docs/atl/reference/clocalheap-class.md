---
title: Klasse CLocalHeap | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CLocalHeap
- ATL::CLocalHeap
- CLocalHeap
dev_langs:
- C++
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
caps.latest.revision: 20
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
ms.openlocfilehash: 6a5caaa360970578aee4432fd40af9aa0e391d90
ms.lasthandoff: 02/24/2017

---
# <a name="clocalheap-class"></a>CLocalHeap-Klasse
Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Funktionen lokalen Heap.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CLocalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLocalHeap::Allocate](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|  
|[CLocalHeap::Free](#free)|Rufen Sie diese Methode, um einen Speicherblock, der von dieser Speicher-Manager frei.|  
|[CLocalHeap::GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der zugeordneten Größe eines Speicherblocks, der von dieser Speicher-Manager.|  
|[CLocalHeap::Reallocate](#reallocate)|Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 `CLocalHeap`implementiert die Speicherverwaltungsfunktionen mithilfe der Win32-Funktionen lokalen Heap.  
  
> [!NOTE]
>  Die lokalen Heap-Funktionen sind langsamer als die anderen Speicherverwaltungsfunktionen und bieten nicht so viele Features. Neue Anwendungen sollten daher verwenden die [heap Funktionen](http://msdn.microsoft.com/library/windows/desktop/aa366711). Diese stehen in der [CWin32Heap](../../atl/reference/cwin32heap-class.md) Klasse.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CLocalHeap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlmem.h  
  
##  <a name="a-nameallocatea--clocalheapallocate"></a><a name="allocate"></a>CLocalHeap::Allocate  
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
 Rufen Sie [CLocalHeap::Free](#free) oder [CLocalHeap::Reallocate](#reallocate) , die von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Implementiert mit [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) mit einem Flag-Parameter des **LMEM_FIXED**.  
  
##  <a name="a-namefreea--clocalheapfree"></a><a name="free"></a>CLocalHeap::Free  
 Rufen Sie diese Methode, um einen Speicherblock, der von dieser Speicher-Manager frei.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde. NULL ist ein gültiger Wert, und es wird keine Aktion ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert mit [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730).  
  
##  <a name="a-namegetsizea--clocalheapgetsize"></a><a name="getsize"></a>CLocalHeap::GetSize  
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
 Implementiert mit [LocalSize](http://msdn.microsoft.com/library/windows/desktop/aa366745).  
  
##  <a name="a-namereallocatea--clocalheapreallocate"></a><a name="reallocate"></a>CLocalHeap::Reallocate  
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
 Rufen Sie [CLocalHeap::Free](#free) , die von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Implementiert mit [LocalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366742).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CComHeap-Klasse](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap-Klasse](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap-Klasse](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)

