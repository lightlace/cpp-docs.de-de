---
title: 'Vorgehensweise: Verwalten einer planerinstanz'
ms.date: 11/04/2016
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
ms.openlocfilehash: f402e82a18f7b804f2c25ebf0a4392d19694d25c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510526"
---
# <a name="how-to-manage-a-scheduler-instance"></a>Vorgehensweise: Verwalten einer planerinstanz

Mit Planerinstanzen können Sie bestimmte Planungsrichtlinien verschiedenen Arten von Arbeitslasten zuordnen. Dieses Thema enthält zwei grundlegende Beispiele, die zeigen, wie eine Planerinstanz erstellt und verwaltet wird.

In den Beispielen werden Planer erstellt, die die standardmäßigen Planerrichtlinien verwenden. Ein Beispiel, das einen Planer erstellt, der eine benutzerdefinierte Richtlinie verwendet [, finden Sie unter Gewusst wie: Geben Sie bestimmte Scheduler](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)-Richtlinien an.

### <a name="to-manage-a-scheduler-instance-in-your-application"></a>So verwalten Sie eine Planerinstanz in der Anwendung

1. Erstellen Sie ein [parallelcurrency:: SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) -Objekt, das die Richtlinien Werte für den zu verwendenden Scheduler enthält.

1. Rufen Sie die [Concurrency:: CurrentScheduler:: Create](reference/currentscheduler-class.md#create) -Methode oder die [Concurrency:: Scheduler:: Create](reference/scheduler-class.md#create) -Methode auf, um eine planerinstanz zu erstellen.

   Wenn Sie die `Scheduler::Create` -Methode verwenden, wenden Sie die Methode " [parallelcurrency:: Scheduler:: Attach](reference/scheduler-class.md#attach) " an, wenn Sie den Scheduler dem aktuellen Kontext zuordnen müssen.

1. Rufen Sie [die Funktion](/windows/win32/api/synchapi/nf-synchapi-createeventw) "-Funktion" auf, um ein Handle für ein nicht signalisiertes Ereignis Objekt zu erstellen, das automatisch zurückgesetzt wird.

1. Übergeben Sie das Handle an das Ereignis Objekt, das Sie soeben erstellt haben, an die [Concurrency:: CurrentScheduler:: registershutdownetvent](reference/currentscheduler-class.md#registershutdownevent) -Methode oder die [Concurrency:: Scheduler:: registershutdownetvent](reference/scheduler-class.md#registershutdownevent) -Methode. Hierdurch wird das Ereignis als festzulegen registriert, wenn der Planer zerstört wird.

1. Führen Sie die Aufgaben aus, die vom aktuellen Planer geplant werden sollen.

1. Wenden Sie die [Concurrency:: CurrentScheduler::D Etach](reference/currentscheduler-class.md#detach) -Methode an, um den aktuellen Planer zu trennen und den vorherigen Scheduler als aktuellen Scheduler wiederherzustellen.

   Wenn Sie die `Scheduler::Create` -Methode verwenden, wird die Methode " [parallelcurrency:: Scheduler:: Release](reference/scheduler-class.md#release) " aufgerufen, um den `Scheduler` Verweis Zähler des Objekts zu Dekrementen.

1. Übergeben Sie das Handle an das-Ereignis an die [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) -Funktion, um zu warten, bis der Scheduler heruntergefahren wird.

1. Ruft die [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) -Funktion auf, um das Handle für das Ereignis Objekt zu schließen.

## <a name="example"></a>Beispiel

Der folgende Code veranschaulicht zwei Möglichkeiten für die Verwaltung einer Planerinstanz. In jedem Beispiel wird zunächst mit dem Standardplaner eine Aufgabe ausgeführt, die den eindeutigen Bezeichner des aktuellen Planers ausgibt. Jedes Beispiel verwendet dann eine Planerinstanz, um die gleiche Aufgabe noch einmal auszuführen. In jedem Beispiel wird schließlich der Standardplaner als aktueller Planer wiederhergestellt und die Aufgabe noch einmal ausgeführt.

Im ersten Beispiel wird die [Concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) -Klasse verwendet, um eine planerinstanz zu erstellen und Sie dem aktuellen Kontext zuzuordnen. Im zweiten Beispiel wird die gleiche Aufgabe mithilfe der Klasse " [parallelcurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) " durchgeführt. In der Regel wird die `CurrentScheduler`-Klasse verwendet, um mit dem aktuellen Planer zu arbeiten. Das zweite Beispiel, das die `Scheduler`-Klasse verwendet, ist nützlich, wenn Sie steuern möchten, wann der Planer dem aktuellen Kontext zugeordnet wird, oder wenn Sie bestimmte Planer bestimmten Aufgaben zuordnen möchten.

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

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ dazu können Sie `scheduler-instance.cpp` ihn auch in eine Datei mit dem Namen einfügen und dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster ausführen.

**cl. exe/EHsc Scheduler-instance. cpp**

## <a name="see-also"></a>Siehe auch

[Planerinstanzen](../../parallel/concrt/scheduler-instances.md)<br/>
[Vorgehensweise: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)
