---
title: "CCRTAllocator Class"
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
  - "CCRTAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCRTAllocator class"
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CCRTAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Verwalten des Arbeitsspeichers mithilfe der CRT\-Arbeitsspeicherroutinen bereit.  
  
## Syntax  
  
```  
  
class ATL::CCRTAllocator  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CCRTAllocator::Allocate](../Topic/CCRTAllocator::Allocate.md)|\(Statisch\) Rufen Sie diese Methode auf, um Speicher reserviert.|  
|[CCRTAllocator::Free](../Topic/CCRTAllocator::Free.md)|\(Statisch\) Rufen Sie diese Methode auf, um Speicher freizugeben.|  
|[CCRTAllocator::Reallocate](../Topic/CCRTAllocator::Reallocate.md)|\(Statisch\) Rufen Sie diese Methode auf, um Arbeitsspeicher neu belegen.|  
  
## Hinweise  
 Diese Klasse wird von [CHeapPtr](../../atl/reference/cheapptr-class.md) verwendet, um die CRT\-Speicherbelegungsroutinen bereitzustellen.  Die Entsprechungsklasse, [CComAllocator](../../atl/reference/ccomallocator-class.md), stellt die gleichen Methoden mithilfe COM\-Routinen bereit.  
  
## Anforderungen  
 **Header:** atlcore.h  
  
## Siehe auch  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CComAllocator Class](../../atl/reference/ccomallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)