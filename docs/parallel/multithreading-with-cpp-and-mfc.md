---
title: "Multithreading mit C++ und MFC"
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
  - "CWinThread-Klasse, Zweck"
  - "MFC [C++], Multithreading"
  - "Multithreading [C++], MFC"
  - "Synchronisierung [C++], Multithreading"
  - "Synchronisierungsklassen [C++]"
  - "Threading [C++], MFC"
  - "Threading [MFC]"
  - "Threading [MFC], Informationen über das Threading"
  - "Benutzeroberflächenthreads [C++]"
  - "Arbeitsthreads [C++]"
ms.assetid: 979605f8-3988-44b5-ac9c-b8cce7fcce14
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading mit C++ und MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die MFC\-Bibliothek \(Microsoft Foundation Class\) bietet Unterstützung für Multithreadanwendungen.  In diesem Thema werden Prozesse und Threads sowie das MFC\-Multithreading beschrieben.  
  
 Ein Prozess ist eine ausführende Instanz einer Anwendung.  Wenn Sie z. B. auf das Symbol von Editor doppelklicken, starten Sie einen Prozess, der Editor ausführt.  
  
 Ein Thread ist ein Ausführungspfad innerhalb eines Prozesses.  Wenn Sie Editor starten, erstellt das Betriebssystem einen Prozess und beginnt mit der Ausführung des primären Threads dieses Prozesses.  Bei Beendung des Threads wird auch der Prozess beendet.  Dieser primäre Thread wird dem Betriebssystem durch den Startcode in Form einer Funktionsadresse zur Verfügung gestellt.  Normalerweise handelt es sich hierbei um die Adresse der **main**\-Funktion oder der `WinMain`\-Funktion.  
  
 Bei Bedarf können Sie in einer Anwendung zusätzliche Threads erstellen.  Dies bietet sich z. B. zur Verarbeitung von Hintergrund\- oder Verwaltungsaufgaben an. Auf diese Weise muss der Benutzer nicht auf deren Beendung warten.  Sämtliche Threads in MFC\-Anwendungen werden durch [CWinThread](../mfc/reference/cwinthread-class.md)\-Objekte dargestellt.  In den meisten Fällen ist die explizite Erstellung dieser Objekte nicht erforderlich. Sie können stattdessen die Framework\-Hilfsfunktion [AfxBeginThread](../Topic/AfxBeginThread.md) aufrufen, die das `CWinThread`\-Objekt für Sie erstellt.  
  
 In MFC werden zwei Threadtypen unterschieden: Benutzeroberflächenthreads und Arbeitsthreads.  Benutzeroberflächenthreads werden normalerweise verwendet, um Benutzereingaben zu behandeln und um auf vom Benutzer generierte Ereignisse und Meldungen zu reagieren.  Arbeitsthreads werden normalerweise verwendet, um Aufgaben durchzuführen, für die keine Benutzereingaben erforderlich sind \(z. B. Neuberechnungen\).  In der Win32\-API findet keine Unterscheidung zwischen Threadtypen statt; es muss lediglich die Startadresse des Threads bekannt sein, damit mit dessen Ausführung begonnen werden kann.  In MFC wird ein spezielles Verfahren zur Behandlung von Benutzeroberflächenthreads verwendet: es wird eine Meldungsverteilschleife für Ereignisse in der Benutzeroberfläche zur Verfügung gestellt.  `CWinApp` ist ein Beispiel für ein Benutzeroberflächenthread\-Objekt, da es von `CWinThread` abgeleitet ist und Ereignisse und Meldungen behandelt, die vom Benutzer generiert wurden.  
  
 In Fällen, in denen mehrere Threads auf dasselbe Objekt zugreifen müssen, sollten Sie besondere Vorsicht walten lassen.  Im Thema [Multithreading: Tipps für die Programmierung](../parallel/multithreading-programming-tips.md) werden Verfahren erläutert, mit denen Sie Probleme umgehen können, die in solchen Fällen möglicherweise auftreten.  Im Thema [Multithreading: Verwendungshinweise der Synchronisierungsklassen](../parallel/multithreading-how-to-use-the-synchronization-classes.md) finden Sie Hinweise zur Verwendung der Klassen, mit denen der Zugriff von mehreren Threads auf ein einzelnes Objekt synchronisiert werden kann.  
  
 Das Schreiben und Debuggen von Multithreadprogrammen ist naturgemäß ein komplexes und schwieriges Unterfangen, da Sie sicherstellen müssen, dass nur jeweils ein Thread auf die Objekte zugreift.  In den Themen zu Multithreading werden keine Grundlagen der Multithreadprogrammierung vermittelt. Sie erfahren lediglich, wie MFC in einem Multithreadprogramm verwendet werden kann.  In den in Visual C\+\+ enthaltenen MFC\-Multithreadbeispielen werden einige Möglichkeiten zum Hinzufügen weiterer Multithreadfunktionen sowie einige Win32\-APIs erläutert, die in MFC nicht enthalten sind. Sie sollten diese jedoch lediglich als Ausgangspunkt betrachten.  
  
 Weitere Informationen dazu, wie Prozesse und Threads vom Betriebssystem behandelt werden, finden Sie im [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] unter [Processes and Threads](http://msdn.microsoft.com/library/windows/desktop/ms684841).  
  
 Weitere Informationen zur Multithreadunterstützung in MFC finden Sie in folgenden Themen:  
  
-   [Multithreading: Erstellen von Benutzeroberflächenthreads](../parallel/multithreading-creating-user-interface-threads.md)  
  
-   [Multithreading: Erstellen von Arbeitsthreads](../parallel/multithreading-creating-worker-threads.md)  
  
-   [Multithreading: Verwendungsweise der Synchronisierungsklassen](../parallel/multithreading-how-to-use-the-synchronization-classes.md)  
  
-   [Multithreading: Beenden von Threads](../parallel/multithreading-terminating-threads.md)  
  
-   [Multithreading: Tipps für die Programmierung](../parallel/multithreading-programming-tips.md)  
  
-   [Multithreading: Verwendungsmöglichkeiten der Synchronisierungsklassen](../parallel/multithreading-when-to-use-the-synchronization-classes.md)  
  
## Siehe auch  
 [Multithreadingunterstützung für älteren Code \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)