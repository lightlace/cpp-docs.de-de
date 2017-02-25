---
title: "CStringElementTraitsI Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CStringElementTraitsI"
  - "CStringElementTraitsI"
  - "ATL.CStringElementTraitsI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringElementTraitsI class"
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CStringElementTraitsI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die statischen Funktionen bereit, die den Zeichenfolgen verknüpft werden, die in den Auflistungsklassenobjekten gespeichert werden.  Es ist zu [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) ähnlich, jedoch führt Vergleiche, bei denen nicht zwischen Groß\- und Kleinschreibung unterschieden wird, aus.  
  
## Syntax  
  
```  
  
      template<  
   typename T,  
   class CharTraits = CDefaultCharTraits< T::XCHAR >  
>  
class CStringElementTraitsI : public CElementTraitsBase< T >  
```  
  
#### Parameter  
 `T`  
 Der Typ von den in der Auflistung gespeichert werden, Daten.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CStringElementTraitsI::INARGTYPE](../Topic/CStringElementTraitsI::INARGTYPE.md)|Der für das Hinzufügen von Elementen zum Auflistungsklassenobjekt Datentyp, zu verwenden.|  
|[CStringElementTraitsI::OUTARGTYPE](../Topic/CStringElementTraitsI::OUTARGTYPE.md)|Der für das Abrufen von Elementen vom Datentyp, Auflistungsklassenobjekt zu verwenden.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CStringElementTraitsI::CompareElements](../Topic/CStringElementTraitsI::CompareElements.md)|Rufen Sie diese statische Funktion auf, um zwei Zeichenfolgenelemente auf Gleichheit zu ignorieren und Unterschiede bei.|  
|[CStringElementTraitsI::CompareElementsOrdered](../Topic/CStringElementTraitsI::CompareElementsOrdered.md)|Rufen Sie diese statische Funktion auf, um zwei Zeichenfolgenelemente zu vergleichen und Unterschiede bei ignorieren.|  
|[CStringElementTraitsI::Hash](../Topic/CStringElementTraitsI::Hash.md)|Rufen Sie diese statische Funktion auf, um einen Hashwert für das angegebene Zeichenfolgenelement zu berechnen.|  
  
## Hinweise  
 Diese Klasse stellt statische Funktionen für Zeichenfolgen und zum Erstellen eines Hashwerts bereit.  Diese Funktionen sind nützlich, wenn eine Auflistungsklasse, die zeichenfolgenbasierte zum Speichern von Daten verwendet.  Verwenden Sie [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), wenn die Zeichenfolgenobjekte, mit behandelt als Verweise sein sollen.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Vererbungshierarchie  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [CElementTraitsBase Class](../../atl/reference/celementtraitsbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CStringElementTraits Class](../../atl/reference/cstringelementtraits-class.md)