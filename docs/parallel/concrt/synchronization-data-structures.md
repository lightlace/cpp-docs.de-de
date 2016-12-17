---
title: "Synchronisierungsdatenstrukturen"
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
  - "Strukturen für Synchronisierungsdaten"
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
caps.latest.revision: 26
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# Synchronisierungsdatenstrukturen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Concurrency Runtime stellt mehrere Datenstrukturen bereit, mit denen Sie den Zugriff auf freigegebene Daten von mehreren Threads synchronisieren können.  Diese Datenstrukturen sind nützlich, wenn Sie Daten freigegeben haben, die Sie selten ändern.  Ein Synchronisierungsobjekt wie beispielsweise ein kritischer Abschnitt bewirkt, dass andere Threads warten, bis die freigegebene Ressource verfügbar ist.  Wenn Sie ein derartiges Objekt verwenden, um den Zugriff auf häufig verwendete Daten zu synchronisieren, können Sie daher in der Anwendung Skalierbarkeit verlieren.  [Parallel Patterns Library \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) stellt die Klasse, die [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md), mit der Sie eine Ressource für mehrere Threads oder Aufgaben ohne die Anforderung für Synchronisierung freizugeben.  Weitere Informationen über die `combinable`\-Klasse finden Sie unter [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md).  
  
##  <a name="top"></a> Abschnitte  
 In diesem Thema werden folgende asynchrone Meldungsblocktypen im Detail beschrieben:  
  
