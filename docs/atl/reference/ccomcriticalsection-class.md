---
title: "CComCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComCriticalSection"
  - "CComCriticalSection"
  - "ATL::CComCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCriticalSection class"
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnittsobjekts bereit.  
  
## Syntax  
  
```  
  
class CComCriticalSection  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComCriticalSection::CComCriticalSection](../Topic/CComCriticalSection::CComCriticalSection.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComCriticalSection::Init](../Topic/CComCriticalSection::Init.md)|Erstellt und initialisiert ein kritisches Abschnittsobjekt.|  
|[CComCriticalSection::Lock](../Topic/CComCriticalSection::Lock.md)|Ruft den Besitzer des kritischen Abschnittsobjekts.|  
|[CComCriticalSection::Term](../Topic/CComCriticalSection::Term.md)|Gibt die Systemressourcen frei, die vom kritischen Abschnittsobjekt verwendet werden.|  
|[CComCriticalSection::Unlock](../Topic/CComCriticalSection::Unlock.md)|Gibt den Besitzer des kritischen Abschnittsobjekts frei.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComCriticalSection::m\_sec](../Topic/CComCriticalSection::m_sec.md)|Ein **CRITICAL\_SECTION**\-Objekt.|  
  
## Hinweise  
 `CComCriticalSection` ist ähnlich, [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) zu erstellen, außer dass Sie müssen den kritischen Abschnitt explizit initialisieren und herausgeben.  
  
 In der Regel verwenden Sie `CComCriticalSection` durch den Namen `typedef`[CriticalSection](../Topic/CComMultiThreadModel::CriticalSection.md).  Dies `CComCriticalSection` Namensverweise, wenn [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwendet wird.  
  
 Siehe [CComCritSecLock\-Klasse](../../atl/reference/ccomcritseclock-class.md), damit eine sicherere Methode diese Klasse als verwendet, `Lock` und `Unlock` direkt aufgerufen.  
  
## Anforderungen  
 **Header:**  atlcore.h  
  
## Siehe auch  
 [CComFakeCriticalSection Class](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComCritSecLock Class](../../atl/reference/ccomcritseclock-class.md)