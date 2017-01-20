---
title: "IAtlMemMgr Class"
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
  - "IAtlMemMgr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlMemMgr class"
  - "Speicher, Verwalten"
  - "Speicher, memory manager"
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IAtlMemMgr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Schnittstelle für einen Speicher\-Manager dar.  
  
## Syntax  
  
```  
  
__interface __declspec( uuid( "654F7EF5-CFDF-4df9-A450-6C6A13C622C0" )) IAtlMemMgr  
  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[Ordnen Sie zu](../Topic/IAtlMemMgr::Allocate.md)|Rufen Sie diese Methode auf, um einen Speicherblock zuzuordnen.|  
|[Frei](../Topic/IAtlMemMgr::Free.md)|Rufen Sie diese Methode auf, um einen Speicherblock freizugeben.|  
|[GetSize](../Topic/IAtlMemMgr::GetSize.md)|Rufen Sie diese Methode auf, um die Größe eines reservierten Speicherblocks abzurufen.|  
|[Teilen Sie neu zu](../Topic/IAtlMemMgr::Reallocate.md)|Rufen Sie diese Methode auf, um einen Speicherblock neu belegen.|  
  
## Hinweise  
 Diese Schnittstelle wird von [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [CLocalHeap](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md) oder [CWin32Heap](../../atl/reference/cwin32heap-class.md) implementiert.  
  
> [!NOTE]
>  Die lokale und die globalen Heapfunktionen sind langsamer als andere Speicherverwaltungsfunktionen und stellen keine bis zu Funktionen.  Daher sollten neue Anwendungen [Heapfunktionen](http://msdn.microsoft.com/library/windows/desktop/aa366711) verwenden.  Diese sind in der [CWin32Heap](../../atl/reference/cwin32heap-class.md)\-Klasse verfügbar.  
  
## Beispiel  
 [!CODE [NVC_ATL_Utilities#94](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#94)]  
  
## Anforderungen  
 **Header:** atlmem.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)