---
title: 'Exemplarische Vorgehensweise: Verwenden von Join zum Verhindern von Deadlocks | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45669b4838925ed671646ca1aad16a3fdbe6de77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377278"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>Exemplarische Vorgehensweise: Verhindern von Deadlocks mit join

In diesem Thema verwendet das Philosophenproblem um zu veranschaulichen, wie Sie mit der [Concurrency:: Join](../../parallel/concrt/reference/join-class.md) Klasse, um zu verhindern, dass Deadlocks in der Anwendung. In einer Softwareanwendung kommt es zu einem *Deadlock*, wenn zwei oder mehr Prozesse jeweils eine Ressource halten und gegenseitig darauf warten, dass ein anderer Prozess eine andere Ressource freigibt.

Das Philosophenproblem ist ein spezifisches Beispiel dafür, welche Probleme allgemein auftreten können, wenn ein Satz von Ressourcen von mehreren gleichzeitig ablaufenden Prozessen gemeinsam verwendet wird.

## <a name="prerequisites"></a>Erforderliche Komponenten

Lesen Sie sich folgende Themen durch, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:

- [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)

- [Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)

- [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)

- [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)

- [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)

##  <a name="top"></a> Abschnitte

Diese exemplarische Vorgehensweise enthält folgende Abschnitte:

