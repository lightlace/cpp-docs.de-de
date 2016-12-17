---
title: "CComApartment Class"
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
  - "ATL::CComApartment"
  - "CComApartment"
  - "ATL.CComApartment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "apartments in ATL EXE modules"
  - "CComApartment class"
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CComApartment Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Unterstützung für das Verwalten eines Apartments in einem EXE\-Modul mit Threadpool.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CComApartment  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComApartment::CComApartment](../Topic/CComApartment::CComApartment.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComApartment::Apartment](../Topic/CComApartment::Apartment.md)|Markiert die Startadresse des Threads.|  
|[CComApartment::GetLockCount](../Topic/CComApartment::GetLockCount.md)|Gibt die aktuelle Sperrenanzahl des Threads zurück.|  
|[CComApartment::Lock](../Topic/CComApartment::Lock.md)|Inkrementiert die Sperrenanzahl des Threads.|  
|[CComApartment::Unlock](../Topic/CComApartment::Unlock.md)|Dekrementiert die Sperrenanzahl des Threads.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComApartment::m\_dwThreadID](../Topic/CComApartment::m_dwThreadID.md)|Enthält den Bezeichner des Threads.|  
|[CComApartment::m\_hThread](../Topic/CComApartment::m_hThread.md)|Enthält das Handle des Threads.|  
|[CComApartment::m\_nLockCnt](../Topic/CComApartment::m_nLockCnt.md)|Enthält die aktuelle Sperrenanzahl des Threads.|  
  
## Hinweise  
 `CComApartment` wird durch [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) verwendet, um ein Apartment in einem Threadpool mit EXE\-Modul zu verwalten.  `CComApartment` stellt Methoden zum Erhöhen und Verringern der Sperrenanzahl in einem Thread bereit.  
  
## Anforderungen  
 **Header:**  atlbase.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)