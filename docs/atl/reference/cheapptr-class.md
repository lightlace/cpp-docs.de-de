---
title: "CHeapPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CHeapPtr"
  - "CHeapPtr"
  - "ATL.CHeapPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtr class"
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CHeapPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Klasse des intelligenten Zeigermechanismus zum Verwalten von Heapzeigern.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<  
typename T,  
class Allocator= CCRTAllocator  
> class CHeapPtr :  
public CHeapPtrBase< T, Allocator>  
```  
  
#### Parameter  
 `T`  
 Der auf dem Heap gespeichert werden, Objekttyp.  
  
 `Allocator`  
 Die Speicherbelegungsklasse zur Verwendung.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHeapPtr::CHeapPtr](../Topic/CHeapPtr::CHeapPtr.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CHeapPtr::Allocate](../Topic/CHeapPtr::Allocate.md)|Rufen Sie diese Methode auf, um auf dem Heap zu den Speicherobjekten Speicher reserviert.|  
|[CHeapPtr::Reallocate](../Topic/CHeapPtr::Reallocate.md)|Rufen Sie diese Methode auf, um den Arbeitsspeicher auf dem Heap neu belegen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHeapPtr::operator \=](../Topic/CHeapPtr::operator%20=.md)|Der Zuweisungsoperator.|  
  
## Hinweise  
 `CHeapPtr` wird von abgeleitet und [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) standardmäßig die CRT\-Routinen \(in [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)\) zum Arbeitsspeicher reserviert und freigegeben.  Die Klasse [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) verwendet werden, um eine Liste von Heapzeigern zu erstellen.  Siehe auch [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), das COM\-Speicherbelegungsroutinen verwendet.  
  
## Vererbungshierarchie  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## Anforderungen  
 **Header:** atlcore.h  
  
## Siehe auch  
 [CHeapPtrBase Class](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator Class](../../atl/reference/ccrtallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)