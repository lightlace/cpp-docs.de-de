---
title: "Bewährte Methoden in der Asynchronous Agents Library | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- best practices, Asynchronous Agents Library
- Asynchronous Agents Library, best practices
- Asynchronous Agents Library, practices to avoid
- practices to avoid, Asynchronous Agents Library
ms.assetid: 85f52354-41eb-4b0d-98c5-f7344ee8a8cf
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8d4b52839675334ab343adf48790bdce390dd5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="best-practices-in-the-asynchronous-agents-library"></a>Empfohlene Vorgehensweisen in der Asynchronous Agents Library
In diesem Dokument wird die effektive Verwendung der Asynchronous Agents Library beschrieben. Die Agents Library begünstigt ein akteurbasiertes Programmiermodell und die prozessinterne Nachrichtenübergabe für simple Datenfluss- und Pipelinesaufgaben.  
  
 Weitere Informationen zur Agents Library finden Sie unter [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md).  
  
##  <a name="top"></a> Abschnitte  
 Dieses Dokument enthält folgende Abschnitte:  
  
- [Isolieren von Status mit der Agents](#isolation)  
  
- [Verwenden Sie einen Einschränkungsmechanismus zum Begrenzen der Anzahl von Nachrichten in einer Datenpipeline](#throttling)  
  
- [Führen Sie keine detaillierte Arbeit in einer Datenpipeline](#fine-grained)  
  
- [Übergabe von großer Nutzlasten für Nachrichten anhand des Werts](#large-payloads)  
  
- [Verwenden von Shared_ptr in einem Data Datennetzwekr bei unklarem Besitzer](#ownership)  
  
##  <a name="isolation"></a>Isolieren von Status mit der Agents  
 Die Agents Library stellt Alternativen zum Freigabezustand bereit, indem sie das Verbinden isolierter Komponenten durch einen asynchronen Nachrichtenübergabemechanismum ermöglicht. Asynchrone Agents sind am effektivsten, wenn der interne Zustand von anderen Komponenten isoliert werden kann. Aufgrund der Isolierung des Status wirken mehrere Komponenten i. d. R. nicht auf freigegebene Daten. Die Isolierung des Status ermöglicht eine Skalierung der Anwendung, da Konflikte im freigegebenen Speicher reduziert werden. Ferner wird dadurch die Wahrscheinlichkeit von Deadlocks und Racebedingungen verringert, da der Zugriff auf die freigegebenen Daten nicht zwischen den Komponenten synchronisiert werden muss.  
  
 Status in einem Agent werden i. d. R. isoliert, indem Datenmember im Abschnitt `private` oder im Abschnitt `protected` der Agent-Klasse platziert und Statusänderungen mit Nachrichtenpuffern kommuniziert werden. Das folgende Beispiel zeigt die `basic_agent` -Klasse, abgeleitet von [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md). Die `basic_agent`-Klasse verwendet zwei Meldungspuffer zur Kommunikation mit externen Komponenten. Ein Nachrichtenpuffer enthält eingehende Meldungen, der andere Nachrichtenpuffer enthält ausgehende Nachrichten.  
  
 [!code-cpp[concrt-simple-agent#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_1.cpp)]  
  
 Vollständige Beispiele zum Definieren und Verwenden von Agents finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md) und [Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agents](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="throttling"></a>Verwenden Sie einen Einschränkungsmechanismus zum Begrenzen der Anzahl von Nachrichten in einer Datenpipeline  
 Viele Nachrichtenpuffertypen wie z. B. [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), kann eine unbegrenzte Anzahl von Nachrichten enthalten. Wenn Nachrichten vom Nachrichtenproducer schneller an eine Datenpipeline gesendet werden, als diese vom Consumer verarbeitet werden können, kann der Speicherstatus der Anwendung auf Speichermangel hinweisen. Mit einem Einschränkungsmechanismus wie einem Semaphor können Sie die Anzahl der Nachrichten begrenzen, die zu einem gegebenen Zeitpunkt gleichzeitg in einer Datenpipepline aktiv sind.  
  
 Im Folgenden einfachen Beispiel wird veranschaulicht, wie die Anzahl der Nachrichten in einer Datenpipeline mit einem Semaphor eingeschränkt wird. Die Datenpipeline verwendet die [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) Funktion, um einen Vorgang zu simulieren, die mindestens 100 Millisekunden dauert. Da die Nachrichten vom Absender schneller erzeugt werden, als diese vom Consumer verarbeitet werden können, wird in diesem Beispiel die `semaphore`-Klasse definiert, sodass die Anzahl der aktiven Nachrichten von der Anwendung eingeschränkt werden kann.  
  
 [!code-cpp[concrt-message-throttling#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_2.cpp)]  
  
 Die Pipeline wird vom `semaphore`-Objekt eingeschränkt, sodass maximal zwei Nachrichten gleichzeitig verarbeitet werden können.  
  
 Der Producer in diesem Beispiel sendet verhältnismäßig wenig Nachrichten an den Consumer. Daher ist dieses Beispiel ungeeignet, um eine Situation mit einem Mangel an Arbeitsspeicher zu veranschaulichen. Dieser Mechanismus ist jedoch hilfreich, wenn eine Datenpipeline eine relativ hohe Anzahl von Meldungen enthält.  
  
 Weitere Informationen zur Vorgehensweise beim Erstellen der Semaphore-Klasse, die verwendet wird, in diesem Beispiel finden Sie unter [Vorgehensweise: Verwenden der Context-Klasse zum Implementieren einer kooperativen Semaphore](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="fine-grained"></a>Führen Sie keine detaillierte Arbeit in einer Datenpipeline  
 Die Agents Library ist besonders hilfreich, wenn die Arbeit, die von einer Datenpipeline ausgeführt wird, eher simpel ist. Beispielsweise könnte eine Anwendungskomponente Daten aus einer Datei oder einer Netzwerkverbindung lesen und ab und zu Daten an eine andere Komponente senden. Die von der Agents Library verwendeten Protokolls zur Weitergabe von Nachrichten führt dazu, dass den Meldungsübergabe Mechanismus mehr Aufwand beim Nachrichtenübergabemechanismus gegenüber den parallelen Konstrukten der Aufgabe, die von bereitgestellt werden die [Parallel Patterns Library](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). Deshalb müssen Sie sicherstellen, dass die Arbeit, die von einer Datenpipeline ausgeführt wird, lang genug dauert, um diesen Mehraufwand auszugleichen.  
  
 Obwohl eine Datenpipeline am effektivsten ist, wenn die Aufgaben simpel sind, können in jeder Phase der Datenpipeline PPL-Konstrukte wie Aufgabengruppen und parallele Algorithmen verwendet werden, um differenziertere Aufgaben auszuführen. Ein Beispiel für ein undifferenzierte-Netzwerke, die eine differenzierte Parallelität in den einzelnen Phasen der Verarbeitung verwendet, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="large-payloads"></a>Übergabe von großer Nutzlasten für Nachrichten anhand des Werts  

 In einigen Fällen wird von der Laufzeit eine Kopie einer Nachricht erstellt und von einem Nachrichtenpuffer an einen anderen Nachrichtenpuffer übergeben. Z. B. die [Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) Klasse bietet eine Kopie jeder Nachricht, die sie für jedes der zugehörigen Ziele empfängt. Die Common Language Runtime auch eine Kopie der Nachrichtendaten erstellt, wenn Sie Nachrichtenübergabefunktionen, z. B. verwenden [Concurrency:: Send](reference/concurrency-namespace-functions.md#send) und [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) zu schreiben und Lesen von Nachrichten aus einer Nachricht Puffer. Auch wenn dieser Mechanismus dazu beiträgt, das Risiko zu verringern, dass freigegebene Daten gleichzeitig geschrieben werden, kann die Arbeitsspeicherleistung darunter leiden, dass die Nachrichten relativ hoch ist.  
  
 Sie können die Arbeitsspeicherleistung beim Übergeben von Nachrichten mit einer großen Nutzlast verbessern, indem Sie Zeiger und Verweise verwenden. Im folgenden Beispiel wird die Übergabe umfangreicher Nachrichten anhand des Werts mit der Übergabe von Zeigern auf den gleichen Nachrichtentyp verglichen. Im Beispiel werden zwei Agent-Typen definiert, `producer` und `consumer`, die auf `message_data`-Objekte angewendet werden. In dem Beispiel wird die Zeit, die der Producer benötigt, um mehrere `message_data`-Objekte an den Consumer zu senden, mit der Zeit verglichen, die der Producer-Agent benötigt, um mehrere Zeiger auf `message_data`-Objekte an den Consumer zu senden.  
  
 [!code-cpp[concrt-message-payloads#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_3.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
```Output  
Using message_data...  
took 437ms.  
Using message_data*...  
took 47ms.  
```  
  
 Die Version mit Zeiger weist eine bessere Leistungauf, da von der Laufzeit während der Übergabe vom Producer an den Consumer nicht eine vollständige Kopie jedes `message_data`-Objekts erstellt werden muss.  
  
 [[Nach oben](#top)]  
  
##  <a name="ownership"></a>Verwenden von Shared_ptr in einem Data Datennetzwekr bei unklarem Besitzer  
 Beim Senden von Nachrichten anhand des Zeigers über eine Pipeline oder ein Netzwerk zur Übergabe von Nachrichten wird der Arbeitsspeicher für jede Nachricht i. d. R. am Anfang des Netzwerks zugewiesen und am Ende des Netzwerks freigegeben. Obwohl dieser Mechanismus normalerweise gut funktioniert, kann er jedoch in einigen Fällen kaum oder nicht verwendet werden. Betrachten Sie beispielsweise den Fall eines Datennetzwerkes mit mehreren Endknoten. In diesem Fall gibt es keine klare Position, um den Arbeitsspeicher für die Nachrichten freizugeben.  
  
 Um dieses Problem zu beheben, können Sie einen Mechanismus, z. B. [Std:: shared_ptr](../../standard-library/shared-ptr-class.md), mit der ein Zeiger auf das im Besitz mehrerer Komponenten sein. Wenn das endgültige `shared_ptr`-Objekt zerstört wird, das eine Ressource besitzt, wird auch die Ressource freigegeben.  
  
 Im folgenden Beispiel wird veranschaulicht, wie mit `shared_ptr` Zeigerwerte für mehrere Nachrichtenpuffer gemeinsam verwendet werden können. Im Beispiel verbindet eine [Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) -Objekt mit drei [Call](../../parallel/concrt/reference/call-class.md) Objekte. Die `overwrite_buffer`-Klasse stellt Nachrichten für die einzelnen Ziele bereit. Da das Datennetzwerk am Ende mehrere Besitzer der Daten aufweist, werden die einzelnen `shared_ptr`-Objekte mit `call` in die Lage versetzt, den Besitz der Nachrichten zu teilen.  
  
 [!code-cpp[concrt-message-sharing#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_4.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
```Output  
Creating resource 42...  
receiver1: received resource 42  
Creating resource 64...  
receiver2: received resource 42  
receiver1: received resource 64  
Destroying resource 42...  
receiver2: received resource 64  
Destroying resource 64...  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency Runtime bewährte Methoden](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)   
 [Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agents](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)   
 [Exemplarische Vorgehensweise: Erstellen einer Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [Empfohlene Vorgehensweisen in der Parallel Patterns Library](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [Allgemein bewährte Methoden in der Concurrency Runtime](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)

