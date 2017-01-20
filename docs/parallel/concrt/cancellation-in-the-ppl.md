---
title: "Abbruch in der PPL"
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
  - "Abbrechen paralleler Algorithmen [Concurrency Runtime]"
  - "Abbrechen paralleler Aufgaben [Concurrency Runtime]"
  - "Abbruch in der PPL"
  - "Parallele Algorithmen, Abbrechen [Concurrency Runtime]"
  - "Parallele Aufgaben, Abbrechen [Concurrency Runtime]"
  - "Parallele Arbeitsstrukturen [Concurrency Runtime]"
ms.assetid: baaef417-b2f9-470e-b8bd-9ed890725b35
caps.latest.revision: 31
caps.handback.revision: "28"
ms.author: "mblome"
manager: "ghogen"
---
# Abbruch in der PPL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument wird die Rolle des Abbruchs in der Parallel Patterns Library \(PPL\) erläutert und beschrieben, wie Sie die parallele Arbeitsvorgänge abbrechen, und wie Sie erkennen können, ob parallele Arbeitsvorgänge abgebrochen wurden.  
  
> [!NOTE]
>  Die Laufzeit implementiert Abbrüche mithilfe der Ausnahmebehandlung.  Diese Ausnahmen dürfen im eigenen Code nicht abgefangen oder behandelt werden.  Außerdem empfiehlt es sich, ausnahmesicheren Code in den Funktionsrümpfen der Aufgaben zu schreiben.  Zum Beispiel können Sie das RAII \(*Resource Acquisition Is Initialization*\)\-Muster verwenden, um sicherzustellen, dass Ressourcen ordnungsgemäß behandelt werden, wenn eine Ausnahme im Rumpf einer Aufgabe ausgelöst wird.  Ein vollständiges Beispiel, in dem das RAII\-Muster verwendet wird, um in einer abbrechbaren Aufgabe eine Ressource zu bereinigen, finden Sie unter [Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md).  
  
## Wesentliche Punkte  
  
-   Das Abbrechen ist ein kooperativer Vorgang und beinhaltet die Koordination zwischen dem Code, der den Abbruch verlangt, und der Aufgabe, die auf den Abbruch reagieren muss.  
  
-   Verwenden Sie wenn möglich Abbruchtoken, um Arbeitsvorgänge abzubrechen.  Die [concurrency::cancellation\_token](../../parallel/concrt/reference/cancellation-token-class.md)\-Klasse definiert ein Abbruchtoken.  
  
-   Verwenden Sie mit den Abbruchtoken die [concurrency::cancellation\_token\_source::cancel](../Topic/cancellation_token_source::cancel%20Method.md)\-Methode, um den Abbruch zu initiieren, und die Funktion [concurrency::cancel\_current\_task](../Topic/cancel_current_task%20Function.md), um auf den Abbruch zu reagieren.  
  
-   Der Abbruch erfolgt nicht unmittelbar.  Es werden zwar keine neuen Arbeitsvorgänge gestartet, wenn eine Aufgabe oder eine Aufgabengruppe abgebrochen wird, aktive Arbeitsvorgänge müssen den Abbruch aber überprüfen und auf diesen reagieren.  
  
-   Eine wertbasierte Fortsetzung erbt das Abbruchtoken ihrer Vorgängeraufgabe.  Eine aufgabenbasierte Fortsetzung erbt das Token der Vorgängeraufgabe dagegen nicht.  
  
-   Verwenden Sie die [concurrency::cancellation\_token::none](../Topic/cancellation_token::none%20Method.md)\-Methode, wenn Sie einen Konstruktor oder eine Funktion aufrufen, der bzw. die ein `cancellation_token`\-Objekt akzeptiert, Sie aber nicht möchten, dass der Vorgang abbrechbar ist.  Wenn Sie kein Abbruchtoken an den [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md)\-Konstruktor oder die [concurrency::create\_task](../Topic/create_task%20Function.md)\-Funktion übergeben, ist diese Aufgabe ebenfalls nicht abbrechbar.  
  
##  <a name="top"></a> In diesem Dokument  
  
