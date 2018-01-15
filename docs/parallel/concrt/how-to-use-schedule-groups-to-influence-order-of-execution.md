---
title: "Vorgehensweise: Verwenden von Planungsgruppen, die beeinflussen der Ausführungsreihenfolge | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- schedule groups, using [Concurrency Runtime]
- using schedule groups [Concurrency Runtime]
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcb37c1c14a9d09230bfa5d4fdce1da5eddfb4f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>Gewusst wie: Beeinflussen der Ausführungsreihenfolge mithilfe von Zeitplangruppen
In der Concurrency Runtime ist die Reihenfolge, in der Aufgaben geplant werden, nicht deterministisch. Sie können die Reihenfolge der Aufgabenausführung jedoch mithilfe von Planungsrichtlinien beeinflussen. In diesem Thema wird gezeigt, wie Planungsgruppen zusammen mit den [SchedulingProtocol](reference/concurrency-namespace-enums.md#policyelementkey) Planerrichtlinie, die die Reihenfolge beeinflussen, in dem Aufgaben ausgeführt werden.  

  
 In diesem Beispiel wird eine Gruppe von Aufgaben zweimal ausgeführt, wobei jedes Mal eine andere Planungsrichtlinie verwendet wird. Beide Richtlinien beschränken die maximale Anzahl von Verarbeitungsressourcen auf zwei. Der ersten Ausführung wird dem `EnhanceScheduleGroupLocality` Richtlinie, dies ist die Standardeinstellung, und die zweite führen verwendet die `EnhanceForwardProgress` Richtlinie. Unter der `EnhanceScheduleGroupLocality`-Richtlinie führt der Planer alle Aufgaben in einer Planungsgruppe aus, bis alle Aufgaben beendet oder erzeugt wurden. Unter der `EnhanceForwardProgress`-Richtlinie wechselt der Planer mittels Roundrobin zur nächsten Planungsgruppe, nachdem eine Aufgabe beendet oder erzeugt wurde.  
  
 Wenn alle Planungsgruppen verwandte Aufgaben enthalten, ist die `EnhanceScheduleGroupLocality`-Richtlinie in der Regel leistungsfähiger, da die Cachelokalität zwischen Aufgaben erhalten bleibt. Die `EnhanceForwardProgress`-Richtlinie ermöglicht es, dass Aufgaben Fortschritte machen. Zudem ist sie nützlich, wenn über Planungsgruppen hinweg Planungsfairness erforderlich ist.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die `work_yield_agent` -Klasse, abgeleitet von [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md). Die `work_yield_agent`-Klasse führt eine Arbeitseinheit aus, erzeugt den aktuellen Kontext und führt dann eine weitere Arbeitseinheit aus. Der Agent verwendet die [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) Funktion, um den aktuellen Kontext gemeinsam zu erstellen, sodass andere Kontexte ausgeführt werden können.  
  
 In diesem Beispiel werden vier `work_yield_agent`-Objekte erstellt. Im Beispiel werden die ersten beiden Agents einer Planungsgruppe und die anderen beiden Agents einer anderen Planungsgruppe zugeordnet, um zu zeigen, wie Planerrichtlinien zum Beeinflussen der Ausführungsreihenfolge von Agents festgelegt werden. Im Beispiel wird die [ScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) Methode zum Erstellen der [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Objekte. Im Beispiel werden alle vier Agents zweimal ausgeführt, wobei jedes Mal eine andere Planungsrichtlinie verwendet wird.  
  
 [!code-cpp[concrt-scheduling-protocol#1](../../parallel/concrt/codesnippet/cpp/how-to-use-schedule-groups-to-influence-order-of-execution_1.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
Using EnhanceScheduleGroupLocality...  
group 0,
    task 0: first loop...  
group 0,
    task 1: first loop...  
group 0,
    task 0: waiting...  
group 1,
    task 0: first loop...  
group 0,
    task 1: waiting...  
group 1,
    task 1: first loop...  
group 1,
    task 0: waiting...  
group 0,
    task 0: second loop...  
group 1,
    task 1: waiting...  
group 0,
    task 1: second loop...  
group 0,
    task 0: finished...  
group 1,
    task 0: second loop...  
group 0,
    task 1: finished...  
group 1,
    task 1: second loop...  
group 1,
    task 0: finished...  
group 1,
    task 1: finished...  
 
Using EnhanceForwardProgress...  
group 0,
    task 0: first loop...  
group 1,
    task 0: first loop...  
group 0,
    task 0: waiting...  
group 0,
    task 1: first loop...  
group 1,
    task 0: waiting...  
group 1,
    task 1: first loop...  
group 0,
    task 1: waiting...  
group 0,
    task 0: second loop...  
group 1,
    task 1: waiting...  
group 1,
    task 0: second loop...  
group 0,
    task 0: finished...  
group 0,
    task 1: second loop...  
group 1,
    task 0: finished...  
group 1,
    task 1: second loop...  
group 0,
    task 1: finished...  
group 1,
    task 1: finished...  
```  
  
 Beide Richtlinien erzeugen dieselbe Sequenz von Ereignissen. Die Richtlinie, die `EnhanceScheduleGroupLocality` verwendet, startet jedoch beide Agents, die Teil der ersten Planungsgruppe sind, bevor sie die Agents startet, die Teil der zweiten Gruppe sind. Die Richtlinie, die `EnhanceForwardProgress` verwendet, startet einen Agent aus der ersten Gruppe und startet dann den ersten Agent in der zweiten Gruppe.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `scheduling-protocol.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc / scheduling-protocol.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Planungsgruppen](../../parallel/concrt/schedule-groups.md)   
 [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)

