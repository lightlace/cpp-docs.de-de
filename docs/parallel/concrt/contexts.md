---
title: Kontexte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- contexts [Concurrency Runtime]
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fb14544a799861053c2fdf2a5bb92f210eb5c46
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163828"
---
# <a name="contexts"></a>Kontexte

Dieses Dokument beschreibt die Rolle von Kontexten, in der Concurrency Runtime. Ein Thread, der an einen Planer angefügt ist, wird als bezeichnet ein *Ausführungskontext*, oder nur *Kontext*. Die [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) -Funktion und die Parallelität::[Kontextklasse](../../parallel/concrt/reference/context-class.md) ermöglichen es Ihnen, die das Verhalten von Kontexten zu steuern. Verwenden der `wait` Funktion, um den aktuellen Kontext für einen bestimmten Zeitraum angehalten. Verwenden der `Context` Klasse, wenn Sie mehr Kontrolle über wann Kontexte blockieren, entsperren und ergeben, oder wenn Sie den aktuellen Kontext überzeichnen möchten benötigen.

> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner die Leistung Ihrer Anwendungen optimieren können, es wird empfohlen, zunächst die [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) möchten noch nicht mit der Concurrency Runtime.

## <a name="the-wait-function"></a>Die Wait-Funktion

Die [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) Funktion kooperativ zurückgehalten die Ausführung des aktuellen Kontexts für eine angegebene Anzahl von Millisekunden. Die Common Language Runtime verwendet die "yield"-Zeit, um andere Aufgaben auszuführen. Nachdem die angegebene Zeit verstrichen ist, plant die Runtime den Kontext für die Ausführung neu. Aus diesem Grund die `wait` Funktion kann den aktuellen Kontext, der länger als der Wert für die Unterbrechung der `milliseconds` Parameter.

