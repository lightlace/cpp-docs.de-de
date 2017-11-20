---
title: Planerinstanzen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b21ea045d8c875bac6ca5b068cdeb919f0d6ad85
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="scheduler-instances"></a>Planerinstanzen
Dieses Dokument beschreibt die Rolle des Scheduler-Instanzen in der Concurrency Runtime sowie zum Verwenden der [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) und [Concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) Klassen zum Erstellen und verwalten Scheduler-Instanzen. Planerinstanzen sind nützlich, wenn Sie explizite Planungsrichtlinien bestimmten Arten von Arbeitslasten zuordnen möchten. Beispielsweise können Sie eine Planerinstanz erstellen, um einige Aufgaben mit höherer Threadpriorität auszuführen und andere Aufgaben mit dem Standardplaner mit normaler Threadpriorität auszuführen.  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie beim Optimieren der Leistung Ihrer Anwendungen unterstützt, empfiehlt es sich, dass die zu Beginn der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) Domänenmodus noch nicht mit der Concurrency Runtime.  
  
##  <a name="top"></a> Abschnitte  
  
-   [Der Planer und CurrentScheduler-Klasse](#classes)  
  
-   [Erstellen einer Planerinstanz](#creating)  
  
-   [Verwalten der Lebensdauer einer Planerinstanz](#managing)  
  
-   [Methoden und Funktionen](#features)  
  
-   [Beispiel](#example)  
  
##  <a name="classes"></a>Der Planer und CurrentScheduler-Klasse  
 Der Taskplaner ermöglicht es Anwendungen, eine oder mehrere *Planerinstanzen* zum Planen der Arbeit. Die [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) Klasse stellt eine Planerinstanz und kapselt die Funktionalität, die im Zusammenhang mit der Planung von Aufgaben ist.  
  
 Ein Thread, der an einen Planer angefügt ist, wird als bezeichnet ein *Ausführungskontext*, oder nur *Kontext*. Ein Planer kann zu einem beliebigen Zeitpunkt im aktuellen Kontext aktiv sein. Der aktive Planer ist auch bekannt als die *aktuellen Planer*. Die Concurrency Runtime verwendet die [Concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) Klasse, um den Zugriff auf den aktuellen Planer zu ermöglichen. Die aktuellen Planer für einen Kontext kann sich vom aktuellen Planer für einen anderen Kontext unterscheiden. Die Common Language Runtime stellt eine auf Prozessebene-Darstellung des aktuellen Planers nicht bereit.  
  
 In der Regel die `CurrentScheduler` Klasse wird verwendet, um den aktuellen Planer zugreifen. Die `Scheduler` Klasse ist hilfreich, wenn müssen Sie einen Planer zu verwalten, die nicht dem aktuellen Objekt ist.  
  
 In den folgenden Abschnitten wird beschrieben, wie zum Erstellen und Verwalten einer Planerinstanz. Ein vollständiges Beispiel, in dem diese Aufgaben veranschaulicht, finden Sie unter [Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="creating"></a>Erstellen einer Planerinstanz  
 Es sind diese drei Methoden zum Erstellen einer `Scheduler` Objekt:  
  
-   Wenn kein Zeitplan vorhanden ist, erstellt die Laufzeit einen Standardplaner für Sie aus, wenn Sie Laufzeitfunktionen, z. B. parallele Algorithmen verwenden, Arbeitsvorgänge auszuführen. Der Standardplaner wird dem aktuellen Planer für den Kontext, der die parallelen Arbeitsvorgänge initiiert.  
  

-   Die [CurrentScheduler](reference/currentscheduler-class.md#create) Methode erstellt ein `Scheduler` Objekt, das eine bestimmte Richtlinie verwendet, und ordnet diesen Planer dem aktuellen Kontext.  
  
-   Die [Scheduler](reference/scheduler-class.md#create) Methode erstellt eine `Scheduler` -Objekt, das eine bestimmte Richtlinie verwendet, aber nicht mit dem aktuellen Kontext zuzuordnen.  

  
 Ermöglicht die Laufzeit einen Standardplaner erstellt, können alle gleichzeitigen Aufgaben auf demselben Zeitplanungsmodul freigeben. In der Regel die Funktionalität, die von bereitgestellte der [Parallel Patterns Library](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) oder die [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) wird verwendet, um parallele Arbeitsvorgänge auszuführen. Aus diesem Grund müssen Sie nicht direkt mit der Planer zum Steuern der Richtlinie oder Lebensdauer zu arbeiten. Bei Verwendung von der PPL oder der Agents Library erstellt die Laufzeit den Standardplaner, wenn sie nicht vorhanden, und erhöht die aktuellen Planer für jeden Kontext. Wenn Sie einen Planer erstellen und als aktueller Planer festgelegt haben, verwendet die Laufzeit diesen Planer Aufgaben planen. Erstellen Sie zusätzliche Planerinstanzen nur, wenn Sie eine bestimmte Planungsrichtlinie benötigen. Weitere Informationen zu den Richtlinien, die einem Zeitplanungsmodul zugeordnet sind, finden Sie unter [Planerrichtlinien](../../parallel/concrt/scheduler-policies.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="managing"></a>Verwalten der Lebensdauer einer Planerinstanz  
 Die Common Language Runtime verwendet einen verweiszählung Mechanismus zur Steuerung der Lebensdauer des `Scheduler` Objekte.  
  

 Bei Verwendung der `CurrentScheduler::Create` Methode oder die `Scheduler::Create` Methode zum Erstellen einer `Scheduler` -Objekt, die Common Language Runtime setzt den Verweiszähler des Planers auf 1. Die Common Language Runtime inkrementiert den Verweiszähler beim Aufrufen der [Concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) Methode. Die `Scheduler::Attach` Methode ordnet die `Scheduler` -Objekts zusammen mit den aktuellen Kontext. Dies macht es den aktuellen Planer. Beim Aufrufen der `CurrentScheduler::Create` -Methode, die Laufzeit erstellt eine `Scheduler` -Objekt und fügt es an den aktuellen Kontext (und setzt den Verweiszähler auf einen). Sie können auch die [Verweiszählerwert](reference/scheduler-class.md#reference) Methode inkrementiert den Verweiszähler des ein `Scheduler` Objekt.  
  
 Die Common Language Runtime den Verweiszähler beim Aufrufen der [CurrentScheduler](reference/currentscheduler-class.md#detach) Methode, um den aktuellen Planer zu trennen, oder rufen Sie die [Concurrency::Scheduler::Release](reference/scheduler-class.md#release) Methode. Wenn der Verweiszähler 0 erreicht hat, zerstört die Runtime die `Scheduler` Objekt, nachdem alle geplanten Aufgaben beendet. Ein aktuell ausgeführter Task ist zulässig, um den Verweiszähler der aktuellen Planer zu erhöhen. Aus diesem Grund, wenn der Verweiszähler, 0 (null erreicht), und eine Aufgabe den Verweiszähler dieser Planergruppe inkrementiert, die Common Language Runtime nicht zerstört die `Scheduler` Objekt, bis der Verweiszähler erneut 0 (null) erreicht und alle Aufgaben abgeschlossen sind.  

  
 Die Common Language Runtime verwaltet einen internen Stapel von `Scheduler` Objekte für jeden Kontext. Beim Aufrufen der `Scheduler::Attach` oder `CurrentScheduler::Create` überträgt mithilfe von Push-Methode, die Common Language Runtime, die `Scheduler` Objekt im Stapel für den aktuellen Kontext. Dies macht es den aktuellen Planer. Beim Aufruf `CurrentScheduler::Detach`, die Laufzeit wird der aktuelle Planer vom Stapel für den aktuellen Kontext und das vorherige Objekt als aktueller Planer festgelegt.  
  
 Die Common Language Runtime bietet verschiedene Methoden zum Verwalten der Lebensdauer einer Planerinstanz. Die folgende Tabelle zeigt die entsprechende Methode, die frei, oder trennt den Planer aus dem aktuellen Kontext für jede Methode, die erstellt oder einen Planer an den aktuellen Kontext angefügt.  
  
|Erstellen oder die attach-Methode|Freigeben oder detach-Methode|  
|-----------------------------|------------------------------|  
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|  
|`Scheduler::Create`|`Scheduler::Release`|  
|`Scheduler::Attach`|`CurrentScheduler::Detach`|  
|`Scheduler::Reference`|`Scheduler::Release`|  
  
 Aufrufen der ungeeigneten freigeben Sie oder trennen Sie die Methode verursacht nicht definiertes Verhalten in der Common Language Runtime.  
  
 Bei Verwendung von Funktionen, z. B. die PPL, die die Laufzeit der Standardplaner für Sie erstellt wird, nicht freigeben oder diesen Planer zu trennen. Die Common Language Runtime verwaltet die Lebensdauer des einen Planer ein, dem erstellt wird.  
  

 Da die Runtime nicht zerstört ist ein `Scheduler` Objekt auf, bevor alle Aufgaben abgeschlossen haben, können Sie die [Concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) Methode oder die [Concurrency:: CurrentScheduler:: RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) Methode, um eine Benachrichtigung, wenn ein `Scheduler` -Objekt zerstört wird. Dies ist nützlich, wenn Sie für jede Aufgabe warten müssen, die von geplant wird ein `Scheduler` Objekt, um den Vorgang abzuschließen.  
  
 [[Nach oben](#top)]  
  
##  <a name="features"></a>Methoden und Funktionen  
 In diesem Abschnitt werden die Hauptmethoden der der `CurrentScheduler` und `Scheduler` Klassen.  
  
 Denken Sie an der `CurrentScheduler` Klasse als ein Hilfsprogramm zum Erstellen eines Planers für die Verwendung auf dem aktuellen Kontext. Die `Scheduler` -Klasse können Sie einen Planer zu steuern, die zu einem anderen Kontext gehört.  
  
 Die folgende Tabelle zeigt die wichtigen Methoden, die von definiert sind die `CurrentScheduler` Klasse.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Erstellen](reference/currentscheduler-class.md#create)|Erstellt ein `Scheduler` Objekt, das die angegebene Richtlinie verwendet, und ordnet sie dem aktuellen Kontext.|  
|[Get](reference/currentscheduler-class.md#get)|Ruft einen Zeiger auf die `Scheduler` Objekt, mit dem aktuellen Kontext zugeordnet ist. Diese Methode inkrementiert den Verweiszähler der nicht der `Scheduler` Objekt.|  
|[Trennen](reference/currentscheduler-class.md#detach)|Trennt den aktuellen Planer aus dem aktuellen Kontext aus, und das vorherige Objekt als aktueller Planer festgelegt.|  
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|Registriert ein Ereignis, das die Common Language Runtime festgelegt, wenn es sich bei der aktuellen Planer zerstört wird.|  
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|Erstellt eine [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Objekt im aktuellen Planer.|  
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|Der zeitplanwarteschlange des aktuellen Planers hinzugefügt eine einfache Aufgabe.|  
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|Ruft eine Kopie der Richtlinie, die vom aktuellen Planer zugeordnet ist.|  
  
 Die folgende Tabelle zeigt die wichtigen Methoden, die von definiert sind die `Scheduler` Klasse.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Erstellen](reference/scheduler-class.md#create)|Erstellt eine `Scheduler` -Objekt, das die angegebene Richtlinie verwendet.|  
|[Anfügen](reference/scheduler-class.md#attach)|Ordnet die `Scheduler` -Objekts zusammen mit den aktuellen Kontext.|  
|[Referenz](reference/scheduler-class.md#reference)|Inkrementiert den Verweiszähler des dem `Scheduler` Objekt.|  
|[Version](reference/scheduler-class.md#release)|Dekrementiert den Verweiszähler des dem `Scheduler` Objekt.|  
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|Registriert ein Ereignis, das die Common Language Runtime festgelegt wird, wenn die `Scheduler` -Objekt zerstört wird.|  
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|Erstellt eine [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Objekt in der `Scheduler` Objekt.|  
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|Plant eine einfache Aufgabe aus der `Scheduler` Objekt.|  
|[GetPolicy](reference/scheduler-class.md#getpolicy)|Ruft eine Kopie der Richtlinie zugeordnet ist, die die `Scheduler` Objekt.|  
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|Legt die Richtlinie für die Laufzeit zu verwendende Standardplaner erstellt.|  
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|Die Standardrichtlinie auf das Projekt, das vor dem Aufruf von aktiv war wiederhergestellt `SetDefaultSchedulerPolicy`. Wenn nach dem Aufruf der Standardplaner erstellt wird, verwendet die Runtime die Einstellungen der Standardrichtlinie, erstellt der Planer.|  

  
 [[Nach oben](#top)]  
  
##  <a name="example"></a> Beispiel  
 Einfache Beispiele für das Erstellen und Verwalten einer Planerinstanz finden Sie unter [Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)   
 [Planungsgruppen](../../parallel/concrt/schedule-groups.md)

