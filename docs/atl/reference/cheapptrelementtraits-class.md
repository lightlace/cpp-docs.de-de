---
title: "CHeapPtrElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CHeapPtrElementTraits"
  - "CHeapPtrElementTraits"
  - "ATL::CHeapPtrElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrElementTraits class"
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CHeapPtrElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden, statische Funktionen und die Typdefinitionen, wenn sie die Auflistungen Heapzeiger nützlich sind, erstellt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<  
typename T,  
class Allocator= ATL::CCRTAllocator  
>  
class CHeapPtrElementTraits : public CDefaultElementTraits<  
ATL::CHeapPtr< T, Allocator>  
>  
```  
  
#### Parameter  
 `T`  
 Der in der Auflistungsklasse gespeichert werden, Objekttyp.  
  
 `Allocator`  
 Die Speicherbelegungsklasse zur Verwendung.  Der Standardwert ist [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CHeapPtrElementTraits::INARGTYPE](../Topic/CHeapPtrElementTraits::INARGTYPE.md)|Der für das Hinzufügen von Elementen zum Auflistungsklassenobjekt Datentyp, zu verwenden.|  
|[CHeapPtrElementTraits::OUTARGTYPE](../Topic/CHeapPtrElementTraits::OUTARGTYPE.md)|Der für das Abrufen von Elementen vom Datentyp, Auflistungsklassenobjekt zu verwenden.|  
  
## Hinweise  
 Diese Klasse stellt Methoden, statische Funktionen und Typdefinitionen für die Unterstützung der Erstellung der Auflistungsklassenobjekte bereit, die Heapzeiger enthalten.  Die Klasse wird von abgeleitet `CHeapPtrList``CHeapPtrElementTraits`.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Vererbungshierarchie  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CHeapPtrElementTraits`  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [CComHeapPtr Class](../../atl/reference/ccomheapptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)