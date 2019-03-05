---
title: Planerinstanzen
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
ms.openlocfilehash: 19bd871857dcef6aaef153798388c0272239fa1f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301297"
---
# <a name="scheduler-instances"></a>Planerinstanzen

Dieses Dokument beschreibt die Rolle des Scheduler-Instanzen in der Concurrency Runtime und wie Sie mit der [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) und [Concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) Klassen zum Erstellen und verwalten Scheduler-Instanzen. Planerinstanzen sind nützlich, wenn Sie explizite Planungsrichtlinien bestimmten Arten von Arbeitslasten zuordnen möchten. Beispielsweise können Sie eine Planerinstanz erstellen, um einige Aufgaben mit höherer Threadpriorität auszuführen und andere Aufgaben mit dem Standardplaner mit normaler Threadpriorität auszuführen.

> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner die Leistung Ihrer Anwendungen optimieren können, es wird empfohlen, zunächst die [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) möchten noch nicht mit der Concurrency Runtime.

##  <a name="top"></a> Abschnitte

- [Der Scheduler und die CurrentScheduler-Klasse](#classes)

- [Erstellen einer Planerinstanz](#creating)

- [Verwalten der Lebensdauer einer Planerinstanz](#managing)

- [Methoden und Funktionen](#features)

- [Beispiel](#example)

##  <a name="classes"></a> Der Scheduler und die CurrentScheduler-Klasse

Die Aufgabenplanung ermöglicht Anwendungen die eine oder mehrere *Planerinstanzen* um Arbeit einzuplanen. Die [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) Klasse stellt eine Planerinstanz und kapselt die Funktionalität, die sich auf das Planen von Aufgaben beziehen.

Ein Thread, der an einen Planer angefügt ist, wird als bezeichnet ein *Ausführungskontext*, oder nur *Kontext*. Ein Planer kann zu einem beliebigen Zeitpunkt auf den aktuellen Kontext aktiv sein. Der aktive Planer ist auch bekannt als die *aktuellen Planer*. Die Concurrency Runtime verwendet die [Concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) Klasse, um Zugriff auf den aktuellen Planer zu ermöglichen. Die aktuelle Planer für einen Kontext kann vom aktuellen Planer für einen anderen Kontext unterscheiden. Die Laufzeit stellt keine auf Prozessebene-Darstellung des aktuellen Planers bereit.

In der Regel die `CurrentScheduler` Klasse wird verwendet, um den aktuellen Scheduler zugreifen. Die `Scheduler` Klasse ist hilfreich, wenn es sich bei müssen Sie einen Planer zu verwalten, die nicht dem aktuellen Objekt ist.

In den folgenden Abschnitten wird beschrieben, wie zum Erstellen und Verwalten einer Planerinstanz. Ein vollständiges Beispiel, das diese Aufgaben veranschaulicht, finden Sie unter [Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).

[[Nach oben](#top)]

##  <a name="creating"></a> Erstellen einer Planerinstanz

Es sind diese drei Methoden zum Erstellen einer `Scheduler` Objekt:

- Wenn kein Planer vorhanden ist, erstellt die Laufzeit einen Standardplaner für Sie bei der Verwendung von Common Language Runtime-Funktionen, z. B. parallele Algorithmen, Arbeiten ausführen. Der Standard-Scheduler wird, den aktuellen Scheduler für den Kontext an, der die parallele Verarbeitung initiiert wird.

- Die [CurrentScheduler](reference/currentscheduler-class.md#create) -Methode erstellt eine `Scheduler` Objekt, das eine bestimmte Richtlinie verwendet, und dieser Planer mit dem aktuellen Kontext verknüpft.

- Die [Scheduler](reference/scheduler-class.md#create) -Methode erstellt eine `Scheduler` -Objekt, das eine bestimmte Richtlinie verwendet, aber nicht mit dem aktuellen Kontext zuzuordnen.

Ermöglicht die Laufzeit einen Standardplaner erstellt kann alle gleichzeitig ausgeführten Aufgaben, die demselben Zeitplanungsmodul freizugeben. In der Regel die Funktionalität, die von bereitgestellte der [Parallel Patterns Library](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) oder die [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) wird verwendet, um die Ausführung paralleler arbeiten. Aus diesem Grund müssen Sie nicht direkt mit den Scheduler so steuern die Richtlinie oder für die Lebensdauer zu arbeiten. Bei Verwendung von der PPL oder der Agents Library erstellt die Laufzeit den Standard-Scheduler, wenn es nicht vorhanden, und es den aktuellen Scheduler für jeden Kontext macht. Wenn Sie einen Planer erstellen und als aktuellen Planer festgelegt, verwendet die Runtime dieser Planer, um Aufgaben zu planen. Erstellen Sie zusätzliche Planerinstanzen, nur, wenn Sie eine bestimmte Richtlinie zur Taskplanung benötigen. Weitere Informationen zu den Richtlinien, die einen Planer zugeordnet sind, finden Sie unter [Planerrichtlinien](../../parallel/concrt/scheduler-policies.md).

[[Nach oben](#top)]

##  <a name="managing"></a> Verwalten der Lebensdauer einer Planerinstanz

Die Runtime verwendet einen Mechanismus zum Zählen von verweisen, um die Steuerung der Lebensdauer des `Scheduler` Objekte.

Bei Verwendung der `CurrentScheduler::Create` Methode oder die `Scheduler::Create` Methode zum Erstellen einer `Scheduler` Objekt ist, wird die Laufzeit legt die Initiale Verweisanzahl dieses Planers auf einen. Die Laufzeit inkrementiert den Verweiszähler beim Aufrufen der [Concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) Methode. Die `Scheduler::Attach` Methode ordnet die `Scheduler` Objekt zusammen mit den aktuellen Kontext. Dies macht es den aktuellen Planer. Beim Aufrufen der `CurrentScheduler::Create` -Methode erstellt die Runtime eine `Scheduler` Objekt und fügt sie an den aktuellen Kontext (und legt die Anzahl der Verweise auf einen). Sie können auch die [Verweiszählerwert](reference/scheduler-class.md#reference) Methode inkrementiert den Verweiszähler des eine `Scheduler` Objekt.

Die Common Language Runtime dekrementiert den Verweiszähler beim Aufruf der [CurrentScheduler](reference/currentscheduler-class.md#detach) Methode, um die aktuellen Planer zu trennen, oder rufen Sie die [Concurrency::Scheduler::Release](reference/scheduler-class.md#release) Methode. Wenn der Verweiszähler null erreicht, löscht die Laufzeit die `Scheduler` Objekt nach dem alle geplanten Aufgaben beendet. Ein aktuell ausgeführter Task ist zulässig, um den Verweiszähler des dem aktuellen Planer zu erhöhen. Aus diesem Grund, wenn der Verweiszähler, 0 (null erreicht), eine Aufgabe den Verweiszähler inkrementiert die Laufzeit nicht zerstört die `Scheduler` Objekt, bis der Verweiszähler wird erneut 0 (null) erreicht, und alle Aufgaben abgeschlossen sind.

Die Common Language Runtime verwaltet einen internen Stapel von `Scheduler` Objekte für jeden Kontext. Beim Aufrufen der `Scheduler::Attach` oder `CurrentScheduler::Create` -Methode, die Laufzeit pushvorgängen, die `Scheduler` Objekt im Stapel für den aktuellen Kontext. Dies macht es den aktuellen Planer. Beim Aufruf `CurrentScheduler::Detach`, die Laufzeit wird der aktuelle Planer aus dem Stapel für den aktuellen Kontext und das vorherige Objekt als aktuellen Planer festgelegt.

Die Runtime bietet verschiedene Möglichkeiten zum Verwalten der Lebensdauer einer Planerinstanz. Die folgende Tabelle zeigt die entsprechende Methode, die frei, oder trennt den Planer im aktuellen Kontext für jede Methode, die erstellt oder einen Planer an den aktuellen Kontext angefügt.

|Erstellen oder die attach-Methode|Freigegeben oder detach-Methode|
|-----------------------------|------------------------------|
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|
|`Scheduler::Create`|`Scheduler::Release`|
|`Scheduler::Attach`|`CurrentScheduler::Detach`|
|`Scheduler::Reference`|`Scheduler::Release`|

Aufrufen der ungeeignete freigegeben Sie oder trennen Sie die Methode verursacht nicht definiertes Verhalten in der Runtime.

Bei Verwendung von Funktionen, z. B. in der PPL, die bewirkt, die Laufzeit den Standardplaner für Sie erstellt dass, nicht freigeben oder Trennen von diesem Zeitplanungsmodul. Die Runtime verwaltet die Lebensdauer des einen Planer, den erstellt wird.

Da die Runtime nicht zerstört wird eine `Scheduler` Objekt auf, bevor alle Aufgaben abgeschlossen haben, können Sie die [Concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) Methode oder der [Concurrency:: CurrentScheduler:: RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) Methode, um eine Benachrichtigung bei einem `Scheduler` -Objekt zerstört wird. Dies ist nützlich, wenn Sie für jede Aufgabe warten müssen, die von geplant wird eine `Scheduler` Objekt, um den Vorgang abzuschließen.

[[Nach oben](#top)]

##  <a name="features"></a> Methoden und Funktionen

In diesem Abschnitt werden die Hauptmethoden der zusammengefasst die `CurrentScheduler` und `Scheduler` Klassen.

Stellen Sie sich die `CurrentScheduler` Klasse als ein Hilfsprogramm zum Erstellen eines Planers für auf dem aktuellen Kontext. Die `Scheduler` Klasse können Sie einen Planer steuern, die zu einem anderen Kontext gehört.

Die folgende Tabelle zeigt die wichtigen Methoden, die von definiert sind die `CurrentScheduler` Klasse.

|Methode|Beschreibung|
|------------|-----------------|
|[Erstellen](reference/currentscheduler-class.md#create)|Erstellt eine `Scheduler` -Objekt, das die angegebene Richtlinie verwendet und ordnet sie dem aktuellen Kontext.|
|[Get](reference/currentscheduler-class.md#get)|Ruft einen Zeiger auf die `Scheduler` -Objekt, das mit dem aktuellen Kontext verknüpft ist. Diese Methode nicht inkrementiert den Verweiszähler des dem `Scheduler` Objekt.|
|[Trennen](reference/currentscheduler-class.md#detach)|Trennt den aktuellen Planer aus dem aktuellen Kontext und dem vorherigen Beispiel als aktuellen Planer legt sie fest.|
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|Registriert ein Ereignis, das die Laufzeit legt fest, wenn die aktuelle Planer zerstört wird.|
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|Erstellt eine [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Objekt im aktuellen Planer.|
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|Eine einfache Aufgabe und der zeitplanwarteschlange des aktuellen Planer hinzugefügt.|
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|Ruft eine Kopie der Richtlinie, die den aktuellen Planer zugeordnet ist.|

Die folgende Tabelle zeigt die wichtigen Methoden, die von definiert sind die `Scheduler` Klasse.

|Methode|Beschreibung|
|------------|-----------------|
|[Erstellen](reference/scheduler-class.md#create)|Erstellt eine `Scheduler` Objekt, das die angegebene Richtlinie verwendet.|
|[Anfügen](reference/scheduler-class.md#attach)|Ordnet die `Scheduler` Objekt zusammen mit den aktuellen Kontext.|
|[Verweis](reference/scheduler-class.md#reference)|Inkrementiert den Verweiszähler des dem `Scheduler` Objekt.|
|[Version](reference/scheduler-class.md#release)|Dekrementiert den Verweiszähler des dem `Scheduler` Objekt.|
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|Registriert ein Ereignis, das die Laufzeit festgelegt wird, wenn die `Scheduler` -Objekt zerstört wird.|
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|Erstellt eine [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) -Objekt in der `Scheduler` Objekt.|
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|Plant eine einfache Aufgabe aus der `Scheduler` Objekt.|
|[GetPolicy](reference/scheduler-class.md#getpolicy)|Ruft eine Kopie der Richtlinie zugeordnet ist, die die `Scheduler` Objekt.|
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|Legt die Richtlinie für die Laufzeit verwendet wird, wenn es den Standard-Scheduler erstellt.|
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|Stellt wieder her, die vor dem Aufruf von aktiv war die Standardrichtlinie `SetDefaultSchedulerPolicy`. Wenn nach dem Aufruf der Standard-Scheduler erstellt wird, verwendet die Runtime die Einstellungen der Standardrichtlinie für den Scheduler zu erstellen.|

[[Nach oben](#top)]

##  <a name="example"></a> Beispiel

Einfache Beispiele für das Erstellen und Verwalten einer Planerinstanz, finden Sie unter [Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).

## <a name="see-also"></a>Siehe auch

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)<br/>
[Planungsgruppen](../../parallel/concrt/schedule-groups.md)
