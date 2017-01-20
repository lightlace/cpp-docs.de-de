---
title: "Exemplarische Vorgehensweise: Anpassen von vorhandenem Code f&#252;r die Verwendung einfacher Aufgaben"
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
  - "Verwenden von einfachen Aufgaben [Concurrency Runtime]"
  - "Einfache Aufgaben, Verwenden [Concurrency Runtime]"
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
caps.latest.revision: 14
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Anpassen von vorhandenem Code f&#252;r die Verwendung einfacher Aufgaben
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie vorhandener Code, der die Windows\-API verwendet, zum Erstellen und Ausführen eines Threads für die Ausführung einer einfachen Aufgabe angepasst wird.  
  
 Eine *einfache Aufgabe* ist eine Aufgabe, die Sie direkt von einem [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md)\-Objekt oder einem [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md)\-Objekt planen.  Einfache Aufgaben sind nützlich, wenn Sie vorhandenen Code anpassen, um die Planungsfunktionalität der Concurrency Runtime zu verwenden.  
  
## Vorbereitungsmaßnahmen  
 Bevor Sie mit dieser exemplarische Vorgehensweise beginnen, lesen Sie das Thema [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
## Beispiel  
  
### **Beschreibung**  
 Das folgende Beispiel veranschaulicht die typische Verwendung der Windows\-API zum Erstellen und Ausführen eines Threads.  In diesem Beispiel wird die [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453)\-Funktion verwendet, um die `MyThreadFunction` in einem separaten Thread aufzurufen.  
  
### Code  
 [!CODE [concrt-windows-threads#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-windows-threads#1)]  
  
### Kommentare  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **Parameters \= 50, 100** Die folgenden Schritte geben an, wie das Codebeispiel angepasst wird, um die Concurrency Runtime zum Durchführen der gleichen Aufgabe zu verwenden.  
  
### So passen Sie das Beispiel an, um eine einfache Aufgabe zu verwenden  
  
1.  Fügen Sie eine `#include`\-Direktive für die Headerdatei concrt.h hinzu.  
  
     [!CODE [concrt-migration-lwt#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-migration-lwt#2)]  
  
2.  Fügen Sie für den `concurrency`\-Namespace eine `using`\-Direktive hinzu.  
  
     [!CODE [concrt-migration-lwt#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-migration-lwt#3)]  
  
3.  Ändern Sie die Deklaration von `MyThreadFunction` so, dass die `__cdecl`\-Aufrufkonvention verwendet und `void` zurückgegeben wird.  
  
     [!CODE [concrt-migration-lwt#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-migration-lwt#4)]  
  
4.  Ändern Sie die `MyData`\-Struktur so, dass ein [concurrency::event](../../parallel/concrt/reference/event-class.md)\-Objekt eingeschlossen wird, das der Hauptanwendung den Abschluss der Aufgabe signalisiert.  
  
     [!CODE [concrt-migration-lwt#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-migration-lwt#5)]  
  
5.  Ersetzen Sie den Aufruf von `CreateThread` durch einen Aufruf der [concurrency::CurrentScheduler::ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md)\-Methode.  
  
     [!CODE [concrt-migration-lwt#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-migration-lwt#6)]  
  
6.  Ersetzen Sie den Aufruf von `WaitForSingleObject` durch einen Aufruf der [concurrency::event::wait](../Topic/event::wait%20Method.md)\-Methode, um auf den Abschluss der Aufgabe zu warten.  
  
     [!CODE [concrt-migration-lwt#7](../CodeSnippet/VS_Snippets_ConcRT/concrt-migration-lwt#7)]  
  
7.  Entfernen Sie den Aufruf von `CloseHandle`.  
  
8.  Ändern Sie die Signatur der Definition von `MyThreadFunction` so, dass sie Schritt 3 entspricht.  
  
     [!CODE [concrt-migration-lwt#8](../CodeSnippet/VS_Snippets_ConcRT/concrt-migration-lwt#8)]  
  
9. Rufen Sie am Ende der `MyThreadFunction`\-Funktion die [concurrency::event::set](../Topic/event::set%20Method.md)\-Methode auf, um der Hauptanwendung den Abschluss der Aufgabe zu signalisieren.  
  
     [!CODE [concrt-migration-lwt#9](../CodeSnippet/VS_Snippets_ConcRT/concrt-migration-lwt#9)]  
  
10. Entfernen Sie die `return`\-Anweisung von `MyThreadFunction`.  
  
## Beispiel  
  
### **Beschreibung**  
 Im folgenden vollständigen Beispiel wird eine einfache Aufgabe verwendet, um die `MyThreadFunction`\-Funktion aufzurufen.  
  
### Code  
 [!CODE [concrt-migration-lwt#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-migration-lwt#1)]  
  
### Kommentare  
  
## Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Scheduler\-Klasse](../../parallel/concrt/reference/scheduler-class.md)