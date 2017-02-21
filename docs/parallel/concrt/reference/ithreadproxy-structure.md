---
title: "IThreadProxy-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IThreadProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IThreadProxy-Struktur"
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# IThreadProxy-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Abstraktion für einen Thread der Ausführung.  Abhängig von dem von Ihnen erstellten `SchedulerType`\-Richtlinienschlüssel des Planers, gewährt der Ressourcen\-Manager eine Threadproxy, der entweder von einem regulären Win32\-Thread oder einem im Benutzermodus planbaren \(UMS\) Thread unterstützt wird.  UMS\-Threads werden auf 64\-Bit\-Betriebssystemen mit Version Windows 7 und höher unterstützt.  
  
## Syntax  
  
```  
struct IThreadProxy;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IThreadProxy::GetId\-Methode](../Topic/IThreadProxy::GetId%20Method.md)|Gibt einen eindeutigen Bezeichner für den Threadproxy zurück.|  
|[IThreadProxy::SwitchOut\-Methode](../Topic/IThreadProxy::SwitchOut%20Method.md)|Hebt die Zuordnung des Kontexts vom zugrunde liegenden virtuellen Prozessorstamm auf.|  
|[IThreadProxy::SwitchTo\-Methode](../Topic/IThreadProxy::SwitchTo%20Method.md)|Führt einen kooperativen Kontextwechsel vom derzeit ausgeführten Kontext zu einem anderen durch.|  
|[IThreadProxy::YieldToSystem\-Methode](../Topic/IThreadProxy::YieldToSystem%20Method.md)|Bewirkt, dass der aufrufende Thread die Ausführung an einen anderen Thread übergibt, der auf dem aktuellen Prozessor ausgeführt werden kann.  Das Betriebssystem wählt den nächsten Thread für die Ausführung aus.|  
  
## Hinweise  
 Threadproxys werden mit Ausführungskontexten verbunden, die von der Schnittstelle `IExecutionContext` als Mittel dargestellt werden, die Arbeit weiterzuleiten.  
  
## Vererbungshierarchie  
 `IThreadProxy`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IExecutionContext\-Struktur](../../../parallel/concrt/reference/iexecutioncontext-structure.md)   
 [IScheduler\-Struktur](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IVirtualProcessorRoot\-Struktur](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)