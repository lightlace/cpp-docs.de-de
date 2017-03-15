---
title: "Concurrency Runtime | Microsoft Docs"
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
  - "Concurrency Runtime, erste Schritte"
  - "ConcRT (siehe Concurrency Runtime)"
  - "Concurrency Runtime"
ms.assetid: 874bc58f-8dce-483e-a3a1-4dcc9e52ed2c
caps.latest.revision: 40
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 39
---
# Concurrency Runtime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Concurrency Runtime für C\+\+ hilft Ihnen beim Schreiben robuster, skalierbarer und reaktionsschneller paralleler Anwendungen. Es stellt eine höhere Abstraktionsebene bereit, sodass Sie die Infrastrukturdetails im Zusammenhang mit der Parallelität nicht verwalten müssen. Sie können mit ihm außerdem Planungsrichtlinien angeben, die den Servicequalitätsforderungen Ihrer Anwendungen entsprechen. Verwenden Sie diese Ressourcen für die ersten Schritte beim Arbeiten mit der Concurrency Runtime.  
  
 Die Referenzdokumentation finden Sie unter [Referenz](../../parallel/concrt/reference/reference-concurrency-runtime.md).  
  
> [!TIP]
>  Die Concurrency Runtime basiert stark auf C\+\+11\-Funktionen und übernimmt den moderneren C\+\+\-Stil. Weitere Informationen finden Sie unter [Willkommen zurück bei C\+\+](../../cpp/welcome-back-to-cpp-modern-cpp.md).  
  
## Auswählen von Concurrency Runtime\-Funktionen  
  
