---
title: "CStringElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CStringElementTraits<T>"
  - "ATL::CStringElementTraits<T>"
  - "CStringElementTraits"
  - "ATL.CStringElementTraits"
  - "ATL::CStringElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringElementTraits class"
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CStringElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die statischen Funktionen, die von der Auflistungsklassen verwendet werden, die `CString`\-Objekte speichern.  
  
## Syntax  
  
```  
  
      template<  
   typename T   
>  
class CStringElementTraits  
```  
  
#### Parameter  
 `T`  
 Der Typ von den in der Auflistung gespeichert werden, Daten.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](../Topic/CStringElementTraits::INARGTYPE.md)|Der für das Hinzufügen von Elementen zum Auflistungsklassenobjekt Datentyp, zu verwenden.|  
|[CStringElementTraits::OUTARGTYPE](../Topic/CStringElementTraits::OUTARGTYPE.md)|Der für das Abrufen von Elementen vom Datentyp, Auflistungsklassenobjekt zu verwenden.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](../Topic/CStringElementTraits::CompareElements.md)|\(Statisch\) rufen Sie diese Funktion auf, um zwei Zeichenfolgenelemente auf Gleichheit zu.|  
|[CStringElementTraits::CompareElementsOrdered](../Topic/CStringElementTraits::CompareElementsOrdered.md)|\(Statisch\) rufen Sie diese Funktion auf, um zwei Zeichenfolgenelemente zu vergleichen.|  
|[CStringElementTraits::CopyElements](../Topic/CStringElementTraits::CopyElements.md)|\(Statisch\) rufen Sie diese Funktion auf, um `CString`\-Elemente zu kopieren, die in einem Auflistungsklassenobjekt gespeichert werden.|  
|[CStringElementTraits::Hash](../Topic/CStringElementTraits::Hash.md)|\(Statisch\) rufen Sie diese Funktion auf, um einen Hashwert für das angegebene Zeichenfolgenelement zu berechnen.|  
|[CStringElementTraits::RelocateElements](../Topic/CStringElementTraits::RelocateElements.md)|\(Statisch\) rufen Sie diese Funktion auf, um `CString`\-Elemente zu verschieben, die in einem Auflistungsklassenobjekt gespeichert werden.|  
  
## Hinweise  
 Diese Klasse stellt statische Funktionen zum Kopieren, Verschieben und das Vergleichen von Zeichenfolgen und zum Erstellen eines Hashwerts bereit.  Diese Funktionen sind nützlich, wenn eine Auflistungsklasse, die zeichenfolgenbasierte zum Speichern von Daten verwendet.  Verwendung [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), wenn Vergleiche, bei denen nicht zwischen Groß\- und Kleinschreibung unterschieden wird, erforderlich sind.  Verwenden Sie [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), wenn mit die Zeichenfolgenobjekte als Verweise verarbeitet werden sollen.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Anforderungen  
 **Header:** cstringt.h  
  
## Siehe auch  
 [CElementTraitsBase Class](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI Class](../../atl/reference/cstringelementtraitsi-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)