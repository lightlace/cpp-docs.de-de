---
title: Multithreading mit C++ und MFC
ms.date: 08/27/2018
helpviewer_keywords:
- MFC [C++], multithreading
- threading [C++], MFC
- worker threads [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], about threading
- CWinThread class, purpose of
- multithreading [C++], MFC
- threading [MFC]
- user interface threads [C++]
ms.assetid: 979605f8-3988-44b5-ac9c-b8cce7fcce14
ms.openlocfilehash: bcffc2964d8e15fd47f437366863748175e12622
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258345"
---
# <a name="multithreading-with-c-and-mfc"></a>Multithreading mit C++ und MFC

Die MFC-Bibliothek (Microsoft Foundation Class) bietet Unterstützung für Multithreadanwendungen. In diesem Thema werden Prozesse und Threads sowie das MFC-Multithreading beschrieben.

Ein Prozess ist eine ausführende Instanz einer Anwendung. Wenn Sie z. B. auf das Symbol von Editor doppelklicken, starten Sie einen Prozess, der Editor ausführt.

Ein Thread ist ein Ausführungspfad innerhalb eines Prozesses. Wenn Sie Editor starten, erstellt das Betriebssystem einen Prozess und beginnt mit der Ausführung des primären Threads dieses Prozesses. Bei Beendung des Threads wird auch der Prozess beendet. Dieser primäre Thread wird dem Betriebssystem durch den Startcode in Form einer Funktionsadresse zur Verfügung gestellt. Normalerweise ist dies die Adresse der `main` oder `WinMain` -Funktion, die bereitgestellt wird.

Bei Bedarf können Sie in einer Anwendung zusätzliche Threads erstellen. Dies bietet sich z. B. zur Verarbeitung von Hintergrund- oder Verwaltungsaufgaben an. Auf diese Weise muss der Benutzer nicht auf deren Beendung warten. Alle Threads in MFC-Anwendungen werden durch dargestellt [CWinThread](../mfc/reference/cwinthread-class.md) Objekte. In den meisten Fällen müssen Sie auch keinen dieser Objekte explizit zu erstellen; Rufen Sie stattdessen die Framework-Hilfsfunktion [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), erstellt die `CWinThread` -Objekt für Sie.

In MFC werden zwei Threadtypen unterschieden: Benutzeroberflächenthreads und Arbeitsthreads. Benutzeroberflächenthreads werden normalerweise verwendet, um Benutzereingaben zu behandeln und um auf vom Benutzer generierte Ereignisse und Meldungen zu reagieren. Arbeitsthreads werden normalerweise verwendet, um Aufgaben durchzuführen, für die keine Benutzereingaben erforderlich sind (z. B. Neuberechnungen). In der Win32-API findet keine Unterscheidung zwischen Threadtypen statt; es muss lediglich die Startadresse des Threads bekannt sein, damit mit dessen Ausführung begonnen werden kann. In MFC wird ein spezielles Verfahren zur Behandlung von Benutzeroberflächenthreads verwendet: es wird eine Meldungsverteilschleife für Ereignisse in der Benutzeroberfläche zur Verfügung gestellt. `CWinApp` ist ein Beispiel für ein Benutzeroberflächenthread-Objekt, da es von `CWinThread` abgeleitet ist und Ereignisse und Meldungen behandelt, die vom Benutzer generiert wurden.

In Fällen, in denen mehrere Threads auf dasselbe Objekt zugreifen müssen, sollten Sie besondere Vorsicht walten lassen. [Multithreading: Tipps für die Programmierung](multithreading-programming-tips.md) Beschreibt Techniken, mit denen Sie Probleme umgehen, die in diesen Situationen auftreten können. [Multithreading: Gewusst wie: der Synchronisierungsklassen](multithreading-how-to-use-the-synchronization-classes.md) beschreibt, wie die Klassen, die zum Synchronisieren des Zugriffs von mehreren Threads auf ein einzelnes Objekt verfügbar sind.

Das Schreiben und Debuggen von Multithreadprogrammen ist naturgemäß ein komplexes und schwieriges Unterfangen, da Sie sicherstellen müssen, dass nur jeweils ein Thread auf die Objekte zugreift. In den Themen zu Multithreading werden keine Grundlagen der Multithreadprogrammierung vermittelt. Sie erfahren lediglich, wie MFC in einem Multithreadprogramm verwendet werden kann. In den in Visual C++ enthaltenen MFC-Multithreadbeispielen werden einige Möglichkeiten zum Hinzufügen weiterer Multithreadfunktionen sowie einige Win32-APIs erläutert, die in MFC nicht enthalten sind. Sie sollten diese jedoch lediglich als Ausgangspunkt betrachten.

Weitere Informationen zur Behandlung des Betriebssystems auf Prozesse und Threads finden Sie unter [Prozesse und Threads](/windows/desktop/ProcThread/processes-and-threads) im Windows SDK.

Weitere Informationen zur Multithreadunterstützung in MFC finden Sie in folgenden Themen:

- [Multithreading: Erstellen von Benutzeroberflächenthreads](multithreading-creating-user-interface-threads.md)

- [Multithreading: Erstellen von Arbeitsthreads](multithreading-creating-worker-threads.md)

- [Multithreading: Gewusst wie: der Synchronisierungsklassen](multithreading-how-to-use-the-synchronization-classes.md)

- [Multithreading: Beenden von Threads](multithreading-terminating-threads.md)

- [Multithreading: Tipps für die Programmierung](multithreading-programming-tips.md)

- [Multithreading: Wenn der Synchronisierungsklassen](multithreading-when-to-use-the-synchronization-classes.md)

## <a name="see-also"></a>Siehe auch

[Multithreadingunterstützung für älteren Code (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)
