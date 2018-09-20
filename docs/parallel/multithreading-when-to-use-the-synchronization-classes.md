---
title: 'Multithreading: Wenn die MFC-Synchronisierungsklassen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 018623e9e6a093c4f86b8768e0fd5329f4ea3282
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443773"
---
# <a name="multithreading-when-to-use-the-mfc-synchronization-classes"></a>Multithreading: Wenn die MFC-Synchronisierungsklassen

Multithreadanwendungen mit MFC bereitgestellten Klassen, die in zwei Kategorien unterteilen: Synchronisierungsobjekte ([CSyncObject](../mfc/reference/csyncobject-class.md), [CSemaphore](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [ CCriticalSection](../mfc/reference/ccriticalsection-class.md), und [CEvent](../mfc/reference/cevent-class.md)) und die Synchronisierungsobjekte für den Zugriff ([CMultiLock](../mfc/reference/cmultilock-class.md) und [CSingleLock](../mfc/reference/csinglelock-class.md)).

Synchronisierungsklassen werden verwendet, wenn der Zugriff auf eine Ressource gesteuert werden muss, um die Integrität der Ressource sicherzustellen. Synchronisierungszugriffsklassen werden verwendet, um den Zugriff auf diese gesteuerten Ressourcen zu erhalten. In diesem Thema wird beschrieben, wann auf jede Klasse zu verwenden.

Um welche Synchronisierungsklasse zu ermitteln, sollten Sie verwenden, stellen Sie die folgende Reihe von Fragen:

1. Muss die Anwendung warten kann, bevor sie die Ressource zugreifen kann (z. B. Daten müssen empfangen werden von einem Kommunikationsanschluss bevor es in eine Datei geschrieben werden kann)?

     Wenn Ja, verwenden Sie `CEvent`.

2. Kann mehrere Threads innerhalb der gleichen Anwendungszugriff dieser Ressource gleichzeitig (z. B. für Ihre Anwendung kann bis zu fünf Windows mit Ansichten des gleichen Dokuments)?

     Wenn Ja, verwenden Sie `CSemaphore`.

3. Kann mehr als eine Anwendung verwenden Sie diese Ressource (z. B. die Ressource wird in eine DLL-Datei)?

     Wenn Ja, verwenden Sie `CMutex`.

     Wenn Nein, verwenden Sie `CCriticalSection`.

`CSyncObject` wird nie direkt verwendet werden. Es ist die Basisklasse für die anderen vier Synchronisierungsklassen.

## <a name="example-1-using-three-synchronization-classes"></a>Beispiel 1: Verwenden von drei Synchronisierungsklassen

Als Beispiel wird eine Anwendung verwendet, in der eine verknüpfte Liste von Konten verwaltet wird. In dieser Anwendung können drei Konten in verschiedenen Fenstern untersucht werden, es kann jedoch nur jeweils ein Konto aktualisiert werden. Bei der Aktualisierung eines Kontos werden die aktualisierten Daten über das Netzwerk an ein Datenarchiv gesendet.

In dieser Beispielanwendung kommen alle drei Arten von Synchronisierungsklassen zum Einsatz. Da bis zu drei Konten gleichzeitig untersucht werden können, verwendet es `CSemaphore` Zugriff auf drei Ansichtsobjekte beschränkt. Beim Versuch, ein viertes Konto anzuzeigen, wartet die Anwendung entweder, bis eines der ersten drei Fenster geschlossen wird, oder der Versuch schlägt fehl. Wenn ein Konto aktualisiert wird, um die Anwendung verwendet `CCriticalSection` , stellen Sie sicher, dass nur ein Konto zu einem Zeitpunkt aktualisiert wird. Nach erfolgreicher Aktualisierung signalisiert sie `CEvent`, die einen Thread für das Ereignis signalisiert wird, gibt. Dieser Thread sendet die neuen Daten an das Datenarchiv.

## <a name="example-2-using-synchronization-access-classes"></a>Beispiel 2: Verwenden von Synchronisierungszugriffsklassen

Auswählen der Synchronisierungsklasse Zugriff verwenden, sogar noch einfacher wird. Wenn Ihre Anwendung mit dem Zugriff auf nur eine einzelne gesteuerte Ressource geht, verwenden Sie `CSingleLock`. Wenn sie Zugriff auf eine beliebige Anzahl von gesteuerten Ressourcen erforderlich ist, verwenden Sie `CMultiLock`. In Beispiel 1 `CSingleLock` verwendet worden wären, da jeweils nur eine Ressource zu einem bestimmten Zeitpunkt erforderlich ist.

Weitere Informationen zur Verwendung von Synchronisierungsklassen finden Sie unter [Multithreading: Gewusst wie: der Synchronisierungsklassen](multithreading-how-to-use-the-synchronization-classes.md). Weitere Informationen zur Synchronisierung finden Sie unter [Synchronisierung](/windows/desktop/Sync/synchronization) im Windows SDK. Weitere Informationen zur Unterstützung von multithreading in MFC finden Sie unter [Multithreading mit C++ und MFC](multithreading-with-cpp-and-mfc.md).

## <a name="see-also"></a>Siehe auch

[Multithreading mit C++ und MFC](multithreading-with-cpp-and-mfc.md)