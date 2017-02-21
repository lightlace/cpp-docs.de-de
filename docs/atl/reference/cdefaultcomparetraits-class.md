---
title: "CDefaultCompareTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CDefaultCompareTraits<T>"
  - "ATL::CDefaultCompareTraits"
  - "ATL.CDefaultCompareTraits"
  - "ATL::CDefaultCompareTraits<T>"
  - "CDefaultCompareTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultCompareTraits class"
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CDefaultCompareTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse bietet Standardverhalten Elementvergleichsfunktionen.  
  
## Syntax  
  
```  
  
      template<  
   typename T  
>  
class CDefaultCompareTraits  
```  
  
#### Parameter  
 `T`  
 Der Typ von den in der Auflistung gespeichert werden, Daten.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](../Topic/CDefaultCompareTraits::CompareElements.md)|\(Statisch\) rufen Sie diese Funktion auf, um zwei Elemente auf Gleichheit zu.|  
|[CDefaultCompareTraits::CompareElementsOrdered](../Topic/CDefaultCompareTraits::CompareElementsOrdered.md)|\(Statisch\) rufen Sie diese Funktion auf, um das größere und wenig Element zu bestimmen.|  
  
## Hinweise  
 Diese Klasse enthält zwei statische Funktionen zum Vergleichen von Elementen, die in einem Auflistungsklassenobjekt gespeichert werden.  Diese Klasse wird von [CDefaultElementTraits\-Klasse](../../atl/reference/cdefaultelementtraits-class.md) verwendet.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)