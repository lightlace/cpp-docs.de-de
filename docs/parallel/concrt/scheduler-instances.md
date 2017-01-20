---
title: "Planerinstanzen"
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
  - "Planerinstanzen"
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
caps.latest.revision: 7
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Planerinstanzen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument werden die Rolle von Planerinstanzen in der Concurrency Runtime sowie die Verwendung der Klassen [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) und [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) verwendet, um zu Planerinstanzen erstellen und zu verwalten.  Planerinstanzen sind nützlich, wenn Sie bestimmten Arten von Arbeitslasten explizite Planungsrichtlinien zuordnen möchten.  Beispielsweise können Sie eine Planerinstanz erstellen, um einige Aufgaben mit höherer Threadpriorität auszuführen und andere Aufgaben mit dem Standardplaner mit normaler Threadpriorität auszuführen.  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Es ist daher nicht erforderlich, einen Planer in der Anwendung zu erstellen.  Der Taskplaner ermöglicht eine genauere Steuerung der Leistung von Anwendungen. Aus diesem Grund wird empfohlen, mit der [Parallel Patterns Library \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie noch nicht mit der Concurrency Runtime vertraut sind.  
  
##  <a name="top"></a> Abschnitte  
  
-   [Die Scheduler\-Klasse und die CurrentScheduler\-Klasse](#classes)  
  
-   [Erstellen einer Planerinstanz](#creating)  
  
-   [Verwalten der Lebensdauer einer Planerinstanz](#managing)  
  
-   [Methoden und Funktionen](#features)  
  
-   [Beispiel](#example)  
  
##  <a name="classes"></a> Die Scheduler\-Klasse und die CurrentScheduler\-Klasse  
 Der Taskplaner ermöglicht Anwendungen die Arbeitsplanung mittels einer oder mehrerer *Planerinstanzen*.  Die [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md)\-Klasse stellt eine Planerinstanz dar und kapselt die Funktionalität, die im Zusammenhang mit Aufgaben verknüpft wird.  
  
 Der an einen Planer angefügte Thread wird als *Ausführungskontext* oder einfach als *Kontext* bezeichnet.  Ein Planer kann zu jedem beliebigen Zeitpunkt im aktuellen Kontext aktiv sein.  Der aktive Planer wird auch als *aktueller Planer* bezeichnet.  Die Concurrency Runtime verwendet die [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md)\-Klasse, um Zugriff auf den aktuellen Planer über.  Der aktuelle Planer für einen Kontext kann sich vom aktuellen Planer für einen anderen Kontext unterscheiden.  Von der Runtime wird keine Darstellung des aktuellen Planers auf Prozessebene bereitgestellt.  
  
 In der Regel wird die `CurrentScheduler`\-Klasse für den Zugriff auf den aktuellen Planer verwendet.  Die `Scheduler`\-Klasse ist hilfreich, wenn Sie einen anderen Planer als den aktuellen verwalten müssen.  
  
 In den folgenden Abschnitten erfahren Sie, wie Sie eine Planerinstanz erstellen und verwalten.  Ein vollständiges Beispiel zur Veranschaulichung dieser Aufgaben finden Sie unter [Gewusst wie: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="creating"></a> Erstellen einer Planerinstanz  
 Es gibt drei Möglichkeiten, ein `Scheduler`\-Objekt zu erstellen:  
  
-   Wenn kein Planer vorhanden ist, erstellt die Runtime automatisch einen Standardplaner, wenn Sie Laufzeitfunktionen, wie z. B. einen parallelen Algorithmus, zur Ausführung von Arbeiten verwenden.  Der Standardplaner wird als aktueller Planer für den Kontext festgelegt, mit dem die parallele Verarbeitung initiiert wird.  
  
-   Die [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md)\-Methode erstellt ein `Scheduler`\-Objekt, das eine bestimmte Richtlinie und weist dieses Objekt bzw. diesen Planer dem aktuellen Kontext zu.  
  
-   Die [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md)\-Methode erstellt ein `Scheduler`\-Objekt, das eine bestimmte Richtlinie verwendet, weist dieses aber nicht dem aktuellen Kontext zu.  
  
 Bei der Erstellung eines Standardplaners durch die Runtime können alle gleichzeitig ausgeführten Aufgaben denselben Planer nutzen.  In der Regel wird die von der [Parallel Patterns Library](../../parallel/concrt/parallel-patterns-library-ppl.md) \(PPL\) oder von der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) bereitgestellte Funktionalität zur Ausführung paralleler Arbeitsschritte verwendet.  Somit müssen Sie die Richtlinie und die Lebensdauer des Planers nicht direkt steuern.  Bei Nutzung der PPL oder der Agents Library erstellt die Runtime den Standardplaner, falls kein Planer vorhanden ist, und legt diesen als aktuellen Planer für jeden Kontext fest.  Wenn Sie einen Planer erstellen und als aktuellen Planer festlegen, verwendet die Laufzeit diesen Planer, um Aufgaben zu planen.  Erstellen Sie zusätzliche Planerinstanzen nur, wenn Sie eine bestimmte Planungsrichtlinie benötigen.  Weitere Informationen zu Richtlinien, die einem Planer zugeordnet sind, finden Sie [Planerrichtlinien](../../parallel/concrt/scheduler-policies.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="managing"></a> Verwalten der Lebensdauer einer Planerinstanz  
 Die Runtime steuert die Lebensdauer von `Scheduler`\-Objekten mithilfe eines Mechanismus zum Zählen von Verweisen.  
  
 Wenn Sie die `CurrentScheduler::Create`\-Methode oder die `Scheduler::Create`\-Methode zur Erstellung eines `Scheduler`\-Objekts verwenden, setzt die Runtime den Verweiszähler dieses Planers auf 1.  Der Wert des Verweiszählers wird erhöht, wenn Sie die [concurrency::Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md)\-Methode aufrufen.  Die `Scheduler::Attach`\-Methode ordnet das `Scheduler`\-Objekt dem aktuellen Kontext zu.  Dadurch wird das Objekt als aktueller Planer festgelegt.  Wenn Sie die `CurrentScheduler::Create`\-Methode aufrufen, erstellt die Runtime ein `Scheduler`\-Objekt und weist dieses dem aktuellen Kontext zu \(und setzt den Verweiszähler auf 1\).  Sie können die Methode auch [concurrency::Scheduler::Reference](../Topic/Scheduler::Reference%20Method.md) verwenden, um den Verweiszähler `Scheduler` eines Objekts zu erhöhen.  
  
 Der Wert des Verweiszählers, wenn Sie die Methode [concurrency::CurrentScheduler::Detach](../Topic/CurrentScheduler::Detach%20Method.md) aufrufen, um den aktuellen Planer abzutrennen, oder ruft die Methode [concurrency::Scheduler::Release](../Topic/Scheduler::Release%20Method.md) auf.  Wenn der Verweiszähler 0 \(null\) erreicht, zerstört die Runtime das `Scheduler`\-Objekt, nachdem alle geplanten Aufgaben beendet wurden.  Eine ausgeführte Aufgabe kann den Verweiszählerwert des aktuellen Planers erhöhen.  Wenn also der Verweiszähler 0 \(null\) erreicht und eine Aufgabe den Zählerwert erhöht, wird das `Scheduler`\-Objekt nicht zerstört, bis der Verweiszähler erneut 0 \(null\) erreicht und alle Aufgaben beendet sind.  
  
 Die Runtime behält für jeden Kontext einen internen Stapel von `Scheduler`\-Objekten bei.  Wenn Sie die `Scheduler::Attach`\-Methode oder die `CurrentScheduler::Create`\-Methode aufrufen, wird das `Scheduler`\-Objekt auf dem Stapel für den aktuellen Kontext abgelegt \(Push\-Verfahren\).  Dadurch wird das Objekt als aktueller Planer festgelegt.  Wenn Sie `CurrentScheduler::Detach` aufrufen, wird der aktuelle Planer vom Stapel für den aktuellen Kontext aufgenommen \(Pop\-Verfahren\) und das vorherige Objekt als aktueller Planer festgelegt.  
  
 Die Runtime bietet mehrere Möglichkeiten zur Verwaltung der Lebensdauer einer Planerinstanz.  Die folgende Tabelle enthält die jeweils entsprechende Methode zum Freigeben bzw. Trennen des Planers vom aktuellen Kontext für die Methoden zum Erstellen bzw. Zuweisen eines Planers zum aktuellen Kontext.  
  
|Methode zum Erstellen bzw. Zuweisen|Methode zum Freigeben bzw. Trennen|  
|-----------------------------------------|----------------------------------------|  
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|  
|`Scheduler::Create`|`Scheduler::Release`|  
|`Scheduler::Attach`|`CurrentScheduler::Detach`|  
|`Scheduler::Reference`|`Scheduler::Release`|  
  
 Das Aufrufen einer nicht geeigneten release\- oder detach\-Methode verursacht nicht definiertes Verhalten zur Laufzeit.  
  
 Wenn Sie Funktionen verwenden, die bewirken, dass zur Laufzeit automatisch ein Standardplaner erstellt wird, wie z. B. die PPL, müssen Sie diesen Planer nicht manuell freigeben\/trennen.  Die Lebensdauer automatisch erstellter Planer wird von der Runtime verwaltet.  
  
 Da die Runtime ein `Scheduler`\-Objekt zerstört, wenn alle Aufgaben beendet haben, können Sie die Methode [concurrency::Scheduler::RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md) oder die [concurrency::CurrentScheduler::RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md)\-Methode verwenden, um eine Benachrichtigung zu empfangen, wenn ein `Scheduler`\-Objekt zerstört wird.  Dies ist nützlich, wenn Sie auf das Beenden der einzelnen von einem `Scheduler`\-Objekt geplanten Aufgaben warten müssen.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="features"></a> Methoden und Funktionen  
 In diesem Abschnitt sind alle wichtigen Methoden der `CurrentScheduler`\-Klasse und der `Scheduler`\-Klasse zusammengefasst.  
  
 Betrachten Sie die `CurrentScheduler`\-Klasse als Hilfsklasse zur Erstellung eines Planers für den aktuellen Kontext.  Mit der `Scheduler`\-Klasse können Sie einen Planer steuern, der einem anderen Kontext zugewiesen ist.  
  
 Die folgende Tabelle enthält alle wichtigen von der `CurrentScheduler`\-Klasse definierten Methoden.  
  
|Methode|**Beschreibung**|  
|-------------|----------------------|  
|[Create](../Topic/CurrentScheduler::Create%20Method.md)|Erstellt ein `Scheduler`\-Objekt, das die angegebene Richtlinie verwendet, und weist dieses dem aktuellen Kontext zu.|  
|[Get](../Topic/CurrentScheduler::Get%20Method.md)|Ruft einen Zeiger auf das `Scheduler`\-Objekt ab, das dem aktuellen Kontext zugewiesen ist.  Diese Methode erhöht den Verweiszählerwert des `Scheduler`\-Objekts nicht.|  
|[Trennen](../Topic/CurrentScheduler::Detach%20Method.md)|Trennt den aktuellen Planer vom aktuellen Kontext und legt den vorherigen Planer als aktuellen Planer fest.|  
|[RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md)|Registriert ein Ereignis, das von der Runtime festgelegt wird, wenn der aktuelle Planer zerstört wird.|  
|[CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md)|Erstellt ein [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md)\-Objekt im aktuellen Planer.|  
|[ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md)|Fügt der Warteschlange des aktuellen Planers eine einfache Aufgabe hinzu.|  
|[GetPolicy](../Topic/CurrentScheduler::GetPolicy%20Method.md)|Ruft eine Kopie der Richtlinie ab, die dem aktuellen Planer zugeordnet ist.|  
  
 Die folgende Tabelle enthält alle wichtigen von der `Scheduler`\-Klasse definierten Methoden.  
  
|Methode|**Beschreibung**|  
|-------------|----------------------|  
|[Create](../Topic/Scheduler::Create%20Method.md)|Erstellt ein `Scheduler`\-Objekt, das die angegebene Richtlinie verwendet.|  
|[Anfügen](../Topic/Scheduler::Attach%20Method.md)|Ordnet das `Scheduler`\-Objekt dem aktuellen Kontext zu.|  
|[Verweis](../Topic/Scheduler::Reference%20Method.md)|Erhöht den Verweiszählerwert des `Scheduler`\-Objekts.|  
|[Release](../Topic/Scheduler::Release%20Method.md)|Verringert den Verweiszählerwert des `Scheduler`\-Objekts.|  
|[RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md)|Registriert ein Ereignis, das von der Runtime festgelegt wird, wenn das `Scheduler`\-Objekt zerstört wird.|  
|[CreateScheduleGroup](../Topic/Scheduler::CreateScheduleGroup%20Method.md)|Erstellt ein [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md)\-Objekt im `Scheduler`\-Objekt.|  
|[ScheduleTask](../Topic/Scheduler::ScheduleTask%20Method.md)|Plant eine einfache Aufgabe im `Scheduler`\-Objekt.|  
|[GetPolicy](../Topic/Scheduler::GetPolicy%20Method.md)|Ruft eine Kopie der Richtlinie ab, die dem `Scheduler`\-Objekt zugeordnet ist.|  
|[SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)|Legt die Richtlinie fest, die beim Erstellen des Standardplaners von der Runtime verwendet wird.|  
|[ResetDefaultSchedulerPolicy](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md)|Stellt die Richtlinie, die vor dem Aufruf von `SetDefaultSchedulerPolicy` aktiviert war, als Standardrichtlinie wieder her.  Wenn der Standardplaner nach diesem Aufruf erstellt wird, verwendet die Runtime die Standardrichtlinieneinstellungen beim Erstellen des Planers.|  
  
 \[[Nach oben](#top)\]  
  
##  <a name="example"></a> Beispiel  
 Zwei grundlegende Beispiele zum Erstellen und Verwalten einer Planerinstanz finden Sie unter [Gewusst wie: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md).  
  
## Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Gewusst wie: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)   
 [Planungsgruppen](../../parallel/concrt/schedule-groups.md)