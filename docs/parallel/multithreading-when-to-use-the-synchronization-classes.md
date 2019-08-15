---
title: 'Multithreading: Verwendungszwecke der MFC-Synchronisierungs Klassen'
ms.date: 08/27/2018
helpviewer_keywords:
- threading [MFC], synchronization classes
- resources [C++], multithreading
- synchronization classes [C++]
- synchronization [C++], multithreading
- controlled resource access [C++]
- synchronization access classes [C++]
- threading [C++], synchronization
- multithreading [C++], synchronization classes
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
ms.openlocfilehash: cb68487e036093ce4718c39c18c9d1e75afe0f7c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511996"
---
# <a name="multithreading-when-to-use-the-mfc-synchronization-classes"></a>Multithreading: Verwendungszwecke der MFC-Synchronisierungs Klassen

Die Multithread-Klassen, die mit MFC bereitgestellt werden, lassen sich in zwei Kategorien unterteilen: Synchronisierungs Objekte ([CSyncObject](../mfc/reference/csyncobject-class.md), [CSemaphore](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [CCriticalSection](../mfc/reference/ccriticalsection-class.md)und [CEvent](../mfc/reference/cevent-class.md)) und Synchronisierungs Zugriffs Objekte ([ CMultiLock](../mfc/reference/cmultilock-class.md) und [CSingleLock](../mfc/reference/csinglelock-class.md)).

Synchronisierungs Klassen werden verwendet, wenn der Zugriff auf eine Ressource gesteuert werden muss, um die Integrität der Ressource sicherzustellen. Synchronisierungs Zugriffs Klassen werden verwendet, um Zugriff auf diese kontrollierten Ressourcen zu erhalten. In diesem Thema wird beschrieben, wann die einzelnen Klassen verwendet werden.

Um zu ermitteln, welche Synchronisierungs Klasse Sie verwenden sollten, stellen Sie sich die folgenden Fragen:

1. Muss die Anwendung darauf warten, dass etwas passiert, bevor Sie auf die Ressource zugreifen kann (z. b. müssen Daten von einem Kommunikationsport empfangen werden, bevor Sie in eine Datei geschrieben werden können)?

   Wenn ja, verwenden `CEvent`Sie.

2. Kann mehr als ein Thread in derselben Anwendung gleichzeitig auf diese Ressource zugreifen (z. b., wenn Ihre Anwendung bis zu fünf Fenster mit Ansichten auf demselben Dokument zulässt)?

   Wenn ja, verwenden `CSemaphore`Sie.

3. Kann mehr als eine Anwendung diese Ressource verwenden (z. b. befindet sich die Ressource in einer DLL)?

   Wenn ja, verwenden `CMutex`Sie.

   Wenn Nein, verwenden `CCriticalSection`Sie.

`CSyncObject`wird niemals direkt verwendet. Es ist die Basisklasse für die anderen vier Synchronisierungs Klassen.

## <a name="example-1-using-three-synchronization-classes"></a>Beispiel 1: Verwenden von drei Synchronisierungs Klassen

Als Beispiel wird eine Anwendung verwendet, in der eine verknüpfte Liste von Konten verwaltet wird. In dieser Anwendung können drei Konten in verschiedenen Fenstern untersucht werden, es kann jedoch nur jeweils ein Konto aktualisiert werden. Bei der Aktualisierung eines Kontos werden die aktualisierten Daten über das Netzwerk an ein Datenarchiv gesendet.

In dieser Beispielanwendung kommen alle drei Arten von Synchronisierungsklassen zum Einsatz. Da bis zu drei Konten gleichzeitig überprüft werden können, wird `CSemaphore` der Zugriff auf drei Ansichts Objekte mithilfe von beschränkt. Beim Versuch, ein viertes Konto anzuzeigen, wartet die Anwendung entweder, bis eines der ersten drei Fenster geschlossen wird, oder der Versuch schlägt fehl. Wenn ein Konto aktualisiert wird, verwendet `CCriticalSection` die Anwendung, um sicherzustellen, dass jeweils nur ein Konto aktualisiert wird. Nachdem das Update erfolgreich abgeschlossen wurde, `CEvent`signalisiert es, dass einen Thread freigibt, der auf die Signalisierung des Ereignisses wartet. Dieser Thread sendet die neuen Daten an das Datenarchiv.

## <a name="example-2-using-synchronization-access-classes"></a>Beispiel 2: Verwenden von Synchronisierungs Zugriffs Klassen

Die Auswahl der zu verwendenden Synchronisierungs zugriffsklasse ist noch einfacher. Wenn Ihre Anwendung nur den Zugriff auf eine einzelne kontrollierte Ressource betrifft, verwenden `CSingleLock`Sie. Wenn Sie Zugriff auf eine von einer Reihe von kontrollierten Ressourcen benötigen, verwenden `CMultiLock`Sie. In Beispiel 1 `CSingleLock` wurde verwendet, da in jedem Fall nur eine Ressource zu einem bestimmten Zeitpunkt benötigt wird.

Informationen zur Verwendung der Synchronisierungs Klassen finden [Sie unter Multithreading: Verwenden der Synchronisierungs Klassen](multithreading-how-to-use-the-synchronization-classes.md) Weitere Informationen zur Synchronisierung finden Sie unter [Synchronisierung](/windows/win32/Sync/synchronization) in der Windows SDK. Weitere Informationen zur Unterstützung von Multithreading in MFC finden Sie unter [Multithreading mit C++ und MFC](multithreading-with-cpp-and-mfc.md).

## <a name="see-also"></a>Siehe auch

[Multithreading mit C++ und MFC](multithreading-with-cpp-and-mfc.md)
