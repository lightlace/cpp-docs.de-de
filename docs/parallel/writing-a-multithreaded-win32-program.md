---
title: "Schreiben von Win32-Multithreadprogrammen"
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
  - "Kommunikation [C++], Zwischen Threads"
  - "Multithreading [C++], Gemeinsame Nutzung allgemeiner Ressourcen"
  - "Multithreading [C++], Threadstapel"
  - "Mutex [C++]"
  - "Gegenseitiger Ausschluss [C++]"
  - "Ressourcen [C++], Multithreading"
  - "Gemeinsame Ressourcen [C++]"
  - "Stapel [C++]"
  - "Threadstapel [C++]"
  - "Threading [C++], Gemeinsame Nutzung allgemeiner Ressourcen"
  - "Threading [C++], Threadstapel"
ms.assetid: 1415f47d-417f-4f42-949b-946fb28aab0e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Schreiben von Win32-Multithreadprogrammen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie ein Programm mit mehreren Threads schreiben, müssen Sie deren Verhalten und deren [Verwendung der Programmressourcen](#_core_sharing_common_resources_between_threads) koordinieren.  Außerdem müssen Sie sicherstellen, dass jeder Thread [seinen eigenen Stapel](#_core_thread_stacks) erhält.  
  
##  <a name="_core_sharing_common_resources_between_threads"></a> Teilen gemeinsamer Ressourcen zwischen Threads  
  
> [!NOTE]
>  Eine vergleichbare Erläuterung in Bezug auf MFC finden Sie unter [Multithreading: Tipps für die Programmierung](../parallel/multithreading-programming-tips.md) und unter [Multithreading: Verwendungsmöglichkeiten der Synchronisierungsklassen](../parallel/multithreading-when-to-use-the-synchronization-classes.md).  
  
 Jeder Thread verfügt über einen eigenen Stapel und eine eigene Kopie der CPU\-Register.  Andere Ressourcen, z. B. Dateien, statische Daten und Heapspeicher, werden von allen Threads im Prozess gemeinsam genutzt.  Threads, die diese gemeinsamen Ressourcen verwenden, müssen synchronisiert werden.  Win32 bietet verschiedene Möglichkeiten zur Synchronisierung von Ressourcen, einschließlich Semaphore, kritischen Abschnitten, Ereignissen und Mutexen.  
  
 Wenn mehrere Threads auf statische Daten zugreifen, muss das Programm mögliche Ressourcenkonflikte verarbeiten können.  Stellen Sie sich ein Programm vor, bei dem ein Thread eine statische Datenstruktur aktualisiert, die *x*,*y*\-Koordinaten für Elemente enthält, die von einem anderen Thread angezeigt werden.  Wenn der Aktualisierungsthread die *x*\-Koordinate ändert und unterbrochen wird, bevor er die *y*\-Koordinate ändern kann, wird der Anzeigethread möglicherweise vom Scheduler gestartet, bevor die *y*\-Koordinate aktualisiert wird.  In diesem Fall wird das Element an der falschen Stelle angezeigt.  Durch die Verwendung von Semaphore zur Steuerung des Zugriffs auf die Struktur können Sie dieses Problem vermeiden.  
  
 Ein Mutex \(Kurzform für *mut*ual *ex*clusion, gegenseitiger Ausschluss\) ist eine Art der Kommunikation zwischen Threads oder Prozessen, die asynchron zueinander ausgeführt werden.  Diese Kommunikation wird üblicherweise zur Koordination der Aktivitäten mehrerer Threads oder Prozesse eingesetzt; hierbei wird normalerweise der Zugriff auf eine gemeinsam genutzte Ressource durch Sperren und Entsperren der jeweiligen Ressource gesteuert.  Zur Behebung des Aktualisierungsproblems der *x*,*y*\-Koordinate wird vom Aktualisierungsthread vor Durchführung der Aktualisierung ein Mutex festgelegt, aus dem hervorgeht, dass die Datenstruktur derzeit verwendet wird.  Nach Verarbeitung der beiden Koordinaten wird der Mutex aufgehoben.  Der Anzeigethread muss abwarten, bis der Mutex aufgehoben ist, bevor er die Anzeige aktualisieren kann.  Dieser Prozess des Wartens auf einen Mutex wird oft als Blockieren eines Mutexes bezeichnet, da der Prozess blockiert ist und nicht fortfahren kann, bis der Mutex aufgehoben wird.  
  
 Das in [Beispiel für ein C\-Multithreadprogramm](../parallel/sample-multithread-c-program.md) angezeigte Bounce.c\-Programm verwendet einen Mutex mit dem Namen `ScreenMutex`, um Bildschirmaktualisierungen zu koordinieren.  Jedes Mal, wenn einer der Anzeigethreads für den Schreibvorgang am Bildschirm zur Verfügung steht, ruft er mit dem Handle für `ScreenMutex` und der **INFINITE**\-Konstante **WaitForSingleObject** auf, um anzugeben, dass durch den **WaitForSingleObject**\-Aufruf der Mutex blockiert werden und kein Timeout eintreten soll.  Wenn `ScreenMutex` aufgehoben wurde, wird der Mutex von der Wartefunktion aktiviert, sodass die Anzeige nicht durch andere Threads beeinflusst werden kann, und die Ausführung des Threads wird fortgesetzt.  Ansonsten wird der Thread solange blockiert, bis der Mutex aufgehoben wird.  Sobald der Thread die Aktualisierung der Anzeige abgeschlossen hat, wird der Mutex durch Aufruf von **ReleaseMutex** freigegeben.  
  
 Bildschirmaktualisierungen und statische Daten sind nur zwei der Ressourcen, bei deren Verwaltung mit Bedacht vorgegangen werden muss.  Ein Programm verfügt möglicherweise über mehrere Threads, die auf dieselbe Datei zugreifen.  Da durch einen anderen Thread möglicherweise der Dateizeiger verschoben wurde, muss von jedem Thread vor dem Lese\- oder Schreibvorgang der Dateizeiger zurückgesetzt werden.  Außerdem muss von jedem Thread sichergestellt werden, dass er zwischen der Positionierung des Zeigers und des Zugriffs auf die Datei nicht unterbrochen wird.  Von diesen Threads sollte ein Semaphore verwendet werden, mit dem der Zugriff auf die Datei durch **WaitForSingleObject**\- und **ReleaseMutex**\-Aufrufe koordiniert wird.  Diese Vorgehensweise wird anhand des folgenden Codefragments erläutert:  
  
```  
HANDLE    hIOMutex= CreateMutex (NULL, FALSE, NULL);  
  
WaitForSingleObject( hIOMutex, INFINITE );  
fseek( fp, desired_position, 0L );  
fwrite( data, sizeof( data ), 1, fp );  
ReleaseMutex( hIOMutex);  
```  
  
##  <a name="_core_thread_stacks"></a> Threadstapel  
 Der gesamte standardmäßige Stapelspeicher einer Anwendung ist für den ersten Ausführungsthread belegt, der als Thread 1 bezeichnet wird.  Folglich müssen Sie für jeden von einem Programm zusätzlich benötigten Thread angeben, wie viel mehr Speicherplatz für einen separaten Stapel belegt werden soll.  Das Betriebssystem ordnet dem Thread bei Bedarf zusätzlichen Stapelspeicher zu, Sie müssen jedoch einen Standardwert angeben.  
  
 Das erste Argument im `_beginthread`\-Aufruf ist ein Zeiger auf die **BounceProc**\-Funktion, die die Threads ausführt.  Das zweite Argument legt die Standardgröße des Stapel für den Thread fest.  Das letzte Argument ist eine ID\-Nummer, die an **BounceProc** übergeben wird.  **BounceProc** verwendet die ID\-Nummer, um den Zufallsgenerator zu starten und um Farbattribut und Anzeigezeichen des Threads auszuwählen.  
  
 Threads, die Aufrufe an die C\-Laufzeitbibliothek oder die Win32\-API richten, müssen über ausreichend Stapelspeicher für die Bibliotheks\- und API\-Funktionen verfügen, die von ihnen aufgerufen werden.  Von der `printf`\-Funktion \(einer C\-Funktion\) werden über 500 Bytes an Stapelspeicher benötigt. Für den Aufruf von Routinen der Win32\-API müssen 2 KB an Stapelspeicher verfügbar sein.  
  
 Da jeder Thread über einen eigenen Stapel verfügt, können Sie potenzielle Konflikte in Bezug auf Datenelemente vermeiden, indem Sie so wenig statische Daten wie möglich verwenden.  Achten Sie bei der Entwicklung eines Programms darauf, dass es automatische Stapelvariablen für alle Daten verwendet, die einem Thread zugehörig sein können.  Die einzigen globalen Variablen im Programm Bounce.c sind entweder Mutexe oder Variablen, die nach ihrer Initialisierung unverändert bleiben.  
  
 Win32 stellt für die Speicherung von auf einzelne Threads bezogenen Daten außerdem einen lokalen Threadspeicher \(Thread\-Local Storage, TLS\) zur Verfügung.  Weitere Informationen finden Sie unter [Lokaler Threadspeicher \(TLS\)](../parallel/thread-local-storage-tls.md).  
  
## Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)