---
title: "CComMultiThreadModel Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComMultiThreadModel"
  - "ATL.CComMultiThreadModel"
  - "ATL::CComMultiThreadModel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Multithreading"
  - "CComMultiThreadModel class"
  - "Threading [ATL]"
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComMultiThreadModel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComMultiThreadModel` stellt threadsichere Methoden zum Erhöhen und Verringern des Werts einer Variablen bereit.  
  
## Syntax  
  
```  
  
class CComMultiThreadModel  
  
```  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CComMultiThreadModel::AutoCriticalSection](../Topic/CComMultiThreadModel::AutoCriticalSection.md)|Verweisklasse [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|  
|[CComMultiThreadModel::CriticalSection](../Topic/CComMultiThreadModel::CriticalSection.md)|Verweisklasse [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).|  
|[CComMultiThreadModel::ThreadModelNoCS](../Topic/CComMultiThreadModel::ThreadModelNoCS.md)|Verweisklasse [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComMultiThreadModel::Decrement](../Topic/CComMultiThreadModel::Decrement.md)|\(Statisch\) verringert den Wert der angegebenen Variablen in einer threadsicheren Weise.|  
|[CComMultiThreadModel::Increment](../Topic/CComMultiThreadModel::Increment.md)|\(Statisch\) erhöht den Wert der angegebenen Variablen in einer threadsicheren Weise.|  
  
## Hinweise  
 In der Regel verwenden Sie `CComMultiThreadModel` durch einen von zwei `typedef` Namen, entweder [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) oder [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  Die Klasse, die von jedes `typedef` verwiesen wird, hängt vom verwendeten Threadingmodell, wie in der folgenden Tabelle aus:  
  
|typedef|Einzelnes Threading|Apartmentthreading|Freethreading|  
|-------------|-------------------------|------------------------|-------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S\=`CComSingleThreadModel`; M\=`CComMultiThreadModel`  
  
 `CComMultiThreadModel` selbst definiert drei `typedef` Namen.  `AutoCriticalSection` und `CriticalSection` verweisen Klassen, die Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts bereitstellen.  `ThreadModelNoCS` Verweisklasse [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
## Anforderungen  
 **Header:**  atlbase.h  
  
## Siehe auch  
 [CComSingleThreadModel Class](../../atl/reference/ccomsinglethreadmodel-class.md)   
 [CComAutoCriticalSection Class](../../atl/reference/ccomautocriticalsection-class.md)   
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)