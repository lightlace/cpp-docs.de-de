---
title: "CElementTraitsBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CElementTraitsBase"
  - "ATL::CElementTraitsBase"
  - "ATL.CElementTraitsBase<T>"
  - "ATL::CElementTraitsBase<T>"
  - "ATL.CElementTraitsBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CElementTraitsBase class"
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CElementTraitsBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Standard Kopie und Verschiebungsmethoden für eine Auflistungsklasse bereit.  
  
## Syntax  
  
```  
  
      template<  
   typename T  
>  
class CElementTraitsBase  
```  
  
#### Parameter  
 `T`  
 Der Typ von den in der Auflistung gespeichert werden, Daten.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CElementTraitsBase::INARGTYPE](../Topic/CElementTraitsBase::INARGTYPE.md)|Der für das Hinzufügen von Elementen zum Auflistungsklassenobjekt Datentyp, zu verwenden.|  
|[CElementTraitsBase::OUTARGTYPE](../Topic/CElementTraitsBase::OUTARGTYPE.md)|Der für das Abrufen von Elementen vom Datentyp, Auflistungsklassenobjekt zu verwenden.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CElementTraitsBase::CopyElements](../Topic/CElementTraitsBase::CopyElements.md)|Rufen Sie diese Methode auf, um die Elemente zu kopieren, die in einem Auflistungsklassenobjekt gespeichert werden.|  
|[CElementTraitsBase::RelocateElements](../Topic/CElementTraitsBase::RelocateElements.md)|Rufen Sie diese Methode auf, um die Elemente zu verschieben, die in einem Auflistungsklassenobjekt gespeichert werden.|  
  
## Hinweise  
 Diese Basisklasse definiert Methoden für das Kopieren und Verschieben von Elementen in einer Auflistungsklasse.  Es wird durch die Klassen [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) und [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) verwendet.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)