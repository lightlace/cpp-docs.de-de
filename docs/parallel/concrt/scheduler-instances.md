---
title: Planerinstanzen
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
ms.openlocfilehash: e9e9b8124254084ac30191d37d49f2ef72bd677e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142295"
---
# <a name="scheduler-instances"></a>Planerinstanzen

In diesem Dokument wird die Rolle von Scheduler-Instanzen in der Concurrency Runtime und die Verwendung der [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) -Klasse und der [Concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) -Klasse zum Erstellen und Verwalten von Scheduler-Instanzen beschrieben. Scheduler-Instanzen sind hilfreich, wenn Sie explizite Planungsrichtlinien bestimmten Arten von Arbeits Auslastungen zuordnen möchten. Beispielsweise können Sie eine Planerinstanz erstellen, um einige Aufgaben mit höherer Threadpriorität auszuführen und andere Aufgaben mit dem Standardplaner mit normaler Threadpriorität auszuführen.

> [!TIP]
> Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie bei der Feinabstimmung der Leistung Ihrer Anwendungen unterstützt, empfehlen wir Ihnen, mit der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie mit der Concurrency Runtime noch nicht vertraut sind.

## <a name="top"></a> Abschnitte

- [Die Scheduler-Klasse und die CurrentScheduler-Klasse](#classes)

- [Erstellen einer planerinstanz](#creating)

- [Verwalten der Lebensdauer einer planerinstanz](#managing)

- [Methoden und Features](#features)

- [Beispiel](#example)

## <a name="classes"></a>Die Scheduler-Klasse und die CurrentScheduler-Klasse

Der-Taskplaner ermöglicht Anwendungen die Verwendung einer oder mehrerer *Scheduler-Instanzen* zum Planen von Arbeit. Die " [parallelcurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) "-Klasse stellt eine planerinstanz dar und kapselt die Funktionalität, die mit Planungsaufgaben verknüpft ist.

Ein Thread, der an einen Scheduler angefügt ist, wird als *Ausführungs Kontext*oder nur als *Kontext*bezeichnet. Ein Scheduler kann jederzeit im aktuellen Kontext aktiv sein. Der aktive Scheduler wird auch als *Aktueller Planer*bezeichnet. Der Concurrency Runtime verwendet die [Concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) -Klasse, um den Zugriff auf den aktuellen Scheduler bereitzustellen. Der aktuelle Scheduler für einen Kontext kann sich vom aktuellen Zeit Planungs Modul für einen anderen Kontext unterscheiden. Die Laufzeit stellt keine Darstellung des aktuellen Zeit Planungs Moduls auf Prozessebene bereit.

In der Regel wird die `CurrentScheduler`-Klasse für den Zugriff auf den aktuellen Scheduler verwendet. Die `Scheduler`-Klasse ist nützlich, wenn Sie einen Scheduler verwalten müssen, der nicht der aktuelle ist.

In den folgenden Abschnitten wird beschrieben, wie eine Scheduler-Instanz erstellt und verwaltet wird. Ein umfassendes Beispiel, das diese Aufgaben veranschaulicht, finden [Sie unter Gewusst wie: Verwalten einer planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).

[[Nach oben](#top)]

## <a name="creating"></a>Erstellen einer planerinstanz

Es gibt drei Möglichkeiten, ein `Scheduler` Objekt zu erstellen:

- Wenn kein Scheduler vorhanden ist, erstellt die Laufzeit einen Standard Planer für Sie, wenn Sie Lauf Zeitfunktionen verwenden, z. b. einen parallelen Algorithmus, um Arbeit auszuführen. Der Standard Planer wird zum aktuellen Scheduler für den Kontext, der die parallele Arbeit initiiert.

- Die [Concurrency:: CurrentScheduler:: Create](reference/currentscheduler-class.md#create) -Methode erstellt ein `Scheduler` Objekt, das eine bestimmte Richtlinie verwendet und diesem Scheduler den aktuellen Kontext zuordnet.

- Die [parallelcurrency:: Scheduler:: Create](reference/scheduler-class.md#create) -Methode erstellt ein `Scheduler` Objekt, das eine bestimmte Richtlinie verwendet, aber nicht dem aktuellen Kontext zuordnet.

Wenn die Laufzeit einen Standard Planer erstellen kann, können alle gleichzeitigen Tasks denselben Planer gemeinsam verwenden. In der Regel werden die Funktionen, die von der [Parallel Patterns Library](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) bereitgestellt werden, verwendet, um parallele Arbeiten auszuführen. Daher müssen Sie nicht direkt mit dem Scheduler zusammenarbeiten, um seine Richtlinie oder Lebensdauer zu steuern. Wenn Sie die PPL-oder die Agents-Bibliothek verwenden, erstellt die Laufzeit den Standard Planer, wenn er nicht vorhanden ist, und macht ihn zum aktuellen Planer für jeden Kontext. Wenn Sie einen Scheduler erstellen und ihn als aktuellen Planer festlegen, verwendet die Common Language Runtime den Scheduler, um Aufgaben zu planen. Erstellen Sie zusätzliche Scheduler-Instanzen nur dann, wenn Sie eine bestimmte Planungsrichtlinie benötigen. Weitere Informationen zu den Richtlinien, die einem Scheduler zugeordnet sind, finden Sie unter [Scheduler Policies](../../parallel/concrt/scheduler-policies.md).

[[Nach oben](#top)]

## <a name="managing"></a>Verwalten der Lebensdauer einer planerinstanz

Die Laufzeit verwendet einen Mechanismus zur Verweis Zählung, um die Lebensdauer von `Scheduler` Objekten zu steuern.

Wenn Sie die `CurrentScheduler::Create`-Methode oder die `Scheduler::Create`-Methode verwenden, um ein `Scheduler`-Objekt zu erstellen, legt die Laufzeit den anfänglichen Verweis Zähler dieses Zeit Planungs Moduls auf 1 fest. Die Laufzeit erhöht den Verweis Zähler, wenn Sie die [parallelcurrency:: Scheduler:: Attach](reference/scheduler-class.md#attach) -Methode aufzurufen. Die `Scheduler::Attach`-Methode ordnet das `Scheduler`-Objekt zusammen mit dem aktuellen Kontext zu. Dadurch wird es zum aktuellen Scheduler. Wenn Sie die `CurrentScheduler::Create`-Methode aufzurufen, erstellt die Laufzeit ein `Scheduler`-Objekt und fügt es an den aktuellen Kontext an (und legt den Verweis Zähler auf 1 fest). Sie können auch die Methode " [parallelcurrency:: Scheduler:: Reference](reference/scheduler-class.md#reference) " verwenden, um den Verweis Zähler eines `Scheduler` Objekts zu erhöhen.

Die Laufzeit verringert den Verweis Zähler, wenn Sie die [Concurrency:: CurrentScheduler::D Etach](reference/currentscheduler-class.md#detach) -Methode zum Trennen des aktuellen Zeit Planungs Moduls aufzurufen, oder Sie können die [Concurrency:: Scheduler:: Release](reference/scheduler-class.md#release) -Methode aufzurufen. Wenn der Verweis Zähler Null erreicht, zerstört die Laufzeit das `Scheduler` Objekt, nachdem alle geplanten Aufgaben abgeschlossen sind. Ein ausgelaufender Task darf den Verweis Zähler des aktuellen Zeit Planungs Moduls erhöhen. Wenn also der Verweis Zähler Null erreicht und ein Task den Verweis Zähler Inkremente, zerstört die Laufzeit das `Scheduler` Objekt erst, wenn der Verweis Zähler erneut Null erreicht und alle Aufgaben abgeschlossen sind.

Die Laufzeit verwaltet einen internen Stapel von `Scheduler`-Objekten für jeden Kontext. Wenn Sie die `Scheduler::Attach`-oder `CurrentScheduler::Create`-Methode aufzurufen, überträgt die Laufzeit dieses `Scheduler` Objekt für den aktuellen Kontext auf den Stapel. Dadurch wird es zum aktuellen Scheduler. Wenn Sie `CurrentScheduler::Detach`aufzurufen, ruft die Laufzeit den aktuellen Scheduler aus dem Stapel für den aktuellen Kontext ab und legt den vorherigen Zeit Planungs Modul als aktuellen Planer fest.

Die Laufzeit bietet mehrere Möglichkeiten zum Verwalten der Lebensdauer einer planerinstanz. Die folgende Tabelle zeigt die entsprechende Methode, die den Scheduler für jede Methode, die einen Planer erstellt oder an den aktuellen Kontext anfügt, vom aktuellen Kontext freigibt bzw. trennt.

|Create-oder Attach-Methode|Release-oder trennen-Methode|
|-----------------------------|------------------------------|
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|
|`Scheduler::Create`|`Scheduler::Release`|
|`Scheduler::Attach`|`CurrentScheduler::Detach`|
|`Scheduler::Reference`|`Scheduler::Release`|

Wenn Sie die ungeeignete Release-oder trennen-Methode aufrufen, wird in der Laufzeit nicht bestimmtes Verhalten erzeugt.

Wenn Sie z. b. die-Funktion verwenden, die bewirkt, dass die Laufzeit den Standard Planer für Sie erstellt, dürfen Sie diesen Scheduler nicht freigeben oder trennen. Die Laufzeit verwaltet die Lebensdauer eines beliebigen Schedulers, den Sie erstellt.

Da die Laufzeit ein `Scheduler` Objekt nicht zerstört, bevor alle Aufgaben abgeschlossen sind, können Sie die [Concurrency:: Scheduler:: registershutdownetvent](reference/scheduler-class.md#registershutdownevent) -Methode oder die [Concurrency:: CurrentScheduler:: registershutdownetvent](reference/currentscheduler-class.md#registershutdownevent) -Methode verwenden, um eine Benachrichtigung zu erhalten, wenn ein `Scheduler` Objekt zerstört wird. Dies ist hilfreich, wenn Sie auf die Beendigung aller Aufgaben warten müssen, die von einem `Scheduler`-Objekt geplant werden.

[[Nach oben](#top)]

## <a name="features"></a>Methoden und Features

In diesem Abschnitt werden die wichtigen Methoden der Klassen `CurrentScheduler` und `Scheduler` zusammengefasst.

Stellen Sie sich die `CurrentScheduler`-Klasse als Hilfsmethode zum Erstellen eines Zeit Planungs Moduls zur Verwendung im aktuellen Kontext vor. Mit der `Scheduler`-Klasse können Sie einen Planer steuern, der zu einem anderen Kontext gehört.

In der folgenden Tabelle sind die wichtigen Methoden aufgeführt, die von der `CurrentScheduler`-Klasse definiert werden.

|Methode|BESCHREIBUNG|
|------------|-----------------|
|[Erstellen](reference/currentscheduler-class.md#create)|Erstellt ein `Scheduler` Objekt, das die angegebene Richtlinie verwendet und dem aktuellen Kontext zuordnet.|
|[Get](reference/currentscheduler-class.md#get)|Ruft einen Zeiger auf das `Scheduler` Objekt ab, das dem aktuellen Kontext zugeordnet ist. Diese Methode erhöht nicht den Verweis Zähler des `Scheduler` Objekts.|
|[Trennen](reference/currentscheduler-class.md#detach)|Trennt den aktuellen Planer vom aktuellen Kontext und legt den vorherigen Zeit Planungs Modul als aktuellen Planer fest.|
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|Registriert ein Ereignis, das von der Laufzeit festgelegt wird, wenn der aktuelle Scheduler zerstört wird.|
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|Erstellt ein [parallelcurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) -Objekt im aktuellen Scheduler.|
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|Fügt der Planungs Warteschlange des aktuellen Zeit Planungs Moduls einen Lightweight-Task hinzu.|
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|Ruft eine Kopie der Richtlinie ab, die dem aktuellen Scheduler zugeordnet ist.|

In der folgenden Tabelle sind die wichtigen Methoden aufgeführt, die von der `Scheduler`-Klasse definiert werden.

|Methode|BESCHREIBUNG|
|------------|-----------------|
|[Erstellen](reference/scheduler-class.md#create)|Erstellt ein `Scheduler` Objekt, das die angegebene Richtlinie verwendet.|
|[Anfügen](reference/scheduler-class.md#attach)|Ordnet das `Scheduler`-Objekt zusammen mit dem aktuellen Kontext zu.|
|[Referenz](reference/scheduler-class.md#reference)|Inkremente den Verweis Zählers des `Scheduler` Objekts.|
|[Release](reference/scheduler-class.md#release)|Dekremente den Verweis Zählers des `Scheduler` Objekts.|
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|Registriert ein Ereignis, das von der Laufzeit festgelegt wird, wenn das `Scheduler` Objekt zerstört wird.|
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|Erstellt ein [parallelcurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) -Objekt im `Scheduler` Objekt.|
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|Plant eine leichte Aufgabe aus dem `Scheduler`-Objekt.|
|[GetPolicy](reference/scheduler-class.md#getpolicy)|Ruft eine Kopie der Richtlinie ab, die dem `Scheduler` Objekt zugeordnet ist.|
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|Legt die Richtlinie fest, die beim Erstellen des Standardzeit Planungs Moduls von der Laufzeit verwendet werden soll.|
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|Stellt die Standard Richtlinie wieder her, die vor dem Aufruf`SetDefaultSchedulerPolicy`aktiv war. Wenn der Standard Planer nach diesem-Befehl erstellt wird, verwendet die Common Language Runtime die Standardrichtlinien Einstellungen, um den Scheduler zu erstellen.|

[[Nach oben](#top)]

## <a name="example"></a> Beispiel

Grundlegende Beispiele zum Erstellen und Verwalten einer Scheduler-Instanz finden Sie unter Gewusst [wie: Verwalten einer planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).

## <a name="see-also"></a>Weitere Informationen

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)<br/>
[Planungsgruppen](../../parallel/concrt/schedule-groups.md)
