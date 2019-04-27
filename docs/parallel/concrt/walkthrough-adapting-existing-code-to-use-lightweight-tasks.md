---
title: 'Exemplarische Vorgehensweise: Anpassen von vorhandenem Code Verwendung einfache Aufgaben'
ms.date: 04/25/2019
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
ms.openlocfilehash: 43e928e7d82b41b83fde5e8a7abaeeeb8d6fefa9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186022"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>Exemplarische Vorgehensweise: Anpassen von vorhandenem Code Verwendung einfache Aufgaben

In diesem Thema wird erläutert, wie vorhandener Code, der die Windows-API verwendet, zum Erstellen und Ausführen eines Threads für die Ausführung einer einfachen Aufgabe angepasst wird.

Ein *einfache Aufgabe* ist eine Aufgabe, die Sie direkt aus Planen einer [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) oder [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Objekt. Einfache Aufgaben sind nützlich, wenn Sie vorhandenen Code anpassen, um die Planungsfunktionalität der Concurrency Runtime zu verwenden.

## <a name="prerequisites"></a>Vorraussetzungen

Bevor Sie in dieser exemplarischen Vorgehensweise beginnen, lesen Sie das Thema [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel veranschaulicht die typische Verwendung der Windows-API zum Erstellen und Ausführen eines Threads. Dieses Beispiel verwendet die [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) aufzurufenden Funktion der `MyThreadFunction` in einem separaten Thread.

### <a name="code"></a>Code

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

### <a name="comments"></a>Kommentare

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

1. Ändern der `MyData` -Struktur so, dass eine [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) -Objekt, für die hauptanwendung signalisiert, dass der Vorgang abgeschlossen ist.

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. Ersetzen Sie den Aufruf von `CreateThread` durch einen Aufruf der [Concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask) Methode.

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. Ersetzen Sie den Aufruf von `WaitForSingleObject` durch einen Aufruf der [Concurrency](reference/event-class.md#wait) Methode, um auf den Abschluss der Aufgabe warten.

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. Entfernen Sie den Aufruf von `CloseHandle`.

1. Ändern Sie die Signatur der Definition von `MyThreadFunction` so, dass sie Schritt 3 entspricht.

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

9. Am Ende der `MyThreadFunction` funktioniert, rufen Sie die [Concurrency::event::set](reference/event-class.md#set) Methode, um der hauptanwendung signalisiert, dass der Vorgang abgeschlossen ist.

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

10. Entfernen Sie die `return`-Anweisung von `MyThreadFunction`.

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Im folgenden vollständigen Beispiel wird eine einfache Aufgabe verwendet, um die `MyThreadFunction`-Funktion aufzurufen.

### <a name="code"></a>Code

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

### <a name="comments"></a>Kommentare

## <a name="see-also"></a>Siehe auch

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Scheduler-Klasse](../../parallel/concrt/reference/scheduler-class.md)
