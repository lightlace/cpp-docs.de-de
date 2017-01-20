---
title: "Gewusst wie: Beeinflussen der Ausf&#252;hrungsreihenfolge mithilfe von Zeitplangruppen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Planungsgruppen, Verwenden [Concurrency Runtime]"
  - "Verwenden von Planungsgruppen [Concurrency Runtime]"
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
caps.latest.revision: 15
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Beeinflussen der Ausf&#252;hrungsreihenfolge mithilfe von Zeitplangruppen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In der Concurrency Runtime ist die Reihenfolge, in der Aufgaben geplant werden, nicht deterministisch.  Sie können die Reihenfolge der Aufgabenausführung jedoch mithilfe von Planungsrichtlinien beeinflussen.  In diesem Thema wird beschrieben, wie Planungsgruppen zusammen mit der [concurrency::SchedulingProtocol](../Topic/PolicyElementKey%20Enumeration.md)\-Planerrichtlinie verwendet werden, um die Reihenfolge der Aufgabenausführung zu beeinflussen.  
  
 In diesem Beispiel wird eine Gruppe von Aufgaben zweimal ausgeführt, wobei jedes Mal eine andere Planungsrichtlinie verwendet wird.  Beide Richtlinien beschränken die maximale Anzahl von Verarbeitungsressourcen auf zwei.  Bei der ersten Ausführung wird die `EnhanceScheduleGroupLocality` \-Richtlinie \(Standard\) verwendet, während bei der zweiten Ausführung die `EnhanceForwardProgress`\-Richtlinie verwendet wird.  Unter der `EnhanceScheduleGroupLocality`\-Richtlinie führt der Planer alle Aufgaben in einer Planungsgruppe aus, bis alle Aufgaben beendet oder erzeugt wurden.  Unter der `EnhanceForwardProgress`\-Richtlinie wechselt der Planer mittels Roundrobin zur nächsten Planungsgruppe, nachdem eine Aufgabe beendet oder erzeugt wurde.  
  
 Wenn alle Planungsgruppen verwandte Aufgaben enthalten, ist die `EnhanceScheduleGroupLocality`\-Richtlinie in der Regel leistungsfähiger, da die Cachelokalität zwischen Aufgaben erhalten bleibt.  Die `EnhanceForwardProgress`\-Richtlinie ermöglicht es, dass Aufgaben Fortschritte machen. Zudem ist sie nützlich, wenn über Planungsgruppen hinweg Planungsfairness erforderlich ist.  
  
## Beispiel  
 In diesem Beispiel wird die `work_yield_agent`\-Klasse beschrieben, die von der [concurrency::agent](../../parallel/concrt/reference/agent-class.md)\-Klasse abgeleitet wird.  Die `work_yield_agent`\-Klasse führt eine Arbeitseinheit aus, erzeugt den aktuellen Kontext und führt dann eine weitere Arbeitseinheit aus.  Der Agent verwendet die [concurrency::wait](../Topic/wait%20Function.md)\-Funktion, um den aktuellen Kontext gemeinsam zu erstellen, sodass andere Kontexte ausgeführt werden können.  
  
 In diesem Beispiel werden vier `work_yield_agent`\-Objekte erstellt.  Im Beispiel werden die ersten beiden Agents einer Planungsgruppe und die anderen beiden Agents einer anderen Planungsgruppe zugeordnet, um zu zeigen, wie Planerrichtlinien zum Beeinflussen der Ausführungsreihenfolge von Agents festgelegt werden.  Im Beispiel werden die [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md)\-Objekte mit der [Concurrency::CurrentScheduler::CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md)\-Methode erstellt.  Im Beispiel werden alle vier Agents zweimal ausgeführt, wobei jedes Mal eine andere Planungsrichtlinie verwendet wird.  
  
 [!CODE [concrt-scheduling-protocol#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-scheduling-protocol#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **Using EnhanceScheduleGroupLocality...**  
**group 0,task 0: first loop...**  
**group 0,task 1: first loop...**  
**group 0,task 0: waiting...**  
**group 1,task 0: first loop...**  
**group 0,task 1: waiting...**  
**group 1,task 1: first loop...**  
**group 1,task 0: waiting...**  
**group 0,task 0: second loop...**  
**group 1,task 1: waiting...**  
**group 0,task 1: second loop...**  
**group 0,task 0: finished...**  
**group 1,task 0: second loop...**  
**group 0,task 1: finished...**  
**group 1,task 1: second loop...**  
**group 1,task 0: finished...**  
**group 1,task 1: finished...**  
**Using EnhanceForwardProgress...**  
**group 0,task 0: first loop...**  
**group 1,task 0: first loop...**  
**group 0,task 0: waiting...**  
**group 0,task 1: first loop...**  
**group 1,task 0: waiting...**  
**group 1,task 1: first loop...**  
**group 0,task 1: waiting...**  
**group 0,task 0: second loop...**  
**group 1,task 1: waiting...**  
**group 1,task 0: second loop...**  
**group 0,task 0: finished...**  
**group 0,task 1: second loop...**  
**group 1,task 0: finished...**  
**group 1,task 1: second loop...**  
**group 0,task 1: finished...**  
**group 1,task 1: finished...** Beide Richtlinien erzeugen dieselbe Sequenz von Ereignissen.  Die Richtlinie, die `EnhanceScheduleGroupLocality` verwendet, startet jedoch beide Agents, die Teil der ersten Planungsgruppe sind, bevor sie die Agents startet, die Teil der zweiten Gruppe sind.  Die Richtlinie, die `EnhanceForwardProgress` verwendet, startet einen Agent aus der ersten Gruppe und startet dann den ersten Agent in der zweiten Gruppe.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `scheduling-protocol.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc scheduling\-protocol.cpp**  
  
## Siehe auch  
 [Planungsgruppen](../../parallel/concrt/schedule-groups.md)   
 [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)