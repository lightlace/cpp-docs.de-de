---
title: "CComAutoDeleteCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComAutoDeleteCriticalSection"
  - "CComAutoDeleteCriticalSection"
  - "ATL::CComAutoDeleteCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAutoDeleteCriticalSection class"
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CComAutoDeleteCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnittsobjekts bereit.  
  
## Syntax  
  
```  
  
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection  
  
```  
  
## Hinweise  
 `CComAutoDeleteCriticalSection` wird von der Klasse abgeleitet [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md).  überschreibt jedoch `CComAutoDeleteCriticalSection` die [Begriff](../Topic/CComSafeDeleteCriticalSection::Term.md)\-Methode zu `private` Zugriff, der Bereinigung des internen Speichers anweisen, die auftreten, wenn Instanzen dieser Klasse den Gültigkeitsbereich verlassen oder explizit aus dem Arbeitsspeicher gelöscht werden.  
  
 Diese Klasse stellt keine zusätzlichen Methoden zu ihrer Basisklasse vor.  Siehe [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) und [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) weitere Informationen zu Hilfsklassen des kritischen Abschnitts.  
  
## Vererbungshierarchie  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## Anforderungen  
 **Header:**  atlcore.h  
  
## Siehe auch  
 [CComSafeDeleteCriticalSection Class](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)