---
title: Multithreading mit C++ und MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 778602a0e9236ad8cc788d8a2306e8f2d143ec49
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688569"
---
# <a name="multithreading-with-c-and-mfc"></a>Multithreading mit C++ und MFC
Die MFC-Bibliothek (Microsoft Foundation Class) bietet Unterstützung für Multithreadanwendungen. In diesem Thema werden Prozesse und Threads sowie das MFC-Multithreading beschrieben.  
  
 Ein Prozess ist eine ausführende Instanz einer Anwendung. Wenn Sie z. B. auf das Symbol von Editor doppelklicken, starten Sie einen Prozess, der Editor ausführt.  
  
 Ein Thread ist ein Ausführungspfad innerhalb eines Prozesses. Wenn Sie Editor starten, erstellt das Betriebssystem einen Prozess und beginnt mit der Ausführung des primären Threads dieses Prozesses. Bei Beendung des Threads wird auch der Prozess beendet. Dieser primäre Thread wird dem Betriebssystem durch den Startcode in Form einer Funktionsadresse zur Verfügung gestellt. Normalerweise ist dies die Adresse des dem **main** oder `WinMain` -Funktion, die bereitgestellt wird.  
  
 Bei Bedarf können Sie in einer Anwendung zusätzliche Threads erstellen. Dies bietet sich z. B. zur Verarbeitung von Hintergrund- oder Verwaltungsaufgaben an. Auf diese Weise muss der Benutzer nicht auf deren Beendung warten. Alle Threads in MFC-Anwendungen werden durch dargestellt [CWinThread](../mfc/reference/cwinthread-class.md) Objekte. In den meisten Fällen müssen Sie auch keinen diese Objekte explizit zu erstellen; Rufen Sie stattdessen die Framework-Hilfsfunktion [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), erstellt der `CWinThread` Objekt für Sie.  
  
 In MFC werden zwei Threadtypen unterschieden: Benutzeroberflächenthreads und Arbeitsthreads. Benutzeroberflächenthreads werden normalerweise verwendet, um Benutzereingaben zu behandeln und um auf vom Benutzer generierte Ereignisse und Meldungen zu reagieren. Arbeitsthreads werden normalerweise verwendet, um Aufgaben durchzuführen, für die keine Benutzereingaben erforderlich sind (z. B. Neuberechnungen). In der Win32-API findet keine Unterscheidung zwischen Threadtypen statt; es muss lediglich die Startadresse des Threads bekannt sein, damit mit dessen Ausführung begonnen werden kann. In MFC wird ein spezielles Verfahren zur Behandlung von Benutzeroberflächenthreads verwendet: es wird eine Meldungsverteilschleife für Ereignisse in der Benutzeroberfläche zur Verfügung gestellt. `CWinApp` ist ein Beispiel für ein Benutzeroberflächenthread-Objekt, da es von `CWinThread` abgeleitet ist und Ereignisse und Meldungen behandelt, die vom Benutzer generiert wurden.  
  
 In Fällen, in denen mehrere Threads auf dasselbe Objekt zugreifen müssen, sollten Sie besondere Vorsicht walten lassen. [Multithreading: Tipps für die Programmierung](../parallel/multithreading-programming-tips.md) Beschreibt Techniken, mit denen Sie Probleme umgehen können, die in diesen Situationen auftreten können. [Multithreading: Wie der Synchronisierungsklassen](../parallel/multithreading-how-to-use-the-synchronization-classes.md) beschreibt, wie die Klassen, die zum Synchronisieren des Zugriffs von mehreren Threads auf ein einzelnes Objekt verfügbar sind.  
  
 Das Schreiben und Debuggen von Multithreadprogrammen ist naturgemäß ein komplexes und schwieriges Unterfangen, da Sie sicherstellen müssen, dass nur jeweils ein Thread auf die Objekte zugreift. In den Themen zu Multithreading werden keine Grundlagen der Multithreadprogrammierung vermittelt. Sie erfahren lediglich, wie MFC in einem Multithreadprogramm verwendet werden kann. In den in Visual C++ enthaltenen MFC-Multithreadbeispielen werden einige Möglichkeiten zum Hinzufügen weiterer Multithreadfunktionen sowie einige Win32-APIs erläutert, die in MFC nicht enthalten sind. Sie sollten diese jedoch lediglich als Ausgangspunkt betrachten.  
  
 Weitere Informationen dazu, wie das Betriebssystem, Prozesse und Threads behandelt, finden Sie unter [Prozesse und Threads](http://msdn.microsoft.com/library/windows/desktop/ms684841) in der [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 Weitere Informationen zur Multithreadunterstützung in MFC finden Sie in folgenden Themen:  
  
-   [Multithreading: Erstellen von Benutzeroberflächenthreads](../parallel/multithreading-creating-user-interface-threads.md)  
  
-   [Multithreading: Erstellen von Arbeitsthreads](../parallel/multithreading-creating-worker-threads.md)  
  
-   [Multithreading: Verwendungsweise der Synchronisierungsklassen](../parallel/multithreading-how-to-use-the-synchronization-classes.md)  
  
-   [Multithreading: Beenden von Threads](../parallel/multithreading-terminating-threads.md)  
  
-   [Multithreading: Tipps für die Programmierung](../parallel/multithreading-programming-tips.md)  
  
-   [Multithreading: Verwendungsmöglichkeiten der Synchronisierungsklassen](../parallel/multithreading-when-to-use-the-synchronization-classes.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreadingunterstützung für älteren Code (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)