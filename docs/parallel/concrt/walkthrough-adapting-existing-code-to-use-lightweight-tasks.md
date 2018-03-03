---
title: 'Exemplarische Vorgehensweise: Anpassen von vorhandenem Code Verwendung einfache Aufgaben | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8a50ad04421d7b4bcdc4a2c98de8f5a57b255c75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>Exemplarische Vorgehensweise: Anpassen von vorhandenem Code für die Verwendung einfacher Aufgaben
In diesem Thema wird erläutert, wie vorhandener Code, der die Windows-API verwendet, zum Erstellen und Ausführen eines Threads für die Ausführung einer einfachen Aufgabe angepasst wird.  
  
 Ein *einfache Aufgabe* ist eine Aufgabe, die Sie direkt aus Planen einer [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) oder [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Objekt. Einfache Aufgaben sind nützlich, wenn Sie vorhandenen Code anpassen, um die Planungsfunktionalität der Concurrency Runtime zu verwenden.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Bevor Sie in dieser exemplarischen Vorgehensweise beginnen, lesen Sie das Thema [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel veranschaulicht die typische Verwendung der Windows-API zum Erstellen und Ausführen eines Threads. Dieses Beispiel verwendet die [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) aufzurufenden Funktion der `MyThreadFunction` in einem separaten Thread.  
  
### <a name="code"></a>Code  
 [!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]  
  
### <a name="comments"></a>Kommentare  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
Parameters = 50, 100  
```  
  
 Die folgenden Schritte geben an, wie das Codebeispiel angepasst wird, um die Concurrency Runtime zum Durchführen der gleichen Aufgabe zu verwenden.  
  
### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>So passen Sie das Beispiel an, um eine einfache Aufgabe zu verwenden  
  
1.  Fügen Sie eine `#include`-Direktive für die Headerdatei concrt.h hinzu.  
  
 [!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]  
  
2.  Fügen Sie eine `using`-Direktive für den `concurrency`-Namespace hinzu.  
  
 [!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]  
  
3.  Ändern Sie die Deklaration von `MyThreadFunction` so, dass die `__cdecl`-Aufrufkonvention verwendet und `void` zurückgegeben wird.  
  
 [!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]  
  
4.  Ändern der `MyData` -Struktur so, dass eine [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) -Objekt, das der hauptanwendung signalisiert, dass die Aufgabe abgeschlossen wurde.  
  
 [!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]  
  
5.  Ersetzen Sie den Aufruf von `CreateThread` durch einen Aufruf der [Concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask) Methode.  

  
 [!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]  
  

6.  Ersetzen Sie den Aufruf von `WaitForSingleObject` durch einen Aufruf der [Concurrency](reference/event-class.md#wait) Methode für den Abschluss der Aufgabe zu warten.  

 [!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]  
  
7.  Entfernen Sie den Aufruf von `CloseHandle`.  
  
8.  Ändern Sie die Signatur der Definition von `MyThreadFunction` so, dass sie Schritt 3 entspricht.  
  
 [!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]  
  
9. Am Ende der `MyThreadFunction` funktionieren, rufen Sie die [Concurrency::event::set](reference/event-class.md#set) Methode, um die Hauptassembly der Anwendung zu signalisieren, dass der Vorgang abgeschlossen ist.  
  
 [!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]  
  
10. Entfernen Sie die `return`-Anweisung von `MyThreadFunction`.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgenden vollständigen Beispiel wird eine einfache Aufgabe verwendet, um die `MyThreadFunction`-Funktion aufzurufen.  
  
### <a name="code"></a>Code  
 [!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]  
  
### <a name="comments"></a>Kommentare  
  
## <a name="see-also"></a>Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Scheduler-Klasse](../../parallel/concrt/reference/scheduler-class.md)
