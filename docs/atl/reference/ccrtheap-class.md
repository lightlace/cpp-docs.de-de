---
title: "CCRTHeap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CCRTHeap"
  - "ATL.CCRTHeap"
  - "CCRTHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCRTHeap class"
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CCRTHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der CRT\-Heapfunktionen.  
  
## Syntax  
  
```  
  
class CCRTHeap : public IAtlMemMgr  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CCRTHeap::Allocate](../Topic/CCRTHeap::Allocate.md)|Rufen Sie diese Methode auf, um einen Speicherblock zuzuordnen.|  
|[CCRTHeap::Free](../Topic/CCRTHeap::Free.md)|Rufen Sie diese Methode auf, um einen Speicherblock freizugeben, der von diesem Speicher\-Manager zugeordnet ist.|  
|[CCRTHeap::GetSize](../Topic/CCRTHeap::GetSize.md)|Rufen Sie diese Methode auf, um die zugeordnete Größe eines Speicherblocks abzurufen, der von diesem Speicher\-Manager zugeordnet ist.|  
|[CCRTHeap::Reallocate](../Topic/CCRTHeap::Reallocate.md)|Rufen Sie diese Methode auf, um den Arbeitsspeicher neu belegen, der von diesem Speicher\-Manager zugeordnet ist.|  
  
## Hinweise  
 `CCRTHeap` Werkzeugspeicherbelegungsfunktionen mithilfe des CRT häufen Funktionen, einschließlich [malloc](../../c-runtime-library/reference/malloc.md), [frei](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md) und [\_msize](../../c-runtime-library/reference/msize.md).  
  
## Beispiel  
 Im Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## Anforderungen  
 **Header:** atlmem.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)