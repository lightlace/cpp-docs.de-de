---
title: "CComAutoCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComAutoCriticalSection"
  - "ATL::CComAutoCriticalSection"
  - "CComAutoCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAutoCriticalSection class"
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComAutoCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComAutoCriticalSection` stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnittsobjekts bereit.  
  
## Syntax  
  
```  
  
class CComAutoCriticalSection : public CComCriticalSection  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](../Topic/CComAutoCriticalSection::CComAutoCriticalSection.md)|Der \-Konstruktor.|  
|[CComAutoCriticalSection::~CComAutoCriticalSection](../Topic/CComAutoCriticalSection::~CComAutoCriticalSection.md)|Der Destruktor.|  
  
## Hinweise  
 `CComAutoCriticalSection` ist ähnlich, [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) zu erstellen, außer `CComAutoCriticalSection` automatisch das kritischen Abschnittsobjekt im Konstruktor initialisiert.  
  
 In der Regel verwenden Sie `CComAutoCriticalSection` durch den Namen `typedef`[AutoCriticalSection](../Topic/CComMultiThreadModel::AutoCriticalSection.md).  Dies `CComAutoCriticalSection` Namensverweise, wenn [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwendet wird.  
  
 Die `Init` und `Term`\-Methoden von [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) sind nicht verfügbar, wenn sie diese Klasse verwenden.  
  
## Vererbungshierarchie  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## Anforderungen  
 **Header:**  atlcore.h  
  
## Siehe auch  
 [CComFakeCriticalSection Class](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)