- [Das Philosophenproblem](#problem)

- [Eine naive Implementierung](#deadlock)

- [Mithilfe von Join zum Verhindern von Deadlocks](#solution)

##  <a name="problem"></a> Das Philosophenproblem

Das Philosophenproblem veranschaulicht, wie Deadlocks in einer Anwendung auftreten. Bei diesem Problem sitzen fünf Philosophen an einem runden Tisch. Die einzelnen Philosophen haben Phasen, in denen sie denken, und Phasen, in denen sie essen. Jeder Philosoph muss ein Essstäbchen mit dem Tischnachbarn zu seiner Linken und ein anderes Essstäbchen mit dem Tischnachbarn zu seiner Rechten teilen. Die folgende Abbildung veranschaulicht diese Anordnung.

![Das Problem der dinierenden Philosophen](../../parallel/concrt/media/dining_philosophersproblem.png "Dining_philosophersproblem")

Um essen zu können, benötigt ein Philosoph zwei Essstäbchen. Wenn jeder Philosoph nur ein Essstäbchen hat und auf das zweite wartet, kann kein Philosoph essen und alle bleiben hungrig.

[[Nach oben](#top)]

##  <a name="deadlock"></a> Eine naive Implementierung

Im folgenden Beispiel wird eine naive Implementierung des Philosophenproblems veranschaulicht. Die `philosopher` -Klasse, die abgeleitet [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md), kann jeder Philosoph unabhängig handeln. Im Beispiel wird ein freigegebenes Array von [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) Objekte, damit jedes `philosopher` -Objekt exklusiven Zugriff auf ein Paar Essstäbchen hat.

Um die Implementierung mit der Abbildung in Verbindung zu bringen, stellt die `philosopher`-Klasse einen Philosophen dar. Jedes Essstäbchen wird durch eine `int`-Variable dargestellt. Die `critical_section`-Objekte dienen als Halter für die Essstäbchen. Die `run`-Methode simuliert das Leben des Philosophen. Die `think`-Methode simuliert das Denken und die `eat`-Methode das Essen.

Ein `philosopher`-Objekt sperrt beide `critical_section`-Objekte, um das Herausnehmen der Essstäbchen aus den Haltern zu simulieren, bevor die `eat`-Methode aufgerufen wird. Nach dem Aufruf von `eat` werden die Essstäbchen wieder vom `philosopher`-Objekt in die Halter zurückgelegt, und zwar durch Zurücksetzen der `critical_section`-Objekte in den entsperrten Zustand.

Die `pickup_chopsticks`-Methode veranschaulicht, wo ein Deadlock auftreten kann. Wenn jedes `philosopher`-Objekt Zugriff auf eine der Sperren erlangt, kann kein `philosopher`-Objekt fortfahren, weil die andere Sperre von einem anderen `philosopher`-Objekt gesteuert wird.

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

### <a name="code"></a>Code

[!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `philosophers-deadlock.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc Philosophers-deadlock.cpp**

[[Nach oben](#top)]

##  <a name="solution"></a> Mithilfe von Join zum Verhindern von Deadlocks

In diesem Abschnitt wird gezeigt, wie Meldungspuffer und Meldungsübergabefunktionen verwendet werden, um Deadlocks zu vermeiden.

In diesem Beispiel mit der früheren, Verbinden der `philosopher` Klasse ersetzt jede `critical_section` -Objekt unter Verwendung einer [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) Objekt und ein `join` Objekt. Das `join`-Objekt dient als Vermittler, das dem Philosophen die Essstäbchen bereitstellt.

In diesem Beispiel wird die `unbounded_buffer`-Klasse verwendet, da die Meldung aus der Meldungswarteschlange entfernt wird, wenn ein Ziel eine Meldung von einem `unbounded_buffer`-Objekt empfängt. So kann ein `unbounded_buffer`-Objekt, das eine Meldung enthält, darauf hinweisen, dass das Essstäbchen zur Verfügung steht. Ein `unbounded_buffer`-Objekt, das keine Meldung enthält, weist darauf hin, dass das Essstäbchen verwendet wird.

In diesem Beispiel wird ein nicht gieriges `join`-Objekt verwendet, da ein nicht gieriger Join nur dann jedem `philosopher`-Objekt Zugriff auf beide Essstäbchen gewährt, wenn beide `unbounded_buffer`-Objekte eine Meldung enthalten. Ein gieriger Join würde Deadlocks nicht verhindern, da Meldungen von ihm akzeptiert werden, sobald sie verfügbar sind. Deadlocks können auftreten, wenn alle gierigen `join`-Objekte eine der Meldungen empfangen, aber ewig warten, bis die andere verfügbar wird.

Weitere Informationen zu gierigen und nicht gierige Joins und die Unterschiede zwischen den verschiedenen Meldungspuffertypen finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md).

#### <a name="to-prevent-deadlock-in-this-example"></a>So verhindern Sie Deadlocks in diesem Beispiel

1. Entfernen Sie folgenden Code aus dem Beispiel.

[!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]

1. Ändern Sie den Typ der Datenmember `_left` und `_right` der `philosopher`-Klasse in `unbounded_buffer`.

[!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]

1. Ändern Sie den `philosopher`-Konstruktor, damit `unbounded_buffer`-Objekte als Parameter verwendet werden.

[!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]

1. Ändern Sie die `pickup_chopsticks`-Methode, um ein nicht gieriges `join`-Objekt zum Empfangen von Meldungen von den Meldungspuffern für beide Essstäbchen.

[!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]

1. Ändern Sie die `putdown_chopsticks`-Methode, um den Zugriff auf die Essstäbchen freizugeben, indem eine Meldung an die Meldungspuffer für beide Essstäbchen gesendet wird.

[!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]

1. Ändern Sie die `run`-Methode, um die Ergebnisse der `pickup_chopsticks`-Methode aufzunehmen und diese Ergebnisse an die `putdown_chopsticks`-Methode weiterzuleiten.

[!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]

1. Ändern Sie die Deklaration der `chopsticks`-Variable in der `wmain`-Funktion, damit sie ein Array von `unbounded_buffer`-Objekten ist, die jeweils über eine Meldung verfügen.

[!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Nachfolgend sehen Sie das vollständige Beispiel, bei dem nicht gierige `join`-Objekte verwendet werden, um das Risiko von Deadlocks auszuschließen.

### <a name="code"></a>Code

[!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]

### <a name="comments"></a>Kommentare

Folgende Ergebnisse werden zurückgegeben:

```Output
aristotle ate 50 times.
descartes ate 50 times.
hobbes ate 50 times.
socrates ate 50 times.
plato ate 50 times.
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `philosophers-join.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc Philosophers-join.cpp**

[[Nach oben](#top)]

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)<br/>
[Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)
