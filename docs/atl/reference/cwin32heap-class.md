---
title: Klasse CWin32Heap | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CWin32Heap
- ATL.CWin32Heap
- CWin32Heap
dev_langs:
- C++
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 407f777b52529a333251c7d00481fdbfb14db619
ms.lasthandoff: 02/24/2017

---
# <a name="cwin32heap-class"></a>CWin32Heap-Klasse
Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32-Heapreservierungsfunktionen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CWin32Heap : public IAtlMemMgr
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWin32Heap::CWin32Heap](#cwin32heap)|Der Konstruktor.|  
|[CWin32Heap:: ~ CWin32Heap](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWin32Heap::Allocate](#allocate)|Führt eine Belegung eines Speicherblocks vom Heapobjekt durch.|  
|[CWin32Heap:: Attach](#attach)|Fügt die heapobjekt an ein vorhandenes Heap.|  
|[CWin32Heap::Detach](#detach)|Trennt die heapobjekt aus einem vorhandenen Heap.|  
|[CWin32Heap::Free](#free)|Zuvor aus dem Heap zugeordneten Arbeitsspeicher frei.|  
|[CWin32Heap::GetSize](#getsize)|Gibt die Größe des Objekts Heap belegten Speicherblocks zurück.|  
|[CWin32Heap::Reallocate](#reallocate)|Führt eine Neubelegung eines Speicherblocks vom Heapobjekt durch.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|Ein Flag, das zum Ermitteln der aktuellen Besitzer des Heap-Handles.|  
|[CWin32Heap::m_hHeap](#m_hheap)|Handle für den heapobjekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CWin32Heap`Arbeitsspeicher-Zuordnungsmethoden mit Win32 Heapreservierungsfunktionen, einschließlich implementiert [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597) und [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701). Im Gegensatz zu anderen Klassen Heap `CWin32Heap` muss einem gültigen Heaphandle bereitgestellt werden, bevor der Speicher belegt wird: der andere Klassen die standardmäßig den Prozessheap. Das Handle kann angegeben werden, an den Konstruktor oder in der [CWin32Heap:: Attach](#attach) Methode. Finden Sie unter der [CWin32Heap::CWin32Heap](#cwin32heap) Methode für weitere Details.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CWin32Heap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlmem.h  
  
##  <a name="a-nameallocatea--cwin32heapallocate"></a><a name="allocate"></a>CWin32Heap::Allocate  
 Führt eine Belegung eines Speicherblocks vom Heapobjekt durch.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Die angeforderte Anzahl von Bytes im neuen Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den neu belegten Speicherblock zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [CWin32Heap::Free](#free) oder [CWin32Heap::Reallocate](#reallocate) , die von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Implementiert mit [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597).  
  
##  <a name="a-nameattacha--cwin32heapattach"></a><a name="attach"></a>CWin32Heap:: Attach  
 Fügt die heapobjekt an ein vorhandenes Heap.  
  
```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hHeap`  
 Ein vorhandenes Heaphandle.  
  
 `bTakeOwnership`  
 Ein Flag gibt an, wenn die `CWin32Heap` Objekt besteht darin, den Besitz über die Ressourcen des Heaps.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bTakeOwnership` true festgelegt ist, wird die `CWin32Heap` -Objekt ist verantwortlich für das Löschen des Heap-Handles.  
  
##  <a name="a-namecwin32heapa--cwin32heapcwin32heap"></a><a name="cwin32heap"></a>CWin32Heap::CWin32Heap  
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
 `hHeap`  
 Ein vorhandenes Heapobjekt.  
  
 `dwFlags`  
 Bei der Erstellung des Heaps verwendete Flags.  
  
 *nInitialSize*  
 Die Anfangsgröße des Heaps.  
  
 `nMaxSize`  
 Die maximale Größe des Heaps.  
  
### <a name="remarks"></a>Hinweise  
 Vor dem Zuordnen von Speicher muss das `CWin32Heap`-Objekt mit einem gültigen Heaphandle bereitgestellt werden. Das geht am einfachsten mit dem Prozessheap:  
  
 [!code-cpp[NVC_ATL_Utilities&#92;](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]  
  
 Es ist auch möglich, ein vorhandenes Heaphandle an den Konstruktor auszugeben; in diesem Fall übernimmt das neue Objekt nicht Besitz des Heaps. Wenn das `CWin32Heap`-Objekt gelöscht wird, ist das ursprüngliche Heaphandle weiterhin gültig.  
  
 Ein vorhandenes Heap kann auch angefügt werden, auf das neue Objekt mit [CWin32Heap:: Attach](#attach).  
  
 Wenn ein Heap erforderlich ist, in dem alle Operationen von einem einzigen Thread ausgeführt werden, empfiehlt es sich, das Objekt folgendermaßen zu erstellen:  
  
 [!code-cpp[NVC_ATL_Utilities&#93;](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]  
  
 Der Parameter **HEAP_NO_SERIALIZE** gibt an, dass der gegenseitiger Ausschluss nicht verwendet wird, wenn die Heapfunktionen zuordnen und Freigeben von Arbeitsspeicher, mit der sich die Leistung in.  
  
 Der dritte Parameter beträgt standardmäßig 0; dadurch kann das Heap nach Bedarf vergrößert werden. Finden Sie unter [HeapCreate](http://msdn.microsoft.com/library/windows/desktop/aa366599\(v=vs.85\).aspx) eine Erläuterung der Speichergrößen und Flags.  
  
##  <a name="a-namedtora--cwin32heapcwin32heap"></a><a name="dtor"></a>CWin32Heap:: ~ CWin32Heap  
 Der Destruktor.  
  
```
~CWin32Heap() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Handle des Heaps zerstört, wenn die `CWin32Heap` Objekt hat den Besitz des Heaps.  
  
##  <a name="a-namedetacha--cwin32heapdetach"></a><a name="detach"></a>CWin32Heap::Detach  
 Trennt die heapobjekt aus einem vorhandenen Heap.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Handle für den Heap, den das Objekt bereits vorher angefügt wurde.  
  
##  <a name="a-namefreea--cwin32heapfree"></a><a name="free"></a>CWin32Heap::Free  
 Zuvor aus dem Heap vom zugeordneten Arbeitsspeicher frei [CWin32Heap::Allocate](#allocate) oder [CWin32Heap::Reallocate](#reallocate).  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Zeiger auf den Speicherblock freizugeben. NULL ist ein gültiger Wert, und es wird keine Aktion ausgeführt.  
  
##  <a name="a-namegetsizea--cwin32heapgetsize"></a><a name="getsize"></a>CWin32Heap::GetSize  
 Gibt die Größe des Objekts Heap belegten Speicherblocks zurück.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Zeiger auf den Speicherblock, deren Größe die Methode erhält. Dies ist ein Zeiger, der von zurückgegebene [CWin32Heap::Allocate](#allocate) oder [CWin32Heap::Reallocate](#reallocate).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Größe des belegten Speicherblocks in Bytes zurück.  
  
##  <a name="a-namembownheapa--cwin32heapmbownheap"></a><a name="m_bownheap"></a>CWin32Heap::m_bOwnHeap  
 Ein Flag, das zum Ermitteln der aktuellen Besitzer des Heap-Handles, die in gespeicherten [M_hHeap](#m_hheap).  
  
```
bool m_bOwnHeap;
```  
  
##  <a name="a-namemhheapa--cwin32heapmhheap"></a><a name="m_hheap"></a>CWin32Heap::m_hHeap  
 Handle für den heapobjekt.  
  
```
HANDLE m_hHeap;
```  
  
### <a name="remarks"></a>Hinweise  
 Eine Variable verwendet, um ein Handle für den heapobjekt zu speichern.  
  
##  <a name="a-namereallocatea--cwin32heapreallocate"></a><a name="reallocate"></a>CWin32Heap::Reallocate  
 Führt eine Neubelegung eines Speicherblocks vom Heapobjekt durch.  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Zeiger auf den neu zu belegenden Speicherblock.  
  
 `nBytes`  
 Die neue Größe des belegten Blocks in Bytes. Der Block kann größer oder kleiner gemacht werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den neu belegten Speicherblock zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `p` NULL ist, wird davon ausgegangen, dass der Speicherblock noch nicht zugeordnet wurde und [CWin32Heap::Allocate](#allocate) aufgerufen wird, mit dem Argument `nBytes`.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [IAtlMemMgr-Klasse](../../atl/reference/iatlmemmgr-class.md)   
 [CLocalHeap-Klasse](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap-Klasse](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap-Klasse](../../atl/reference/ccrtheap-class.md)   
 [CComHeap-Klasse](../../atl/reference/ccomheap-class.md)

