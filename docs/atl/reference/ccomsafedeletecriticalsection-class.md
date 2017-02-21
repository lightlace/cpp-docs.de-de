---
title: "CComSafeDeleteCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComSafeDeleteCriticalSection"
  - "ATL::CComSafeDeleteCriticalSection"
  - "ATL.CComSafeDeleteCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeDeleteCriticalSection class"
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CComSafeDeleteCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnittsobjekts bereit.  
  
## Syntax  
  
```  
  
class CComSafeDeleteCriticalSection : public CComCriticalSection  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection.md)|Der \-Konstruktor.|  
|[CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::Init](../Topic/CComSafeDeleteCriticalSection::Init.md)|Erstellt und initialisiert ein kritisches Abschnittsobjekt.|  
|[CComSafeDeleteCriticalSection::Lock](../Topic/CComSafeDeleteCriticalSection::Lock.md)|Ruft den Besitzer des kritischen Abschnittsobjekts.|  
|[CComSafeDeleteCriticalSection::Term](../Topic/CComSafeDeleteCriticalSection::Term.md)|Gibt die Systemressourcen frei, die vom kritischen Abschnittsobjekt verwendet werden.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_bInitialized](../Topic/CComSafeDeleteCriticalSection::m_bInitialized.md)|Kennzeichnet, ob das interne **CRITICAL\_SECTION**\-Objekt initialisiert wurde.|  
  
## Hinweise  
 `CComSafeDeleteCriticalSection` wird von der Klasse abgeleitet [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  stellt jedoch `CComSafeDeleteCriticalSection` zusätzliche Sperrvorrichtungen über [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  
  
 Wenn eine Instanz von `CComSafeDeleteCriticalSection` im Gültigkeitsbereich befindet oder explizit aus dem Arbeitsspeicher gelöscht wird, wird das zugrunde liegende kritischen Abschnittsobjekt automatisch in bereinigt, wenn es noch gültig ist.  Außerdem beendet die [CComSafeDeleteCriticalSection::Term](../Topic/CComSafeDeleteCriticalSection::Term.md)\-Methode ordnungsgemäß, wenn das zugrunde liegende kritischen Abschnittsobjekt noch nicht zugeordnet wurde oder bereits vom Arbeitsspeicher freigegeben wurde.  
  
 Siehe [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) weitere Informationen zu Hilfsklassen des kritischen Abschnitts.  
  
## Vererbungshierarchie  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## Anforderungen  
 **Header:**  atlcore.h  
  
## Siehe auch  
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)