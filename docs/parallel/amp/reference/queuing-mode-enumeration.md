---
title: "queuing_mode-Enumeration"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::queuing_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queuing_mode-Enumeration"
ms.assetid: 8c641054-906d-40b3-bbb4-f62af9356a14
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# queuing_mode-Enumeration
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Gibt die Modi für das Hinzufügen zur Warteschlange an, die auf dem Beschleuniger unterstützt werden.  
  
## Syntax  
  
```  
enum queuing_mode;  
```  
  
## Member  
  
### Werte  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`queuing_mode_immediate`|Ein Queuingmodus, der angibt, dass alle Befehle, beispielsweise [parallel\_for\_each\-Funktion \(C\+\+ AMP\)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md), zum entsprechenden Zugriffstastengerät gesendet werden, sobald sie zum Aufrufer zurückkehren.|  
|`queuing_mode_automatic`|Ein Queuingmodus, der angibt, dass Befehle in einer Befehlswarteschlange in die Warteschlange gestellt werden, die dem [accelerator\_view](../../../parallel/amp/reference/accelerator-view-class.md)\-Objekt entspricht.  Befehle werden an das Gerät gesendet, wenn der Befehl [accelerator\_view::flush](../Topic/accelerator_view::flush%20Method.md) aufgerufen wird.|  
  
## Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)