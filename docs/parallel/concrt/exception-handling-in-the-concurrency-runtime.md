---
title: "Ausnahmebehandlung in der Concurrency Runtime"
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
  - "Einfache Aufgaben, Ausnahmebehandlung [Concurrency Runtime]"
  - "Ausnahmebehandlung [Concurrency Runtime]"
  - "Strukturierte Aufgabengruppen, Ausnahmebehandlung [Concurrency Runtime]"
  - "Agents, Ausnahmebehandlung [Concurrency Runtime]"
  - "Aufgabengruppen, Ausnahmebehandlung [Concurrency Runtime]"
ms.assetid: 4d1494fb-3089-4f4b-8cfb-712aa67d7a7a
caps.latest.revision: 29
caps.handback.revision: "26"
ms.author: "mblome"
manager: "ghogen"
---
# Ausnahmebehandlung in der Concurrency Runtime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Concurrency Runtime übermittelt viele Arten von Fehlern mithilfe der C\+\+\-Ausnahmebehandlung.  Zu diesen Fehlern zählen die falsche Verwendung der Runtime, Runtime\-Fehler wie etwa das Nichtabrufen einer Ressource sowie Fehler, die in Arbeitsfunktionen auftreten, die Sie für Aufgaben und Aufgabengruppen bereitstellen.  Wenn eine Aufgabe oder eine Aufgabengruppe eine Ausnahme auslöst, wird diese Ausnahme von der Runtime gespeichert und an den Kontext gemarshallt, der wartet, bis die Aufgabe oder Aufgabengruppe beendet wird.  Bei Komponenten wie bei einfachen Aufgaben und Agents verwaltet die Runtime keine Ausnahmen.  In diesen Fällen müssen Sie einen eigenen Mechanismus für die Ausnahmenbehandlung implementieren.  In diesem Thema wird beschrieben, wie die Runtime Ausnahmen behandelt, die von Aufgaben, Aufgabengruppen, einfachen Aufgaben und asynchronen Agents ausgelöst werden, und wie auf Ausnahmen von den Anwendungen reagiert wird.  
  
## Wesentliche Punkte  
  
-   Wenn eine Aufgabe oder eine Aufgabengruppe eine Ausnahme auslöst, wird diese Ausnahme von der Runtime gespeichert und an den Kontext gemarshallt, der wartet, bis die Aufgabe oder Aufgabengruppe beendet wird.  
  
-   Umschließen Sie nach Möglichkeit jeden Aufruf von [concurrency::task::get](../Topic/task::get%20Method.md) und [concurrency::task::wait](../Topic/task::wait%20Method.md) mit einem `try`\/`catch`\-Block, um Fehler zu behandeln, die Sie beheben können.  Die Runtime beendet die App, wenn eine Aufgabe eine Ausnahme auslöst und diese Ausnahme nicht durch die Aufgabe, eine ihrer Fortsetzungen oder die Haupt\-App abgefangen wird.  
  
-   Eine aufgabenbasierte Fortsetzung wird immer ausgeführt. Dabei ist unerheblich, ob die Vorgängeraufgabe erfolgreich abgeschlossen wurde, eine Ausnahme ausgelöst hat oder abgebrochen wurde.  Eine wertbasierte Fortsetzung wird nicht ausgeführt, wenn die Vorgängeraufgabe eine Ausnahme auslöst oder abgebrochen wird.  
  
-   Da aufgabenbasierte Fortsetzungen immer ausgeführt werden, erwägen Sie, am Ende der Fortsetzungskette eine aufgabenbasierte Fortsetzung hinzuzufügen.  Damit kann sichergestellt werden, dass der Code alle Ausnahmen berücksichtigt.  
  
-   Die Runtime löst [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md) aus, wenn Sie [concurrency::task::get](../Topic/task::get%20Method.md) aufrufen und diese Aufgabe abgebrochen wird.  
  
-   Die Runtime verwaltet keine Ausnahmen für einfache Aufgaben und Agents.  
  
##  <a name="top"></a> In diesem Dokument  
  
