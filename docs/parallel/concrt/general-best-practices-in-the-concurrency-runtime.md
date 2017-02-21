---
title: "Allgemein empfohlene Vorgehensweisen in der Concurrency Runtime | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Concurrency Runtime, allgemein bewährte Methoden"
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Allgemein empfohlene Vorgehensweisen in der Concurrency Runtime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Dokument beschreibt empfohlene Vorgehensweisen, die für mehrere Bereiche der Concurrency Runtime gelten.  
  
##  <a name="top"></a> Abschnitte  
 Dieses Dokument enthält folgende Abschnitte:  
  
-   [Verwenden Sie nach Möglichkeit Konstrukte für die kooperative Synchronisierung](#synchronization)  
  
-   [Vermeiden Sie langwierige Aufgaben, die nicht zurückgehalten werden](#yield)  
  
-   [Verwenden Sie die Überzeichnung für den Offset von blockierenden Vorgängen oder von Vorgängen mit langer Wartezeit](#oversubscription)  
  
-   [Verwenden Sie nach Möglichkeit parallele Speicherverwaltungsfunktionen](#memory)  
  
-   [Verwenden Sie RAII zum Verwalten der Lebensdauer von Parallelitätsobjekten](#raii)  
  
-   [Erstellen Sie keine Parallelitätsobjekte im globalen Gültigkeitsbereich](#global-scope)  
  
-   [Verwenden Sie keine Parallelitätsobjekte in freigegebenen Datensegmenten](#shared-data)  
  
##  <a name="synchronization"></a> Verwenden Sie nach Möglichkeit Konstrukte für die kooperative Synchronisierung  
 Die Concurrency Runtime stellt viele parallelitätssichere Konstrukte bereit, die kein externes Synchronisierungsobjekt erfordern.  Beispielsweise stellt die [concurrency::concurrent\_vector](../../parallel/concrt/reference/concurrent-vector-class.md)\-Klasse parallelitätssichere Anfügevorgänge und parallelitätssicheren Elementzugriff bereit.  Für Fälle, in denen Sie exklusiven Zugriff auf eine Ressource benötigen, stellt die Laufzeit jedoch die Klassen [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md), [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) und [concurrency::event](../../parallel/concrt/reference/event-class.md) bereit.  Diese Typen weisen kooperatives Verhalten auf. Deshalb kann der Taskplaner Verarbeitungsressourcen neu einem anderen Kontext zuteilen, während die erste Aufgabe auf Daten wartet.  Verwenden Sie nach Möglichkeit diese Synchronisierungstypen statt anderer Synchronisierungsmechanismen, z. B. die von der Windows\-API bereitgestellten Synchronisierungsmechanismen, die kein kooperatives Verhalten aufweisen.  Weitere Informationen zu diesen Synchronisierungstypen und ein Codebeispiel finden Sie unter [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md) und [Vergleich der Synchronisierungsdatenstrukturen mit der Windows\-API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="yield"></a> Vermeiden Sie langwierige Aufgaben, die nicht zurückgehalten werden  
 Da sich der Taskplaner kooperativ verhält, stellt er keine Fairness zwischen Aufgaben bereit.  Daher kann eine Aufgabe das Starten anderer Aufgaben verhindern.  Dies ist zwar in manchen Fällen akzeptabel, kann jedoch in anderen Fällen Deadlocks oder Ressourcenmangel verursachen.  
  
 Im folgenden Beispiel übersteigt die Anzahl der ausgeführten Aufgaben die Anzahl der zugeteilten Verarbeitungsressourcen.  Die erste Aufgabe wird nicht an den Taskplaner abgetreten, und daher wird die zweite Aufgabe erst gestartet, nachdem die erste Aufgabe beendet wurde.  
  
 [!CODE [concrt-cooperative-tasks#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-cooperative-tasks#1)]  
  
 In diesem Beispiel wird die folgende Ausgabe erzeugt:  
  
 1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000  
  
 Es gibt mehrere Möglichkeiten, die Zusammenarbeit zwischen den beiden Aufgaben zu ermöglichen.  Eine Möglichkeit besteht darin, eine Aufgabe mit langer Ausführungszeit gelegentlich an den Taskplaner abzutreten.  Im folgenden Beispiel wird die `task`\-Funktion geändert, um die [concurrency::Context::Yield](../Topic/Context::Yield%20Method.md)\-Methode aufzurufen, damit die Ausführung an den Taskplaner abgetreten wird und eine andere Aufgabe ausgeführt werden kann.  
  
 [!CODE [concrt-cooperative-tasks#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-cooperative-tasks#2)]  
  
 In diesem Beispiel wird die folgende Ausgabe erzeugt:  
  
  **1: 250000000**  
**2: 250000000**  
**1: 500000000**  
**2: 500000000**  
**1: 750000000**  
**2: 750000000**  
**1: 1000000000**  
**2: 1000000000** Die `Context::Yield`\-Methode gibt nur an einen anderen aktiven Thread des Planers, zu dem der aktuelle Thread gehört, an eine einfache Aufgabe oder an einen anderen Betriebssystemthread zurück.  Diese Methode hält keine Arbeitsvorgänge zugunsten von Arbeitsvorgängen zurück, die für die Ausführung in einem [concurrency::task\_group](../Topic/task_group%20Class.md)\-Objekt oder einem [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md)\-Objekt geplant sind, jedoch noch nicht gestartet wurden.  
  
 Es gibt weitere Verfahren, die Zusammenarbeit zwischen Aufgaben mit langer Ausführungsdauer zu ermöglichen.  Sie können eine große Aufgabe in kleinere Unteraufgaben aufteilen.  Sie können auch Überzeichnung während einer langwierigen Aufgabe aktivieren.  Durch Überzeichnung können Sie mehr Threads als die Anzahl der verfügbaren Hardwarethreads erstellen.  Überzeichnung ist von besonderem Nutzen, wenn eine langwierige Aufgabe einen hohen Betrag an Wartezeit beinhaltet, z. B. das Lesen von Daten von einem Datenträger oder über eine Netzwerkverbindung.  Weitere Informationen zu einfachen Aufgaben und Überzeichnung finden Sie unter [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="oversubscription"></a> Verwenden Sie die Überzeichnung für den Offset von blockierenden Vorgängen oder von Vorgängen mit langer Wartezeit  
 Die Concurrency Runtime stellt Synchronisierungsprimitive, z. B. [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md), bereit, die das kooperative Blockieren und Zurückhalten von Aufgaben ermöglichen.  Wenn eine Aufgabe kooperativ blockiert oder zurückgehalten wird, kann der Taskplaner Verarbeitungsressourcen neu einem anderen Kontext zuteilen, während die erste Aufgabe auf Daten wartet.  
  
 Es gibt Fälle, in denen Sie den von der Concurrency Runtime bereitgestellten kooperativen Blockierungsmechanismus nicht verwenden können.  Zum Beispiel verwendet eine externe Bibliothek möglicherweise einen anderen Synchronisierungsmechanismus.  Ein weiteres Beispiel ist das Ausführen eines Vorgangs, der einen hohen Betrag an Wartezeit beinhalten kann, wenn Sie z. B. die `ReadFile`\-Funktion der Windows\-API zum Lesen von Daten über eine Netzwerkverbindung verwenden.  In diesen Fällen kann Überzeichnung die Ausführung anderer Aufgaben ermöglichen, wenn sich eine andere Aufgabe im Leerlauf befindet.  Durch Überzeichnung können Sie mehr Threads als die Anzahl der verfügbaren Hardwarethreads erstellen.  
  
 Betrachten Sie die folgende Funktion `download`, mit der die Datei an der angegebenen URL heruntergeladen wird.  In diesem Beispiel wird mit der [concurrency::Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md)\-Methode die Anzahl aktiver Threads vorübergehend erhöht.  
  
 [!CODE [concrt-download-oversubscription#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-download-oversubscription#4)]  
  
 Da die `GetHttpFile`\-Funktion einen Vorgang mit potenzieller Wartezeit ausführt, kann Überzeichnung die Ausführung anderer Aufgaben ermöglichen, während die aktuelle Aufgabe auf Daten wartet.  Die vollständige Version dieses Beispiels finden Sie unter [Gewusst wie: Verwenden der Überzeichnung zum Kompensieren der Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="memory"></a> Verwenden Sie nach Möglichkeit parallele Speicherverwaltungsfunktionen  
 Verwenden Sie die Speicherverwaltungsfunktionen [concurrency::Alloc](../Topic/Alloc%20Function.md) und [concurrency::Free](../Topic/Free%20Function.md), wenn differenzierte Aufgaben häufig Speicher für kleine Objekte mit relativ kurzer Lebensdauer reservieren.  Die Concurrency Runtime verwaltet für jeden ausgeführten Thread einen eigenen Arbeitsspeichercache.  Die `Alloc`\-Funktion und die `Free`\-Funktion reservieren Arbeitsspeicher in diesen Caches und geben Arbeitsspeicher in den Caches frei, ohne Sperren oder Arbeitsspeicherbarrieren zu verwenden.  
  
 Weitere Informationen zu diesen Speicherverwaltungsfunktionen finden Sie unter [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  Ein Beispiel, das diese Funktionen veranschaulicht, finden Sie unter [Gewusst wie: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="raii"></a> Verwenden Sie RAII zum Verwalten der Lebensdauer von Parallelitätsobjekten  
 Die Concurrency Runtime verwendet die Ausnahmebehandlung zum Implementieren von Funktionen, z. B. Abbruch.  Schreiben Sie daher ausnahmesicheren Code, wenn Sie die Laufzeit oder eine andere Bibliothek aufrufen, die die Laufzeit aufruft.  
  
 Das *RAII \(Resource Acquisition Is Initialization\)*\-Muster bietet eine Möglichkeit, die Lebensdauer eines Parallelitätsobjekts in einem angegebenen Bereich sicher zu verwalten.  Unter dem RAII\-Muster wird dem Stapel eine Datenstruktur zugeordnet.  Diese Datenstruktur initialisiert oder ruft eine Ressource ab, wenn sie erstellt wird, und zerstört oder gibt diese Ressource frei, wenn die Datenstruktur zerstört wird.  Das RAII\-Muster garantiert, dass der Destruktor aufgerufen wird, bevor der einschließende Bereich beendet wird.  Dieses Muster ist hilfreich, wenn eine Funktion mehrere `return`\-Anweisungen enthält.  Das Muster erleichtert Ihnen außerdem das Schreiben von ausnahmesicherem Code.  Wenn eine `throw`\-Anweisung das Entladen des Stapels verursacht, wird der Destruktor für das RAII\-Objekt aufgerufen. Daher wird die Ressource immer ordnungsgemäß gelöscht oder freigegeben.  
  
 Die Laufzeit definiert mehrere Klassen, die das RAII\-Muster verwenden, z. B. [concurrency::critical\_section::scoped\_lock](../Topic/critical_section::scoped_lock%20Class.md) und [concurrency::reader\_writer\_lock::scoped\_lock](../Topic/reader_writer_lock::scoped_lock%20Class.md).  Diese Hilfsklassen werden als *bewertete Sperren* bezeichnet.  Diese Klassen bieten mehrere Vorteile, wenn Sie mit [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md)\-Objekten oder [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)\-Objekten arbeiten.  Der Konstruktor dieser Klassen erhält Zugriff auf das bereitgestellte `critical_section`\-Objekt bzw. `reader_writer_lock`\-Objekt, und der Destruktor gibt den Zugriff auf das Objekt frei.  Da eine bewertete Sperre den Zugriff auf das gegenseitige Ausschlussobjekt automatisch freigibt, wenn es zerstört wird, muss das zugrunde liegende Objekt nicht manuell entsperrt werden.  
  
 Betrachten Sie die folgende Klasse `account`, die durch eine externe Bibliothek definiert ist und deshalb nicht geändert werden kann.  
  
 [!CODE [concrt-account-transactions#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-account-transactions#1)]  
  
 Im folgenden Beispiel werden mehrere Transaktionen für ein `account`\-Objekt parallel ausgeführt.  Im Beispiel wird ein `critical_section`\-Objekt zum Synchronisieren des Zugriffs auf das `account`\-Objekt verwendet, da die `account`\-Klasse nicht parallelitätssicher ist.  Für jeden parallelen Vorgang wird ein `critical_section::scoped_lock`\-Objekt verwendet, um sicherzustellen, dass das `critical_section`\-Objekt entsperrt wird, wenn der Vorgang erfolgreich ausgeführt wird oder fehlschlägt.  Wenn der Kontostand negativ ist, löst der `withdraw`\-Vorgang eine Ausnahme aus und schlägt fehl.  
  
 [!CODE [concrt-account-transactions#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-account-transactions#2)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
  **Balance before deposit: 1924**  
**Balance after deposit: 2924**  
**Balance before withdrawal: 2924**  
**Balance after withdrawal: \-76**  
**Balance before withdrawal: \-76**  
**Error details:**  
 **negative balance: \-76** Weitere Beispiele, in denen das RAII\-Muster zum Verwalten der Lebensdauer von Parallelitätsobjekten verwendet wird, finden Sie unter [Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md), [Gewusst wie: Implementieren einer kooperativen Semaphore mithilfe der Context\-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md) und [Gewusst wie: Verwenden der Überzeichnung zum Kompensieren der Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="global-scope"></a> Erstellen Sie keine Parallelitätsobjekte im globalen Gültigkeitsbereich  
 Wenn Sie ein Parallelitätsobjekt im globalen Gültigkeitsbereich erstellen, kann dies zu Problemen wie Deadlocks oder Arbeitsspeicher\-Zugriffsverletzungen in der Anwendung führen.  
  
 Wenn Sie z. B. ein Concurrency Runtime\-Objekt erstellen, erstellt die Laufzeit einen Standardplaner, sofern noch kein Planer erstellt wurde.  Ein Laufzeitobjekt, das während der globalen Objekterstellung erstellt wird, führt dementsprechend dazu, dass die Laufzeit diesen Standardplaner erstellt.  Dieser Vorgang verwendet jedoch eine interne Sperre, die die Initialisierung anderer Objekte behindern kann, die die Concurrency Runtime\-Infrastruktur unterstützen.  Diese interne Sperre wird eventuell von einem anderen Infrastrukturobjekt benötigt, das noch nicht initialisiert wurde, und daher tritt möglicherweise ein Deadlock in der Anwendung auf.  
  
 Im folgenden Beispiel wird die Erstellung eines globalen [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md)\-Objekts veranschaulicht.  Dieses Muster gilt nicht nur für die `Scheduler`\-Klasse, sondern auch für alle anderen Typen, die von der Concurrency Runtime bereitgestellt werden.  Es wird empfohlen, dieses Muster nicht anzuwenden, da es zu einem unerwarteten Verhalten in der Anwendung führen kann.  
  
 [!CODE [concrt-global-scheduler#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-global-scheduler#1)]  
  
 Beispiele für die ordnungsgemäße Vorgehensweise zum Erstellen von `Scheduler`\-Objekten finden Sie unter [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 \[[Nach oben](#top)\]  
  
##  <a name="shared-data"></a> Verwenden Sie keine Parallelitätsobjekte in freigegebenen Datensegmenten  
 Die Concurrency Runtime unterstützt nicht die Verwendung von Parallelitätsobjekten in einem freigegebenen Datenabschnitt, z. B. in einem mit der [data\_seg](../../preprocessor/data-seg.md) `#pragma`\-Direktive erstellten Datenabschnitt.  Ein über Prozessgrenzen hinweg gemeinsam genutztes Parallelitätsobjekt kann einen inkonsistenten oder ungültigen Zustand der Laufzeit verursachen.  
  
 \[[Nach oben](#top)\]  
  
## Siehe auch  
 [Empfohlene Vorgehensweisen im Zusammenhang mit der Concurrency Runtime](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [Parallel Patterns Library \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Synchronisierungsdatenstrukturen](../../parallel/concrt/synchronization-data-structures.md)   
 [Vergleich der Synchronisierungsdatenstrukturen mit der Windows\-API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)   
 [Gewusst wie: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)   
 [Gewusst wie: Verwenden der Überzeichnung zum Kompensieren der Latenz](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)   
 [Gewusst wie: Implementieren einer kooperativen Semaphore mithilfe der Context\-Klasse](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)   
 [Empfohlene Vorgehensweisen in der Parallel Patterns Library](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [Empfohlene Vorgehensweisen in der Asynchronous Agents Library](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)