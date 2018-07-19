---
title: Kontexte | Microsoft Docs
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
ms.openlocfilehash: 9a8297c8a7a779140f6464f39491e73950ddaeeb
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696187"
---
# <a name="contexts"></a>Kontexte

Dieses Dokument beschreibt die Rolle von Kontexten in der Concurrency Runtime. Ein Thread, der an einen Planer angefügt ist, wird als bezeichnet ein *Ausführungskontext*, oder nur *Kontext*. Die [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) -Funktion und die Concurrency::[Kontextklasse](../../parallel/concrt/reference/context-class.md) ermöglichen es Ihnen, die das Verhalten von Kontexten zu steuern. Verwenden der `wait` Funktion, um den aktuellen Kontext für einen festgelegten Zeitraum anhalten. Verwenden der `Context` Klasse bei der benötigen Sie besser steuern, wann Kontexte blockieren, Blockierung und Zurückhalten, oder wenn Sie den aktuellen Kontext überzeichnen möchten.  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie beim Optimieren der Leistung Ihrer Anwendungen unterstützt, empfiehlt es sich, dass die zu Beginn der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) Domänenmodus noch nicht mit der Concurrency Runtime.  
  
## <a name="the-wait-function"></a>Die Wait-Funktion  

 Die [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) Funktion kooperativ ergibt die Ausführung des aktuellen Kontexts für eine angegebene Anzahl von Millisekunden. Die Common Language Runtime verwendet die Yield-Zeit, um andere Aufgaben ausführen. Nachdem die angegebene Zeit verstrichen ist, plant die Common Language Runtime den Kontext für die Ausführung an. Aus diesem Grund die `wait` Funktion kann den aktuellen Kontext, die länger als der Wert für die Unterbrechung der `milliseconds` Parameter.  
  
 Übergeben 0 (null) für die `milliseconds` Parameter bewirkt, dass die Laufzeit des aktuellen Kontexts anhalten, bis alle anderen aktiven Kontexte die Möglichkeit, Aufgaben angegeben sind. Dadurch können Sie eine Aufgabe für alle aktiven Aufgaben zu erhalten.  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel, verwendet der `wait` Funktion, um den aktuellen Kontext zu erstellen, und dies ermöglicht die für andere Kontexte ausgeführt werden, finden Sie unter [Vorgehensweise: Verwenden Sie Planungsgruppen beeinflussen die Reihenfolge der Ausführung](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
## <a name="the-context-class"></a>Der Context-Klasse  
 Die Concurrency::[Kontextklasse](../../parallel/concrt/reference/context-class.md) bietet eine Programmiermodelle Abstraktion für einen Ausführungskontext und bietet zwei wichtige Funktionen: die Möglichkeit, kooperativ blockiert, Blockierung und führen den aktuellen Kontext und die Möglichkeit, zu überzeichnen Sie den aktuellen Kontext.  
  
### <a name="cooperative-blocking"></a>Kooperative Blockierung  
 Mit der `Context`-Klasse können Sie den aktuellen Ausführungskontext blockieren oder zurückhalten. Das Blockieren oder Zurückhalten ist nützlich, wenn es sich bei der aktuelle Kontext kann nicht fortgesetzt werden, weil eine Ressource nicht verfügbar ist.  
  

 Die [Concurrency::Context::Block](reference/context-class.md#block) Methode blockiert den aktuellen Kontext. Ein Kontext, der blockiert ist ergibt die Verarbeitungsressourcen, damit die Laufzeit andere Aufgaben ausführen kann. Die [Concurrency::Context::Unblock](reference/context-class.md#unblock) Methode hebt die Blockierung eines blockierten Kontexts. Die `Context::Unblock` -Methode muss aufgerufen werden, von einem anderen Kontext als den aufgerufen `Context::Block`. Löst die Laufzeit [concurrency::context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md) , wenn ein Kontext versucht, das Aufheben der eigenen Blockierung.  
  
 Um das kooperative Blockieren und Zulassen eines Kontexts, rufen Sie in der Regel [Concurrency::Context::CurrentContext](reference/context-class.md#currentcontext) abzurufenden einen Zeiger auf die `Context` Objekt, mit dem aktuellen Thread, und speichern Sie das Ergebnis zugeordnet ist. Rufen Sie dann die `Context::Block` Methode, um den aktuellen Kontext zu blockieren. Rufen Sie später `Context::Unblock` aus einem separaten Kontext aus, um die Blockierung aufzuheben.  
  
 Sie müssen jedes Paar von Aufrufe entsprechen `Context::Block` und `Context::Unblock`. Löst die Laufzeit [context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) bei der `Context::Block` oder `Context::Unblock` Methode hintereinander ohne einen übereinstimmenden Aufruf an die andere Methode aufgerufen wird. Aber Sie müssen keine Aufrufen `Context::Block` vor dem Aufruf `Context::Unblock`. Wenn ein Kontext ruft z. B. `Context::Unblock` bevor ein anderer Kontext ruft `Context::Block` für den gleichen Kontext bleibt dieser Kontext weiterhin entsperrt.  
  
 Die [yield](reference/context-class.md#yield) Methode setzt die Ausführung aus, damit die Laufzeit andere Aufgaben ausführen und Planen Sie den Kontext für die Ausführung kann. Beim Aufrufen der `Context::Block` des Kontexts von der Common Language Runtime-Methode ist nicht neu planen.  

  
#### <a name="example"></a>Beispiel  
 Ein Beispiel, verwendet der `Context::Block`, `Context::Unblock`, und `Context::Yield` Methoden zum Implementieren einer kooperativen Semaphore-Klasse, finden Sie unter [wie: Implementieren einer kooperativen Semaphore mithilfe der Kontext-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).  
  
##### <a name="oversubscription"></a>Überzeichnung  
 Der Standardplaner erstellt die gleiche Anzahl von Threads an, wie verfügbaren Hardwarethreads vorhanden sind. Sie können *Überzeichnung* zur Erstellung zusätzlicher Threads für einen bestimmten Hardwarethread.  
  
 Für rechenintensive Vorgänge skaliert Überzeichnung in der Regel nicht, da es Mehraufwand führt. Allerdings kann für Aufgaben, die eine hohe Latenz aufweisen, z. B. Lesen von Daten vom Datenträger oder von einer Netzwerkverbindung, durch die Überzeichnung verbessern die allgemeine Effizienz einiger Anwendungen.  
  
> [!NOTE]
>  Aktivieren Sie die Überzeichnung nur von einem Thread, der von der Concurrency Runtime erstellt wurde. Überzeichnung ist wirkungslos, wenn sie von einem anderen Thread aufgerufen wird, die nicht von der Common Language Runtime (einschließlich des Haupt-Threads) erstellt wurde.  
  
 Aufrufen, um die Aktivierung der Überzeichnung im aktuellen Kontext, der [Oversubscribe](reference/context-class.md#oversubscribe) Methode mit der `_BeginOversubscription` Parametersatz auf `true`. Wenn Sie die Überzeichnung auf einen Thread, die von der Concurrency Runtime erstellt wurde aktivieren, wird die Laufzeit einen zusätzlichen Thread erstellt. Rufen Sie nach dem alle Aufgaben, die Überzeichnung Fertig stellen erfordern, `Context::Oversubscribe` mit der `_BeginOversubscription` Parameter festgelegt wird, um `false`.  

  
 Sie können Überzeichnung mehrmals aus dem aktuellen Kontext aktivieren, aber Sie müssen es deaktivieren, die gleiche Anzahl von der Häufigkeit, mit der Sie ihn aktivieren. Durch Überzeichnung kann auch geschachtelt werden. d. h. kann eine Aufgabe, die von einer anderen Aufgabe erstellt wird, die Überzeichnung verwendet seinen Kontext überzeichnen. Jedoch, wenn eine geschachtelte Aufgabe und seinem übergeordneten Element an den gleichen Kontext, nur die äußersten Aufruf zum gehören `Context::Oversubscribe` bewirkt die Erstellung eines zusätzlichen Threads.  
  
> [!NOTE]
>  Löst die Laufzeit [concurrency::invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md) Wenn Überzeichnung deaktiviert ist, bevor es aktiviert wird.  
  
###### <a name="example"></a>Beispiel  
 Ein Beispiel, Überzeichnung zum kompensieren der Latenz, die beim Lesen von Daten über eine Netzwerkverbindung verursacht wird, finden Sie unter [wie: Verwenden von Überzeichnung Offset Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Vorgehensweise: Verwenden von Planungsgruppen, die Reihenfolge der Ausführung beeinflussen](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)   
 [Vorgehensweise: Implementieren einer kooperativen Semaphore mithilfe der Kontextklasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [Vorgehensweise: Verwenden der Überzeichnung zum Versetzen der Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)

