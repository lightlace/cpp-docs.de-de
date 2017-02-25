---
title: "CComHeapPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComHeapPtr"
  - "ATL.CComHeapPtr<T>"
  - "ATL::CComHeapPtr<T>"
  - "CComHeapPtr"
  - "ATL.CComHeapPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComHeapPtr class"
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComHeapPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Klasse des intelligenten Zeigermechanismus zum Verwalten von Heapzeigern.  
  
## Syntax  
  
```  
  
      template<  
   typename T  
> class CComHeapPtr :  
   public CHeapPtr< T, CComAllocator >  
```  
  
#### Parameter  
 `T`  
 Der auf dem Heap gespeichert werden, Objekttyp.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComHeapPtr::CComHeapPtr](../Topic/CComHeapPtr::CComHeapPtr.md)|Der \-Konstruktor.|  
  
## Hinweise  
 `CComHeapPtr` wird von abgeleitet `CHeapPtr`, jedoch vor der Verwendung [CComAllocator](../../atl/reference/ccomallocator-class.md), mit COM\-Routinen Speicher reserviert.  Siehe [CHeapPtr](../../atl/reference/cheapptr-class.md) und [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) für die verfügbaren Methoden.  
  
## Vererbungshierarchie  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrBase Class](../../atl/reference/cheapptrbase-class.md)   
 [CComAllocator Class](../../atl/reference/ccomallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)