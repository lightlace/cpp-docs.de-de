---
title: "CurrentScheduler-Klasse"
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
  - "concrt/concurrency::CurrentScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CurrentScheduler-Klasse"
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CurrentScheduler-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Abstraktion für den aktuellen Planer dar, der dem aufrufenden Kontext zugeordnet ist.  
  
## Syntax  
  
```  
class CurrentScheduler;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[CurrentScheduler::Create\-Methode](../Topic/CurrentScheduler::Create%20Method.md)|Erstellt einen neuen Planer, dessen Verhalten mit dem `_Policy`\-Parameter beschrieben wird, und fügt ihn an den aufrufenden Kontext an.  Der neu erstellte Planer wird der aktuelle Planer für den aufrufenden Kontext.|  
|[CurrentScheduler::CreateScheduleGroup\-Methode](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md)|Überladen.  Erstellt eine neue Planungsgruppe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet ist.  Die Version, die den Parameter akzeptiert `_Placement`, verursacht Aufgaben innerhalb der neu erstellten Planungsgruppe, zum Ausführung am Speicherort beeinflusst werden, dass durch diesen Parameter angegeben.|  
|[CurrentScheduler::Detach\-Methode](../Topic/CurrentScheduler::Detach%20Method.md)|Trennt den aktuellen Planer vom aufrufenden Kontext und stellt, sofern vorhanden, den zuvor angefügten Planer als aktuellen Planer wieder her.  Nach der Methodenrückgabe, wird der aufrufende Kontext dann vom Planer verwaltet, der zuvor den Kontext entweder mit `CurrentScheduler::Create` oder `Scheduler::Attach`\-Methode zugeordnet wurde.|  
|[CurrentScheduler::Get\-Methode](../Topic/CurrentScheduler::Get%20Method.md)|Gibt einen Zeiger auf den Planer zurück, der dem aufrufenden Kontext \(auch aktueller Planer genannt\) zugeordnet ist.|  
|[CurrentScheduler::GetNumberOfVirtualProcessors\-Methode](../Topic/CurrentScheduler::GetNumberOfVirtualProcessors%20Method.md)|Gibt die aktuelle Anzahl virtueller Prozessoren für den dem aufrufenden Kontext zugeordneten Planer zurück.|  
|[CurrentScheduler::GetPolicy\-Methode](../Topic/CurrentScheduler::GetPolicy%20Method.md)|Gibt eine Kopie der Richtlinie zurück, mit der der aktuelle Planer erstellt wurde.|  
|[CurrentScheduler::Id\-Methode](../Topic/CurrentScheduler::Id%20Method.md)|Gibt einen eindeutigen Bezeichner für den aktuellen Planer zurück.|  
|[CurrentScheduler::IsAvailableLocation\-Methode](../Topic/CurrentScheduler::IsAvailableLocation%20Method.md)|Bestimmt, ob eine bestimmte Position im aktuellen Planer verfügbar ist.|  
|[CurrentScheduler::RegisterShutdownEvent\-Methode](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md)|Veranlasst, dass das im `_ShutdownEvent`\-Parameter übergebene Windows\-Ereignishandle signalisiert wird, wenn der dem aktuellen Kontext zugeordnete Planer sich herunterfährt und zerstört.  Zur Zeit, wenn das Ereignis signalisiert wird, ist alle Arbeit, die für den Planer geplant wurde, abgeschlossen.  Mehrere Herunterfahrereignisse können über diese Methode registriert werden.|  
|[CurrentScheduler::ScheduleTask\-Methode](../Topic/CurrentScheduler::ScheduleTask%20Method.md)|Überladen.  Plant eine einfache Aufgabe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet ist.  Die einfache Aufgabe wird in einer Planungsgruppe platziert, die durch die Laufzeit bestimmt wird.  Die Version, die den `_Placement`\-Parameter akzeptiert, durch die die Aufgabe, zum Ausführung an der angegebenen Position beeinflusst werden.|  
  
## Hinweise  
 Wenn dem aufrufenden Kontext kein Planer \(siehe [Planer](../../../parallel/concrt/reference/scheduler-class.md)\) zugeordnet ist, veranlassen viele Methoden innerhalb der `CurrentScheduler`\-Klasse, dass der Standardplaner des Prozesses angefügt wird.  Dies bedeutet möglicherweise auch, dass der Standardplaner des Prozesses während eines solchen Aufrufs erstellt wird.  
  
## Vererbungshierarchie  
 `CurrentScheduler`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler\-Klasse](../../../parallel/concrt/reference/scheduler-class.md)   
 [PolicyElementKey\-Enumeration](../Topic/PolicyElementKey%20Enumeration.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)