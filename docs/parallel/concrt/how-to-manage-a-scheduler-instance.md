---
title: 'Vorgehensweise: Verwalten einer Planerinstanz'
ms.date: 11/04/2016
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
ms.openlocfilehash: bc7adfaeb4c96245488bbcb5cd70cdae9daf9e26
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276160"
---
# <a name="how-to-manage-a-scheduler-instance"></a>Vorgehensweise: Verwalten einer Planerinstanz

Mit Planerinstanzen können Sie bestimmte Planungsrichtlinien verschiedenen Arten von Arbeitslasten zuordnen. Dieses Thema enthält zwei grundlegende Beispiele, die zeigen, wie eine Planerinstanz erstellt und verwaltet wird.

In den Beispielen werden Planer erstellt, die die standardmäßigen Planerrichtlinien verwenden. Ein Beispiel für die Erstellung eines Planers, eine benutzerdefinierte Richtlinie verwendet, finden Sie unter [Vorgehensweise: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).

### <a name="to-manage-a-scheduler-instance-in-your-application"></a>So verwalten Sie eine Planerinstanz in der Anwendung

1. Erstellen Sie eine [Concurrency:: SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) -Objekt, das die Richtlinie enthält Werte, für das Zeitplanungsmodul verwenden.

1. Rufen Sie die [CurrentScheduler](reference/currentscheduler-class.md#create) Methode oder der [Scheduler](reference/scheduler-class.md#create) Methode, um eine Planerinstanz zu erstellen.

   Bei Verwendung der `Scheduler::Create` -Methode, rufen die [Concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) Methode, wenn Sie den Planer mit dem aktuellen Kontext zuordnen müssen.

1. Rufen Sie die [CreateEvent](/windows/desktop/api/synchapi/nf-synchapi-createeventa) Funktion, um ein Handle für ein nicht signalisiertes automatisches Zurücksetzen Zurücksetzungobjekt zu erstellen.

1. Übergeben Sie das Handle für das Ereignisobjekt, das Sie gerade erstellt, um haben die [RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) Methode oder der [Concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) Methode. Hierdurch wird das Ereignis als festzulegen registriert, wenn der Planer zerstört wird.

1. Führen Sie die Aufgaben aus, die vom aktuellen Planer geplant werden sollen.

1. Rufen Sie die [CurrentScheduler](reference/currentscheduler-class.md#detach) Methode, um den aktuellen Planer zu trennen und den vorherigen Planer als aktuellen Planer wiederherzustellen.

   Bei Verwendung der `Scheduler::Create` -Methode, rufen die [Concurrency::Scheduler::Release](reference/scheduler-class.md#release) Methode dekrementiert den Verweiszähler des dem `Scheduler` Objekt.

1. Übergeben Sie das Handle für das Ereignis, das die [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject) Funktion warten, bis der Planer beendet.

1. Rufen Sie die ["CloseHandle"](/windows/desktop/api/handleapi/nf-handleapi-closehandle) Funktion, um das Handle für das Ereignisobjekt zu schließen.

## <a name="example"></a>Beispiel

Der folgende Code veranschaulicht zwei Möglichkeiten für die Verwaltung einer Planerinstanz. In jedem Beispiel wird zunächst mit dem Standardplaner eine Aufgabe ausgeführt, die den eindeutigen Bezeichner des aktuellen Planers ausgibt. Jedes Beispiel verwendet dann eine Planerinstanz, um die gleiche Aufgabe noch einmal auszuführen. In jedem Beispiel wird schließlich der Standardplaner als aktueller Planer wiederhergestellt und die Aufgabe noch einmal ausgeführt.

Im ersten Beispiel wird die [Concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) Klasse, um eine Planerinstanz zu erstellen, und ordnen Sie es mit dem aktuellen Kontext. Im zweiten Beispiel wird die [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) Klasse, um die gleiche Aufgabe auszuführen. In der Regel wird die `CurrentScheduler`-Klasse verwendet, um mit dem aktuellen Planer zu arbeiten. Das zweite Beispiel, das die `Scheduler`-Klasse verwendet, ist nützlich, wenn Sie steuern möchten, wann der Planer dem aktuellen Kontext zugeordnet wird, oder wenn Sie bestimmte Planer bestimmten Aufgaben zuordnen möchten.

[!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/cpp/how-to-manage-a-scheduler-instance_1.cpp)]

Folgende Ergebnisse werden zurückgegeben:

```Output
Using CurrentScheduler class...

Current scheduler id: 0
Creating and attaching scheduler...
Current scheduler id: 1
Detaching scheduler...
Current scheduler id: 0

Using Scheduler class...

Current scheduler id: 0
Creating scheduler...
Attaching scheduler...
Current scheduler id: 2
Detaching scheduler...
Current scheduler id: 0
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `scheduler-instance.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc Scheduler-instance.cpp**

## <a name="see-also"></a>Siehe auch

[Planerinstanzen](../../parallel/concrt/scheduler-instances.md)<br/>
[Vorgehensweise: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)
