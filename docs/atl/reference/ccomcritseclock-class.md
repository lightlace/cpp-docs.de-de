---
title: "CComCritSecLock Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComCritSecLock"
  - "ATL.CComCritSecLock<TLock>"
  - "ATL::CComCritSecLock<TLock>"
  - "ATL.CComCritSecLock"
  - "CComCritSecLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCritSecLock class"
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComCritSecLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Sperren und Entsperren eines das kritischen Abschnittsobjekts bereit.  
  
## Syntax  
  
```  
  
      template<  
   class TLock  
> class CComCritSecLock  
```  
  
#### Parameter  
 *TLock*  
 Das zu sperrende Objekt und entsperrt wurden.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](../Topic/CComCritSecLock::CComCritSecLock.md)|Der \-Konstruktor.|  
|[CComCritSecLock::~CComCritSecLock](../Topic/CComCritSecLock::~CComCritSecLock.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComCritSecLock::Lock](../Topic/CComCritSecLock::Lock.md)|Rufen Sie diese Methode auf, um das kritischen Abschnittsobjekt zu sperren.|  
|[CComCritSecLock::Unlock](../Topic/CComCritSecLock::Unlock.md)|Rufen Sie diese Methode auf, um das kritischen Abschnittsobjekt zu entsperren.|  
  
## Hinweise  
 Verwenden Sie diese Klasse, um Objekte auf eine Weise als mit [CComCriticalSections\-Klasse](../../atl/reference/ccomcriticalsection-class.md) oder [CComAutoCriticalSections\-Klasse](../../atl/reference/ccomautocriticalsection-class.md) zu sperren und zu entsperren.  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection Class](../../atl/reference/ccomautocriticalsection-class.md)