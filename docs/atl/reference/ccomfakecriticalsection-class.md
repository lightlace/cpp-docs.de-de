---
title: "CComFakeCriticalSection Class"
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
  - "ATL.CComFakeCriticalSection"
  - "CComFakeCriticalSection"
  - "ATL::CComFakeCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComFakeCriticalSection class"
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CComFakeCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die bereit, die dieselben Methoden wie [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) stellt aber keinen kritischen Abschnitt.  
  
## Syntax  
  
```  
  
class CComFakeCriticalSection  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComFakeCriticalSection::Init](../Topic/CComFakeCriticalSection::Init.md)|Keine Auswirkung, da es keinen kritischen Abschnitt gibt.|  
|[CComFakeCriticalSection::Lock](../Topic/CComFakeCriticalSection::Lock.md)|Keine Auswirkung, da es keinen kritischen Abschnitt gibt.|  
|[CComFakeCriticalSection::Term](../Topic/CComFakeCriticalSection::Term.md)|Keine Auswirkung, da es keinen kritischen Abschnitt gibt.|  
|[CComFakeCriticalSection::Unlock](../Topic/CComFakeCriticalSection::Unlock.md)|Keine Auswirkung, da es keinen kritischen Abschnitt gibt.|  
  
## Hinweise  
 `CComFakeCriticalSection` führt die Methoden, die in [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) gefunden werden.  stellt jedoch `CComFakeCriticalSection` keinen kritischen Abschnitt; Daher gehen seine Methoden nichts.  
  
 In der Regel verwenden Sie `CComFakeCriticalSection` durch einen `typedef` Namen, entweder `AutoCriticalSection` oder `CriticalSection`.  Wenn [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), Verweis beider `typedef` Namen `CComFakeCriticalSection` verwendet werden.  Wenn sie [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwenden, verweisen darauf [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) und `CComCriticalSection`, bzw.  
  
## Anforderungen  
 **Header:** atlcore.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)