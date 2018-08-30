---
title: Abbruch in der PPL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel algorithms, canceling [Concurrency Runtime]
- canceling parallel algorithms [Concurrency Runtime]
- parallel tasks, canceling [Concurrency Runtime]
- cancellation in the PPL
- parallel work trees [Concurrency Runtime]
- canceling parallel tasks [Concurrency Runtime]
ms.assetid: baaef417-b2f9-470e-b8bd-9ed890725b35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd12bff6638ef86205b1037a8a7c7e348767ae9a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221754"
---
# <a name="cancellation-in-the-ppl"></a>Abbruch in der PPL
In diesem Dokument wird die Rolle des Abbruchs in der Parallel Patterns Library (PPL) erläutert und beschrieben, wie Sie die parallele Arbeitsvorgänge abbrechen, und wie Sie erkennen können, ob parallele Arbeitsvorgänge abgebrochen wurden.  
  
> [!NOTE]
>  Die Laufzeit implementiert Abbrüche mithilfe der Ausnahmebehandlung. Diese Ausnahmen dürfen im eigenen Code nicht abgefangen oder behandelt werden. Außerdem empfiehlt es sich, ausnahmesicheren Code in den Funktionsrümpfen der Aufgaben zu schreiben. Beispielsweise können Sie die *Resource Acquisition Is Initialization* (RAII)-Muster können Sie sicherstellen, dass Ressourcen ordnungsgemäß behandelt werden, wenn im Text einer Aufgabe eine Ausnahme ausgelöst wird. Ein vollständiges Beispiel, das das RAII-Muster verwendet, um eine Ressource in einer abbrechbaren Aufgabe zu bereinigen, finden Sie unter [Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md).  
  
## <a name="key-points"></a>Wesentliche Punkte  
  
-   Das Abbrechen ist ein kooperativer Vorgang und beinhaltet die Koordination zwischen dem Code, der den Abbruch verlangt, und der Aufgabe, die auf den Abbruch reagieren muss.  
  
-   Verwenden Sie wenn möglich Abbruchtoken, um Arbeitsvorgänge abzubrechen. Die [Concurrency:: cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) -Klasse definiert ein Abbruchtoken.  
  

