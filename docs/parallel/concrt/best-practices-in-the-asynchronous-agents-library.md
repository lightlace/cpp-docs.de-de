---
title: Empfohlene Vorgehensweisen in der Asynchronous Agents Library
ms.date: 11/04/2016
helpviewer_keywords:
- best practices, Asynchronous Agents Library
- Asynchronous Agents Library, best practices
- Asynchronous Agents Library, practices to avoid
- practices to avoid, Asynchronous Agents Library
ms.assetid: 85f52354-41eb-4b0d-98c5-f7344ee8a8cf
ms.openlocfilehash: c61393957a63895a9ecbdaaae8d83a5fbd710de3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266418"
---
# <a name="best-practices-in-the-asynchronous-agents-library"></a>Empfohlene Vorgehensweisen in der Asynchronous Agents Library

In diesem Dokument wird die effektive Verwendung der Asynchronous Agents Library beschrieben. Die Agents Library begünstigt ein akteurbasiertes Programmiermodell und die prozessinterne Nachrichtenübergabe für simple Datenfluss- und Pipelinesaufgaben.

Weitere Informationen zur Agents Library finden Sie unter [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md).

##  <a name="top"></a> Abschnitte

Dieses Dokument enthält folgende Abschnitte:

- [Verwenden Sie Agents zum Isolieren von Status](#isolation)

- [Verwenden Sie einen Mechanismus zur Moduleinschränkung, um die Anzahl der Nachrichten in einer Datenpipeline beschränken](#throttling)

- [Führen Sie keine detaillierte Arbeit in einer Datenpipeline](#fine-grained)

- [Übergeben Sie großer Nutzlasten für Nachrichten nicht nach Wert](#large-payloads)

- [Verwenden von Shared_ptr in einen Daten-Netzwerk beim Besitz ist nicht definiert](#ownership)

##  <a name="isolation"></a> Verwenden Sie Agents zum Isolieren von Status

Die Agents Library stellt Alternativen zum Freigabezustand bereit, indem sie das Verbinden isolierter Komponenten durch einen asynchronen Nachrichtenübergabemechanismum ermöglicht. Asynchrone Agents sind am effektivsten, wenn der interne Zustand von anderen Komponenten isoliert werden kann. Aufgrund der Isolierung des Status wirken mehrere Komponenten i. d. R. nicht auf freigegebene Daten. Die Isolierung des Status ermöglicht eine Skalierung der Anwendung, da Konflikte im freigegebenen Speicher reduziert werden. Ferner wird dadurch die Wahrscheinlichkeit von Deadlocks und Racebedingungen verringert, da der Zugriff auf die freigegebenen Daten nicht zwischen den Komponenten synchronisiert werden muss.

Status in einem Agent werden i. d. R. isoliert, indem Datenmember im Abschnitt `private` oder im Abschnitt `protected` der Agent-Klasse platziert und Statusänderungen mit Nachrichtenpuffern kommuniziert werden. Das folgende Beispiel zeigt die `basic_agent` -Klasse, die abgeleitet [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md). Die `basic_agent`-Klasse verwendet zwei Meldungspuffer zur Kommunikation mit externen Komponenten. Ein Nachrichtenpuffer enthält eingehende Meldungen, der andere Nachrichtenpuffer enthält ausgehende Nachrichten.

[!code-cpp[concrt-simple-agent#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_1.cpp)]

Vollständige Beispiele zum Definieren und verwenden die Agents, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md) und [Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agents](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md).

[[Nach oben](#top)]

##  <a name="throttling"></a> Verwenden Sie einen Mechanismus zur Moduleinschränkung, um die Anzahl der Nachrichten in einer Datenpipeline beschränken

Viele Nachrichtenpuffertypen wie z. B. [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), kann eine unbegrenzte Anzahl von Nachrichten enthalten. Wenn Nachrichten vom Nachrichtenproducer schneller an eine Datenpipeline gesendet werden, als diese vom Consumer verarbeitet werden können, kann der Speicherstatus der Anwendung auf Speichermangel hinweisen. Mit einem Einschränkungsmechanismus wie einem Semaphor können Sie die Anzahl der Nachrichten begrenzen, die zu einem gegebenen Zeitpunkt gleichzeitg in einer Datenpipepline aktiv sind.

Im Folgenden einfachen Beispiel wird veranschaulicht, wie die Anzahl der Nachrichten in einer Datenpipeline mit einem Semaphor eingeschränkt wird. Die Datenpipeline verwendet die [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) Funktion, um einen Vorgang zu simulieren, die mindestens 100 Millisekunden dauert. Da die Nachrichten vom Absender schneller erzeugt werden, als diese vom Consumer verarbeitet werden können, wird in diesem Beispiel die `semaphore`-Klasse definiert, sodass die Anzahl der aktiven Nachrichten von der Anwendung eingeschränkt werden kann.

[!code-cpp[concrt-message-throttling#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_2.cpp)]

Die Pipeline wird vom `semaphore`-Objekt eingeschränkt, sodass maximal zwei Nachrichten gleichzeitig verarbeitet werden können.

Der Producer in diesem Beispiel sendet verhältnismäßig wenig Nachrichten an den Consumer. Daher ist dieses Beispiel ungeeignet, um eine Situation mit einem Mangel an Arbeitsspeicher zu veranschaulichen. Dieser Mechanismus ist jedoch hilfreich, wenn eine Datenpipeline eine relativ hohe Anzahl von Meldungen enthält.

Weitere Informationen zum Erstellen der Semaphore-Klasse, die verwendet wird, in diesem Beispiel finden Sie unter [Vorgehensweise: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).

[[Nach oben](#top)]

##  <a name="fine-grained"></a> Führen Sie keine detaillierte Arbeit in einer Datenpipeline

Die Agents Library ist besonders hilfreich, wenn die Arbeit, die von einer Datenpipeline ausgeführt wird, eher simpel ist. Beispielsweise könnte eine Anwendungskomponente Daten aus einer Datei oder einer Netzwerkverbindung lesen und ab und zu Daten an eine andere Komponente senden. Das Protokoll, das die Agents Library verwendet wird, um die Weitergabe von Nachrichten führt dazu, dass den Message-Passing-Mechanismus, um einen höheren Aufwand als parallelen Konstrukten der Aufgabe zu erhalten, die von bereitgestellt werden die [Parallel Patterns Library](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). Deshalb müssen Sie sicherstellen, dass die Arbeit, die von einer Datenpipeline ausgeführt wird, lang genug dauert, um diesen Mehraufwand auszugleichen.

Obwohl eine Datenpipeline am effektivsten ist, wenn die Aufgaben simpel sind, können in jeder Phase der Datenpipeline PPL-Konstrukte wie Aufgabengruppen und parallele Algorithmen verwendet werden, um differenziertere Aufgaben auszuführen. Ein Beispiel für ein simple Datennetzwerk, die eine differenzierte Parallelität in jeder Verarbeitungsphase verwendet, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eine Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

[[Nach oben](#top)]

##  <a name="large-payloads"></a> Übergeben Sie großer Nutzlasten für Nachrichten nicht nach Wert

In einigen Fällen wird von der Laufzeit eine Kopie einer Nachricht erstellt und von einem Nachrichtenpuffer an einen anderen Nachrichtenpuffer übergeben. Z. B. die [Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) -Klasse bietet eine Kopie jeder Nachricht, die sie für jedes der zugehörigen Ziele empfängt. Die Laufzeit erstellt auch eine Kopie der Nachrichtendaten, wenn Sie Nachrichtenübergabefunktionen, z. B. verwenden [Concurrency:: Send](reference/concurrency-namespace-functions.md#send) und [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) zu schreiben und Lesen von Nachrichten aus einer Nachricht Puffer. Auch wenn dieser Mechanismus dazu beiträgt, das Risiko zu verringern, dass freigegebene Daten gleichzeitig geschrieben werden, kann die Arbeitsspeicherleistung darunter leiden, dass die Nachrichten relativ hoch ist.

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

##  <a name="ownership"></a> Verwenden von Shared_ptr in einen Daten-Netzwerk beim Besitz ist nicht definiert

Beim Senden von Nachrichten anhand des Zeigers über eine Pipeline oder ein Netzwerk zur Übergabe von Nachrichten wird der Arbeitsspeicher für jede Nachricht i. d. R. am Anfang des Netzwerks zugewiesen und am Ende des Netzwerks freigegeben. Obwohl dieser Mechanismus normalerweise gut funktioniert, kann er jedoch in einigen Fällen kaum oder nicht verwendet werden. Betrachten Sie beispielsweise den Fall eines Datennetzwerkes mit mehreren Endknoten. In diesem Fall gibt es keine klare Position, um den Arbeitsspeicher für die Nachrichten freizugeben.

Um dieses Problem zu beheben, können Sie einen Mechanismus, z. B. [Std:: shared_ptr](../../standard-library/shared-ptr-class.md), ermöglicht einen Zeiger auf die von mehreren Komponenten gehören. Wenn das endgültige `shared_ptr`-Objekt zerstört wird, das eine Ressource besitzt, wird auch die Ressource freigegeben.

Im folgenden Beispiel wird veranschaulicht, wie mit `shared_ptr` Zeigerwerte für mehrere Nachrichtenpuffer gemeinsam verwendet werden können. Im Beispiel verbindet eine [Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) Objekt, das drei [Concurrency:: Call](../../parallel/concrt/reference/call-class.md) Objekte. Die `overwrite_buffer`-Klasse stellt Nachrichten für die einzelnen Ziele bereit. Da das Datennetzwerk am Ende mehrere Besitzer der Daten aufweist, werden die einzelnen `shared_ptr`-Objekte mit `call` in die Lage versetzt, den Besitz der Nachrichten zu teilen.

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

[Bewährte Methoden im Zusammenhang mit der Concurrency Runtime](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br/>
[Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agents](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[Bewährte Methoden in der Parallel Patterns Library](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br/>
[Allgemein bewährte Methoden in der Concurrency Runtime](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)