Übergeben 0 (null) für die `milliseconds` Parameter bewirkt, dass die Laufzeit des aktuellen Kontexts angehalten, bis alle anderen aktiven Kontexte die Möglichkeit, Aufgaben angegeben werden. Dadurch können Sie eine Aufgabe für alle anderen aktiven Aufgaben zu erhalten.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung der `wait` Funktion, um den aktuellen Kontext und bieten daher anderen Kontexten ausführen, finden Sie unter [Vorgehensweise: Verwenden Sie Planungsgruppen Einfluss Reihenfolge der Ausführung](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

## <a name="the-context-class"></a>Der Context-Klasse

Die Concurrency::[Kontextklasse](../../parallel/concrt/reference/context-class.md) sorgt für eine Programmabstraktion für einen Ausführungskontext und bietet zwei wichtige Funktionen: die Möglichkeit, kooperativ blockiert, Blockierung und ergibt den aktuellen Kontext und die Möglichkeit, zu überzeichnen Sie den aktuellen Kontext.

### <a name="cooperative-blocking"></a>Kooperative Blockierung

Mit der `Context`-Klasse können Sie den aktuellen Ausführungskontext blockieren oder zurückhalten. Das Blockieren oder Zurückhalten ist nützlich, wenn der aktuelle Kontext kann nicht fortgesetzt werden, weil eine Ressource nicht verfügbar ist.

Die [Concurrency::Context::Block](reference/context-class.md#block) Methode blockiert den aktuellen Kontext. Ein Kontext, der blockiert ist ergibt die Verarbeitungsressourcen, damit die Laufzeit andere Aufgaben ausführen kann. Die [Concurrency::Context::Unblock](reference/context-class.md#unblock) Methode hebt die Blockierung eines blockierten Kontexts. Die `Context::Unblock` -Methode muss aufgerufen werden, von einem anderen Kontext als diejenige, die Namen `Context::Block`. Löst die Laufzeit [concurrency::context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md) , wenn ein Kontext versucht, sich selbst zu entsperren.

Um kooperativ blockieren und entsperren einen Kontext an, rufen Sie in der Regel [Concurrency::Context::CurrentContext](reference/context-class.md#currentcontext) abzurufenden einen Zeiger auf die `Context` Objekt, mit dem aktuellen Thread, und speichern das Ergebnis zugeordnet ist. Rufen Sie dann die `Context::Block` Methode blockiert den aktuellen Kontext. Rufen Sie später `Context::Unblock` aus einem separaten Kontext aus, um die Blockierung aufzuheben.

Sie müssen jedes Paar Aufrufe entsprechen `Context::Block` und `Context::Unblock`. Löst die Laufzeit [context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) bei der `Context::Block` oder `Context::Unblock` Methode aufgerufen wird, nacheinander ohne einen entsprechenden Aufruf an die andere Methode. Sie sind jedoch keine aufzurufende `Context::Block` vor dem Aufruf `Context::Unblock`. Wenn ein Kontext ruft z. B. `Context::Unblock` vor einem anderen kontextaufrufen `Context::Block` für den gleichen Kontext, bleibt dieser Kontext weiterhin aufgehoben wurde.

Die [yield](reference/context-class.md#yield) Methode setzt die Ausführung aus, damit die Laufzeit andere Aufgaben ausführen kann, und Planen Sie den Kontext für die Ausführung. Beim Aufrufen der `Context::Block` des Kontexts von der Runtime-Methode ist nicht neu planen.

#### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung der `Context::Block`, `Context::Unblock`, und `Context::Yield` Methoden zum Implementieren einer kooperativen Semaphore-Klasse, finden Sie unter [Vorgehensweise: Verwenden der Context-Klasse zum Implementieren einer kooperativen Semaphore](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).

##### <a name="oversubscription"></a>Überzeichnung

Der Standard-Scheduler erstellt die gleiche Anzahl von Threads an, wie es verfügbaren Hardwarethreads. Sie können *Überzeichnung* zusätzliche Threads für einen bestimmten Hardwarethread zu erstellen.

Für die Ausführung rechenintensiver Vorgänge skaliert Überzeichnung in der Regel nicht, da dies zu Mehraufwand führt. Allerdings kann für Aufgaben, die einen hohen Betrag an Wartezeit aufweisen, z. B. Lesen von Daten vom Datenträger oder von einer Netzwerkverbindung, Überzeichnung die allgemeine Effizienz einiger Anwendungen verbessern.

> [!NOTE]
>  Aktivieren Sie die Überzeichnung nur von einem Thread, der von der Concurrency Runtime erstellt wurde. Überzeichnung hat keine Auswirkungen, wenn sie von einem anderen Thread aufgerufen wird, die nicht von der Laufzeit (einschließlich des Haupt-Threads) erstellt wurde.

Rufen Sie zum Aktivieren der Überzeichnung im aktuellen Kontext der [Oversubscribe](reference/context-class.md#oversubscribe) -Methode mit dem `_BeginOversubscription` Parametersatz zu **"true"**. Wenn Sie die Überzeichnung in einem Thread, die von der Concurrency Runtime erstellt wurde aktivieren, wird die Laufzeit einen zusätzlichen Thread erstellt wird. Rufen Sie nach dem alle Aufgaben, die Überzeichnung "Fertig stellen" erfordern, `Context::Oversubscribe` mit der `_BeginOversubscription` Parametersatz zu **"false"**.

Überzeichnung mehrmals aus dem aktuellen Kontext können, aber Sie müssen es deaktivieren, die gleiche Anzahl von Wiederholungen, die Sie ihn aktivieren. Überzeichnung kann auch geschachtelt werden. d. h. kann eine Aufgabe, die von einer anderen Aufgabe erstellt wird, die Überzeichnung verwendet seinen Kontext überzeichnen. Allerdings, wenn sowohl das übergeordnete Element als auch eine geschachtelte Aufgabe zum gleichen Kontext ist nur beim Aufruf von gehören `Context::Oversubscribe` bewirkt, dass ein zusätzlicher Thread.

> [!NOTE]
>  Löst die Laufzeit [concurrency::invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md) Wenn Überzeichnung deaktiviert ist, bevor sie aktiviert ist.

###### <a name="example"></a>Beispiel

Ein Beispiel, die Überzeichnung verwendet, um die Latenz zu versetzen, die durch das Lesen von Daten über eine Netzwerkverbindung verursacht wird, finden Sie unter [Vorgehensweise: Verwenden der Überzeichnung Offset Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

## <a name="see-also"></a>Siehe auch

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Vorgehensweise: Beeinflussen der Ausführungsreihenfolge mithilfe von Zeitplangruppen](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)<br/>
[Vorgehensweise: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[Vorgehensweise: Verwenden der Überzeichnung zum Versetzen der Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)

