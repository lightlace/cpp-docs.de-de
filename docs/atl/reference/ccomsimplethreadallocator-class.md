---
title: "CComSimpleThreadAllocator Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComSimpleThreadAllocator"
  - "ATL::CComSimpleThreadAllocator"
  - "ATL.CComSimpleThreadAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL threads"
  - "ATL threads, Reservieren"
  - "CComSimpleThreadAllocator class"
  - "Threading [ATL], selecting threads"
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComSimpleThreadAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse verwaltet Thread\-Auswahl für die Klasse `CComAutoThreadModule`.  
  
## Syntax  
  
```  
  
class CComSimpleThreadAllocator  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComSimpleThreadAllocator::GetThread](../Topic/CComSimpleThreadAllocator::GetThread.md)|Wählt einen Thread aus.|  
  
## Hinweise  
 `CComSimpleThreadAllocator` verwaltet Thread\-Auswahl für [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  `CComSimpleThreadAllocator::GetThread` wird einfach durch jeden Thread diese und gibt die folgenden in der Sequenz zurück.  
  
## Anforderungen  
 **Header:**  atlbase.h  
  
## Siehe auch  
 [CComApartment Class](../../atl/reference/ccomapartment-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)