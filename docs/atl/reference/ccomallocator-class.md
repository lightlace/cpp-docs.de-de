---
title: "CComAllocator Class"
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
  - "ATL.CComAllocator"
  - "ATL::CComAllocator"
  - "CComAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAllocator class"
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CComAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Verwalten des Arbeitsspeichers mithilfe der COM\-Arbeitsspeicherroutinen bereit.  
  
## Syntax  
  
```  
  
class CComAllocator  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComAllocator::Allocate](../Topic/CComAllocator::Allocate.md)|Rufen Sie die statische Methode auf, um Speicher reserviert.|  
|[CComAllocator::Free](../Topic/CComAllocator::Free.md)|Rufen Sie die statische Methode auf, um reservierten Speicher freizugeben.|  
|[CComAllocator::Reallocate](../Topic/CComAllocator::Reallocate.md)|Rufen Sie die statische Methode auf, um Arbeitsspeicher neu belegen.|  
  
## Hinweise  
 Diese Klasse wird von [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) verwendet, um die COM\-Speicherbelegungsroutinen bereitzustellen.  Die Entsprechungsklasse, [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), stellt die gleichen Methoden mithilfe CRT\-Routinen bereit.  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [CComHeapPtr Class](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator Class](../../atl/reference/ccrtallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)