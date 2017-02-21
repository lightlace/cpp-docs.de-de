---
title: "Scheduler-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::Scheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Scheduler-Klasse"
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Scheduler-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Abstraktion für einen Concurrency Runtime\-Planer dar.  
  
## Syntax  
  
```  
class Scheduler;  
```  
  
## Member  
  
### Geschützte Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Scheduler::Scheduler\-Konstruktor](../Topic/Scheduler::Scheduler%20Constructor.md)|Ein Objekt der `Scheduler`\-Klasse kann nur mit Factorymethoden oder implizit erstellt werden.|  
|[Scheduler::~Scheduler\-Destruktor](../Topic/Scheduler::~Scheduler%20Destructor.md)|Ein Objekt der `Scheduler`\-Klasse wird implizit zerstört, sobald keine externen Verweise mehr vorhanden sind.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Scheduler::Attach\-Methode](../Topic/Scheduler::Attach%20Method.md)|Fügt den Planer an den aufrufenden Kontext an.  Nachdem diese Methode zurückgekehrt ist, wird der aufrufende Kontext vom Planer verwaltet, und der Planer wird der aktuelle Planer.|  
|[Scheduler::Create\-Methode](../Topic/Scheduler::Create%20Method.md)|Erstellt einen neuen Planer, dessen Verhalten vom `_Policy`\-Parameter beschrieben wird, platziert einen anfänglichen Verweis auf den Planer und gibt einen Zeiger darauf zurück.|  
|[Scheduler::CreateScheduleGroup\-Methode](../Topic/Scheduler::CreateScheduleGroup%20Method.md)|Überladen.  Erstellt eine neue Planungsgruppe innerhalb des Planers.  Die Version, die den Parameter akzeptiert `_Placement`, verursacht Aufgaben innerhalb der neu erstellten Planungsgruppe, zum Ausführung am Speicherort beeinflusst werden, dass durch diesen Parameter angegeben.|  
|[Scheduler::GetNumberOfVirtualProcessors\-Methode](../Topic/Scheduler::GetNumberOfVirtualProcessors%20Method.md)|Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer zurück.|  
|[Scheduler::GetPolicy\-Methode](../Topic/Scheduler::GetPolicy%20Method.md)|Gibt eine Kopie der Richtlinie zurück, mit der der Planer erstellt wurde.|  
|[Scheduler::Id\-Methode](../Topic/Scheduler::Id%20Method.md)|Gibt einen eindeutigen Bezeichner für den Planer zurück.|  
|[Scheduler::IsAvailableLocation\-Methode](../Topic/Scheduler::IsAvailableLocation%20Method.md)|Bestimmt, ob eine bestimmte Position im Planer verfügbar ist.|  
|[Scheduler::Reference\-Methode](../Topic/Scheduler::Reference%20Method.md)|Inkrementiert den Planerverweiszähler.|  
|[Scheduler::RegisterShutdownEvent\-Methode](../Topic/Scheduler::RegisterShutdownEvent%20Method.md)|Veranlasst, dass das im `_Event`\-Parameter übergebene Windows\-Ereignishandle signalisiert wird, wenn der Planer sich herunterfährt und zerstört.  Zur Zeit, wenn das Ereignis signalisiert wird, ist alle Arbeit, die für den Planer geplant wurde, abgeschlossen.  Mehrere Herunterfahrereignisse können über diese Methode registriert werden.|  
|[Scheduler::Release\-Methode](../Topic/Scheduler::Release%20Method.md)|Dekrementiert den Planerverweiszähler.|  
|[Scheduler::ResetDefaultSchedulerPolicy\-Methode](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md)|Setzt die Standardplanerrichtlinie zum Ablaufstandard zurück.  Beim nächsten Aufruf ein Standardplaner erstellt wird, verwendet er die Ablaufstandardrichtlinieeinstellungen.|  
|[Scheduler::ScheduleTask\-Methode](../Topic/Scheduler::ScheduleTask%20Method.md)|Überladen.  Plant eine einfache Aufgabe innerhalb des Planers.  Die einfache Aufgabe wird in einer Planungsgruppe platziert, die durch die Laufzeit bestimmt wird.  Die Version, die den `_Placement`\-Parameter akzeptiert, durch die die Aufgabe, zum Ausführung an der angegebenen Position beeinflusst werden.|  
|[Scheduler::SetDefaultSchedulerPolicy\-Methode](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)|Ermöglicht das Verwenden einer benutzerdefinierten Richtlinie zum Erstellen des Standardplaners.  Diese Methode kann aufgerufen werden, wenn kein Standardplaner innerhalb des Prozesses vorhanden ist.  Nachdem eine Standardrichtlinie festgelegt wurde, bleibt sie bestehen bis die folgenden gültigen Aufruf entweder zu `SetDefaultSchedulerPolicy` oder der Methode [ResetDefaultSchedulerPolicy](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md).|  
  
## Hinweise  
 Der Concurrency Runtime\-Planer Ausführungskontexte verwendet, die den Betriebssystemausführungskontexten, beispielsweise ein Thread zuordnen, um die Aufgaben auszuführen, die auf sie von der Anwendung in die Warteschlange gestellt wird.  Die Parallelitätsebene eines Planers ist immer gleich der Anzahl virtueller Prozessoren, die vom Ressourcen\-Manager gewährt wurden.  Ein virtueller Prozessor ist eine Abstraktion für eine Verarbeitungsressource und wird einem Hardwarethread des zugrunde liegenden Systems zugeordnet.  Nur ein einzelner Planerkontext kann jeweils auf einem virtuellen Prozessor ausgeführt werden.  
  
 Die Concurrency Runtime erstellt pro Prozess einen Standardplaner, um Arbeit parallel auszuführen.  Darüber hinaus können Sie eigene Planerinstanzen erstellen und sie mit der Klasse bearbeiten.  
  
## Vererbungshierarchie  
 `Scheduler`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler Class](../../../parallel/concrt/reference/scheduler-class.md)   
 [PolicyElementKey\-Enumeration](../Topic/PolicyElementKey%20Enumeration.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)