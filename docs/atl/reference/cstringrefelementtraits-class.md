---
title: "CStringRefElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStringRefElementTraits"
  - "ATL.CStringRefElementTraits"
  - "ATL::CStringRefElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringRefElementTraits class"
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CStringRefElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die statischen Funktionen bereit, die den Zeichenfolgen verknüpft werden, die in den Auflistungsklassenobjekten gespeichert werden.  Mit die Zeichenfolgenobjekte werden als Verweise verarbeitet.  
  
## Syntax  
  
```  
  
      template<   
   typename T  
>  
class CStringRefElementTraits : public CElementTraitsBase< T >  
```  
  
#### Parameter  
 `T`  
 Der Typ von den in der Auflistung gespeichert werden, Daten.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](../Topic/CStringRefElementTraits::CompareElements.md)|Rufen Sie diese statische Funktion auf, um zwei Zeichenfolgenelemente auf Gleichheit zu.|  
|[CStringRefElementTraits::CompareElementsOrdered](../Topic/CStringRefElementTraits::CompareElementsOrdered.md)|Rufen Sie diese statische Funktion auf, um zwei Zeichenfolgenelemente zu vergleichen.|  
|[CStringRefElementTraits::Hash](../Topic/CStringRefElementTraits::Hash.md)|Rufen Sie diese statische Funktion auf, um einen Hashwert für das angegebene Zeichenfolgenelement zu berechnen.|  
  
## Hinweise  
 Diese Klasse stellt statische Funktionen für Zeichenfolgen und zum Erstellen eines Hashwerts bereit.  Diese Funktionen sind nützlich, wenn eine Auflistungsklasse, die zeichenfolgenbasierte zum Speichern von Daten verwendet.  Anders als [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) und [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) bewirkt `CStringRefElementTraits` die `CString`\-Argumente, als **const CString&** Verweise übergeben werden.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Vererbungshierarchie  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [CElementTraitsBase Class](../../atl/reference/celementtraitsbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)