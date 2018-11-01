---
title: Schreiben von Win32-Multithreadprogrammen
ms.date: 11/04/2016
helpviewer_keywords:
- thread stacks [C++]
- resources [C++], multithreading
- stacks [C++]
- shared resources [C++]
- threading [C++], sharing common resources
- multithreading [C++], thread stacks
- multithreading [C++], sharing common resources
- mutual exclusion [C++]
- communications [C++], between threads
- mutex [C++]
- threading [C++], thread stacks
ms.assetid: 1415f47d-417f-4f42-949b-946fb28aab0e
ms.openlocfilehash: c7d9790cfee39fbddd9ab545d48fa375d56f3a05
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561329"
---
# <a name="writing-a-multithreaded-win32-program"></a>Schreiben von Win32-Multithreadprogrammen

Wenn Sie ein Programm mit mehreren Threads schreiben, müssen Sie deren Verhalten koordinieren und [Verwendung der Programmressourcen](#_core_sharing_common_resources_between_threads). Sie müssen auch sicherstellen, dass jeder Thread empfängt [einen eigenen Stapel](#_core_thread_stacks).

##  <a name="_core_sharing_common_resources_between_threads"></a> Teilen gemeinsamer Ressourcen zwischen Threads

> [!NOTE]
>  Eine vergleichbare Erläuterung von MFC-Sicht, finden Sie unter [Multithreading: Tipps für die Programmierung](multithreading-programming-tips.md) und [Multithreading: Wenn der Synchronisierungsklassen](multithreading-when-to-use-the-synchronization-classes.md).

Jeder Thread verfügt über einen eigenen Stapel und eine eigene Kopie der CPU-Register. Andere Ressourcen, z. B. Dateien, statische Daten und Heapspeicher, werden von allen Threads im Prozess gemeinsam genutzt. Threads, die diese gemeinsamen Ressourcen verwenden, müssen synchronisiert werden. Win32 bietet verschiedene Möglichkeiten zur Synchronisierung von Ressourcen, einschließlich Semaphore, kritischen Abschnitten, Ereignissen und Mutexen.

Wenn mehrere Threads auf statische Daten zugreifen, muss das Programm mögliche Ressourcenkonflikte verarbeiten können. Ein Programm, in denen ein Thread aktualisiert eine statische Daten-Struktur mit *x*,*y* -Koordinaten für Elemente, die von einem anderen Thread angezeigt werden. Wenn der Aktualisierungsthread die *x* koordinieren und präemptiv unterbrochen, bevor es ändern kann die *y* koordinieren, der Anzeigethread geplant werden, bevor Sie die *y* Koordinate ist aktualisiert. In diesem Fall wird das Element an der falschen Stelle angezeigt. Durch die Verwendung von Semaphore zur Steuerung des Zugriffs auf die Struktur können Sie dieses Problem vermeiden.

Ein Mutex (Kurzform für *Mut*benutzerzugriffsprotokollierung *ex*clusion, gegenseitiger Ausschluss) ist eine Art der Kommunikation zwischen Threads oder Prozessen, die asynchron zueinander ausgeführt werden. Diese Kommunikation wird üblicherweise zur Koordination der Aktivitäten mehrerer Threads oder Prozesse eingesetzt; hierbei wird normalerweise der Zugriff auf eine gemeinsam genutzte Ressource durch Sperren und Entsperren der jeweiligen Ressource gesteuert. Um dieses Problem zu lösen *x*,*y* -Koordinate Aktualisierungsproblem, die Update-Thread ein Mutex festgelegt, der angibt, dass die Datenstruktur vor Durchführung der Aktualisierung wird. Nach Verarbeitung der beiden Koordinaten wird der Mutex aufgehoben. Der Anzeigethread muss abwarten, bis der Mutex aufgehoben ist, bevor er die Anzeige aktualisieren kann. Dieser Prozess des Wartens auf einen Mutex wird oft als Blockieren eines Mutexes bezeichnet, da der Prozess blockiert ist und nicht fortfahren kann, bis der Mutex aufgehoben wird.

Das Programm Bounce.c in [Beispiel C-Multithreadprogramm](sample-multithread-c-program.md) verwendet einen Mutex, mit dem Namen `ScreenMutex` um bildschirmaktualisierungen zu koordinieren. Jedes Mal, die einem der Threads anzeigen, auf dem Bildschirm zu schreiben kann, er ruft `WaitForSingleObject` mit dem Handle `ScreenMutex` und Konstanten UNENDLICH an, dass die `WaitForSingleObject` Aufruf sollte auf den Mutex und kein Timeout blockiert. Wenn `ScreenMutex` aufgehoben wurde, wird der Mutex von der Wartefunktion aktiviert, sodass die Anzeige nicht durch andere Threads beeinflusst werden kann, und die Ausführung des Threads wird fortgesetzt. Ansonsten wird der Thread solange blockiert, bis der Mutex aufgehoben wird. Wenn der Thread die Aktualisierung der Anzeige abgeschlossen ist, werden durch Aufrufen von Mutex frei `ReleaseMutex`.

Bildschirmaktualisierungen und statische Daten sind nur zwei der Ressourcen, bei deren Verwaltung mit Bedacht vorgegangen werden muss. Ein Programm verfügt möglicherweise über mehrere Threads, die auf dieselbe Datei zugreifen. Da durch einen anderen Thread möglicherweise der Dateizeiger verschoben wurde, muss von jedem Thread vor dem Lese- oder Schreibvorgang der Dateizeiger zurückgesetzt werden. Außerdem muss von jedem Thread sichergestellt werden, dass er zwischen der Positionierung des Zeigers und des Zugriffs auf die Datei nicht unterbrochen wird. Diese Threads sollte eine Semaphore verwenden, um Zugriff auf die Datei zu koordinieren, durch die einzelnen Dateizugriff mit Klammern `WaitForSingleObject` und `ReleaseMutex` aufrufen. Diese Vorgehensweise wird anhand des folgenden Codefragments erläutert:

```
HANDLE    hIOMutex= CreateMutex (NULL, FALSE, NULL);

WaitForSingleObject( hIOMutex, INFINITE );
fseek( fp, desired_position, 0L );
fwrite( data, sizeof( data ), 1, fp );
ReleaseMutex( hIOMutex);
```

##  <a name="_core_thread_stacks"></a> Threadstapel

Der gesamte standardmäßige Stapelspeicher einer Anwendung ist für den ersten Ausführungsthread belegt, der als Thread 1 bezeichnet wird. Folglich müssen Sie für jeden von einem Programm zusätzlich benötigten Thread angeben, wie viel mehr Speicherplatz für einen separaten Stapel belegt werden soll. Das Betriebssystem ordnet dem Thread bei Bedarf zusätzlichen Stapelspeicher zu, Sie müssen jedoch einen Standardwert angeben.

Das erste Argument in der `_beginthread` Aufruf ist ein Zeiger auf die `BounceProc` -Funktion, die die Threads ausführt. Das zweite Argument legt die Standardgröße des Stapel für den Thread fest. Das letzte Argument ist eine ID-Nummer, die übergeben werden `BounceProc`. `BounceProc` werden die ID-Nummer, Seeding für den Zufallszahlen-Generator sowie zum Auswählen des Threads Farbattribut und Anzeigezeichen verwendet.

Threads, die Aufrufe an die C-Laufzeitbibliothek oder die Win32-API richten, müssen über ausreichend Stapelspeicher für die Bibliotheks- und API-Funktionen verfügen, die von ihnen aufgerufen werden. Von der `printf`-Funktion (einer C-Funktion) werden über 500 Bytes an Stapelspeicher benötigt. Für den Aufruf von Routinen der Win32-API müssen 2 KB an Stapelspeicher verfügbar sein.

Da jeder Thread über einen eigenen Stapel verfügt, können Sie potenzielle Konflikte in Bezug auf Datenelemente vermeiden, indem Sie so wenig statische Daten wie möglich verwenden. Achten Sie bei der Entwicklung eines Programms darauf, dass es automatische Stapelvariablen für alle Daten verwendet, die einem Thread zugehörig sein können. Die einzigen globalen Variablen im Programm Bounce.c sind entweder Mutexe oder Variablen, die nach ihrer Initialisierung unverändert bleiben.

Win32 stellt für die Speicherung von auf einzelne Threads bezogenen Daten außerdem einen lokalen Threadspeicher (Thread-Local Storage, TLS) zur Verfügung. Weitere Informationen finden Sie unter [threadlokaler Speicher (TLS)](thread-local-storage-tls.md).

## <a name="see-also"></a>Siehe auch

[Multithreading bei C und Win32](multithreading-with-c-and-win32.md)