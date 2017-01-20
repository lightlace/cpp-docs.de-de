---
title: "CGlobalHeap Class"
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
  - "ATL.CGlobalHeap"
  - "ATL::CGlobalHeap"
  - "CGlobalHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGlobalHeap class"
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
caps.latest.revision: 19
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CGlobalHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der globalen Heapfunktionen Win32.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CGlobalHeap : public IAtlMemMgr  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CGlobalHeap::Allocate](../Topic/CGlobalHeap::Allocate.md)|Rufen Sie diese Methode auf, um einen Speicherblock zuzuordnen.|  
|[CGlobalHeap::Free](../Topic/CGlobalHeap::Free.md)|Rufen Sie diese Methode auf, um einen Speicherblock freizugeben, der von diesem Speicher\-Manager zugeordnet ist.|  
|[CGlobalHeap::GetSize](../Topic/CGlobalHeap::GetSize.md)|Rufen Sie diese Methode auf, um die zugeordnete Größe eines Speicherblocks abzurufen, der von diesem Speicher\-Manager zugeordnet ist.|  
|[CGlobalHeap::Reallocate](../Topic/CGlobalHeap::Reallocate.md)|Rufen Sie diese Methode auf, um den Arbeitsspeicher neu belegen, der von diesem Speicher\-Manager zugeordnet ist.|  
  
## Hinweise  
 `CGlobalHeap` implementiert Speicherbelegungen mithilfe der globalen Heapfunktionen Win32.  
  
> [!NOTE]
>  Die globalen Heapfunktionen sind langsamer als andere Speicherverwaltungsfunktionen und stellen keine bis zu Funktionen.  Daher sollten neue Anwendungen [Heapfunktionen](http://msdn.microsoft.com/library/windows/desktop/aa366711) verwenden.  Diese sind in der [CWin32Heap](../../atl/reference/cwin32heap-class.md)\-Klasse verfügbar.  Globale Funktionen werden weiterhin durch DDE und die Zwischenablagefunktionen verwendet.  
  
## Beispiel  
 Im Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CGlobalHeap`  
  
## Anforderungen  
 **Header:** atlmem.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)