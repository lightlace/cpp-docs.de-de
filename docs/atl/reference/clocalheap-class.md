---
title: "CLocalHeap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CLocalHeap"
  - "ATL::CLocalHeap"
  - "CLocalHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLocalHeap class"
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CLocalHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) mithilfe der lokalen Heapfunktionen Win32.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CLocalHeap : public IAtlMemMgr  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CLocalHeap::Allocate](../Topic/CLocalHeap::Allocate.md)|Rufen Sie diese Methode auf, um einen Speicherblock zuzuordnen.|  
|[CLocalHeap::Free](../Topic/CLocalHeap::Free.md)|Rufen Sie diese Methode auf, um einen Speicherblock freizugeben, der von diesem Speicher\-Manager zugeordnet ist.|  
|[CLocalHeap::GetSize](../Topic/CLocalHeap::GetSize.md)|Rufen Sie diese Methode auf, um die zugeordnete Größe eines Speicherblocks abzurufen, der von diesem Speicher\-Manager zugeordnet ist.|  
|[CLocalHeap::Reallocate](../Topic/CLocalHeap::Reallocate.md)|Rufen Sie diese Methode auf, um den Arbeitsspeicher neu belegen, der von diesem Speicher\-Manager zugeordnet ist.|  
  
## Hinweise  
 `CLocalHeap` Werkzeugspeicherbelegungsfunktionen mithilfe des lokalen Heaps Win32s funktioniert.  
  
> [!NOTE]
>  Die lokalen Heapfunktionen sind langsamer als andere Speicherverwaltungsfunktionen und stellen keine bis zu Funktionen.  Daher sollten neue Anwendungen [Heapfunktionen](http://msdn.microsoft.com/library/windows/desktop/aa366711) verwenden.  Diese sind in der [CWin32Heap](../../atl/reference/cwin32heap-class.md)\-Klasse verfügbar.  
  
## Beispiel  
 Im Beispiel für [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## Vererbungshierarchie  
 `IAtlMemMgr`  
  
 `CLocalHeap`  
  
## Anforderungen  
 **Header:** atlmem.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)