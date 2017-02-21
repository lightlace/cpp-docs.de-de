---
title: "IUMSCompletionList-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSCompletionList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSCompletionList-Struktur"
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# IUMSCompletionList-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt eine UMS\-Vervollständigungsliste dar.  Wenn ein UMS\-Thread blockiert wird, wird der festgelegte Planungskontext des Planers weitergeleitet, um zu entscheiden, was für den Stamm des zugrunde liegenden virtuellen Prozessors geplant werden soll, während der ursprüngliche Thread blockiert ist.  Wenn die Blockierung des ursprünglichen Threads aufgehoben wird, stellt das Betriebssystem ihn in die Warteschlange für die Vervollständigungsliste, auf die über diese Schnittstelle zugegriffen werden kann.  Der Planer kann die Vervollständigungsliste für den festgelegten Planungskontext oder eine beliebige andere Stelle abfragen, in der er nach Arbeit sucht.  
  
## Syntax  
  
```  
struct IUMSCompletionList;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IUMSCompletionList::GetUnblockNotifications\-Methode](../Topic/IUMSCompletionList::GetUnblockNotifications%20Method.md)|Ruft eine Kette von `IUMSUnblockNotification`\-Schnittstellen ab, die die Ausführungskontexte darstellen, deren zugeordnete Threadproxys seit dem letzten Aufruf dieser Methode nicht mehr blockieren.|  
  
## Hinweise  
 Ein Planer muss genau darauf achten, welche Aktionen durchgeführt werden, nachdem diese Schnittstelle zum Entfernen von Elementen aus der Vervollständigungsliste verwendet wurde.  Die Elemente sollten auf der Liste ausführbarer Kontexte des Planers platziert werden, und es soll so schnell wie möglich darauf zugegriffen werden können.  Es ist möglich, dass einem der aus der Warteschlange entfernten Elemente der Besitz einer beliebigen Sperre übertragen wurde.  Der Planer kann keine beliebigen Funktionsaufrufe ausführen, die möglicherweise zwischen dem Aufruf zum Entfernen von Elementen aus der Warteschlange und der Platzierung dieser Elemente in einer Liste zu blockieren, auf die im Allgemeinen von innerhalb des Planers zugegriffen werden kann.  
  
## Vererbungshierarchie  
 `IUMSCompletionList`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler\-Struktur](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [IUMSUnblockNotification\-Struktur](../../../parallel/concrt/reference/iumsunblocknotification-structure.md)