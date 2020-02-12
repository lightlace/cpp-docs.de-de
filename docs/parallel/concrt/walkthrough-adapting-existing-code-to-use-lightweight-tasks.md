---
title: 'Exemplarische Vorgehensweise: Anpassen von vorhandenem Code für die Verwendung einfacher Aufgaben'
ms.date: 04/25/2019
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
ms.openlocfilehash: e7c6096829a1cd45cfdb849a1899d6b4a2d4cb78
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141996"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>Exemplarische Vorgehensweise: Anpassen von vorhandenem Code für die Verwendung einfacher Aufgaben

In diesem Thema wird erläutert, wie vorhandener Code, der die Windows-API verwendet, zum Erstellen und Ausführen eines Threads für die Ausführung einer einfachen Aufgabe angepasst wird.

Eine *leichte Aufgabe* ist eine Aufgabe, die Sie direkt aus einem [parallelcurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) -oder einem [parallelcurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) -Objekt planen. Einfache Aufgaben sind nützlich, wenn Sie vorhandenen Code anpassen, um die Planungsfunktionalität der Concurrency Runtime zu verwenden.

## <a name="prerequisites"></a>Voraussetzungen

Lesen Sie das Thema [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md), bevor Sie mit dieser exemplarischen Vorgehensweise beginnen.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die typische Verwendung der Windows-API zum Erstellen und Ausführen eines Threads. In diesem Beispiel wird die Funktion " [kreatethread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) " verwendet, um die `MyThreadFunction` in einem separaten Thread aufzurufen.

### <a name="initial-code"></a>Ursprünglicher Code

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

Folgende Ergebnisse werden zurückgegeben:

```Output
Parameters = 50, 100
```

Die folgenden Schritte geben an, wie das Codebeispiel angepasst wird, um die Concurrency Runtime zum Durchführen der gleichen Aufgabe zu verwenden.

### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>So passen Sie das Beispiel an, um eine einfache Aufgabe zu verwenden

1. Fügen Sie eine `#include`-Anweisung für die Headerdatei concrt.h hinzu.

[!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]

1. Fügen Sie eine `using`-Direktive für den `concurrency`-Namespace hinzu.

[!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]

1. Ändern Sie die Deklaration von `MyThreadFunction` so, dass die `__cdecl`-Aufrufkonvention verwendet und `void` zurückgegeben wird.

[!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]

1. Ändern Sie die `MyData` Struktur so, dass Sie ein [parallelcurrency:: Event](../../parallel/concrt/reference/event-class.md) -Objekt enthält, das der Hauptanwendung signalisiert, dass der Task abgeschlossen wurde.

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. Ersetzen Sie den `CreateThread`-Aufrufe durch einen-Rückruf der [Concurrency:: CurrentScheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask) -Methode.

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. Ersetzen Sie den-`WaitForSingleObject` durch einen Aufrufe der Methode " [parallelcurrency:: Event:: Wait](reference/event-class.md#wait) ", um auf den Abschluss der Aufgabe zu warten.

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. Entfernen Sie den Aufruf von `CloseHandle`.

1. Ändern Sie die Signatur der Definition von `MyThreadFunction` so, dass sie Schritt 3 entspricht.

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

1. Am Ende der `MyThreadFunction`-Funktion wird die Methode " [parallelcurrency:: Event:: Set](reference/event-class.md#set) " aufgerufen, um der Hauptanwendung zu signalisieren, dass die Aufgabe abgeschlossen wurde.

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

1. Entfernen Sie die `return`-Anweisung von `MyThreadFunction`.

### <a name="completed-code"></a>Abgeschlossener Code

Im folgenden vollständigen Beispiel wird eine einfache Aufgabe verwendet, um die `MyThreadFunction`-Funktion aufzurufen.

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

## <a name="see-also"></a>Weitere Informationen

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Scheduler-Klasse](../../parallel/concrt/reference/scheduler-class.md)
