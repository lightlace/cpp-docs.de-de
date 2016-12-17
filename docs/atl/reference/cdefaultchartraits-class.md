---
title: "CDefaultCharTraits Class"
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
  - "CDefaultCharTraits"
  - "ATL::CDefaultCharTraits<T>"
  - "ATL.CDefaultCharTraits"
  - "ATL.CDefaultCharTraits<T>"
  - "ATL::CDefaultCharTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultCharTraits class"
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CDefaultCharTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt zwei statische Funktionen zum Konvertieren von Zeichen zwischen Groß\- und Kleinschreibung bereit.  
  
## Syntax  
  
```  
  
      template <  
   typename T  
>  
class CDefaultCharTraits  
```  
  
#### Parameter  
 `T`  
 Der Typ von den in der Auflistung gespeichert werden, Daten.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDefaultCharTraits::CharToLower](../Topic/CDefaultCharTraits::CharToLower.md)|\(Statisch\) Rufen Sie diese Funktion auf, um ein Zeichen in Großbuchstaben konvertiert.|  
|[CDefaultCharTraits::CharToUpper](../Topic/CDefaultCharTraits::CharToUpper.md)|\(Statisch\) Rufen Sie diese Funktion auf, um ein Zeichen in Kleinbuchstaben konvertiert.|  
  
## Hinweise  
 Diese Klasse stellt Funktionen, die von der Klasse [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) verwendet werden.  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)