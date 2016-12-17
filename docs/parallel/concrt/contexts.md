---
title: "Kontexte"
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
  - "Kontexte [Parallelitätslaufzeit]"
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Kontexte
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Dokument beschreibt die Rolle von Kontexten in der Concurrency Runtime. Ein Thread, der an einen Planer angefügt ist, wird als bezeichnet ein *Ausführungskontext*, oder nur *Kontext*. Die [Concurrency:: wait](../Topic/wait%20Function.md) -Funktion und die Concurrency::[Kontextklasse](../../parallel/concrt/reference/context-class.md) ermöglichen es Ihnen, das Verhalten von Kontexten steuern. Verwenden der `wait` Funktion den aktuellen Kontext für eine bestimmte Zeit angehalten. Verwenden der `Context` Klasse, wenn Sie besser steuern, wann Kontexte blockieren, zulassen und ergeben oder wenn Sie den aktuellen Kontext überzeichnen möchten benötigen.  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie die Leistung einer Anwendung optimieren können, wird empfohlen, dass Sie mit beginnen die [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) wenn Sie mit der Concurrency Runtime sind.  
  
## <a name="the-wait-function"></a>Die Wait-Funktion  
 Die [Concurrency:: wait](../Topic/wait%20Function.md) Funktion die Ausführung des aktuellen Kontexts für eine angegebene Anzahl von Millisekunden kooperativ zurückgehalten. Die Common Language Runtime verwendet die Yield-Zeit für andere Aufgaben. Nachdem die angegebene Zeit verstrichen ist, plant die Common Language Runtime den Kontext für die Ausführung. Aus diesem Grund die `wait` Funktion kann den aktuellen Kontext, der länger als der Wert für die Unterbrechung der `milliseconds` Parameter.  
  
 Übergeben 0 (null) für den `milliseconds` -Parameter unterbricht die Runtime den aktuellen Kontext angehalten, bis alle anderen aktiven Kontexte die Möglichkeit, Aufgaben angegeben werden. Dadurch können Sie eine Aufgabe für alle aktiven Aufgaben ergeben.  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung der `wait` Funktion, um den aktuellen Kontext und bieten daher anderen Kontexten ausführen, finden Sie unter [Gewusst wie: Verwenden von Planungsgruppen Einfluss Reihenfolge der Ausführung](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
## <a name="the-context-class"></a>Der Context-Klasse  
 Die Concurrency::[Kontextklasse](../../parallel/concrt/reference/context-class.md) bietet eine Programmierung Abstraktion für einen Ausführungskontext und bietet zwei wichtige Funktionen: die Fähigkeit, kooperativ blockiert, Blockierung und zurückzuhalten und die Fähigkeit, den aktuellen Kontext überzeichnen.  
  
### <a name="cooperative-blocking"></a>Kooperative Blockierung  
 Mit der `Context`-Klasse können Sie den aktuellen Ausführungskontext blockieren oder zurückhalten. Blockieren oder Zurückhalten ist nützlich, wenn der aktuelle Kontext kann nicht fortgesetzt werden, da eine Ressource nicht verfügbar ist.  
  
 Die [Concurrency::Context::Block](../Topic/Context::Block%20Method.md) Methode blockiert den aktuellen Kontext. Ein Kontext, der blockiert ist ergibt die Verarbeitungsressourcen, damit die Laufzeit andere Aufgaben ausführen kann. Die [Concurrency::Context::Unblock](../Topic/Context::Unblock%20Method.md) Methode hebt die Blockierung eines blockierten Kontexts. Die `Context::Unblock` -Methode muss aufgerufen werden, aus einem anderen Kontext als den Namen `Context::Block`. Die Runtime löst [concurrency::context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md) wenn ein Kontext versucht, die eigene Blockierung aufzuheben.  
  
 Um kooperativ zu blockieren und Zulassen eines Kontexts, rufen Sie in der Regel [Concurrency::Context::CurrentContext](../Topic/Context::CurrentContext%20Method.md) abzurufenden einen Zeiger auf die `Context` -Objekt, das den aktuellen Thread, und speichern Sie das Ergebnis zugeordnet ist. Rufen Sie dann die `Context::Block` Methode, um den aktuellen Kontext zu blockieren. Später rufen `Context::Unblock` aus einem anderen Kontext, um die Blockierung aufzuheben.  
  
 Jedes Paar von aufrufen müssen übereinstimmen `Context::Block` und `Context::Unblock`. Die Runtime löst [context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) bei der `Context::Block` oder `Context::Unblock` Methode nacheinander ohne einen entsprechenden Aufruf an die andere Methode aufgerufen wird. Aber Sie müssen keinen Aufrufen `Context::Block` vor dem Aufruf von `Context::Unblock`. Beispielsweise, wenn ein Kontext ruft `Context::Unblock` vor einem anderen kontextaufrufen `Context::Block` für den gleichen Kontext, bleibt dieser Kontext weiterhin freigegeben werden soll.  
  
 Die [yield](../Topic/Context::Yield%20Method.md) Methode setzt die Ausführung aus, damit die Laufzeit andere Aufgaben ausführen kann, und Planen Sie den Kontext für die Ausführung. Beim Aufrufen der `Context::Block` des Kontexts von der Common Language Runtime-Methode ist nicht neu planen.  
  
#### <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung der `Context::Block`, `Context::Unblock`, und `Context::Yield` Methoden zum Implementieren einer kooperativen Semaphore-Klasse finden Sie unter [wie: Implementieren einer kooperativen Semaphore mithilfe der Kontext-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).  
  
##### <a name="oversubscription"></a>Überzeichnung  
 Der Standardplaner erstellt die gleiche Anzahl von Threads verfügbaren Hardwarethreads vorhanden sind. Sie können *Überzeichnung* zusätzliche Threads für einen gegebenen Hardwarethread erstellen.  
  
 Für rechenintensive Vorgänge skaliert Überzeichnung in der Regel nicht, da dies zu zusätzlichem Aufwand führt. Allerdings kann für Aufgaben, die eine hohe Latenz aufweisen, z. B. Lesen von Daten vom Datenträger oder aus einer Netzwerkschnittstelle Überzeichnung die allgemeine Effizienz einiger Anwendungen verbessert werden.  
  
> [!NOTE]
>  Aktivieren Sie die Überzeichnung nur von einem Thread, der von der Concurrency Runtime erstellt wurde. Überzeichnung hat keine Auswirkung, wenn sie von einem anderen Thread aufgerufen wird, die nicht von der Common Language Runtime (einschließlich des Hauptthreads) erstellt wurde.  
  
 Rufen Sie zum Aktivieren der Überzeichnung im aktuellen Kontext der [Oversubscribe](../Topic/Context::Oversubscribe%20Method.md) -Methode mit der `_BeginOversubscription` Parametersatz zu `true`. Wenn Sie die Überzeichnung auf einen Thread, die von der Concurrency Runtime erstellt wurde aktivieren, wird die Laufzeit einen zusätzlichen Thread erstellt wird. Aufrufen, nachdem alle Aufgaben, die Überzeichnung Fertig stellen erfordern, `Context::Oversubscribe` mit der `_BeginOversubscription` Parametersatz zu `false`.  
  
 Sie können die Überzeichnung aus dem aktuellen Kontext mehrmals aktivieren, aber Sie müssen es deaktivieren, die gleiche Anzahl von Häufigkeit, mit der Sie ihn aktivieren. Durch Überzeichnung kann auch geschachtelt werden. d. h. kann eine Aufgabe, die von einer anderen Aufgabe erstellt wird, die Überzeichnung verwendet seinen Kontext überzeichnen. Jedoch, wenn eine geschachtelte Aufgabe und seinem übergeordneten Element, an den gleichen Kontext und beim Aufruf von gehören `Context::Oversubscribe` bewirkt die Erstellung eines zusätzlichen Threads.  
  
> [!NOTE]
>  Die Runtime löst [concurrency::invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md) Wenn Überzeichnung deaktiviert ist, bevor es aktiviert wird.  
  
###### <a name="example"></a>Beispiel  
 Ein Beispiel, die Überzeichnung wird verwendet, um die Latenz beim Lesen von Daten aus einer Verbindung verursacht wird, finden Sie unter [Gewusst wie: Verwenden der Überzeichnung Offset Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Gewusst wie: beeinflussen der Ausführungsreihenfolge mithilfe](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)   
 [Gewusst wie: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [Gewusst wie: Verwenden der Überzeichnung zum Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)

