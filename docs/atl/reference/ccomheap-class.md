---
title: "CComHeap Class"
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
  - "CComHeap"
  - "ATL.CComHeap"
  - "ATL::CComHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComHeap class"
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CComHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der COM\-Speicherbelegungsfunktionen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CComHeap : public IAtlMemMgr  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComHeap::Allocate](../Topic/CComHeap::Allocate.md)|Rufen Sie diese Methode auf, um einen Speicherblock zuzuordnen.|  
|[CComHeap::Free](../Topic/CComHeap::Free.md)|Rufen Sie diese Methode auf, um einen Speicherblock freizugeben, der von diesem Speicher\-Manager zugeordnet ist.|  
|[CComHeap::GetSize](../Topic/CComHeap::GetSize.md)|Rufen Sie diese Methode auf, um die zugeordnete Größe eines Speicherblocks abzurufen, der von diesem Speicher\-Manager zugeordnet ist.|  
|[CComHeap::Reallocate](../Topic/CComHeap::Reallocate.md)|Rufen Sie diese Methode auf, um den Arbeitsspeicher neu belegen, der von diesem Speicher\-Manager zugeordnet ist.|  
  
## Hinweise  
 `CComHeap` implementiert Speicherbelegungen mithilfe der COM\-Zuornungsanzahl\-Funktionen, einschließlich [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226) und [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280).  Die Höchstmenge an Arbeitsspeicher, die zugeordnet werden kann, ist gleich \(2147483647 Bytes\) **INT\_MAX**.  
  
## Beispiel  
 Im Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## Anforderungen  
 **Header:** ATLComMem.h  
  
## Siehe auch  
 [DynamicConsumer\-Beispiel](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)