-   Bei Verwendung von Abbruchtoken verwenden die [Concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) Methode, um den Abbruch zu initiieren und die [Concurrency:: cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) Funktion, die auf Antworten Abbruch. Verwenden der [Concurrency::cancellation_token::is_canceled](reference/cancellation-token-class.md#is_canceled) -Methode überprüft, ob es sich bei allen anderen Aufgaben den Abbruch angefordert hat.
  
-   Der Abbruch erfolgt nicht unmittelbar. Es werden zwar keine neuen Arbeitsvorgänge gestartet, wenn eine Aufgabe oder eine Aufgabengruppe abgebrochen wird, aktive Arbeitsvorgänge müssen den Abbruch aber überprüfen und auf diesen reagieren.  
  
-   Eine wertbasierte Fortsetzung erbt das Abbruchtoken ihrer Vorgängeraufgabe. Eine aufgabenbasierte Fortsetzung erbt das Token der Vorgängeraufgabe dagegen nicht.  
  
-   Verwenden der [Concurrency:: cancellation_token:: none](reference/cancellation-token-class.md#none) Methode, wenn Sie rufen einen Konstruktor oder eine Funktion, die akzeptiert eine `cancellation_token` -Objekt, aber Sie möchten nicht, den Vorgang abbrechbar ist. Auch wenn Sie kein Abbruchtoken zu übergeben die [Concurrency:: Task](../../parallel/concrt/reference/task-class.md) Konstruktor oder die [Concurrency:: create_task](reference/concurrency-namespace-functions.md#create_task) -Funktion, die diese Aufgabe kann nicht abgebrochen werden.  


  
##  <a name="top"></a> In diesem Dokument  
  
- [Parallele Arbeitsstrukturen](#trees)  
  
- [Abbrechen paralleler Aufgaben](#tasks)  
  
    - [Verwenden eines Abbruchtokens zum Abbrechen paralleler Aufgaben](#tokens)  
  
    - [Mithilfe der Cancel-Methode zum Abbrechen paralleler Aufgaben](#cancel)  
  
    - [Verwenden von Ausnahmen zum Abbrechen paralleler Aufgaben](#exceptions)  
  
- [Abbrechen von parallelen Algorithmen](#algorithms)  
  
- [Wenn nicht mit dem Abbrechen](#when)  
  
##  <a name="trees"></a> Parallele Arbeitsstrukturen  
 Differenzierte Aufgaben und Berechnungen werden in der PPL mithilfe von Aufgaben und Aufgabengruppen verwaltet. Sie können Aufgabengruppen zu schachteln *Strukturen* paralleler Arbeitsaufgaben. Die folgende Abbildung zeigt eine parallele Arbeitsstruktur. In dieser Abbildung stellen `tg1` und `tg2` Aufgabengruppen dar; `t1`, `t2`, `t3`, `t4` und `t5` stellen die Arbeitsvorgänge dar, die von den Aufgabengruppen durchgeführt wird.  
  
 ![Eine parallele Arbeitsstruktur](../../parallel/concrt/media/parallelwork_trees.png "Parallelwork_trees")  
  
 Das folgende Beispiel zeigt den Code, der zum Erstellen der Struktur in der Abbildung erforderlich ist. In diesem Beispiel `tg1` und `tg2` sind [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Objekte. `t1`, `t2`, `t3`, `t4`, und `t5` sind [Concurrency:: task_handle](../../parallel/concrt/reference/task-handle-class.md) Objekte.  
  
 [!code-cpp[concrt-task-tree#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_1.cpp)]  
  
 Sie können auch die [Concurrency:: task_group](reference/task-group-class.md) Klasse, um eine ähnliche Arbeitsstruktur zu erstellen. Die [Concurrency:: Task](../../parallel/concrt/reference/task-class.md) Klasse unterstützt auch das Konzept einer Arbeitsstruktur. Eine `task`-Struktur ist jedoch eine Abhängigkeitsstruktur. In einer `task`-Struktur werden zukünftige Arbeitsvorgänge nach aktuellen Arbeitsvorgängen abgeschlossen. In einer Aufgabengruppenstruktur werden interne Arbeitsvorgänge vor externen Arbeitsvorgängen abgeschlossen. Weitere Informationen zu den Unterschieden zwischen Aufgaben und Aufgabengruppen finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="tasks"></a> Abbrechen paralleler Aufgaben  

 Es gibt verschiedene Möglichkeiten, parallele Arbeitsvorgänge abzubrechen. Die bevorzugte Methode ist, ein Abbruchtoken zu verwenden. Aufgabengruppen unterstützen auch die [task_group](reference/task-group-class.md#cancel) Methode und die [Concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) Methode. Eine letzte Möglichkeit ist, im Text einer Arbeitsfunktion einer Aufgabe eine Ausnahme auszulösen. Unabhängig von der gewählten Methode sollten Sie bedenken, dass der Abbruch nicht sofort auftritt. Es werden zwar keine neuen Arbeitsvorgänge gestartet, wenn eine Aufgabe oder eine Aufgabengruppe abgebrochen wird, aktive Arbeitsvorgänge müssen den Abbruch aber überprüfen und auf diesen reagieren.  

  
 Weitere Beispiele zum Abbrechen paralleler Aufgaben finden Sie unter [Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML-HTTP-Anforderungen](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md), [Vorgehensweise: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md), und [Vorgehensweise: verwenden Ausnahmebehandlung zum Verlassen einer Parallel-Schleife](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).  
  
###  <a name="tokens"></a> Verwenden eines Abbruchtokens zum Abbrechen paralleler Aufgaben  
 Die Klassen `task`, `task_group` und `structured_task_group` unterstützen Abbruchvorgänge durch die Verwendung von Abbruchtoken. Die PPL definiert die [Concurrency:: cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md) und [Concurrency:: cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) Klassen für diesen Zweck. Wenn Sie Arbeit mithilfe eines Abbruchtokens abbrechen, wird von der Runtime keine neue Verarbeitung gestartet, die dieses Token abonniert. Aufgaben, die bereits aktiv ist können die [Is_canceled](../../parallel/concrt/reference/cancellation-token-class.md#is_canceled) Memberfunktion versucht, das Abbruchtoken, das Überwachen und beenden, wenn möglich.  
  

 Um den Abbruch zu initiieren, rufen Sie die [Concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) Methode. Auf Abbrüche reagieren Sie folgendermaßen:  
  
-   Für `task` Objekte zu verwenden, die [Concurrency:: cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) Funktion. `cancel_current_task` bricht die aktuelle Aufgabe und alle wertbasierten Fortsetzungen ab. (Nicht das Abbruchtoken abgebrochen *token* , der Aufgabe bzw. seinen Fortsetzungen zugeordnet ist.)  
  
-   Verwenden Sie für Aufgabengruppen und parallele Algorithmen, die [Concurrency:: is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling) -Funktion zum Erkennen von Abbruch und zurückgeben so bald wie möglich vom Aufgabentext, wenn diese Funktion zurückkehrt `true`. (Verwenden Sie bei Aufgabengruppen nicht `cancel_current_task`.)  

  
 Das folgende Beispiel zeigt das erste grundlegende Muster für den Aufgabenabbruch. Der Aufgabentext überprüft die Schleife von Zeit zu Zeit auf Abbrüche.  
  
 [!code-cpp[concrt-task-basic-cancellation#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_2.cpp)]  
  
 Die `cancel_current_task`-Funktion löst eine Ausnahme aus; daher müssen Sie nicht explizit von der aktuellen Schleife oder Funktion zurückkehren.  
  
> [!TIP]

>  Sie können alternativ Aufrufen der [Concurrency:: interruption_point](reference/concurrency-namespace-functions.md#interruption_point) -Funktion anstelle von `cancel_current_task`.  
  
 Es ist wichtig, `cancel_current_task` als Reaktion auf einen Abbruch aufzurufen, da die Aufgabe dadurch in den abgebrochenen Zustand übergeht. Wenn Sie zu früh zurückkehren, anstatt `cancel_current_task` aufzurufen, geht der Vorgang in den abgeschlossenen Zustand über, und alle wertbasierten Fortsetzungen werden ausgeführt.  
  
> [!CAUTION]
>  Lösen Sie nie `task_canceled` in Ihrem Code aus. Rufen Sie stattdessen `cancel_current_task` auf.  
  
 Wenn eine Aufgabe im abgebrochenen Zustand endet die [Concurrency](reference/task-class.md#get) -Methode löst [Concurrency:: task_canceled](../../parallel/concrt/reference/task-canceled-class.md). (Im Gegensatz dazu [Concurrency:: Task::](reference/task-class.md#wait) gibt [task_status:: Canceled](reference/concurrency-namespace-enums.md#task_group_status) und wird nicht ausgelöst.) Das folgende Beispiel veranschaulicht dieses Verhalten für eine aufgabenbasierte Fortsetzung. Eine aufgabenbasierte Fortsetzung wird immer aufgerufen, auch wenn die Vorgängeraufgabe abgebrochen wurde.  

  
 [!code-cpp[concrt-task-canceled#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_3.cpp)]  
  
 Da wertbasierte Fortsetzungen das Token der Vorgängeraufgabe erben, wenn sie nicht mit einem expliziten Token erstellt wurden, gehen die Fortsetzungen sofort in den abgebrochenen Zustand über, auch wenn die Vorgängeraufgabe noch ausgeführt wird. Daher wird jede Ausnahme, die von der Vorgängeraufgabe nach dem Abbruch ausgelöst wird, nicht an die Fortsetzungsaufgaben weitergegeben. Der Abbruch überschreibt immer den Status der Vorgängeraufgabe. Das folgende Beispiel ähnelt dem vorhergehenden, veranschaulicht jedoch das Verhalten einer wertbasierten Fortsetzung.  
  
 [!code-cpp[concrt-task-canceled#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_4.cpp)]  
  
> [!CAUTION]

>  Wenn Sie kein Abbruchtoken, übergeben die `task` Konstruktor oder die [Concurrency:: create_task](reference/concurrency-namespace-functions.md#create_task) -Funktion, die diese Aufgabe kann nicht abgebrochen werden. Außerdem müssen Sie an den Konstruktor geschachtelter Aufgaben – Aufgaben, die im Text einer anderen Aufgabe erstellt werden – das Abbruchtoken dieser Aufgabe übergeben, um alle Aufgaben gleichzeitig abzubrechen.  
  
 Sie haben die Möglichkeit, beliebigen Code auszuführen, wenn ein Abbruchtoken abgebrochen wird. Wenn der Benutzer wählt z. B. eine **Abbrechen** Schaltfläche auf der Benutzeroberfläche, um den Vorgang abzubrechen, konnte Sie diese Schaltfläche deaktiviert, bis der Benutzer einen anderen Vorgang startet. Das folgende Beispiel zeigt, wie Sie mit der [Concurrency::cancellation_token::register_callback](reference/cancellation-token-class.md#register_callback) Methode, um eine Rückruffunktion zu registrieren, die ausgeführt wird, wenn ein Abbruchtoken abgebrochen wird.  

  
 [!code-cpp[concrt-task-cancellation-callback#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_5.cpp)]  
  
 Das Dokument [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md) wird der Unterschied zwischen wertbasierten und aufgabenbasierten Fortsetzungen erläutert. Wenn Sie kein `cancellation_token`-Objekt für eine Fortsetzungsaufgabe angeben, erbt die Fortsetzung das Abbruchtoken der Vorgängeraufgabe wie folgt:  
  
-   Eine wertbasierte Fortsetzung erbt immer das Abbruchtoken der Vorgängeraufgabe.  
  
-   Eine aufgabenbasierte Fortsetzung erbt dagegen das Abbruchtoken der Vorgängeraufgabe nicht. Die einzige Möglichkeit, eine aufgabenbasierte Fortsetzung abbrechbar zu machen, ist die explizite Übergabe eines Abbruchtokens.  
  
 Diese Verhalten werden nicht durch eine fehlerhafte Aufgabe beeinträchtigt (das heißt, eine Aufgabe, die eine Ausnahme auslöst). Auch in diesem Fall wird eine wertbasierte Fortsetzung abgebrochen, und eine aufgabenbasierte Fortsetzung wird nicht abgebrochen.  
  
> [!CAUTION]
>  Eine Aufgabe, die in einer anderen Aufgabe erstellt wird (das heißt, eine geschachtelte Aufgabe) erbt nicht das Abbruchtoken der übergeordneten Aufgabe. Nur wertbasierte Fortsetzungen erben das Abbruchtoken ihrer Vorgängeraufgabe.  
  
> [!TIP]

>  Verwenden der [Concurrency:: cancellation_token:: none](reference/cancellation-token-class.md#none) Methode, wenn Sie rufen einen Konstruktor oder eine Funktion, die akzeptiert eine `cancellation_token` -Objekt, und Sie möchten nicht den Vorgang abbrechbar ist.  
  
 Sie können auch ein Abbruchtoken für den Konstruktor eines `task_group`- oder `structured_task_group`-Objekts angeben. Ein wichtiger Aspekt hierfür ist, dass die untergeordneten Aufgabengruppen dieses Abbruchtoken erben. Ein Beispiel für die dieses Konzept unter Verwendung der [Concurrency:: run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) Funktion, die zum Aufrufen von `parallel_for`, finden Sie unter [Abbrechen von parallelen Algorithmen](#algorithms) weiter unten in diesem Dokument.  
  
 [[Nach oben](#top)]  
  
#### <a name="cancellation-tokens-and-task-composition"></a>Abbruchtoken und Aufgabenkomposition  

 Die [Concurrency:: HYPERLINK "https://msdn.microsoft.com/library/system.threading.tasks.task.whenall(v=VS.110).aspx" When_all](reference/concurrency-namespace-functions.md#when_all) und [Concurrency:: when_any](reference/concurrency-namespace-functions.md#when_all) Funktionen können Sie die compose-mehrere Aufgaben aus, um allgemeine Muster zu implementieren. In diesem Abschnitt wird beschrieben, wie diese Funktionen mit Abbruchtoken verwendet werden können.  
  
 Wenn ein Abbruchtoken an die `when_all`- oder `when_any`-Funktion übergeben wird, wird diese Funktion nur abgebrochen, wenn dieses Abbruchtoken abgebrochen wird, oder wenn eine der beteiligten Aufgaben in einem abgebrochenen Zustand endet oder eine Ausnahme auslöst.  
  
 Die Funktion `when_all` erbt das Abbruchtoken von jeder Aufgabe, die zum Gesamtvorgang gehört, sofern Sie ihr kein Abbruchtoken übergeben. Die Aufgabe, die von `when_all` zurückgegeben wird, wird abgebrochen, wenn eines der Token abgebrochen wird, und wenn mindestens eine der beteiligten Aufgaben noch nicht gestartet wurde oder ausgeführt wird. Ein ähnliches Verhalten tritt auf, wenn eine der Aufgaben einer Ausnahme: die Aufgabe, die von zurückgegeben wird `when_all` wird mit dieser Ausnahme sofort abgebrochen.  
  
 Die Runtime wählt das Abbruchtoken für die Aufgabe aus, das von der Funktion `when_any` zurückgegeben wird, wenn diese Aufgabe abgeschlossen ist. Wenn keine der beteiligten Aufgaben mit einem abgeschlossenen Zustand beendet wird und mindestens eine der Aufgaben eine Ausnahme auslöst, wird eine der auslösenden Aufgaben ausgewählt, um `when_any` zu beenden, und dessen Token wird als Token für die letzte Aufgabe ausgewählt. Wenn mehr als eine Aufgabe mit einem abgeschlossenen Zustand beendet wird, endet die Aufgabe, die von der Aufgabe `when_any` zurückgegeben wird, mit einem abgeschlossenen Zustand. Die Runtime versucht, eine abgeschlossene Aufgabe auszuwählen, deren Token zum Zeitpunkt des Abschlusses nicht abgebrochen ist, sodass die Aufgabe, die von `when_any` zurückgegeben wird, nicht sofort abgebrochen wird, auch wenn wenn andere ausgeführte Aufgaben möglicherweise zu einem späteren Zeitpunkt abgeschlossen werden.  
  
 [[Nach oben](#top)]  
  
###  <a name="cancel"></a> Mithilfe der Cancel-Methode zum Abbrechen paralleler Aufgaben  

 Die [task_group](reference/task-group-class.md#cancel) und [Concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) Methoden werden eine Aufgabengruppe auf Zustand "abgebrochen" festgelegt. Nach dem Aufruf der `cancel`-Methode startet die Aufgabengruppe keine neuen Aufgaben mehr. Die `cancel`-Methoden können von mehreren untergeordneten Aufgaben aufgerufen werden. Eine abgebrochene Aufgabe bewirkt, dass die [Concurrency:: task_group::](reference/task-group-class.md#wait) und [structured_task_group](reference/structured-task-group-class.md#wait) Methoden zurückgeben [Concurrency:: Canceled](reference/concurrency-namespace-enums.md#task_group_status).  

  
 Wenn eine Aufgabengruppe abgebrochen wird, können Aufrufe von einzelnen untergeordneten Aufgaben in die Laufzeit Auslösen einer *Unterbrechungspunkt*, die bewirkt, dass die Laufzeit auslösen und Abfangen von einer internen Ausnahmetyp zum Abbrechen aktiver Aufgaben. Die Concurrency Runtime definiert keine bestimmten Unterbrechungspunkte. Diese können in jedem Aufruf der Runtime auftreten. Die Runtime muss die ausgelösten Ausnahmen behandeln, um den Abbruch durchzuführen. Behandeln Sie daher keine unbekannten Ausnahmen im Text einer Aufgabe.  
  
 Wenn eine untergeordnete Aufgabe einen zeitaufwändigen Vorgang ausführt und die Runtime nicht aufruft, muss sie regelmäßig nach einem Abbruch suchen und rechtzeitig beendet werden können. Das folgende Beispiel zeigt eine Möglichkeit zur Bestimmung des Abbruchzeitpunkts. Die Aufgabe `t4` bricht die übergeordnete Aufgabengruppe ab, wenn sie auf einen Fehler stößt. Die Aufgabe `t5` ruft regelmäßig die `structured_task_group::is_canceling`-Methode auf, um nach einem Abbruch zu suchen. Wenn die übergeordnete Aufgabengruppe abgebrochen wird, druckt die Aufgabe `t5` eine Meldung und wird beendet.  
  
 [!code-cpp[concrt-task-tree#6](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_6.cpp)]  
  
 In diesem Beispiel wird überprüft, für den Abbruch für je 100<sup>th</sup> Iteration der Aufgabenschleife. Die Häufigkeit, mit der nach einem Abbruch gesucht wird, hängt vom Arbeitsaufwand der Aufgabe ab und davon, wie schnell die Reaktion der Aufgaben auf den Abbruch sein soll.  
  
 Wenn Sie keinen Zugriff auf das übergeordnete Aufgabengruppenobjekt haben, rufen Sie die [Concurrency:: is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling) Funktion, um zu bestimmen, ob die übergeordnete Aufgabengruppe abgebrochen wird.  

  
 Die `cancel`-Methode wird nur auf die jeweils untergeordneten Aufgaben angewendet. Wenn Sie z. B. die Aufgabengruppe `tg1` in der Abbildung der parallelen Arbeitsstruktur abbrechen, sind alle Aufgaben in der Struktur (`t1`, `t2`, `t3`, `t4` und `t5`) betroffen. Wenn Sie die geschachtelte Aufgabengruppe `tg2` abbrechen, sind dagegen nur die Aufgaben `t4` und `t5` betroffen.  
  
 Wenn Sie die `cancel`-Methode aufrufen, werden auch alle untergeordneten Aufgabengruppen abgebrochen. Dies gilt jedoch nicht für die übergeordneten Elemente der Aufgabengruppe in der parallelen Arbeitsstruktur. In den folgenden Beispielen wird dies auf Grundlage der Abbildung der parallelen Arbeitsstruktur veranschaulicht.  
  
 Im ersten Beispiel wird eine Arbeitsfunktion für die Aufgabe `t4` erstellt, die der Arbeitsgruppe `tg2` untergeordnet ist. Die Arbeitsfunktion ruft die Funktion `work` in einer Schleife auf. Wenn ein Aufruf von `work` fehlschlägt, wird die übergeordnete Aufgabengruppe der Aufgabe abgebrochen. Hierdurch geht die Aufgabengruppe `tg2` in den Zustand "abgebrochen" über, die Aufgabengruppe `tg1` wird jedoch nicht abgebrochen.  
  
 [!code-cpp[concrt-task-tree#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_7.cpp)]  
  
 Dieses zweite Beispiel ähnelt dem ersten, mit dem Unterschied, dass die Aufgabe hier die Aufgabengruppe `tg1` abbricht. Dadurch sind alle Aufgaben in der Struktur betroffen (`t1`, `t2`, `t3`, `t4` und `t5`).  
  
 [!code-cpp[concrt-task-tree#3](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_8.cpp)]  
  
 Die `structured_task_group`-Klasse ist nicht threadsicher. Daher erzeugt eine untergeordnete Aufgabe, die eine Methode des übergeordneten `structured_task_group`-Objekts aufruft, ein nicht spezifiziertes Verhalten. Die Ausnahmen von dieser Regel werden die `structured_task_group::cancel` und [is_canceling](reference/structured-task-group-class.md#is_canceling) Methoden. Eine untergeordnete Aufgabe kann diese Methoden aufrufen, um die übergeordnete Aufgabengruppe abzubrechen und auf einen Abbruch zu prüfen.  

 
> [!CAUTION]
>  Sie können zwar ein Abbruchtoken verwenden, um Arbeitsvorgänge einer Aufgabengruppe abzubrechen, die als untergeordnetes Objekt eines `task`-Objekts ausgeführt werden, Sie können jedoch nicht die Methoden `task_group::cancel` oder `structured_task_group::cancel` verwenden, um `task`-Objekte abzubrechen, die in einer Aufgabengruppe ausgeführt werden.  
  
 [[Nach oben](#top)]  
  
###  <a name="exceptions"></a> Verwenden von Ausnahmen zum Abbrechen paralleler Aufgaben  
 Die Verwendung von Abbruchtoken und `cancel`-Methode ist effizienter als die Ausnahmebehandlung beim Abbrechen einer parallelen Arbeitsstruktur. Abbruchtoken und die `cancel`-Methode brechen eine Aufgabe und alle untergeordneten Aufgaben von oben nach unten ab (Top-Down-Ansatz). Bei der Ausnahmebehandlung wird dagegen die umgekehrte Reihenfolge verwendet (Bottom-Up-Ansatz), sodass jede untergeordnete Aufgabengruppe einzeln abgebrochen werden muss. Das Thema [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md) wird erläutert, wie die Concurrency Runtime Ausnahmen Fehler meldet. Nicht alle Ausnahmen geben jedoch einen Fehler an. Ein Suchalgorithmus kann z. B. die zugeordnete Aufgabe abbrechen, wenn das Ergebnis gefunden wurde. Wie jedoch bereits erwähnt ist die Ausnahmebehandlung im Vergleich zur `cancel`-Methode die weniger effiziente Möglichkeit zum Abbrechen paralleler Aufgaben.  
  
> [!CAUTION]
>  Es wird empfohlen, dass Sie nur dann Ausnahmen verwenden, um parallele Arbeit abzubrechen, wenn dies notwendig ist. Abbruchtoken und die `cancel`-Methoden der Aufgabengruppen sind effizienter und weniger fehleranfällig.  
  
 Wenn Sie im Text einer Arbeitsfunktion, die Sie an eine Aufgabengruppe übergeben, eine Ausnahme auslösen, speichert die Runtime diese Ausnahme und marshallt sie an den Kontext, der auf das Beenden der Aufgabengruppe wartet. Wie auch bei der `cancel`-Methode verwirft die Runtime alle Aufgaben, die noch nicht gestartet wurden, und akzeptiert keine neuen Aufgaben.  
  
 Dieses dritte Beispiel ähnelt dem zweiten, mit dem Unterschied, dass die Aufgabe `t4` eine Ausnahme auslöst, um die Aufgabengruppe `tg2` abzubrechen. Dieses Beispiel verwendet eine `try` - `catch` Block, um nach einem Abbruch gesucht Wenn die Aufgabengruppe `tg2` seine untergeordneten Aufgaben wartet. Wie im ersten Beispiel geht die Aufgabengruppe `tg2` in den Zustand "abgebrochen" über, die Aufgabengruppe `tg1` ist jedoch nicht betroffen.  
  
 [!code-cpp[concrt-task-tree#4](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_9.cpp)]  
  
 In diesem vierten Beispiel wird mithilfe der Ausnahmebehandlung die gesamte Arbeitsstruktur abgebrochen. Im Beispiel wird die Ausnahme abgefangen, wenn Aufgabengruppe `tg1` auf das Beenden der untergeordneten Aufgaben wartet, nicht `tg2`. Wie im zweiten Beispiel gehen so beide Aufgabengruppen in der Struktur (`tg1` und `tg2`) in den Zustand "abgebrochenen" über.  
  
 [!code-cpp[concrt-task-tree#5](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_10.cpp)]  
  
 Da die `task_group::wait`-Methode und die `structured_task_group::wait`-Methode ausgelöst werden, wenn eine untergeordnete Aufgabe eine Ausnahme auslöst, geben diese keinen Rückgabewert aus.  
  
 [[Nach oben](#top)]  
  
##  <a name="algorithms"></a> Abbrechen von parallelen Algorithmen  
 Parallele Algorithmen in der PPL, z. B. `parallel_for`, basieren auf Aufgabengruppen. Daher können Sie die meisten Techniken für Aufgabengruppen auch zum Abbrechen paralleler Algorithmen verwenden.  
  
 In den folgenden Beispielen werden mehrere Möglichkeiten zum Abbrechen eines parallelen Algorithmus gezeigt.  
  
 Im folgenden Beispiel wird die `run_with_cancellation_token`-Funktion verwendet, um den `parallel_for`-Algorithmus aufzurufen. Die `run_with_cancellation_token`-Funktion nimmt ein Abbruchtoken als Argument und ruft die bereitgestellte Arbeitsfunktion synchron auf. Da parallele Algorithmen auf Aufgaben basieren, erben sie das Abbruchtoken der übergeordneten Aufgabe. Daher kann `parallel_for` auf den Abbruch reagieren.  
  
 [!code-cpp[concrt-cancel-parallel-for#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_11.cpp)]  
  

 Im folgenden Beispiel wird die [Concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait) aufzurufende Methode der `parallel_for` Algorithmus. Die `structured_task_group::run_and_wait`-Methode wartet auf das Beenden der angegebenen Aufgabe. Das `structured_task_group`-Objekt aktiviert die Arbeitsfunktion zum Abbrechen der Aufgabe.  
  
 [!code-cpp[concrt-task-tree#7](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_12.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
The task group status is: canceled.  
```  
  
 Im folgenden Beispiel wird eine `parallel_for`-Schleife mithilfe der Ausnahmebehandlung abgebrochen. Die Runtime marshallt die Ausnahme an den aufrufenden Kontext.  
  
 [!code-cpp[concrt-task-tree#9](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_13.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
Caught 50  
```  
  
 Im folgenden Beispiel wird der Abbruch in einer `parallel_for`-Schleife mit einem booleschen Flag koordiniert. Jede Aufgabe wird ausgeführt, da in diesem Beispiel nicht die übergeordnete Aufgabengruppe mit der `cancel`-Methode oder mit Ausnahmebehandlung abgebrochen wird. Diese Methode kann daher mehr Rechenleistung erfordern als die anderen Methoden.  
  
 [!code-cpp[concrt-task-tree#8](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_14.cpp)]  
  
 Jede Abbruchmethode hat andere Vorteile. Wählen Sie die Methode, die Ihren Anforderungen am besten entspricht.  
  
 [[Nach oben](#top)]  
  
##  <a name="when"></a> Wenn nicht mit dem Abbrechen  
 Die Verwendung eines Abbruchs ist sinnvoll, wenn jeder Member einer Gruppe zusammenhängender Aufgaben rechtzeitig beendet werden kann. In einigen Fällen ist ein Abbruch jedoch für die Anwendung nicht sinnvoll. Da der Aufgabenabbruch kooperativ ist, wird die übergeordnete Aufgabengruppe beispielsweise nicht abgebrochen, wenn eine einzelne Aufgabe blockiert wird. Wenn z. B. eine Aufgabe, mit der die Blockierung einer anderen aktiven Aufgabe aufgehoben wird, noch nicht gestartet wurde, wird diese bei Abbruch der Aufgabengruppe nicht gestartet. Dies kann zu einem Deadlock-Fehler in der Anwendung führen. Ein Abbruch ist ebenfalls nicht sinnvoll, wenn eine Aufgabe abgebrochen wird, die untergeordnete Aufgabe jedoch einen wichtigen Vorgang, z. B. das Freigeben einer Ressource, ausführt. Da mit dem Abbruch der übergeordneten Aufgabe der gesamte Satz von Aufgaben abgebrochen wird, wird der Vorgang nicht ausgeführt. Ein Beispiel dieser Punkt veranschaulicht wird, finden Sie unter den [verstehen wie Abbruch und Ausnahmebehandlung beeinflussen Objekt auf die Zerstörung](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) Abschnitt in die bewährten Methoden in der Parallel Patterns Library-Thema.  
  
 [[Nach oben](#top)]  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Vorgehensweise: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)|Zeigt, wie mit dem Abbrechen ein paralleler Suchalgorithmus implementiert wird.|  
|[Vorgehensweise: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel-Schleife](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|Zeigt, wie mit der `task_group`-Klasse ein Suchalgorithmus für eine einfache Baumstruktur geschrieben wird.|  
|[Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Beschreibt, wie die Runtime Ausnahmen behandelt, die von Aufgabengruppen, einfachen Aufgaben und asynchronen Agents ausgelöst werden, und wie in Anwendungen auf Ausnahmen reagiert wird.|  
|[Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Beschreibt, wie sich Aufgaben und Aufgabengruppen zueinander verhalten und wie Sie unstrukturierte und strukturierte Parallelität in Ihren Anwendungen verwenden können.|  
|[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)|Beschreibt die parallelen Algorithmen, die Auflistungen von Daten gleichzeitig verarbeiten.|  
|[Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Eine Übersicht über die Parallel Patterns Library.|  
  
## <a name="reference"></a>Referenz  
 [task-Klasse (Concurrency Runtime)](../../parallel/concrt/reference/task-class.md)  
  
 [cancellation_token_source-Klasse](../../parallel/concrt/reference/cancellation-token-source-class.md)  
  
 [cancellation_token-Klasse](../../parallel/concrt/reference/cancellation-token-class.md)  
  
 [Task_group-Klasse](reference/task-group-class.md)  
  
 [structured_task_group-Klasse](../../parallel/concrt/reference/structured-task-group-class.md)  

 [Parallel_for-Funktion](reference/concurrency-namespace-functions.md#parallel_for)


