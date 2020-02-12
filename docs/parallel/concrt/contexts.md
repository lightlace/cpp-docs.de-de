---
title: Kontext
ms.date: 11/04/2016
helpviewer_keywords:
- contexts [Concurrency Runtime]
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
ms.openlocfilehash: 9eaf21a3d65ae891a48657de9d3e7aff78ce12b9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142187"
---
# <a name="contexts"></a>Kontext

In diesem Dokument wird die Rolle von Kontexten in der Concurrency Runtime beschrieben. Ein Thread, der an einen Scheduler angefügt ist, wird als *Ausführungs Kontext*oder nur als *Kontext*bezeichnet. Die [parallelcurrency:: Wait](reference/concurrency-namespace-functions.md#wait) -Funktion und die "parallelcurrency:: Context"-[Klasse](../../parallel/concrt/reference/context-class.md) ermöglichen Ihnen, das Verhalten von Kontexten zu steuern. Verwenden Sie die `wait`-Funktion, um den aktuellen Kontext für einen angegebenen Zeitraum anzuhalten. Verwenden Sie die `Context`-Klasse, wenn Sie mehr Kontrolle darüber benötigen, wann Kontexte blockiert werden, die Blockierung durchführen oder den aktuellen Kontext überschreiben möchten.

> [!TIP]
> Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie bei der Feinabstimmung der Leistung Ihrer Anwendungen unterstützt, empfehlen wir Ihnen, mit der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie mit der Concurrency Runtime noch nicht vertraut sind.

## <a name="the-wait-function"></a>Die wait-Funktion

Die [parallelcurrency:: Wait](reference/concurrency-namespace-functions.md#wait) -Funktion führt die Ausführung des aktuellen Kontexts für eine angegebene Anzahl von Millisekunden zusammen. Die Laufzeit verwendet die Yield-Zeit, um andere Aufgaben auszuführen. Nachdem die angegebene Zeit abgelaufen ist, plant die Laufzeit den Kontext für die Ausführung erneut. Daher kann die `wait`-Funktion den aktuellen Kontext länger aussetzen, als der für den `milliseconds`-Parameter bereitgestellte Wert.

Wenn 0 (null) für den `milliseconds`-Parameter übergeben wird, wird der aktuelle Kontext von der Laufzeit angehalten, bis allen anderen aktiven Kontexten die Möglichkeit zur Durchführung der Arbeit erteilt wird. Auf diese Weise können Sie für alle anderen aktiven Aufgaben eine Aufgabe durchführen.

### <a name="example"></a>Beispiel

Ein Beispiel, in dem die `wait`-Funktion verwendet wird, um den aktuellen Kontext zu erhalten und damit andere Kontexte ausgeführt werden können, finden Sie unter Gewusst [wie: Verwenden von Zeit Plan Gruppen zum beeinflussen der Ausführungsreihenfolge](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

## <a name="the-context-class"></a>Die Kontext Klasse

Die "parallelcurrency:: Context"-[Klasse](../../parallel/concrt/reference/context-class.md) stellt eine Programmier Abstraktion für einen Ausführungs Kontext bereit und bietet zwei wichtige Features: die Möglichkeit, den aktuellen Kontext kooperativ zu blockieren, zu entsperren und den aktuellen Kontext zu überschreiben sowie die Möglichkeit, den aktuellen Kontext zu überschreiben.

### <a name="cooperative-blocking"></a>Kooperative Blockierung

Mit der `Context`-Klasse können Sie den aktuellen Ausführungskontext blockieren oder zurückhalten. Das Blockieren oder bereitstellen ist nützlich, wenn der aktuelle Kontext nicht fortgesetzt werden kann, da eine Ressource nicht verfügbar ist.

Die [parallelcurrency:: context:: Block](reference/context-class.md#block) -Methode blockiert den aktuellen Kontext. Ein Kontext, der blockiert wird, liefert seine Verarbeitungs Ressourcen, damit die Laufzeit andere Aufgaben ausführen kann. Die [parallelcurrency:: context:: Unblock](reference/context-class.md#unblock) -Methode hebt die Blockierung eines blockierten Kontexts auf. Die `Context::Unblock`-Methode muss von einem anderen Kontext aufgerufen werden als der, der `Context::Block`aufgerufen hat. Die Laufzeit löst " [parallelcurrency:: context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md) " aus, wenn ein Kontext versucht, die Blockierung selbst aufzulösen.

Um einen Kontext kooperativ zu blockieren und freizugeben, rufen Sie in der Regel [Concurrency:: context:: CurrentContext](reference/context-class.md#currentcontext) auf, um einen Zeiger auf das `Context` Objekt abzurufen, das dem aktuellen Thread zugeordnet ist, und speichern Sie das Ergebnis. Anschließend wird die `Context::Block`-Methode aufgerufen, um den aktuellen Kontext zu blockieren. Später wird `Context::Unblock` aus einem separaten Kontext aufgerufen, um die Blockierung des blockierten Kontexts aufzuheben.

Sie müssen jedes Paar von Aufrufen an `Context::Block` und `Context::Unblock`abgleichen. Die Common Language Runtime löst " [parallelcurrency:: context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) " aus, wenn die `Context::Block`-oder `Context::Unblock`-Methode nacheinander aufgerufen wird, ohne dass ein entsprechender Aufruf der anderen Methode erfolgt. Sie müssen `Context::Block` jedoch nicht anrufen, bevor Sie `Context::Unblock`aufgerufen haben. Wenn z. b. ein Kontext `Context::Unblock` aufruft, bevor ein anderer Kontext `Context::Block` für denselben Kontext aufruft, bleibt dieser Kontext unverändert.

Die [parallelcurrency:: context:: Yield](reference/context-class.md#yield) -Methode führt die Ausführung aus, sodass die Runtime andere Tasks ausführen und dann den Kontext für die Ausführung neu planen kann. Wenn Sie die `Context::Block`-Methode aufzurufen, wird der Kontext von der Laufzeit nicht neu geplant.

#### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung der Methoden `Context::Block`, `Context::Unblock`und `Context::Yield` zum Implementieren einer kooperativen Semaphor-Klasse finden Sie unter Gewusst [wie: Implementieren einer kooperativen Semaphor mithilfe der Context-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).

##### <a name="oversubscription"></a>Überzeichnung

Der Standard Planer erstellt die gleiche Anzahl von Threads, wie verfügbare Hardwarethreads vorhanden sind. Sie können *über Abonnements* verwenden, um zusätzliche Threads für einen bestimmten Hardware Thread zu erstellen.

Bei rechenintensiven Vorgängen wird die Überzeichnung in der Regel nicht skaliert, da dadurch zusätzlicher Verwaltungsaufwand entsteht. Bei Aufgaben mit einer hohen Latenzzeit, z. b. beim Lesen von Daten von einem Datenträger oder einer Netzwerkverbindung, kann die Gesamteffizienz einiger Anwendungen dadurch verbessert werden.

> [!NOTE]
> Aktivieren Sie die Überzeichnung nur über einen Thread, der vom Concurrency Runtime erstellt wurde. Die Überzeichnung hat keine Auswirkung, wenn Sie von einem Thread aufgerufen wird, der nicht von der Laufzeit (einschließlich des Haupt Threads) erstellt wurde.

Um die Überzeichnung im aktuellen Kontext zu aktivieren, müssen Sie die [parallelcurrency:: context:: Oversubscribe](reference/context-class.md#oversubscribe) -Methode aufrufen, wobei der `_BeginOversubscription`-Parameter auf **true**festgelegt ist. Wenn Sie die Überzeichnung für einen vom Concurrency Runtime erstellten Thread aktivieren, bewirkt dies, dass die Laufzeit einen zusätzlichen Thread erstellt. Nachdem alle Aufgaben, für die die Überzeichnung abgeschlossen werden muss, abgeschlossen sind, müssen Sie `Context::Oversubscribe` aufrufen, wobei der Parameter `_BeginOversubscription` auf **false**

Sie können die Überzeichnung mehrmals aus dem aktuellen Kontext aktivieren. Sie müssen Sie jedoch so oft deaktivieren, wie Sie Sie aktivieren. Die Überzeichnung kann auch Nested sein. Das heißt, ein Task, der von einer anderen Aufgabe erstellt wird, die overabonnement verwendet, kann seinen Kontext auch überschreiben. Wenn jedoch sowohl eine-als auch die übergeordnete Aufgabe zu demselben Kontext gehört, bewirkt nur der äußerste `Context::Oversubscribe` Aufrufe die Erstellung eines zusätzlichen Threads.

> [!NOTE]
> Die Laufzeit löst " [parallelcurrency:: Invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md) " aus, wenn die Überzeichnung deaktiviert ist, bevor Sie aktiviert wird.

###### <a name="example"></a>Beispiel

Ein Beispiel, bei dem über Abonnements verwendet werden, um die Latenz zu versetzen, die durch das Lesen von Daten aus einer Netzwerkverbindung verursacht wird, finden Sie unter Gewusst [wie: Verwenden der Überzeichnung zum](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)versetzen der Wartezeit.

## <a name="see-also"></a>Weitere Informationen

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Vorgehensweise: Beeinflussen der Ausführungsreihenfolge mithilfe von Zeitplangruppen](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)<br/>
[Vorgehensweise: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[Vorgehensweise: Verwenden der Überzeichnung zum Versetzen der Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)
