---
title: Anwendung und Thread-Unterstützungsklassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.support
dev_langs:
- C++
helpviewer_keywords:
- application objects [MFC], thread support classes
- lock classes [MFC]
- thread support classes [MFC]
- threading [MFC]
- synchronization classes [MFC], multithreading
- application support classes [MFC]
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9f3877cf85e369756b15d565af1481fd6d258df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="application-and-thread-support-classes"></a>Klassen zur Anwendungs- und Threadunterstützung
Jede Anwendung hat nur eine Application-Objekt. Dieses Objekt andere Objekte in der ausgeführten Anwendung koordiniert und stammt aus `CWinApp`.  
  
 Die Microsoft Foundation Class (MFC)-Bibliothek unterstützt mehrere Ausführungsthreads innerhalb einer Anwendung. Alle Anwendungen müssen mindestens einen Thread verfügen; der Thread verwendet werden, indem Sie Ihre `CWinApp` Objekt ist dieser primäre Thread.  
  
 `CWinThread` Kapselt einen Teil des Betriebssystems threading-Funktionen. Um den Einsatz mehrerer Threads einfacher zu gestalten, MFC auch Synchronisierung stellt Objektklassen bereit, um eine C++-Schnittstelle, Win32-Synchronisierungsobjekte bereitzustellen.  
  
## <a name="application-and-thread-classes"></a>Klassen zur Anwendungs- und Threads  
 [CWinApp](../mfc/reference/cwinapp-class.md)  
 Kapselt den Code zum Initialisieren, auszuführen und die Anwendung beenden. Das Application-Objekt wird von dieser Klasse abgeleitet werden.  
  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 Die Basisklasse für alle Threads. Direkt verwenden, oder leiten Sie eine Klasse von `CWinThread` , wenn der Thread der Benutzeroberfläche Funktionen ausführt. `CWinApp` wird von `CWinThread` abgeleitet.  
  
## <a name="synchronization-object-classes"></a>Synchronisierungsklassen-Objekt  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 Die Basisklasse von Synchronisierungsklassen-Objekt.  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 Eine Synchronisierungsklasse, die nur jeweils einem Thread innerhalb eines einzelnen Prozesses Zugriff auf ein Objekt ermöglicht.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 Eine Synchronisierungsklasse, die zwischen 1 und eine angegebene Höchstanzahl von gleichzeitige Zugriffe auf ein Objekt ermöglicht.  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 Eine Synchronisierungsklasse, die nur einen Thread in eine beliebige Anzahl von Prozessen an, auf ein Objekt zugreifen kann.  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 Eine Synchronisierungsklasse, die eine Anwendung benachrichtigt, wenn ein Ereignis aufgetreten ist.  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 In Memberfunktionen von threadsicheren Klassen auf ein Synchronisierungsobjekt, das zum Sperren verwendet.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 In Memberfunktionen von threadsicheren Klassen verwendet, auf eine oder mehrere Synchronisierungsobjekte aus einem Array von Synchronisierungsobjekten gesperrt.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 [CCommandLineInfo](../mfc/reference/ccommandlineinfo-class.md)  
 Analysiert die Befehlszeile, mit denen das Programm gestartet wurde.  
  
 [CWaitCursor](../mfc/reference/cwaitcursor-class.md)  
 Setzt einen Wartecursor auf dem Bildschirm an. Während der langwierige Operationen verwendet.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Verarbeitet die persistente Speicherung von Zustandsdaten Steuerleisten andocken.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 Verwaltet die zuletzt verwendeten Dateiliste (MRU).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

