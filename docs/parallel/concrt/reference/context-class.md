---
title: "Context-Klasse"
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
  - "concrt/concurrency::Context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Context-Klasse"
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
caps.latest.revision: 20
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Context-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Abstraktion für einen Ausführungskontext dar.  
  
## Syntax  
  
```  
class Context;  
```  
  
## Member  
  
### Geschützte Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Context::~Context\-Destruktor](../Topic/Context::~Context%20Destructor.md)||  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Context::Block\-Methode](../Topic/Context::Block%20Method.md)|Blockiert den aktuellen Kontext.|  
|[Context::CurrentContext\-Methode](../Topic/Context::CurrentContext%20Method.md)|Gibt einen Zeiger auf den aktuellen Kontext zurück.|  
|[Context::GetId\-Methode](../Topic/Context::GetId%20Method.md)|Gibt einen Bezeichner für den Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der Kontext gehört.|  
|[Context::GetScheduleGroupId\-Methode](../Topic/Context::GetScheduleGroupId%20Method.md)|Gibt einen Bezeichner für die Planungsgruppe zurück, an der der Kontext gerade arbeitet.|  
|[Context::GetVirtualProcessorId\-Methode](../Topic/Context::GetVirtualProcessorId%20Method.md)|Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der Kontext gerade ausgeführt wird.|  
|[Context::Id\-Methode](../Topic/Context::Id%20Method.md)|Gibt einen Bezeichner für den aktuellen Kontext zurück, der innerhalb des Planers eindeutig ist, zu dem der aktuelle Kontext gehört.|  
|[Context::IsCurrentTaskCollectionCanceling\-Methode](../Topic/Context::IsCurrentTaskCollectionCanceling%20Method.md)|Gibt zurück, ob die Aufgabenauflistung, die gerade inline für den aktuellen Kontext ausgeführt wird, in diesem Moment \(oder in Kürze\) einen Abbruch durchführt.|  
|[Context::IsSynchronouslyBlocked\-Methode](../Topic/Context::IsSynchronouslyBlocked%20Method.md)|Bestimmt, ob der Kontext synchron blockiert ist.  Ein Kontext wird als synchron blockiert angesehen, wenn er explizit eine zu einer Blockierung führende Aktion ausgeführt hat.|  
|[Context::Oversubscribe\-Methode](../Topic/Context::Oversubscribe%20Method.md)|Fügt einen zusätzlichen virtuellen Prozessor für die Dauer eines Codeblocks in einen Planer ein, wenn er für einen Kontext aufgerufen wird, der auf einem der virtuellen Prozessoren in diesem Planer ausgeführt wird.|  
|[Context::ScheduleGroupId\-Methode](../Topic/Context::ScheduleGroupId%20Method.md)|Gibt einen Bezeichner für die Planungsgruppe zurück, an der der aktuelle Kontext arbeitet.|  
|[Context::Unblock\-Methode](../Topic/Context::Unblock%20Method.md)|Hebt die Blockierung des Kontexts auf und bewirkt, dass er ausführbar wird.|  
|[Context::VirtualProcessorId\-Methode](../Topic/Context::VirtualProcessorId%20Method.md)|Gibt einen Bezeichner für den virtuellen Prozessor zurück, auf dem der aktuelle Kontext ausgeführt wird.|  
|[Context::Yield\-Methode](../Topic/Context::Yield%20Method.md)|Setzt die Ausführung aus, damit ein anderer Kontext ausgeführt werden kann.  Wenn kein anderer Kontext für eine Übergabe verfügbar ist, kann der Planer ggf. an einen anderen Betriebssystemthread übergeben.|  
  
## Hinweise  
 Der Concurrency Runtime\-Planer \(siehe [Planer](../../../parallel/concrt/reference/scheduler-class.md)\) verwendet Ausführungskontexte, um die von der Anwendung in die Warteschlange gestellten Arbeiten auszuführen.  Ein Win32\-Thread ist ein Beispiel für einen Ausführungskontext auf einem Windows\-Betriebssystem.  
  
 Die Nebenläufigkeitsebene eines Planers ist immer gleich der Anzahl virtueller Prozessoren, die vom Ressourcen\-Manager gewährt wurden.  Ein virtueller Prozessor ist eine Abstraktion für eine Verarbeitungsressource und wird einem Hardwarethread des zugrunde liegenden Systems zugeordnet.  Nur ein einzelner Planerkontext kann jeweils auf einem virtuellen Prozessor ausgeführt werden.  
  
 Der Planer ist grundsätzlich kooperativ, und ein Ausführungskontext kann seinen virtuellen Prozessor jederzeit für einen anderen Kontext freigeben, wenn er in einen Wartezustand wechseln möchte.  Wenn der Wartevorgang erfüllt wurde, kann solange keine Fortsetzung erfolgen, bis ein verfügbarer virtueller Prozessor vom Planer mit der Ausführung beginnt.  
  
## Vererbungshierarchie  
 `Context`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler\-Klasse](../../../parallel/concrt/reference/scheduler-class.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)