-   [critical\_section](#critical_section)  
  
-   [reader\_writer\_lock](#reader_writer_lock)  
  
-   [scoped\_lock und scoped\_lock\_read](#scoped_lock)  
  
-   [Ereignis](#event)  
  
##  <a name="critical_section"></a> critical\_section  
 Die [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md)\-Klasse stellt ein kooperatives gegenseitiges Ausschlussobjekt dar, das anderen Aufgaben nachgibt, anstatt, ihnen zuvorzukommen.  Kritische Abschnitte sind nützlich, wenn für mehrere Threads exklusiver Lese\- und Schreibzugriff auf freigegebene Daten erforderlich ist.  
  
 Die `critical_section`\-Klasse ist nicht wiedereintretend.  Die [concurrency::critical\_section::lock](../Topic/critical_section::lock%20Method.md)\-Methode löst eine Ausnahme des Typs [concurrency::improper\_lock](../../parallel/concrt/reference/improper-lock-class.md) aus, wenn es vom Thread aufgerufen wird, der bereits die Sperre besitzt.  
  
### Methoden und Funktionen  
 Die folgende Tabelle enthält alle wichtigen von der `critical_section`\-Klasse definierten Methoden.  
  
|Methode|**Beschreibung**|  
|-------------|----------------------|  
|[lock](../Topic/critical_section::lock%20Method.md)|Ruft den kritischen Abschnitt ab.  Der aufrufende Kontext blockiert, bis er die Sperre abruft.|  
|[try\_lock](../Topic/critical_section::try_lock%20Method.md)|Versucht, den kritischen Abschnitt abzurufen, blockiert aber nicht.|  
|[unlock](../Topic/critical_section::unlock%20Method.md)|Gibt den kritischen Abschnitt frei.|  
  
 \[[Nach oben](#top)\]  
  
##  <a name="reader_writer_lock"></a> reader\_writer\_lock  
 Die [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)\-Klasse stellt threadsichere Lese\-\/Schreibvorgänge für freigegebene Daten bereit.  Verwenden Sie Lese\-\/Schreibsperren, wenn für mehrere Threads gleichzeitiger Lesezugriff auf eine freigegebene Ressource erforderlich ist, aber selten auf diese freigegebene Ressource geschrieben wird.  Von dieser Klasse wird jeweils nur einem Thread Schreibzugriff auf ein Objekt gewährt.  
  
 Die `reader_writer_lock`\-Klasse kann eine bessere Leistung als die `critical_section`\-Klasse erzielen, weil ein `critical_section`\-Objekt exklusiven Zugriff auf eine freigegebene Ressource erhält. So wird gleichzeitiger Lesezugriff verhindert.  
  
 Wie die `critical_section`\-Klasse stellt die `reader_writer_lock`\-Klasse ein kooperatives gegenseitiges Ausschlussobjekt dar, das anderen Aufgaben nachgibt anstatt ihnen zuvorzukommen.  
  
 Wenn ein Thread, der auf eine freigegebene Ressource schreiben muss, eine Lese\-\/Schreibsperre abruft, werden andere Threads, die ebenfalls auf die Ressource zugreifen müssen, so lange blockiert, bis der Writer die Sperre aufhebt.  Die `reader_writer_lock`\-Klasse ist ein Beispiel für eine *write\-preference*\-Sperre. Dabei handelt es sich um eine Sperre, die erst die Sperre für wartende Writer und dann die für wartende Reader aufhebt.  
  
 Wie die `critical_section`\-Klasse ist auch die `reader_writer_lock`\-Klasse ist nicht wiedereintretend.  Die [concurrency::reader\_writer\_lock::lock](../Topic/reader_writer_lock::lock%20Method.md) und [concurrency::reader\_writer\_lock::lock\_read](../Topic/reader_writer_lock::lock_read%20Method.md)\-Methoden lösen eine Ausnahme des Typs `improper_lock` aus, wenn sie von einem Thread aufgerufen werden, der bereits die Sperre besitzt.  
  
> [!NOTE]
>  Da die `reader_writer_lock`\-Klasse nicht wieder eintretend ist, können Sie eine schreibgeschützte Sperre nicht auf eine Reader\/Writer\-Sperre aktualisieren und eine Reader\/Writer\-Sperre nicht in eine schreibgeschützte Sperre umwandeln.  Beide Vorgänge führen zu einem nicht definierten Verhalten.  
  
### Methoden und Funktionen  
 Die folgende Tabelle enthält alle wichtigen von der `reader_writer_lock`\-Klasse definierten Methoden.  
  
|Methode|**Beschreibung**|  
|-------------|----------------------|  
|[lock](../Topic/reader_writer_lock::lock%20Method.md)|Ruft Lese\-\/Schreibzugriff auf die Sperre ab.|  
|[try\_lock](../Topic/reader_writer_lock::try_lock%20Method.md)|Versucht, Lese\-\/Schreibzugriff auf die Sperre abzurufen, blockiert aber nicht.|  
|[lock\_read](../Topic/reader_writer_lock::lock_read%20Method.md)|Ruft schreibgeschützten Zugriff auf die Sperre ab.|  
|[try\_lock\_read](../Topic/reader_writer_lock::try_lock_read%20Method.md)|Versucht, schreibgeschützten Zugriff auf die Sperre abzurufen, blockiert aber nicht.|  
|[unlock](../Topic/reader_writer_lock::unlock%20Method.md)|Hebt die Sperre auf.|  
  
 \[[Nach oben](#top)\]  
  
##  <a name="scoped_lock"></a> scoped\_lock und scoped\_lock\_read  
 Die Klassen `critical_section` und `reader_writer_lock` stellen geschachtelte Hilfsklassen bereit, die das Arbeiten mit gegenseitigen Ausschlussobjekten erleichtern.  Diese Hilfsklassen werden als *bewertete Sperren* bezeichnet.  
  
 Die `critical_section`\-Klasse enthält die [concurrency::critical\_section::scoped\_lock](../Topic/critical_section::scoped_lock%20Class.md)\-Klasse.  Der Konstruktor ruft den Zugriff auf das bereitgestellte `critical_section`\-Objekt ab, und die Destruktorversionen greifen auf dieses Objekt zu.  Die `reader_writer_lock`\-Klasse enthält die [concurrency::reader\_writer\_lock::scoped\_lock](../Topic/reader_writer_lock::scoped_lock%20Class.md)\-Klasse, die `critical_section::scoped_lock` mit der Ausnahme ähnelt, dass sie verwaltet den Schreibzugriff auf das bereitgestellte `reader_writer_lock`\-Objekt.  Die `reader_writer_lock`\-Klasse enthält außerdem die [concurrency::reader\_writer\_lock::scoped\_lock\_read](../Topic/reader_writer_lock::scoped_lock_read%20Class.md)\-Klasse.  Diese Klasse verwaltet den Lesezugriff auf das bereitgestellte `reader_writer_lock`\-Objekt.  
  
 Beim manuellen Arbeiten mit den Objekten `critical_section` und `reader_writer_lock` bieten bewertete Sperren mehrere Vorteile.  In der Regel ordnen Sie eine bewertete Sperre auf dem Stapel zu.  Eine bewertete Sperre gibt den Zugriff auf das gegenseitige Ausschlussobjekt automatisch frei, wenn es zerstört wird. Aus diesem Grund muss das zugrunde liegende Objekt nicht manuell entsperrt werden.  Dies ist dann nützlich, wenn eine Funktion mehrere `return`\-Anweisungen enthält.  Durch bewertete Sperren können Sie auch leichter ausnahmesicheren Code schreiben.  Wenn eine `throw`\-Aussage bewirkt, dass der Stapel entladen wird, wird der Destruktor für eine beliebige aktive bewertete Sperre aufgerufen. Dadurch wird das gegenseitige Ausschlussobjekt stets ordnungsgemäß freigegeben.  
  
> [!NOTE]
>  Wenn Sie die Klassen `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock` und `reader_writer_lock::scoped_lock_read` verwenden, geben Sie den Zugriff auf das zugrunde liegende gegenseitige Ausschlussobjekt nicht manuell frei.  Dadurch kann die Laufzeit in einen ungültigen Zustand versetzt werden.  
  
##  <a name="event"></a> Ereignis  
 Die [concurrency::event](../../parallel/concrt/reference/event-class.md)\-Klasse stellt ein Synchronisierungsobjekt dar, dessen Zustand signalisiert oder nicht signalisiert sein kann.  Im Gegensatz zu Synchronisierungsobjekten, z. B. kritischen Abschnitten, die den Zugriff auf freigegebene Daten schützen sollen, synchronisieren Ereignisse den Ausführungsablauf.  
  
 Die `event`\-Klasse ist dann nützlich, wenn Arbeit von einer Aufgabe für eine andere Aufgabe verrichtet wurde.  Beispielsweise könnte eine Aufgabe einer anderen Aufgabe signalisieren, dass Daten von einer Netzwerkverbindung oder einer Datei gelesen wurden.  
  
### Methoden und Funktionen  
 Folgende Tabelle enthält einige der wichtigen von der `event`\-Klasse definierten Methoden.  
  
|Methode|**Beschreibung**|  
|-------------|----------------------|  
|[wait](../Topic/event::wait%20Method.md)|Wartet, bis das Ereignis signalisiert wird.|  
|[set](../Topic/event::set%20Method.md)|Versetzt das Ereignis in den signalisierten Zustand.|  
|[reset](../Topic/event::reset%20Method.md)|Versetzt das Ereignis in den nicht signalisierten Zustand.|  
|[wait\_for\_multiple](../Topic/event::wait_for_multiple%20Method.md)|Wartet, bis mehrere Ereignisse signalisiert werden.|  
  
### Beispiel  
 Ein Beispiel für die Verwendung der `event`\-Klasse finden Sie unter [Vergleich der Synchronisierungsdatenstrukturen mit der Windows\-API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).  
  
 \[[Nach oben](#top)\]  
  
## Verwandte Abschnitte  
 [Vergleich der Synchronisierungsdatenstrukturen mit der Windows\-API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)  
 Vergleicht das Verhalten der Synchronisierungsdatenstrukturen mit denen, die von der Windows\-API bereitgestellt werden.  
  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)  
 Beschreibt die Concurrency Runtime, die die parallele Programmierung vereinfacht, und stellt Links zu verwandten Themen bereit.