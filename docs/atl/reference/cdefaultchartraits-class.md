---
title: "CDefaultCharTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
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