-   [Parallele Arbeitsstrukturen](#trees)  
  
-   [Abbrechen von parallelen Aufgaben](#tasks)  
  
    -   [Verwenden eines Abbruchtokens zum Abbrechen paralleler Aufgaben](#tokens)  
  
    -   [Abbrechen paralleler Aufgaben mit der cancel\-Methode](#cancel)  
  
    -   [Abbrechen paralleler Aufgaben mit Ausnahmen](#exceptions)  
  
-   [Abbrechen von parallelen Algorithmen](#algorithms)  
  
-   [Wann ein Abbruch nicht verwendet werden sollte](#when)  
  
##  <a name="trees"></a> Parallele Arbeitsstrukturen  
 Differenzierte Aufgaben und Berechnungen werden in der PPL mithilfe von Aufgaben und Aufgabengruppen verwaltet.  Sie können Aufgabengruppen schachteln, um *Strukturen* paralleler Arbeitsvorgänge zu bilden.  Die folgende Abbildung zeigt eine parallele Arbeitsstruktur.  In dieser Abbildung stellen `tg1` und `tg2` Aufgabengruppen dar; `t1`, `t2`, `t3`, `t4` und `t5` stellen die Arbeitsvorgänge dar, die von den Aufgabengruppen durchgeführt wird.  
  
 ![Parallele Arbeitsstruktur](../../parallel/concrt/media/parallelwork_trees.png "ParallelWork\_Trees")  
  
 Das folgende Beispiel zeigt den Code, der zum Erstellen der Struktur in der Abbildung erforderlich ist.  `tg1` und `tg2` sind in diesem Beispiel [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md)\-Objekte, und `t1`, `t2`, `t3`, `t4` und `t5` sind [concurrency::task\_handle](../../parallel/concrt/reference/task-handle-class.md)\-Objekte.  
  
 [!CODE [concrt-task-tree#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree#1)]  
  
 Sie können die [concurrency::task\_group](../Topic/task_group%20Class.md)\-Klasse verwenden, um eine ähnliche Arbeitsstruktur zu erstellen.  Die [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md)\-Klasse unterstützt auch das Konzept einer Arbeitsstruktur.  Eine `task`\-Struktur ist jedoch eine Abhängigkeitsstruktur.  In einer `task`\-Struktur werden zukünftige Arbeitsvorgänge nach aktuellen Arbeitsvorgängen abgeschlossen.  In einer Aufgabengruppenstruktur werden interne Arbeitsvorgänge vor externen Arbeitsvorgängen abgeschlossen.  Weitere Informationen über die Unterschiede zwischen Aufgaben und Aufgabengruppen finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="tasks"></a> Abbrechen von parallelen Aufgaben  
 Es gibt verschiedene Möglichkeiten, parallele Arbeitsvorgänge abzubrechen.  Die bevorzugte Methode ist, ein Abbruchtoken zu verwenden.  Aufgabengruppen unterstützen auch die [concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md)\- und die [concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md)\-Methode.  Eine letzte Möglichkeit ist, im Text einer Arbeitsfunktion eine Ausnahme auszulösen.  Unabhängig von der gewählten Methode sollten Sie bedenken, dass der Abbruch nicht sofort auftritt.  Es werden zwar keine neuen Arbeitsvorgänge gestartet, wenn eine Aufgabe oder eine Aufgabengruppe abgebrochen wird, aktive Arbeitsvorgänge müssen den Abbruch aber überprüfen und auf diesen reagieren.  
  
 Weitere Beispiele zum Abbrechen paralleler Aufgaben finden Sie unter [Exemplarische Vorgehensweise: Verbinden von Verwendungsaufgaben und XML\-HTTP\-Anforderungen](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md), [Gewusst wie: Verwenden eines Abbruchs zum Verlassen einer Parallel\-Schleife](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md) und [Gewusst wie: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel\-Schleife](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).  
  
###  <a name="tokens"></a> Verwenden eines Abbruchtokens zum Abbrechen paralleler Aufgaben  
 Die Klassen `task`, `task_group` und `structured_task_group` unterstützen Abbruchvorgänge durch die Verwendung von Abbruchtoken.  Die PPL definiert die [concurrency::cancellation\_token\_source](../../parallel/concrt/reference/cancellation-token-source-class.md)\- und [concurrency::cancellation\_token](../../parallel/concrt/reference/cancellation-token-class.md)\-Klasse zu diesem Zweck.  Wenn Sie Arbeit mithilfe eines Abbruchtokens abbrechen, wird von der Runtime keine neue Verarbeitung gestartet, die dieses Token abonniert.  Für eine bereits aktive Verarbeitung kann das entsprechende Abbruchtoken überwacht und die Verarbeitung zum angegebenen Zeitpunkt beendet werden.  
  
 Um den Abbruch zu initiieren, rufen Sie die [concurrency::cancellation\_token\_source::cancel](../Topic/cancellation_token_source::cancel%20Method.md)\-Methode auf.  Auf Abbrüche reagieren Sie folgendermaßen:  
  
-   Verwenden Sie für `task`\-Objekte die [concurrency::cancel\_current\_task](../Topic/cancel_current_task%20Function.md)\-Funktion.  `cancel_current_task` bricht die aktuelle Aufgabe und alle wertbasierten Fortsetzungen ab.  \(Es wird nicht das *Abbruchtoken* abgebrochen, das der Aufgabe bzw. seinen Fortsetzungen zugeordnet ist.\)  
  
-   Bei Aufgabengruppen und parallelen Algorithmen verwenden Sie die Funktion [concurrency::is\_current\_task\_group\_canceling](../Topic/is_current_task_group_canceling%20Function.md), um den Abbruch zu erkennen und so schnell wie möglich vom Aufgabentext zurückzukehren, wenn diese Funktion `true` zurückgibt.  \(Verwenden Sie bei Aufgabengruppen nicht `cancel_current_task`.\)  
  
 Das folgende Beispiel zeigt das erste grundlegende Muster für den Aufgabenabbruch.  Der Aufgabentext überprüft die Schleife von Zeit zu Zeit auf Abbrüche.  
  
 [!CODE [concrt-task-basic-cancellation#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-basic-cancellation#1)]  
  
 Die `cancel_current_task`\-Funktion löst eine Ausnahme aus; daher müssen Sie nicht explizit von der aktuellen Schleife oder Funktion zurückkehren.  
  
> [!TIP]
>  Alternativ können Sie die [concurrency::interruption\_point](../Topic/interruption_point%20Function.md)\-Funktion anstelle von `cancel_current_task` aufrufen.  
  
 Es ist wichtig, `cancel_current_task` als Reaktion auf einen Abbruch aufzurufen, da die Aufgabe dadurch in den abgebrochenen Zustand übergeht.  Wenn Sie zu früh zurückkehren, anstatt `cancel_current_task` aufzurufen, geht der Vorgang in den abgeschlossenen Zustand über, und alle wertbasierten Fortsetzungen werden ausgeführt.  
  
> [!CAUTION]
>  Lösen Sie nie `task_canceled` in Ihrem Code aus.  Rufen Sie stattdessen `cancel_current_task` auf.  
  
 Wenn diese Aufgabe im abgebrochenen Zustand endet, löst die [concurrency::task::get](../Topic/task::get%20Method.md)\-Methode [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md) aus.  \(Umgekehrt gibt [concurrency::task::wait](../Topic/task::wait%20Method.md) den Status [task\_status::canceled](../Topic/task_group_status%20Enumeration.md) zurück und löst nichts aus.\) Das folgende Beispiel veranschaulicht dieses Verhalten für eine aufgabenbasierte Fortsetzung.  Eine aufgabenbasierte Fortsetzung wird immer aufgerufen, auch wenn die Vorgängeraufgabe abgebrochen wurde.  
  
 [!CODE [concrt-task-canceled#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-canceled#1)]  
  
 Da wertbasierte Fortsetzungen das Token der Vorgängeraufgabe erben, wenn sie nicht mit einem expliziten Token erstellt wurden, gehen die Fortsetzungen sofort in den abgebrochenen Zustand über, auch wenn die Vorgängeraufgabe noch ausgeführt wird.  Daher wird jede Ausnahme, die von der Vorgängeraufgabe nach dem Abbruch ausgelöst wird, nicht an die Fortsetzungsaufgaben weitergegeben.  Der Abbruch überschreibt immer den Status der Vorgängeraufgabe.  Das folgende Beispiel ähnelt dem vorhergehenden, veranschaulicht jedoch das Verhalten einer wertbasierten Fortsetzung.  
  
 [!CODE [concrt-task-canceled#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-canceled#2)]  
  
> [!CAUTION]
>  Wenn Sie kein Abbruchtoken an den `task`\-Konstruktor oder die [concurrency::create\_task\-Funktion](../Topic/create_task%20Function.md) übergeben, ist diese Aufgabe nicht abbrechbar.  Außerdem müssen Sie an den Konstruktor geschachtelter Aufgaben – Aufgaben, die im Text einer anderen Aufgabe erstellt werden – das Abbruchtoken dieser Aufgabe übergeben, um alle Aufgaben gleichzeitig abzubrechen.  
  
 Sie haben die Möglichkeit, beliebigen Code auszuführen, wenn ein Abbruchtoken abgebrochen wird.  Wenn Benutzer zum Beispiel zum Abbrechen auf eine **Abbrechen**\-Schaltfläche klicken müssen, können Sie diese so lange deaktivieren, bis der Benutzer einen anderen Vorgang startet.  Das folgende Beispiel zeigt, wie die [concurrency::cancellation\_token::register\_callback](../Topic/cancellation_token::register_callback%20Method.md)\-Methode verwendet wird, um eine Rückruffunktion zu registrieren, die ausgeführt wird, wenn ein Abbruchtoken abgebrochen wird.  
  
 [!CODE [concrt-task-cancellation-callback#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-cancellation-callback#1)]  
  
 Im Dokument [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md) wird der Unterschied zwischen wertbasierten und aufgabenbasierten Fortsetzungen erläutert.  Wenn Sie kein `cancellation_token`\-Objekt für eine Fortsetzungsaufgabe angeben, erbt die Fortsetzung das Abbruchtoken der Vorgängeraufgabe wie folgt:  
  
-   Eine wertbasierte Fortsetzung erbt immer das Abbruchtoken der Vorgängeraufgabe.  
  
-   Eine aufgabenbasierte Fortsetzung erbt dagegen das Abbruchtoken der Vorgängeraufgabe nicht.  Die einzige Möglichkeit, eine aufgabenbasierte Fortsetzung abbrechbar zu machen, ist die explizite Übergabe eines Abbruchtokens.  
  
 Diese Verhalten werden nicht durch eine fehlerhafte Aufgabe beeinträchtigt \(das heißt, eine Aufgabe, die eine Ausnahme auslöst\).  Auch in diesem Fall wird eine wertbasierte Fortsetzung abgebrochen, und eine aufgabenbasierte Fortsetzung wird nicht abgebrochen.  
  
> [!CAUTION]
>  Eine Aufgabe, die in einer anderen Aufgabe erstellt wird \(das heißt, eine geschachtelte Aufgabe\) erbt nicht das Abbruchtoken der übergeordneten Aufgabe.  Nur wertbasierte Fortsetzungen erben das Abbruchtoken ihrer Vorgängeraufgabe.  
  
> [!TIP]
>  Verwenden Sie die [concurrency::cancellation\_token::none](../Topic/cancellation_token::none%20Method.md)\-Methode, wenn Sie einen Konstruktor oder eine Funktion aufrufen, der bzw. die ein `cancellation_token`\-Objekt akzeptiert, und Sie nicht möchten, dass der Vorgang abbrechbar ist.  
  
 Sie können auch ein Abbruchtoken für den Konstruktor eines `task_group`\- oder `structured_task_group`\-Objekts angeben.  Ein wichtiger Aspekt hierfür ist, dass die untergeordneten Aufgabengruppen dieses Abbruchtoken erben.  Ein Beispiel für dieses Konzept, bei dem die [concurrency::run\_with\_cancellation\_token](../Topic/run_with_cancellation_token%20Function.md)\-Funktion verwendet wird, um `parallel_for` aufzurufen, finden Sie unter [Abbrechen von parallelen Algorithmen](#algorithms) weiter unten in diesem Dokument.  
  
 \[[Nach oben](#top)\]  
  
#### Abbruchtoken und Aufgabenkomposition  
 Mit den [concurrency::when\_all](../Topic/when_all%20Function.md)\- und [concurrency::when\_any](../Topic/when_all%20Function.md)\-Funktionen können Sie mehrere Aufgaben zusammenstellen, um allgemeine Muster zu implementieren.  In diesem Abschnitt wird beschrieben, wie diese Funktionen mit Abbruchtoken verwendet werden können.  
  
 Wenn ein Abbruchtoken an die `when_all`\- oder `when_any`\-Funktion übergeben wird, wird diese Funktion nur abgebrochen, wenn dieses Abbruchtoken abgebrochen wird, oder wenn eine der beteiligten Aufgaben in einem abgebrochenen Zustand endet oder eine Ausnahme auslöst.  
  
 Die Funktion `when_all` erbt das Abbruchtoken von jeder Aufgabe, die zum Gesamtvorgang gehört, sofern Sie ihr kein Abbruchtoken übergeben.  Die Aufgabe, die von `when_all` zurückgegeben wird, wird abgebrochen, wenn eines der Token abgebrochen wird, und wenn mindestens eine der beteiligten Aufgaben noch nicht gestartet wurde oder ausgeführt wird.  Ein ähnliches Verhalten tritt auf, wenn eine der Aufgaben eine Ausnahme auslöst – die Aufgabe, die von `when_all` zurückgegeben wird, wird sofort mit dieser Ausnahme abgebrochen.  
  
 Die Runtime wählt das Abbruchtoken für die Aufgabe aus, das von der Funktion `when_any` zurückgegeben wird, wenn diese Aufgabe abgeschlossen ist.  Wenn keine der beteiligten Aufgaben mit einem abgeschlossenen Zustand beendet wird und mindestens eine der Aufgaben eine Ausnahme auslöst, wird eine der auslösenden Aufgaben ausgewählt, um `when_any` zu beenden, und dessen Token wird als Token für die letzte Aufgabe ausgewählt.  Wenn mehr als eine Aufgabe mit einem abgeschlossenen Zustand beendet wird, endet die Aufgabe, die von der Aufgabe `when_any` zurückgegeben wird, mit einem abgeschlossenen Zustand.  Die Runtime versucht, eine abgeschlossene Aufgabe auszuwählen, deren Token zum Zeitpunkt des Abschlusses nicht abgebrochen ist, sodass die Aufgabe, die von `when_any` zurückgegeben wird, nicht sofort abgebrochen wird, auch wenn wenn andere ausgeführte Aufgaben möglicherweise zu einem späteren Zeitpunkt abgeschlossen werden.  
  
 \[[Nach oben](#top)\]  
  
###  <a name="cancel"></a> Abbrechen paralleler Aufgaben mit der cancel\-Methode  
 Mit den Methoden [concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md) und [concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md) wird der Zustand der Aufgabengruppe auf "Abgebrochen" festgelegt.  Nach dem Aufruf der `cancel`\-Methode startet die Aufgabengruppe keine neuen Aufgaben mehr.  Die `cancel`\-Methoden können von mehreren untergeordneten Aufgaben aufgerufen werden.  Wenn eine Aufgabe abgebrochen wurde, geben die [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md)\-Methode und die [concurrency::structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md)\-Methode [concurrency::canceled](../Topic/task_group_status%20Enumeration.md) zurück.  
  
 Wenn eine Aufgabengruppe abgebrochen wird, kann jeder Laufzeitaufruf durch eine untergeordnete Aufgabe einen *Unterbrechungspunkt* auslösen, der die Runtime veranlasst, einen internen Ausnahmetyp zum Abbrechen aktiver Aufgaben auszulösen und abzufangen.  Die Concurrency Runtime definiert keine bestimmten Unterbrechungspunkte. Diese können in jedem Aufruf der Runtime auftreten.  Die Runtime muss die ausgelösten Ausnahmen behandeln, um den Abbruch durchzuführen.  Behandeln Sie daher keine unbekannten Ausnahmen im Text einer Aufgabe.  
  
 Wenn eine untergeordnete Aufgabe einen zeitaufwändigen Vorgang ausführt und die Runtime nicht aufruft, muss sie regelmäßig nach einem Abbruch suchen und rechtzeitig beendet werden können.  Das folgende Beispiel zeigt eine Möglichkeit zur Bestimmung des Abbruchzeitpunkts.  Die Aufgabe `t4` bricht die übergeordnete Aufgabengruppe ab, wenn sie auf einen Fehler stößt.  Die Aufgabe `t5` ruft regelmäßig die `structured_task_group::is_canceling`\-Methode auf, um nach einem Abbruch zu suchen.  Wenn die übergeordnete Aufgabengruppe abgebrochen wird, druckt die Aufgabe `t5` eine Meldung und wird beendet.  
  
 [!CODE [concrt-task-tree#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree#6)]  
  
 In diesem Beispiel wird bei jedem hundertsten Durchlauf der Aufgabenschleife nach einem Abbruchvorgang gesucht.  Die Häufigkeit, mit der nach einem Abbruch gesucht wird, hängt vom Arbeitsaufwand der Aufgabe ab und davon, wie schnell die Reaktion der Aufgaben auf den Abbruch sein soll.  
  
 Wenn Sie keinen Zugriff auf das übergeordnete Aufgabengruppenobjekt haben, rufen Sie die [concurrency::is\_current\_task\_group\_canceling](../Topic/is_current_task_group_canceling%20Function.md)\-Funktion auf, um zu ermitteln, ob die übergeordnete Aufgabengruppe abgebrochen wird.  
  
 Die `cancel`\-Methode wird nur auf die jeweils untergeordneten Aufgaben angewendet.  Wenn Sie z. B. die Aufgabengruppe `tg1` in der Abbildung der parallelen Arbeitsstruktur abbrechen, sind alle Aufgaben in der Struktur \(`t1`, `t2`, `t3`, `t4` und `t5`\) betroffen.  Wenn Sie die geschachtelte Aufgabengruppe `tg2` abbrechen, sind dagegen nur die Aufgaben `t4` und `t5` betroffen.  
  
 Wenn Sie die `cancel`\-Methode aufrufen, werden auch alle untergeordneten Aufgabengruppen abgebrochen.  Dies gilt jedoch nicht für die übergeordneten Elemente der Aufgabengruppe in der parallelen Arbeitsstruktur.  In den folgenden Beispielen wird dies auf Grundlage der Abbildung oben veranschaulicht.  
  
 Im ersten Beispiel wird eine Arbeitsfunktion für die Aufgabe `t4` erstellt, die der Arbeitsgruppe `tg2` untergeordnet ist.  Die Arbeitsfunktion ruft die Funktion `work` in einer Schleife auf.  Wenn ein Aufruf von `work` fehlschlägt, wird die übergeordnete Aufgabengruppe der Aufgabe abgebrochen.  Hierdurch geht die Aufgabengruppe `tg2` in den Zustand "abgebrochen" über, die Aufgabengruppe `tg1` wird jedoch nicht abgebrochen.  
  
 [!CODE [concrt-task-tree#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree#2)]  
  
 Dieses zweite Beispiel ähnelt dem ersten, mit dem Unterschied, dass die Aufgabe hier die Aufgabengruppe `tg1` abbricht.  Dadurch sind alle Aufgaben in der Struktur betroffen \(`t1`, `t2`, `t3`, `t4` und `t5`\).  
  
 [!CODE [concrt-task-tree#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree#3)]  
  
 Die `structured_task_group`\-Klasse ist nicht threadsicher.  Daher erzeugt eine untergeordnete Aufgabe, die eine Methode des übergeordneten `structured_task_group`\-Objekts aufruft, ein nicht spezifiziertes Verhalten.  Die `structured_task_group::cancel`\-Methode und die [concurrency::structured\_task\_group::is\_canceling](../Topic/structured_task_group::is_canceling%20Method.md)\-Methode sind Ausnahmen von dieser Regel.  Eine untergeordnete Aufgabe kann diese Methoden aufrufen, um die übergeordnete Aufgabengruppe abzubrechen und auf einen Abbruch zu prüfen.  
  
> [!CAUTION]
>  Sie können zwar ein Abbruchtoken verwenden, um Arbeitsvorgänge einer Aufgabengruppe abzubrechen, die als untergeordnetes Objekt eines `task`\-Objekts ausgeführt werden, Sie können jedoch nicht die Methoden `task_group::cancel` oder `structured_task_group::cancel` verwenden, um `task`\-Objekte abzubrechen, die in einer Aufgabengruppe ausgeführt werden.  
  
 \[[Nach oben](#top)\]  
  
###  <a name="exceptions"></a> Abbrechen paralleler Aufgaben mit Ausnahmen  
 Die Verwendung von Abbruchtoken und `cancel`\-Methode ist effizienter als die Ausnahmebehandlung beim Abbrechen einer parallelen Arbeitsstruktur.  Abbruchtoken und die `cancel`\-Methode brechen eine Aufgabe und alle untergeordneten Aufgaben von oben nach unten ab \(Top\-Down\-Ansatz\).  Bei der Ausnahmebehandlung wird dagegen die umgekehrte Reihenfolge verwendet \(Bottom\-Up\-Ansatz\), sodass jede untergeordnete Aufgabengruppe einzeln abgebrochen werden muss.  Im Thema [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md) wird erläutert, wie die Concurrency Runtime über Ausnahmen Fehler meldet.  Nicht alle Ausnahmen geben jedoch einen Fehler an.  Ein Suchalgorithmus kann z. B. die zugeordnete Aufgabe abbrechen, wenn das Ergebnis gefunden wurde.  Wie jedoch bereits erwähnt ist die Ausnahmebehandlung im Vergleich zur `cancel`\-Methode die weniger effiziente Möglichkeit zum Abbrechen paralleler Aufgaben.  
  
> [!CAUTION]
>  Es wird empfohlen, dass Sie nur dann Ausnahmen verwenden, um parallele Arbeit abzubrechen, wenn dies notwendig ist.  Abbruchtoken und die `cancel`\-Methoden der Aufgabengruppen sind effizienter und weniger fehleranfällig.  
  
 Wenn Sie im Text einer Arbeitsfunktion, die Sie an eine Aufgabengruppe übergeben, eine Ausnahme auslösen, speichert die Runtime diese Ausnahme und marshallt sie an den Kontext, der auf das Beenden der Aufgabengruppe wartet.  Wie auch bei der `cancel`\-Methode verwirft die Runtime alle Aufgaben, die noch nicht gestartet wurden, und akzeptiert keine neuen Aufgaben.  
  
 Dieses dritte Beispiel ähnelt dem zweiten, mit dem Unterschied, dass die Aufgabe `t4` eine Ausnahme auslöst, um die Aufgabengruppe `tg2` abzubrechen.  In diesem Beispiel wird ein `try`\-`catch`\-Block verwendet, um nach einem Abbruch zu suchen, wenn die Aufgabengruppe `tg2` auf das Beenden der untergeordneten Aufgaben wartet.  Wie im ersten Beispiel geht die Aufgabengruppe `tg2` in den Zustand "abgebrochen" über, die Aufgabengruppe `tg1` ist jedoch nicht betroffen.  
  
 [!CODE [concrt-task-tree#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree#4)]  
  
 In diesem vierten Beispiel wird mithilfe der Ausnahmebehandlung die gesamte Arbeitsstruktur abgebrochen.  Im Beispiel wird die Ausnahme abgefangen, wenn Aufgabengruppe `tg1` auf das Beenden der untergeordneten Aufgaben wartet, nicht `tg2`.  Wie im zweiten Beispiel gehen so beide Aufgabengruppen in der Struktur \(`tg1` und `tg2`\) in den Zustand "abgebrochenen" über.  
  
 [!CODE [concrt-task-tree#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree#5)]  
  
 Da die `task_group::wait`\-Methode und die `structured_task_group::wait`\-Methode ausgelöst werden, wenn eine untergeordnete Aufgabe eine Ausnahme auslöst, geben diese keinen Rückgabewert aus.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="algorithms"></a> Abbrechen von parallelen Algorithmen  
 Parallele Algorithmen in der PPL, z. B. `parallel_for`, basieren auf Aufgabengruppen.  Daher können Sie die meisten Techniken für Aufgabengruppen auch zum Abbrechen paralleler Algorithmen verwenden.  
  
 In den folgenden Beispielen werden mehrere Möglichkeiten zum Abbrechen eines parallelen Algorithmus gezeigt.  
  
 Im folgenden Beispiel wird die `run_with_cancellation_token`\-Funktion verwendet, um den `parallel_for`\-Algorithmus aufzurufen.  Die `run_with_cancellation_token`\-Funktion nimmt ein Abbruchtoken als Argument und ruft die bereitgestellte Arbeitsfunktion synchron auf.  Da parallele Algorithmen auf Aufgaben basieren, erben sie das Abbruchtoken der übergeordneten Aufgabe.  Daher kann `parallel_for` auf den Abbruch reagieren.  
  
 [!CODE [concrt-cancel-parallel-for#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-cancel-parallel-for#1)]  
  
 Im folgenden Beispiel wird die [concurrency::structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md)\-Methode verwendet, um den `parallel_for`\-Algorithmus aufzurufen.  Die `structured_task_group::run_and_wait`\-Methode wartet auf das Beenden der angegebenen Aufgabe.  Das `structured_task_group`\-Objekt aktiviert die Arbeitsfunktion zum Abbrechen der Aufgabe.  
  
 [!CODE [concrt-task-tree#7](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree#7)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **The task group status is: canceled.** Im folgenden Beispiel wird eine `parallel_for`\-Schleife mithilfe der Ausnahmebehandlung abgebrochen.  Die Runtime marshallt die Ausnahme an den aufrufenden Kontext.  
  
 [!CODE [concrt-task-tree#9](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree#9)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **Caught 50** Im folgenden Beispiel wird der Abbruch in einer `parallel_for`\-Schleife mit einem booleschen Flag koordiniert.  Jede Aufgabe wird ausgeführt, da in diesem Beispiel nicht die übergeordnete Aufgabengruppe mit der `cancel`\-Methode oder mit Ausnahmebehandlung abgebrochen wird.  Diese Methode kann daher mehr Rechenleistung erfordern als die anderen Methoden.  
  
 [!CODE [concrt-task-tree#8](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree#8)]  
  
 Jede Abbruchmethode hat andere Vorteile.  Wählen Sie die Methode, die Ihren Anforderungen am besten entspricht.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="when"></a> Wann ein Abbruch nicht verwendet werden sollte  
 Die Verwendung eines Abbruchs ist sinnvoll, wenn jeder Member einer Gruppe zusammenhängender Aufgaben rechtzeitig beendet werden kann.  In einigen Fällen ist ein Abbruch jedoch für die Anwendung nicht sinnvoll.  Da der Aufgabenabbruch kooperativ ist, wird die übergeordnete Aufgabengruppe beispielsweise nicht abgebrochen, wenn eine einzelne Aufgabe blockiert wird.  Wenn z. B. eine Aufgabe, mit der die Blockierung einer anderen aktiven Aufgabe aufgehoben wird, noch nicht gestartet wurde, wird diese bei Abbruch der Aufgabengruppe nicht gestartet.  Dies kann zu einem Deadlock\-Fehler in der Anwendung führen.  Ein Abbruch ist ebenfalls nicht sinnvoll, wenn eine Aufgabe abgebrochen wird, die untergeordnete Aufgabe jedoch einen wichtigen Vorgang, z. B. das Freigeben einer Ressource, ausführt.  Da mit dem Abbruch der übergeordneten Aufgabe der gesamte Satz von Aufgaben abgebrochen wird, wird der Vorgang nicht ausgeführt.  Ein Beispiel, in dem dieser Punkt veranschaulicht wird, finden Sie im Abschnitt [Verstehen, wie sich Abbruch und Ausnahmebehandlung auf die Objektlöschung auswirken](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) der empfohlenen Vorgehensweisen im Dokument zur Parallel Patterns Library.  
  
 \[[Nach oben](#top)\]  
  
## Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[Gewusst wie: Verwenden eines Abbruchs zum Verlassen einer Parallel\-Schleife](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)|Zeigt, wie mit dem Abbrechen ein paralleler Suchalgorithmus implementiert wird.|  
|[Gewusst wie: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel\-Schleife](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|Zeigt, wie mit der `task_group`\-Klasse ein Suchalgorithmus für eine einfache Baumstruktur geschrieben wird.|  
|[Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Beschreibt, wie die Runtime Ausnahmen behandelt, die von Aufgabengruppen, einfachen Aufgaben und asynchronen Agents ausgelöst werden, und wie in Anwendungen auf Ausnahmen reagiert wird.|  
|[Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Beschreibt, wie sich Aufgaben und Aufgabengruppen zueinander verhalten und wie Sie unstrukturierte und strukturierte Parallelität in Ihren Anwendungen verwenden können.|  
|[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)|Beschreibt die parallelen Algorithmen, die Auflistungen von Daten gleichzeitig verarbeiten.|  
|[Parallel Patterns Library \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Eine Übersicht über die Parallel Patterns Library.|  
  
## Verweis  
 [task\-Klasse \(Concurrency Runtime\)](../../parallel/concrt/reference/task-class-concurrency-runtime.md)  
  
 [cancellation\_token\_source\-Klasse](../../parallel/concrt/reference/cancellation-token-source-class.md)  
  
 [cancellation\_token\-Klasse](../../parallel/concrt/reference/cancellation-token-class.md)  
  
 [task\_group\-Klasse](../Topic/task_group%20Class.md)  
  
 [structured\_task\_group\-Klasse](../../parallel/concrt/reference/structured-task-group-class.md)  
  
 [parallel\_for\-Funktion](../Topic/parallel_for%20Function.md)