---
title: Klassen zur Anwendungs- und Threadunterstützung
ms.date: 11/04/2016
f1_keywords:
- vc.classes.support
helpviewer_keywords:
- application objects [MFC], thread support classes
- lock classes [MFC]
- thread support classes [MFC]
- threading [MFC]
- synchronization classes [MFC], multithreading
- application support classes [MFC]
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
ms.openlocfilehash: 667725a60fb0c907a9c2d017674f9d097d1f4946
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394675"
---
# <a name="application-and-thread-support-classes"></a>Klassen zur Anwendungs- und Threadunterstützung

Jede Anwendung verfügt über nur eine Application-Objekt; Dieses Objekt andere Objekte in das aktive Programm koordiniert und ergibt sich aus `CWinApp`.

Die Microsoft Foundation Class (MFC)-Bibliothek unterstützt mehrere Ausführungsthreads innerhalb einer Anwendung. Alle Anwendungen müssen mindestens einen Thread; der Thread ein, die Ihre `CWinApp` Objekt ist dieser primäre Thread.

`CWinThread` Kapselt einen Teil des Betriebssystems threading-Funktionen. Um mit mehreren Threads einfacher zu machen, MFC auch Synchronisierung stellt Objektklassen bereit, um eine C++-Schnittstelle, Win32-Synchronisierungsobjekte bereitzustellen.

## <a name="application-and-thread-classes"></a>Klassen zur Anwendungs- und Threads

[CWinApp](../mfc/reference/cwinapp-class.md)<br/>
Kapselt den Code zum Initialisieren und Ausführen die Anwendung zu beenden. Diese Klasse wird das Anwendungsobjekt abgeleitet werden.

[CWinThread](../mfc/reference/cwinthread-class.md)<br/>
Die Basisklasse für alle Threads. Direkt verwenden oder leiten eine Klasse von `CWinThread` , wenn der Thread der Funktionen der Benutzeroberfläche führt. `CWinApp` wird von `CWinThread` abgeleitet.

## <a name="synchronization-object-classes"></a>Synchronisierungsklassen-Objekt

[CSyncObject](../mfc/reference/csyncobject-class.md)<br/>
Basisklasse für die Synchronisierung Objektklassen.

[CCriticalSection](../mfc/reference/ccriticalsection-class.md)<br/>
Eine Synchronisierungsklasse, die nur ein Thread innerhalb eines einzelnen Prozesses Zugriff auf ein Objekt zulässt.

[CSemaphore](../mfc/reference/csemaphore-class.md)<br/>
Eine Synchronisierungsklasse, die zwischen 1 und eine angegebene Höchstanzahl von gleichzeitigen Zugriffen auf ein Objekt zulässt.

[CMutex](../mfc/reference/cmutex-class.md)<br/>
Eine Synchronisierungsklasse, die nur ein Thread in eine beliebige Anzahl von Prozessen auf ein Objekt zugreifen kann.

[CEvent](../mfc/reference/cevent-class.md)<br/>
Eine Synchronisierungsklasse, die eine Anwendung benachrichtigt, wenn ein Ereignis aufgetreten ist.

[CSingleLock](../mfc/reference/csinglelock-class.md)<br/>
Verwendet in Memberfunktionen von threadsicheren Klassen auf ein Synchronisierungsobjekt, das gesperrt.

[CMultiLock](../mfc/reference/cmultilock-class.md)<br/>
In Memberfunktionen von threadsicheren Klassen verwendet, um die Sperre auf eine oder mehrere Synchronisierungsobjekte aus einem Array von Synchronisierungsobjekten.

## <a name="related-classes"></a>Verwandte Klassen

[CCommandLineInfo](../mfc/reference/ccommandlineinfo-class.md)<br/>
Analysiert die Befehlszeile, mit denen das Programm gestartet wurde.

[CWaitCursor](../mfc/reference/cwaitcursor-class.md)<br/>
Fügt einen Wartecursor auf dem Bildschirm an. Während der Vorgänge mit langer Ausführungsdauer verwendet.

[CDockState](../mfc/reference/cdockstate-class.md)<br/>
Verarbeitet die dauerhafte Speicherung von Zustandsdaten für Schiebeleisten-Steuerelemente andocken.

[CRecentFileList](../mfc/reference/crecentfilelist-class.md)<br/>
Verwaltet die zuletzt verwendeten Dateiliste (MRU).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
