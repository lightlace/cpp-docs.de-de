---
title: "CComMultiThreadModelNoCS Class"
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
  - "ATL::CComMultiThreadModelNoCS"
  - "CComMultiThreadModelNoCS"
  - "ATL.CComMultiThreadModelNoCS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Multithreading"
  - "CComMultiThreadModelNoCS class"
  - "Threading [ATL]"
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
caps.latest.revision: 18
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CComMultiThreadModelNoCS Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComMultiThreadModelNoCS` stellt threadsichere Methoden zum Erhöhen und Verringern des Werts einer Variablen, ohne Sperre des kritischen Abschnitts oder das Entsperren von Funktionen bereit.  
  
## Syntax  
  
```  
  
class CComMultiThreadModelNoCS  
  
```  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](../Topic/CComMultiThreadModelNoCS::AutoCriticalSection.md)|Verweisklasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComMultiThreadModelNoCS::CriticalSection](../Topic/CComMultiThreadModelNoCS::CriticalSection.md)|Verweisklasse `CComFakeCriticalSection`.|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](../Topic/CComMultiThreadModelNoCS::ThreadModelNoCS.md)|Verweisklasse `CComMultiThreadModelNoCS`.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::Decrement](../Topic/CComMultiThreadModelNoCS::Decrement.md)|\(Statisch\) verringert den Wert der angegebenen Variablen in einer threadsicheren Weise.|  
|[CComMultiThreadModelNoCS::Increment](../Topic/CComMultiThreadModelNoCS::Increment.md)|\(Statisch\) erhöht den Wert der angegebenen Variablen in einer threadsicheren Weise.|  
  
## Hinweise  
 `CComMultiThreadModelNoCS` ist zu [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) insofern ähnlich, dass es threadsichere Methoden zum Erhöhen und Verringern einer Variablen bereitstellt.  Wenn Sie jedoch eine Klasse des kritischen Abschnitts durch `CComMultiThreadModelNoCS` verweisen, sind Methoden wie `Lock` und `Unlock` nichts.  
  
 In der Regel verwenden Sie `CComMultiThreadModelNoCS` durch den Namen `ThreadModelNoCS``typedef`.  Dies `typedef` wird in `CComMultiThreadModelNoCS`, in `CComMultiThreadModel` und in [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) definiert.  
  
> [!NOTE]
>  Die globalen `typedef` Namen [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) und [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md) verweisen nicht `CComMultiThreadModelNoCS`.  
  
 Zusätzlich zu `ThreadModelNoCS` definiert `CComMultiThreadModelNoCS``AutoCriticalSection` und `CriticalSection`.  Zugeordnete Verweis dieser letzten zwei `typedef` Namen [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), der leere Methoden bereitstellt, mit dem Abrufen und dem Freigeben eines kritischen Abschnitts zu.  
  
## Anforderungen  
 **Header:**  atlbase.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)