|||  
|-|-|  
|[Übersicht](../../parallel/concrt/overview-of-the-concurrency-runtime.md)|Erläutert die Bedeutung der Concurrency Runtime und beschreibt ihre wichtigsten Funktionen.|  
|[Vergleich mit anderen Parallelitätsmodellen](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|Beschreibt die Concurrency Runtime im Vergleich mit anderen Parallelitätsmodellen, z. B. dem Windows\-Threadpool und OpenMP, damit Sie das Parallelitätsmodell verwenden können, das die Anforderungen Ihrer Anwendungen am besten erfüllt.|  
|[Migrieren von OpenMP zur Concurrency Runtime](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)|Vergleicht OpenMP mit der Concurrency Runtime und enthält Beispiele, in denen das Migrieren von vorhandenem OpenMP\-Code für die Verwendung der Concurrency Runtime gezeigt wird.|  
|[Parallel Patterns Library \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Stellt die PPL vor, die parallele Schleifen, Aufgaben und parallele Container bereitstellt.|  
|[Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)|Erläutert die Verwendung von asynchronen Agents und asynchroner Nachrichtenübergabe, um auf einfache Weise Datenfluss\- und Pipelineaufgaben in die Anwendungen zu integrieren.|  
|[Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)|Stellt den Aufgabenplaner vor, mit dem Sie die Leistung Ihrer Desktop\-Apps, die die Concurrency Runtime verwenden, optimieren können.|  
  
## Aufgabenparallelität in der PPL  
  
|||  
|-|-|  
|[Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br /><br /> [Gewusst wie: Verwenden von parallel\_invoke zum Schreiben einer Runtime für paralleles Sortieren](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)<br /><br /> [Gewusst wie: Ausführen von parallelen Vorgängen mithilfe von parallel\_invoke](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)<br /><br /> [Gewusst wie: Erstellen einer Aufgabe, die nach einer Verzögerung abgeschlossen wird](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|Beschreibt Aufgaben und Aufgabengruppen, mit denen Sie asynchronen Code schreiben und parallele Arbeit in kleinere Teile zerlegen können.|  
|[Exemplarische Vorgehensweise: Implementieren von Futures](../../parallel/concrt/walkthrough-implementing-futures.md)|Veranschaulicht, wie Concurrency Runtime\-Funktionen kombiniert werden, um den Funktionsumfang zu erweitern.|  
|[Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)|Veranschaulicht, wie die Arbeit, die vom UI\-Thread in einer MFC\-Anwendung ausgeführt wird, in einen Arbeitsthread verschoben wird.|  
|[Empfohlene Vorgehensweisen in der Parallel Patterns Library](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br /><br /> [Allgemein empfohlene Vorgehensweisen in der Concurrency Runtime](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|Bietet Tipps und empfohlene Vorgehensweisen für das Arbeiten mit der PPL.|  
  
## Datenparallelität in der PPL  
  
|||  
|-|-|  
|[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)<br /><br /> [Gewusst wie: Schreiben einer parallel\_for\-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)<br /><br /> [Gewusst wie: Schreiben einer parallel\_for\_each\-Schleife](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)<br /><br /> [Gewusst wie: Paralleles Ausführen von Zuordnungs\- und Reduzierungsoperationen](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|Beschreibt `parallel_for`, `parallel_for_each`, `parallel_invoke` und andere parallele Algorithmen. Verwenden Sie parallele Algorithmen, um Probleme mit *Datenparallelität* im Zusammenhang mit Auflistungen von Daten zu lösen.|  
|[Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)<br /><br /> [Gewusst wie: Erhöhen der Effizienz mithilfe von parallelen Containern](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br /><br /> [Gewusst wie: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br /><br /> [Gewusst wie: Kombinieren von Gruppen mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)|Beschreibt die `combinable`\-Klasse sowie `concurrent_vector`, `concurrent_queue`, `concurrent_unordered_map` und andere parallele Container. Verwenden Sie parallele Container und Objekte, wenn Sie Container benötigen, die threadsicheren Zugriff auf die zugehörigen Elemente bieten.|  
|[Empfohlene Vorgehensweisen in der Parallel Patterns Library](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br /><br /> [Allgemein empfohlene Vorgehensweisen in der Concurrency Runtime](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|Bietet Tipps und empfohlene Vorgehensweisen für das Arbeiten mit der PPL.|  
  
## Abbrechen von Aufgaben und parallelen Algorithmen  
  
|||  
|-|-|  
|[Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md)|Beschreibt die Rolle des Abbruchs in der PPL, einschließlich des Initiierens und Beantwortens von Abbruchanforderungen.|  
|[Gewusst wie: Verwenden eines Abbruchs zum Verlassen einer Parallel\-Schleife](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)<br /><br /> [Gewusst wie: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel\-Schleife](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|Veranschaulicht zwei Möglichkeiten, parallele Arbeit mit Daten abzubrechen.|  
  
## Windows Store\-Apps  
  
|||  
|-|-|  
|[Erstellen von asynchronen Vorgängen in C\+\+ für Windows Store\-Apps](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)|Beschreibt einige der wichtigsten zu beachtenden Punkte für das Verwenden der Concurrency Runtime für asynchrone Vorgänge in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App.|  
|[Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML\-HTTP\-Anforderungen](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)|Zeigt, wie PPL\-Aufgaben mit der `IXMLHTTPRequest2`\- und der `IXMLHTTPRequest2Callback`\-Schnittstelle kombiniert werden, um GET\- und POST\-HTTP\-Anforderungen an einen Webdienst in einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App zu senden.|  
|[Beispiele für Windows Store\-App](http://code.msdn.microsoft.com/windowsapps)|Enthält herunterladbare Codebeispiele und Demo\-Apps für [!INCLUDE[win8](../../build/includes/win8_md.md)]. Die C\+\+\-Beispiele verwenden Concurrency Runtime\-Funktionen wie PPL\-Aufgaben, um Daten im Hintergrund zu verarbeiten und so die Reaktionsfähigkeit aufrechtzuerhalten.|  
  
## Datenflussprogrammierung in der Asynchronous Agents Library  
  
|||  
|-|-|  
|[Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)<br /><br /> [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br /><br /> [Funktionen zum Übergeben von Meldungen](../../parallel/concrt/message-passing-functions.md)<br /><br /> [Gewusst wie: Implementieren verschiedener Producer\-Consumer\-Muster](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)<br /><br /> [Gewusst wie: Bereitstellen von Arbeitsfunktionen für die call\- und transformer\-Klassen](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)<br /><br /> [Gewusst wie: Verwenden von transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br /><br /> [Gewusst wie: Auswählen von abgeschlossenen Aufgaben](../../parallel/concrt/how-to-select-among-completed-tasks.md)<br /><br /> [Gewusst wie: Senden einer Nachricht in regelmäßigen Intervallen](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)<br /><br /> [Gewusst wie: Verwenden eines Nachrichtenblockfilters](../../parallel/concrt/how-to-use-a-message-block-filter.md)|Beschreibt asynchrone Agents, Nachrichtenblöcke und Nachrichtenübergabefunktionen, bei denen es sich um die Bausteine zum Durchführen von Datenflussvorgängen in der Concurrency Runtime handelt.|  
|[Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br /><br /> [Exemplarische Vorgehensweise: Erstellen eines Datenfluss\-Agent](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)|Veranschaulicht die Erstellung von einfachen auf Agents basierenden Anwendungen.|  
|[Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)|Veranschaulicht das Erstellen eines Netzwerks asynchroner Nachrichtenblöcke für die Bildverarbeitung.|  
|[Exemplarische Vorgehensweise: Verhindern von Deadlocks mit join](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)|Veranschaulicht anhand des Philosophenproblems, wie sich mit der Concurrency Runtime Deadlocks in der Anwendung verhindern lassen.|  
|[Exemplarische Vorgehensweise: Erstellen eines benutzerdefinierten Nachrichtenblocks](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)|Veranschaulicht, wie ein benutzerdefinierter Nachrichtenblocktyp erstellt wird, um eingehende Nachrichten nach Priorität zu sortieren.|  
|[Empfohlene Vorgehensweisen in der Asynchronous Agents Library](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)<br /><br /> [Allgemein empfohlene Vorgehensweisen in der Concurrency Runtime](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)|Bietet Tipps und empfohlene Vorgehensweisen für das Arbeiten mit Agents.|  
  
## Ausnahmebehandlung und Debuggen  
  
|||  
|-|-|  
|[Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Beschreibt das Arbeiten mit Ausnahmen in der Concurrency Runtime.|  
|[Diagnosetools für die parallele Ausführung](../../parallel/concrt/parallel-diagnostic-tools-concurrency-runtime.md)|Erläutert, wie Sie die Feinabstimmung von Anwendungen ausführen und die Concurrency Runtime so effizient wie möglich nutzen.|  
  
## Optimieren der Leistung  
  
|||  
|-|-|  
|[Diagnosetools für die parallele Ausführung](../../parallel/concrt/parallel-diagnostic-tools-concurrency-runtime.md)|Erläutert, wie Sie die Feinabstimmung von Anwendungen ausführen und die Concurrency Runtime so effizient wie möglich nutzen.|  
|[Planerinstanzen](../../parallel/concrt/scheduler-instances.md)<br /><br /> [Gewusst wie: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br /><br /> [Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)<br /><br /> [Gewusst wie: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br /><br /> [Gewusst wie: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)|Veranschaulicht das Arbeiten mit Planerinstanzen und Planerrichtlinien. Bei Desktop\-Apps können Sie mit Planerrichtlinien bestimmten Arten von Arbeitslasten spezielle Regeln zuordnen. Beispielsweise können Sie eine Planerinstanz erstellen, um einige Aufgaben mit höherer Threadpriorität auszuführen und andere Aufgaben mit dem Standardplaner mit normaler Threadpriorität auszuführen.|  
|[Planungsgruppen](../../parallel/concrt/schedule-groups.md)<br /><br /> [Gewusst wie: Beeinflussen der Ausführungsreihenfolge mithilfe von Zeitplangruppen](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)|Veranschaulicht die Verwendung von Planungsgruppen, um verwandte Aufgaben zusammen zu gruppieren. Sie können beispielsweise einen hohen Grad an Lokalität zwischen verwandten Aufgaben anfordern, wenn es Vorteile bietet, dass diese Aufgaben auf demselben Prozessorknoten ausgeführt werden.|  
|[Einfache Aufgaben](../../parallel/concrt/lightweight-tasks.md)|Erläutert, wie einfache Aufgaben hilfreich für das Erstellen von Arbeit sind, die keinen Lastenausgleich oder Abbruch erfordert, sowie für das Anpassen von vorhandenem Code für die Verwendung mit der Concurrency Runtime.|  
|[Kontexte](../../parallel/concrt/contexts.md)<br /><br /> [Gewusst wie: Implementieren einer kooperativen Semaphore mithilfe der Context\-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br /><br /> [Gewusst wie: Verwenden der Überzeichnung zum Kompensieren der Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)|Beschreibt, wie das Verhalten der Threads gesteuert wird, die von der Concurrency Runtime verwaltet werden.|  
|[Speicherverwaltungsfunktionen](../../parallel/concrt/memory-management-functions.md)<br /><br /> [Gewusst wie: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)|Beschreibt die Speicherverwaltungsfunktionen der Concurrency Runtime, die das parallele Reservieren und Freigeben von Arbeitsspeicher unterstützen.|  
  
## Zusätzliche Ressourcen  
  
|||  
|-|-|  
|[Muster und Tipps für die asynchrone Programmierung in Hilo \(Windows Store\-Apps mit C\+\+ und XAML\)](http://msdn.microsoft.com/library/windows/apps/jj160321.aspx)|Erfahren Sie, wie wir mit der Concurrency Runtime asynchrone Vorgänge in Hilo, einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App mit C\+\+ und XAML, implementiert haben.|  
|[Code samples for the Concurrency Runtime and Parallel Pattern Library in Visual Studio 2010 \(Codebeispiele für die Concurency Runtime und Parallel Pattern Library in Visual Studio 2010\)](http://go.microsoft.com/fwlink/?LinkID=183875)|Bietet Beispielanwendungen und Hilfsprogramme zur Veranschaulichung der Concurrency Runtime.|  
|[Parallel Programming in Native Code blog \(Blog zum Thema paralleles Programmieren in nativem Code\)](http://go.microsoft.com/fwlink/?LinkID=183873)|Bietet zusätzliche ausführliche Blogartikel zur parallelen Programmierung in der Concurrency Runtime.|  
|[Parallel Computing in C\+\+ and Native Code forum \(Forum zum Thema paralleles Computing in C\+\+ und nativem Code\)](http://go.microsoft.com/fwlink/?LinkID=183874)|Ermöglicht Ihnen die Teilnahme an Communitydiskussionen über die Concurrency Runtime.|  
|[Parallel Programming](../Topic/Parallel%20Programming%20in%20the%20.NET%20Framework.md)|Erläutert das Modell der parallelen Programmierung, das in [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] verfügbar ist.|  
  
## Siehe auch  
 [Referenz](../../parallel/concrt/reference/reference-concurrency-runtime.md)