-   [Aufgaben und Fortsetzungen](#tasks)  
  
-   [Aufgabengruppen und parallele Algorithmen](#task_groups)  
  
-   [Von der Runtime ausgelöste Ausnahmen](#runtime)  
  
-   [Mehrere Ausnahmen](#multiple)  
  
-   [Abbruch](#cancellation)  
  
-   [Einfache Aufgaben](#lwts)  
  
-   [Asynchrone Agents](#agents)  
  
##  <a name="tasks"></a> Aufgaben und Fortsetzungen  
 Dieser Abschnitt beschreibt, wie die Runtime Ausnahmen behandelt, die von [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md)\-Objekten und deren Fortsetzungen ausgelöst werden.  Weitere Informationen zu dieser Aufgabe und diesem Fortsetzungsmodell finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Wenn Sie im Text einer Arbeitsfunktion, die Sie an ein `task`\-Objekt übergeben, eine Ausnahme auslösen, speichert die Runtime diese Ausnahme und marshallt sie an den Kontext, der [concurrency::task::get](../Topic/task::get%20Method.md) oder [concurrency::task::wait](../Topic/task::wait%20Method.md) aufruft.  Das Dokument [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md) beschreibt aufgabenbasierte Fortsetzungen und wertbasierte Fortsetzungen im Vergleich. Zusammenfassend ausgedrückt, akzeptiert eine wertbasierte Fortsetzung einen Parameter vom Typ `T` und eine aufgabenbasierte Fortsetzung einen Parameter vom Typ `task<T>`.  Wenn eine Aufgabe, die ausgelöst wird, über eine oder mehrere wertbasierte Fortsetzungen verfügt, wird die Ausführung dieser Fortsetzungen nicht geplant.  Dieses Verhalten wird im folgenden Beispiel veranschaulicht:  
  
 [!CODE [concrt-eh-task#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-eh-task#1)]  
  
 Eine aufgabenbasierte Fortsetzung ermöglicht es, jede Ausnahme zu behandeln, die von der Vorgängeraufgabe ausgelöst wird.  Eine aufgabenbasierte Fortsetzung wird immer ausgeführt. Dabei ist unerheblich, ob die Aufgabe erfolgreich abgeschlossen wurde, eine Ausnahme ausgelöst hat oder abgebrochen wurde.  Wenn eine Aufgabe eine Ausnahme auslöst, wird die Ausführung ihrer aufgabenbasierten Fortsetzungen geplant.  Im folgenden Beispiel wird eine Aufgabe dargestellt, die immer ausgelöst wird.  Die Aufgabe verfügt über zwei Fortsetzungen: eine ist wertbasiert und die andere aufgabenbasiert.  Die aufgabenbasierte Ausnahme wird immer ausgeführt und können daher die Ausnahme abfangen, die von der Vorgängeraufgabe ausgelöst wird.  Wenn das Beispiel darauf wartet, dass beide Fortsetzungen beendet werden, wird die Ausnahme erneut ausgelöst, da die Aufgabenausnahme immer ausgelöst wird, wenn `task::get` oder `task::wait` aufgerufen wird.  
  
 [!CODE [concrt-eh-continuations#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-eh-continuations#1)]  
  
 Es wird empfohlen, aufgabenbasierte Fortsetzungen zu verwenden, um Ausnahmen abzufangen, die Sie behandeln können.  Da aufgabenbasierte Fortsetzungen immer ausgeführt werden, erwägen Sie, am Ende der Fortsetzungskette eine aufgabenbasierte Fortsetzung hinzuzufügen.  Damit kann sichergestellt werden, dass der Code alle Ausnahmen berücksichtigt.  Im folgenden Beispiel wird eine grundlegende wertbasierte Fortsetzungskette dargestellt.  Die dritte Aufgabe in der Kette wird ausgelöst und daher werden alle folgenden wertbasierten Fortsetzungen nicht ausgeführt.  Allerdings ist die endgültige Fortsetzung aufgabenbasiert und wird daher immer ausgeführt.  Diese letzte Fortsetzung behandelt die Ausnahme, die von der dritten Aufgabe ausgelöst wird.  
  
 Es wird empfohlen, die spezifischsten Ausnahmen möglichst abzufangen.  Sie können diese endgültige aufgabenbasierte Fortsetzung weglassen, wenn Sie keine spezifischen Ausnahmen abzufangen haben.  Alle Ausnahmen werden nicht behandelt und können die App beenden.  
  
 [!CODE [concrt-eh-task-chain#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-eh-task-chain#1)]  
  
> [!TIP]
>  Sie können die [concurrency::task\_completion\_event::set\_exception](../../parallel/concrt/reference/task-completion-event-class.md)\-Methode verwenden, um einer Ausnahme ein Aufgabenabschlussereignis zuzuordnen.  Im Dokument [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md) wird die [concurrency::task\_completion\_event](../../parallel/concrt/reference/task-completion-event-class.md)\-Klasse ausführlich beschrieben.  
  
 [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md) ist ein wichtiger Runtime\-Ausnahmetyp, der mit `task` verknüpft ist.  Die Runtime löst `task_canceled` aus, wenn Sie `task::get` aufrufen und diese Aufgabe abgebrochen wird. \(Umgekehrt gibt `task::wait` [task\_status::canceled](../Topic/task_group_status%20Enumeration.md) zurück und wird nicht ausgelöst.\) Sie können diese Ausnahme von einer aufgabenbasierten Fortsetzung oder beim Aufrufen von `task::get` abfangen und behandeln.  Weitere Informationen zum Aufgabenabbruch finden Sie unter [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
> [!CAUTION]
>  Lösen Sie nie `task_canceled` in Ihrem Code aus.  Rufen Sie stattdessen [concurrency::cancel\_current\_task](../Topic/cancel_current_task%20Function.md) auf.  
  
 Die Runtime beendet die App, wenn eine Aufgabe eine Ausnahme auslöst und diese Ausnahme nicht durch die Aufgabe, eine ihrer Fortsetzungen oder die Haupt\-App abgefangen wird.  Wenn die Anwendung abstürzt, können Sie Visual Studio so konfigurieren, dass eine Unterbrechung erfolgt, wenn C\+\+\-Ausnahmen ausgelöst werden.  Nachdem Sie die Position des Ausnahmefehlers ermittelt haben, verwenden Sie eine aufgabenbasierte Fortsetzung, um ihn zu beheben.  
  
 Im Abschnitt [Von der Runtime ausgelöste Ausnahmen](#runtime) in diesem Dokument wird ausführlicher beschrieben, wie Runtime\-Ausnahmen funktionieren.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="task_groups"></a> Aufgabengruppen und parallele Algorithmen  
 In diesem Abschnitt wird beschrieben, wie die Runtime Ausnahmen behandelt, die von Aufgabengruppen ausgelöst werden.  Dieser Abschnitt gilt auch für parallele Algorithmen, z. B. [concurrency::parallel\_for](../Topic/parallel_for%20Function.md), da diese Algorithmen auf Aufgabengruppen aufbauen.  
  
> [!CAUTION]
>  Es ist wichtig, dass Sie die Auswirkungen von Ausnahmen auf abhängige Aufgaben verstehen.  Empfohlene Vorgehensweisen zum Verwenden der Ausnahmebehandlung bei Aufgaben oder parallelen Algorithmen finden Sie im entsprechenden Abschnitt der Parallel Patterns Library unter [Verstehen, wie sich Abbruch und Ausnahmebehandlung auf die Objektlöschung auswirken](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction).  
  
 Weitere Informationen zu Aufgabengruppen finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  Weitere Informationen zu parallelen Algorithmen finden Sie unter [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
 Wenn im Text einer Arbeitsfunktion, die an ein [concurrency::task\_group](../Topic/task_group%20Class.md)\-Objekt oder an ein [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md)\-Objekt übergeben wird, eine Ausnahme ausgelöst wird, wird diese Ausnahme von der Runtime gespeichert und an den Kontext gemarshallt, der [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md), [concurrency::structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md), [concurrency::task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md) oder [concurrency::structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md) aufruft.  Darüber hinaus werden von der Runtime auch alle aktiven Aufgaben in der Aufgabengruppe \(sowie alle aktiven Aufgaben in untergeordneten Aufgabengruppen\) beendet sowie alle noch nicht gestarteten Aufgaben verworfen.  
  
 Im folgenden Beispiel wird die grundlegende Struktur einer Arbeitsfunktion dargestellt, die eine Ausnahme auslöst.  Im Beispiel werden die Werte von zwei `point`\-Objekten mithilfe eines `task_group`\-Objekts parallel ausgegeben.  Die `print_point`\-Arbeitsfunktion gibt die Werte eines `point`\-Objekts an der Konsole aus.  Die Arbeitsfunktion löst eine Ausnahme aus, wenn der Eingabewert `NULL` ist.  Diese Ausnahme wird von der Runtime gespeichert und an den Kontext gemarshallt, der `task_group::wait` aufruft.  
  
 [!CODE [concrt-eh-task-group#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-eh-task-group#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **X \= 15, Y \= 30**  
**Caught exception: point is NULL.** Ein umfassendes Beispiel für die Verwendung der Ausnahmebehandlung in einer Aufgabengruppe finden Sie unter [Gewusst wie: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel\-Schleife](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="runtime"></a> Von der Runtime ausgelöste Ausnahmen  
 Eine Ausnahme kann von einem Aufruf der Runtime ausgelöst werden.  Die meisten Ausnahmetypen, außer [concurrency::task\_canceled](../../parallel/concrt/reference/task-canceled-class.md) und [concurrency::operation\_timed\_out](../../parallel/concrt/reference/operation-timed-out-class.md), weisen auf einen Programmierfehler hin.  Diese Fehler sind in der Regel nicht behebbar und dürfen daher durch Anwendungscode weder abgefangen noch behandelt werden.  Es wird empfohlen, bei der Diagnose von Programmierfehlern nur nicht behebbare Fehler im Anwendungscode abzufangen oder zu behandeln.  Die von der Runtime definierten Ausnahmetypen zu kennen, erleichtert jedoch die Diagnose von Programmierfehlern.  
  
 Der Mechanismus für die Ausnahmenbehandlung ist bei Ausnahmen, die durch die Runtime ausgelöst werden, derselbe wie bei Ausnahmen, der durch Arbeitsfunktionen ausgelöst werden.  Die [concurrency::receive](../Topic/receive%20Function.md)\-Funktion löst beispielsweise eine `operation_timed_out`\-Ausnahme aus, wenn eine Nachricht nicht im angegebenen Zeitraum empfangen wird.  Wenn `receive` eine Ausnahme in einer Arbeitsfunktion auslöst, die an eine Aufgabengruppe übergeben wird, wird diese Ausnahme von der Runtime gespeichert und an den Kontext gemarshallt, der `task_group::wait`, `structured_task_group::wait`, `task_group::run_and_wait` oder `structured_task_group::run_and_wait` aufruft.  
  
 Im folgenden Beispiel werden zwei Aufgaben mithilfe des [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md)\-Algorithmus parallel ausgeführt.  Die erste Aufgabe wartet fünf Sekunden und sendet dann eine Nachricht an einen Nachrichtenpuffer.  Die zweite Aufgabe wartet mithilfe der `receive`\-Funktion drei Sekunden auf eine Nachricht vom selben Nachrichtenpuffer.  Die `receive`\-Funktion löst die `operation_timed_out`\-Ausnahme aus, wenn die Nachricht nicht im angegebenen Zeitraum empfangen wird.  
  
 [!CODE [concrt-eh-time-out#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-eh-time-out#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **Timeout für den Vorgang.** Um sicherzustellen, dass die Anwendung ordnungsgemäß beendet wird, muss der Code beim Aufrufen der Runtime Ausnahmen behandeln.  Behandeln Sie auch Ausnahmen, wenn Sie externen Code wie etwa die Bibliothek eines Drittanbieters aufrufen, der die Concurrency Runtime verwendet.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="multiple"></a> Mehrere Ausnahmen  
 Wenn eine Aufgabe oder paralleler Algorithmus mehrere Ausnahmen empfängt, wird nur eine dieser Ausnahmen von der Runtime an den aufrufenden Kontext gemarshallt.  Dabei kann nicht vorhergesagt werden, welche Ausnahme von der Runtime gemarshallt wird.  
  
 Im folgenden Beispiel werden mithilfe des `parallel_for`\-Algorithmus Zahlen an der Konsole ausgegeben.  Es wird eine Ausnahme ausgegeben, wenn der Eingabewert kleiner als ein Mindestwert oder größer als ein Maximalwert ist.  In diesem Beispiel können mehrere Arbeitsfunktionen eine Ausnahme auslösen.  
  
 [!CODE [concrt-eh-multiple#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-eh-multiple#1)]  
  
 Nachfolgend wird eine Beispielausgabe für dieses Beispiel angezeigt.  
  
  **8**  
**2**  
**9**  
**3**  
**10**  
**4**  
**5**  
**6**  
**7**  
**Caught exception: \-5: the value is less than the minimum.** \[[Nach oben](#top)\]  
  
##  <a name="cancellation"></a> Abbruch  
 Nicht alle Ausnahmen geben einen Fehler an.  Ein Suchalgorithmus kann beispielsweise mithilfe der Ausnahmenbehandlung die zugehörige Aufgabe beenden, sobald das Ergebnis gefunden ist.  Weitere Informationen zum Verwenden von Abbruchmechanismen im Code finden Sie unter [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="lwts"></a> Einfache Aufgaben  
 Eine einfache Aufgabe ist eine Aufgabe, die Sie direkt über ein [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md)\-Objekt planen.  Einfache Aufgaben erfordern einen geringeren Aufwand als gewöhnliche Aufgaben.  Die Runtime fängt jedoch keine Ausnahmen ab, die von einfachen Aufgaben ausgelöst werden.  Stattdessen wird die Ausnahme vom Handler für nicht behandelte Ausnahmen abgefangen, der den Prozess standardmäßig beendet.  Verwenden Sie daher in der Anwendung einen entsprechenden Fehlerbehandlungsmechanismus.  Weitere Informationen zu einfachen Aufgaben finden Sie unter [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="agents"></a> Asynchrone Agents  
 Die Runtime verwaltet wie bei einfachen Aufgaben auch keine Ausnahmen, die von asynchronen Agents ausgelöst werden.  
  
 Im folgenden Beispiel wird eine Möglichkeit für die Behandlung von Ausnahmen in einer Klasse dargestellt, die von [concurrency::agent](../../parallel/concrt/reference/agent-class.md) abgeleitet wird.  In diesem Beispiel wird die `points_agent`\-Klasse definiert.  Die `points_agent::run`\-Methode liest `point`\-Objekte aus dem Nachrichtenpuffer und gibt sie an der Konsole aus.  Die `run`\-Methode löst beim Empfang eines `NULL`\-Zeigers eine Ausnahme aus.  
  
 Die `run`\-Methode schließt alle Arbeiten in einen `try`\-`catch`\-Block ein.  Die Ausnahme wird vom `catch`\-Block in einem Nachrichtenpuffer gespeichert.  Die Anwendung überprüft, ob im Agent ein Fehler aufgetreten ist. Hierzu wird dieser Puffer nach Abschluss des Agents gelesen.  
  
 [!CODE [concrt-eh-agents#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-eh-agents#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **X: 10 Y: 20**  
**X: 20 Y: 30**  
**error occurred in agent: point must not be NULL**  
**the status of the agent is: done** Da sich der `try`\-`catch`\-Block außerhalb der `while`\-Schleife befindet, beendet der Agent die Verarbeitung, sobald der erste Fehler auftritt.  Wenn sich der `try`\-`catch`\-Block innerhalb der `while`\-Schleife befände, würde der Agent die Verarbeitung nach dem Auftreten eines Fehlers fortsetzen.  
  
 In diesem Beispiel werden Ausnahmen in einem Nachrichtenpuffer gespeichert, damit eine andere Komponente den Agent beim Ausführen auf Fehler überwachen kann.  In diesem Beispiel wird der Fehler mithilfe eines [concurrency::single\_assignment](../../parallel/concrt/reference/single-assignment-class.md)\-Objekts gespeichert.  Wenn ein Agent mehrere Ausnahmen behandelt speichert die `single_assignment`\-Klasse nur die erste Nachricht, die an sie übergeben wird.  Wenn nur die letzte Ausnahme gespeichert werden soll, verwenden Sie die [concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)\-Klasse.  Um alle Ausnahmen zu speichern, verwenden Sie die [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md)\-Klasse.  Weitere Informationen zu diesen Nachrichtenblöcken finden Sie unter [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 Weitere Informationen zu asynchronen Agents finden Sie unter [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="summary"></a> Zusammenfassung  
 \[[Nach oben](#top)\]  
  
## Siehe auch  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)   
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)