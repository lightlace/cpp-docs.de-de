---
title: "Gewusst wie: Verwalten einer Planerinstanz | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verwalten einer Planerinstanz [Concurrency Runtime]"
  - "Planerinstanz, Verwalten [Concurrency Runtime]"
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Gewusst wie: Verwalten einer Planerinstanz
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit Planerinstanzen können Sie bestimmte Planungsrichtlinien verschiedenen Arten von Arbeitslasten zuordnen.  Dieses Thema enthält zwei grundlegende Beispiele, die zeigen, wie eine Planerinstanz erstellt und verwaltet wird.  
  
 In den Beispielen werden Planer erstellt, die die standardmäßigen Planerrichtlinien verwenden.  Ein Beispiel für die Erstellung eines Planers, der eine benutzerdefinierte Richtlinie verwendet, finden Sie unter [Gewusst wie: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).  
  
### So verwalten Sie eine Planerinstanz in der Anwendung  
  
1.  Erstellen Sie ein [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md)\-Objekt, das die Richtlinienwerte für den zu verwendenden Planer enthält.  
  
2.  Rufen Sie die [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md)\-Methode oder die [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md)\-Methode auf, um eine Planerinstanz zu erstellen.  
  
     Wenn Sie die `Scheduler::Create`\-Methode verwenden, rufen Sie die [concurrency::Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md)\-Methode auf, wenn Sie den Planer dem aktuellen Kontext zuordnen müssen.  
  
3.  Rufen Sie die [CreateEvent](http://msdn.microsoft.com/library/windows/desktop/ms682396)\-Funktion auf, um ein Handle für ein nicht signalisiertes automatisches Zurücksetzungobjekt zu erstellen.  
  
4.  Übergeben Sie das Handle für das Ereignisobjekt, das Sie gerade erstellt haben, an die [concurrency::CurrentScheduler::RegisterShutdownEvent](../Topic/CurrentScheduler::RegisterShutdownEvent%20Method.md)\-Methode oder die [concurrency::Scheduler::RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md)\-Methode.  Hierdurch wird das Ereignis als festzulegen registriert, wenn der Planer zerstört wird.  
  
5.  Führen Sie die Aufgaben aus, die vom aktuellen Planer geplant werden sollen.  
  
6.  Rufen Sie die [concurrency::CurrentScheduler::Detach](../Topic/CurrentScheduler::Detach%20Method.md)\-Methode auf, um den aktuellen Planer zu trennen und den vorherigen Planer als aktuellen Planer wiederherzustellen.  
  
     Wenn Sie die `Scheduler::Create`\-Methode verwenden, rufen Sie die [concurrency::Scheduler::Release](../Topic/Scheduler::Release%20Method.md)\-Methode auf, um den Verweiszähler des `Scheduler`\-Objekts zu dekrementieren.  
  
7.  Übergeben Sie das Handle für das Ereignis an die [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032)\-Funktion, um zu warten, bis der Planer herunterfährt.  
  
8.  Rufen Sie die [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211)\-Funktion auf, um das Handle für das Ereignisobjekt zu schließen.  
  
## Beispiel  
 Der folgende Code veranschaulicht zwei Möglichkeiten für die Verwaltung einer Planerinstanz.  In jedem Beispiel wird zunächst mit dem Standardplaner eine Aufgabe ausgeführt, die den eindeutigen Bezeichner des aktuellen Planers ausgibt.  Jedes Beispiel verwendet dann eine Planerinstanz, um die gleiche Aufgabe noch einmal auszuführen.  In jedem Beispiel wird schließlich der Standardplaner als aktueller Planer wiederhergestellt und die Aufgabe noch einmal ausgeführt.  
  
 Im ersten Beispiel wird die [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md)\-Klasse verwendet, um eine Planerinstanz zu erstellen und sie dem aktuellen Kontext zuzuordnen.  Das zweite Beispiel führt die gleiche Aufgabe mithilfe der [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md)\-Klasse aus.  In der Regel wird die `CurrentScheduler`\-Klasse verwendet, um mit dem aktuellen Planer zu arbeiten.  Das zweite Beispiel, das die `Scheduler`\-Klasse verwendet, ist nützlich, wenn Sie steuern möchten, wann der Planer dem aktuellen Kontext zugeordnet wird, oder wenn Sie bestimmte Planer bestimmten Aufgaben zuordnen möchten.  
  
 [!CODE [concrt-scheduler-instance#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-scheduler-instance#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **Using CurrentScheduler class...**  
**Current scheduler id: 0**  
**Creating and attaching scheduler...**  
**Current scheduler id: 1**  
**Detaching scheduler...**  
**Current scheduler id: 0**  
**Using Scheduler class...**  
**Current scheduler id: 0**  
**Creating scheduler...**  
**Attaching scheduler...**  
**Current scheduler id: 2**  
**Detaching scheduler...**  
**Current scheduler id: 0**   
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `scheduler-instance.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc scheduler\-instance.cpp**  
  
## Siehe auch  
 [Planerinstanzen](../../parallel/concrt/scheduler-instances.md)   
 [Gewusst wie: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)