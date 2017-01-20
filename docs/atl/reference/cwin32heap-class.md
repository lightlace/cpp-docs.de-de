---
title: "CWin32Heap Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::CWin32Heap"
  - "ATL.CWin32Heap"
  - "CWin32Heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWin32Heap class"
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
caps.latest.revision: 19
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CWin32Heap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der Win32\-Heapbelegungsfunktionen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CWin32Heap : public IAtlMemMgr  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWin32Heap::CWin32Heap](../Topic/CWin32Heap::CWin32Heap.md)|Der \-Konstruktor.|  
|[CWin32Heap::~CWin32Heap](../Topic/CWin32Heap::~CWin32Heap.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWin32Heap::Allocate](../Topic/CWin32Heap::Allocate.md)|Ordnet einen Speicherblock aus dem Heapobjekt zu.|  
|[CWin32Heap::Attach](../Topic/CWin32Heap::Attach.md)|Fügt das Heapobjekt zu einem vorhandenen Heap an.|  
|[CWin32Heap::Detach](../Topic/CWin32Heap::Detach.md)|Trennt die Heapobjekt aus einem vorhandenen Heap.|  
|[CWin32Heap::Free](../Topic/CWin32Heap::Free.md)|Gibt den Arbeitsspeicher frei, der zuvor vom Heap zugeordnet ist.|  
|[CWin32Heap::GetSize](../Topic/CWin32Heap::GetSize.md)|Gibt die Größe eines Speicherblocks zurück, der vom Heapobjekt zugeordnet ist.|  
|[CWin32Heap::Reallocate](../Topic/CWin32Heap::Reallocate.md)|Teilt einen Speicherblock aus dem Heapobjekt neu zu.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CWin32Heap::m\_bOwnHeap](../Topic/CWin32Heap::m_bOwnHeap.md)|Ein Flag verwendet, um den aktuellen Besitzer des Heaphandles zu bestimmen.|  
|[CWin32Heap::m\_hHeap](../Topic/CWin32Heap::m_hHeap.md)|Handle für Heapobjekt.|  
  
## Hinweise  
 `CWin32Heap` implementiert Speicherbelegungsmethoden mithilfe der Win32\-Heapbelegungsfunktionen, einschließlich [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597) und [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701).  Im Gegensatz zu anderen Heapklassen erfordert `CWin32Heap` ein gültiges Heaphandle bereitgestellt werden, bevor Arbeitsspeicher zugeordnet wird: die anderen Klassen führen zur Verwendung des Prozessheaps.  Das Handle kann an den Konstruktor oder zur [CWin32Heap::Attach](../Topic/CWin32Heap::Attach.md)\-Methode angegeben werden.  Siehe die [CWin32Heap::CWin32Heap](../Topic/CWin32Heap::CWin32Heap.md)\-Methode für weitere Details.  
  
## Beispiel  
 Im Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CWin32Heap`  
  
## Anforderungen  
 **Header:** atlmem.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)