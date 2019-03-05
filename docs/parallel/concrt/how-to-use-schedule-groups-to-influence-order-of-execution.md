---
title: 'Vorgehensweise: Der Ausführungsreihenfolge mithilfe von Zeitplangruppen'
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups, using [Concurrency Runtime]
- using schedule groups [Concurrency Runtime]
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
ms.openlocfilehash: 99e0383fc8d16f3eeb6e43e59424ab0984ee5c14
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284358"
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>Vorgehensweise: Der Ausführungsreihenfolge mithilfe von Zeitplangruppen

In der Concurrency Runtime ist die Reihenfolge, in der Aufgaben geplant werden, nicht deterministisch. Sie können die Reihenfolge der Aufgabenausführung jedoch mithilfe von Planungsrichtlinien beeinflussen. In diesem Thema veranschaulicht, wie Planungsgruppen zusammen mit den [SchedulingProtocol](reference/concurrency-namespace-enums.md#policyelementkey) Planerrichtlinie, um die Reihenfolge beeinflussen, in dem Aufgaben ausgeführt werden.

In diesem Beispiel wird eine Gruppe von Aufgaben zweimal ausgeführt, wobei jedes Mal eine andere Planungsrichtlinie verwendet wird. Beide Richtlinien beschränken die maximale Anzahl von Verarbeitungsressourcen auf zwei. Der ersten Ausführung wird der `EnhanceScheduleGroupLocality` Richtlinie, dies ist die Standardeinstellung, und führen Sie die zweite verwendet den `EnhanceForwardProgress` Richtlinie. Unter der `EnhanceScheduleGroupLocality`-Richtlinie führt der Planer alle Aufgaben in einer Planungsgruppe aus, bis alle Aufgaben beendet oder erzeugt wurden. Unter der `EnhanceForwardProgress`-Richtlinie wechselt der Planer mittels Roundrobin zur nächsten Planungsgruppe, nachdem eine Aufgabe beendet oder erzeugt wurde.

Wenn alle Planungsgruppen verwandte Aufgaben enthalten, ist die `EnhanceScheduleGroupLocality`-Richtlinie in der Regel leistungsfähiger, da die Cachelokalität zwischen Aufgaben erhalten bleibt. Die `EnhanceForwardProgress`-Richtlinie ermöglicht es, dass Aufgaben Fortschritte machen. Zudem ist sie nützlich, wenn über Planungsgruppen hinweg Planungsfairness erforderlich ist.

## <a name="example"></a>Beispiel

Dieses Beispiel definiert die `work_yield_agent` -Klasse, die abgeleitet [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md). Die `work_yield_agent`-Klasse führt eine Arbeitseinheit aus, erzeugt den aktuellen Kontext und führt dann eine weitere Arbeitseinheit aus. Der Agent verwendet die [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) Funktion, um den aktuellen Kontext kooperativ zurückgehalten werden soll, sodass andere Kontexte ausgeführt werden können.

In diesem Beispiel werden vier `work_yield_agent`-Objekte erstellt. Im Beispiel werden die ersten beiden Agents einer Planungsgruppe und die anderen beiden Agents einer anderen Planungsgruppe zugeordnet, um zu zeigen, wie Planerrichtlinien zum Beeinflussen der Ausführungsreihenfolge von Agents festgelegt werden. Im Beispiel wird die [:: CurrentScheduler:: CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) Methode zum Erstellen der [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Objekte. Im Beispiel werden alle vier Agents zweimal ausgeführt, wobei jedes Mal eine andere Planungsrichtlinie verwendet wird.

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

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `scheduling-protocol.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc scheduling-protocol.cpp**

## <a name="see-also"></a>Siehe auch

[Planungsgruppen](../../parallel/concrt/schedule-groups.md)<br/>
[Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)
