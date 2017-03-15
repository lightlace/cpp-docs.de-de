---
title: "Unterst&#252;tzungsklassen f&#252;r Anwendungen und Threads | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.support"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsobjekte [C++], Threadunterstützungsklassen"
  - "Anwendungsunterstützungsklassen [C++]"
  - "Sperrklassen"
  - "Synchronisierungsklassen, Multithreading"
  - "Threadunterstützungsklassen [C++]"
  - "Threading [MFC]"
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Unterst&#252;tzungsklassen f&#252;r Anwendungen und Threads
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede Anwendung verfügt über ein und nur ein Anwendungsobjekt; dieses Objekt koordiniert andere Objekte im ausgeführten Programm und wird von `CWinApp` abgeleitet.  
  
 Die MFC\-Bibliothek \(Microsoft Foundation Class \(MFC\) unterstützt mehrere Threads der Ausführung innerhalb einer Anwendung.  Alle Anwendungen müssen mindestens einen Thread verfügen; der Thread, der vom `CWinApp`\-Objekt verwendet wird, ist dieser primäre Thread.  
  
 `CWinThread` kapselt einen Teil der Durchzugsfunktionen des Betriebssystems.  Um mithilfe mehrerer Threads zu vereinfachen, MFC stellt auch Synchronisierungsobjektklassen um Schnittstelle eine C\+\+\-Klasse zu Win32\-Synchronisierungsobjekten bereitzustellen.  
  
## Anwendungs\- und Thread\-Klassen  
 [CWinApp](../mfc/reference/cwinapp-class.md)  
 Kapselt den Code, um die Anwendung zu initialisieren, auszuführen und zu beenden.  Sie leiten das Anwendungsobjekt von dieser Klasse.  
  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 Die Basisklasse für alle Threads.  Verwenden Sie direkt oder leiten Sie eine Klasse von `CWinThread`, wenn der Thread Benutzeroberflächeaufgaben ausführt.  `CWinApp` ist von `CWinThread` abgeleitet.  
  
## Synchronisierungsobjekt\-Klassen  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 Basisklasse der Synchronisierungsobjektklassen.  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 Eine Synchronisierungsklasse, die nur einen Thread innerhalb eines einzelnen Prozesses ermöglicht, auf ein Objekt zugreifen.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 Eine Synchronisierungsklasse, die zwischen einem zulässt und einer angegebenen maximalen Anzahl gleichzeitigen Zugriffen auf ein Objekt.  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 Eine Synchronisierungsklasse, die nur einen Thread innerhalb jeder Zahl Prozesse ermöglicht, auf ein Objekt zugreifen.  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 Eine Synchronisierungsklasse, die eine Anwendung benachrichtigt, wenn ein Ereignis eintritt.  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 Wird in den Memberfunktionen von threadsicheren Klassen, um in einem Synchronisierungsobjekt zu sperren.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 Wird in den Memberfunktionen von threadsicheren Klassen, die auf einem oder mehreren Synchronisierungsobjekten aus einem Array Synchronisierungsobjekten zu sperren.  
  
## Verwandte Klassen  
 [CCommandLineInfo](../mfc/reference/ccommandlineinfo-class.md)  
 Analysiert die Befehlszeile, mit der das Programm gestartet wurde.  
  
 [CWaitCursor](../mfc/reference/cwaitcursor-class.md)  
 Setzt einen Wartecursor auf den Bildschirm.  Wird während der längeren Vorgänge.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Behandelt dauerhafte Speicherung von Daten des angedockten Zustands für Steuerleisten.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 Führt die zuletzt verwendete \(MRU\)\- Dateiliste.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)