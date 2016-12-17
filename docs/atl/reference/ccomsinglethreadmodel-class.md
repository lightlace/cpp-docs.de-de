---
title: "CComSingleThreadModel Class"
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
  - "ATL.CComSingleThreadModel"
  - "CComSingleThreadModel"
  - "ATL::CComSingleThreadModel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSingleThreadModel class"
  - "single-threaded applications"
  - "single-threaded applications, ATL"
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CComSingleThreadModel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Erhöhen und Verringern des Werts einer Variablen bereit.  
  
## Syntax  
  
```  
  
class CComSingleThreadModel  
  
```  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CComSingleThreadModel::AutoCriticalSection](../Topic/CComSingleThreadModel::AutoCriticalSection.md)|Verweisklasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComSingleThreadModel::CriticalSection](../Topic/CComSingleThreadModel::CriticalSection.md)|Verweisklasse `CComFakeCriticalSection`.|  
|[CComSingleThreadModel::ThreadModelNoCS](../Topic/CComSingleThreadModel::ThreadModelNoCS.md)|Verweist auf `CComSingleThreadModel`.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComSingleThreadModel::Decrement](../Topic/CComSingleThreadModel::Decrement.md)|Dekrementiert den Wert der angegebenen Variablen.  Diese Implementierung ist nicht threadsicher.|  
|[CComSingleThreadModel::Increment](../Topic/CComSingleThreadModel::Increment.md)|Inkrementiert den Wert der angegebenen Variablen.  Diese Implementierung ist nicht threadsicher.|  
  
## Hinweise  
 `CComSingleThreadModel` stellt Methoden zum Erhöhen und Verringern des Werts einer Variablen bereit.  Anders als [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) sind diese Methoden nicht threadsicher.  
  
 In der Regel verwenden Sie `CComSingleThreadModel` durch einen von zwei `typedef` Namen, entweder [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) oder [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  Die Klasse, die von jedes `typedef` verwiesen wird, hängt vom verwendeten Threadingmodell, wie in der folgenden Tabelle aus:  
  
|typedef|Einzelnes Threadingmodell|Apartmentthreadingmodell|Freethreadmodell|  
|-------------|-------------------------------|------------------------------|----------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S\=`CComSingleThreadModel`; M\=`CComMultiThreadModel`  
  
 `CComSingleThreadModel` selbst definiert drei `typedef` Namen.  `ThreadModelNoCS` Verweise `CComSingleThreadModel`.  `AutoCriticalSection` und `CriticalSection` Verweis Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), der die leeren Methoden bereitstellt, die mit dem Abrufen und dem Freigeben des Besitzes eines kritischen Abschnitts zugeordnet werden.  
  
## Anforderungen  
 **Header:**  atlbase.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)