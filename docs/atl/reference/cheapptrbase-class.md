---
title: "CHeapPtrBase Class"
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
  - "ATL.CHeapPtrBase"
  - "ATL::CHeapPtrBase"
  - "CHeapPtrBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrBase class"
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtrBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse bildet die Grundlage für einige intelligente Heapzeigerklassen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class T,  
class Allocator= CCRTAllocator   
> class CHeapPtrBase  
```  
  
#### Parameter  
 `T`  
 Der auf dem Heap gespeichert werden, Objekttyp.  
  
 `Allocator`  
 Die Speicherbelegungsklasse zur Verwendung.  Standardmäßig werden CRT\-Routinen verwendet, um Arbeitsspeicher reserviert und freigegeben.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHeapPtrBase::~CHeapPtrBase](../Topic/CHeapPtrBase::~CHeapPtrBase.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CHeapPtrBase::AllocateBytes](../Topic/CHeapPtrBase::AllocateBytes.md)|Rufen Sie diese Methode auf, um Speicher reserviert.|  
|[CHeapPtrBase::Attach](../Topic/CHeapPtrBase::Attach.md)|Rufen Sie diese Methode auf, um den Besitz einer vorhandenen Zeiger zu akzeptieren.|  
|[CHeapPtrBase::Detach](../Topic/CHeapPtrBase::Detach.md)|Rufen Sie diese Methode auf, um den Besitz eines Zeigers freizugeben.|  
|[CHeapPtrBase::Free](../Topic/CHeapPtrBase::Free.md)|Rufen Sie diese Methode auf, um ein Objekt zu löschen, das von zu `CHeapPtrBase` gezeigt wird.|  
|[CHeapPtrBase::ReallocateBytes](../Topic/CHeapPtrBase::ReallocateBytes.md)|Rufen Sie diese Methode auf, um Arbeitsspeicher neu belegen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHeapPtrBase::operator T\*](../Topic/CHeapPtrBase::operator%20T*.md)|Der Umwandlungsoperator.|  
|[CHeapPtrBase::operator &](../Topic/CHeapPtrBase::operator%20&.md)|Der &\-Operator.|  
|[CHeapPtrBase::operator \-\>](../Topic/CHeapPtrBase::operator%20-%3E.md)|Der Operator Zeiger\-auf\-Member.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CHeapPtrBase::m\_pData](../Topic/CHeapPtrBase::m_pData.md)|Die Zeigerdatenmembervariable.|  
  
## Hinweise  
 Diese Klasse bildet die Grundlage für einige intelligente Heapzeigerklassen.  Die abgeleiteten Klassen beispielsweise [CHeapPtr](../../atl/reference/cheapptr-class.md) und [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), fügen eigene Konstruktoren und Operatoren hinzu.  Siehe diese Klassen für Implementierungsbeispiele.  
  
## Anforderungen  
 **Header:** atlcore.h  
  
## Siehe auch  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr Class](../../atl/reference/ccomheapptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)