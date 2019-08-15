---
title: 'Multithreading: MFC-Programmiertipps'
ms.date: 08/27/2018
helpviewer_keywords:
- multithreading [C++], programming tips
- handle maps [C++]
- access control [C++], multithreading
- objects [C++], multiple threads and
- non-MFC threads [C++]
- threading [MFC], programming tips
- critical sections [C++]
- synchronization [C++], multithreading
- programming [C++], multithreaded
- communications [C++], between threads
- threading [C++], best practices
- troubleshooting [C++], multithreading
- Windows handle maps [C++]
ms.assetid: ad14cc70-c91c-4c24-942f-13a75e58bf8a
ms.openlocfilehash: deaf53d7b337fd33214bbcc4567e73bd33345d49
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511717"
---
# <a name="multithreading-mfc-programming-tips"></a>Multithreading: MFC-Programmiertipps

Multithreadanwendungen erfordern eine strengere Sorgfalt als Single Thread-Anwendungen, um sicherzustellen, dass Vorgänge in der vorgesehenen Reihenfolge erfolgen und dass alle Daten, auf die von mehreren Threads zugegriffen wird, nicht beschädigt sind. In diesem Thema werden die Methoden beschrieben, mit denen potenzielle Probleme bei der Programmierung von Multithreadanwendungen mit Microsoft Foundation Class Library (MFC) vermieden werden können.

- [Zugreifen auf Objekte aus mehreren Threads](#_core_accessing_objects_from_multiple_threads)

- [Zugreifen auf MFC-Objekte über nicht-MFC-Threads](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)

- [Windows Handle-Zuordnungen](#_core_windows_handle_maps)

- [Kommunikation zwischen Threads](#_core_communicating_between_threads)

##  <a name="_core_accessing_objects_from_multiple_threads"></a>Zugreifen auf Objekte aus mehreren Threads

MFC-Objekte sind nicht selbst Thread sicher. Zwei separate Threads können dasselbe Objekt nur dann bearbeiten, wenn Sie die MFC-Synchronisierungs Klassen und/oder die entsprechenden Win32-Synchronisierungs Objekte verwenden, wie z. b. kritische Abschnitte. Weitere Informationen zu kritischen Abschnitten und anderen verwandten Objekten finden Sie unter [Synchronisierung](/windows/win32/Sync/synchronization) in der Windows SDK.

In der Klassenbibliothek werden kritische Abschnitte intern zum Schutz globaler Datenstrukturen verwendet. Diese Datenstrukturen werden z. B. von der Debugspeicherbelegung verwendet.

##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a>Zugreifen auf MFC-Objekte über nicht-MFC-Threads

Wenn Sie über eine Multithreadanwendung verfügen, von der ein Thread nicht mit einem [CWinThread](../mfc/reference/cwinthread-class.md) -Objekt erstellt wird, können Sie von diesem Thread aus nicht auf andere MFC-Objekte zugreifen. Anders ausgedrückt: Wenn Sie von einem sekundären Thread aus auf ein MFC-Objekt zugreifen möchten, müssen Sie diesen Thread mit einer der Methoden erstellen, [die unter Multithreading beschrieben wird: Erstellen von Benutzeroberflächenthreads](multithreading-creating-user-interface-threads.md) oder [Multithreading: Erstellen von Arbeitsthreads](multithreading-creating-worker-threads.md). Nur mithilfe dieser Methoden kann die Klassenbibliothek die internen Variablen initialisieren, die zur Behandlung von Multithreadanwendungen erforderlich sind.

##  <a name="_core_windows_handle_maps"></a>Windows Handle-Zuordnungen

Grundsätzlich kann ein Thread nur auf die von ihm erstellten MFC-Objekte zugreifen. Der Grund hierfür ist, dass temporäre und permanente Windows-Handlezuordnungen im lokalen Threadspeicher verwaltet werden. Auf diese Weise soll der gleichzeitige Zugriff von mehreren Threads aus verhindert werden. Ein Arbeitsthread kann z. B. keine Berechnung durchführen und anschließend die `UpdateAllViews`-Memberfunktion eines Dokuments aufrufen, um die Fenster zu ändern, die Ansichten der neuen Daten enthalten. Dies hat keinerlei Auswirkungen, da die Zuordnung von `CWnd` Objekten zu HWNDs lokal zum primären Thread erfolgt. Dies bedeutet, dass ein bestimmter Thread möglicherweise eine Zuordnung eines Windows-Handles zu einem C++-Objekt aufweist, ein anderer Thread dasselbe Handle jedoch unter Umständen einem anderen C++-Objekt zuordnet. Änderungen, die in einem Thread vorgenommen wurden, werden in einem anderen Thread nicht widergespiegelt.

Es gibt verschiedene Methoden zur Umgehung dieses Problems: Der erste Schritt besteht darin, einzelne Handles (z. b. ein HWND C++ ) anstelle von Objekten an den Arbeits Thread zu übergeben. Der Arbeitsthread fügt anschließend diese Objekte seiner temporären Zuordnung hinzu, indem er die entsprechende `FromHandle`-Memberfunktion aufruft. Sie können das Objekt auch der permanenten Zuordnung des Threads hinzufügen, indem `Attach`Sie aufrufen, aber dies sollte nur erfolgen, wenn Sie sicher sind, dass das Objekt länger als der Thread vorhanden ist.

Eine andere Methode besteht darin, neue benutzerdefinierte Meldungen zu erstellen, die den unterschiedlichen Aufgaben entsprechen, die von den Arbeitsthreads ausgeführt werden, und diese Nachrichten `::PostMessage`mithilfe von im Hauptfenster der Anwendung zu veröffentlichen. Diese Kommunikationsmethode ist mit dem Informationsaustausch zwischen zwei Anwendungen vergleichbar; der Unterschied besteht darin, dass beide Threads im selben Adressbereich ausgeführt werden.

Weitere Informationen zu Handle-Karten finden [Sie unter Technical Note 3](../mfc/tn003-mapping-of-windows-handles-to-objects.md). Weitere Informationen zum lokalen Thread Speicher finden Sie unter [Thread lokaler Speicher](/windows/win32/ProcThread/thread-local-storage) und [Verwenden von lokalem Thread Speicher](/windows/win32/ProcThread/using-thread-local-storage) im Windows SDK.

##  <a name="_core_communicating_between_threads"></a>Kommunikation zwischen Threads

MFC enthält eine Anzahl von Klassen, die es Threads ermöglichen, den Zugriff auf Objekte zu synchronisieren und so die Threadsicherheit aufrechtzuerhalten. Die Verwendung dieser Klassen wird unter [Multithreading beschrieben: So verwenden Sie die Synchronisierungs](multithreading-how-to-use-the-synchronization-classes.md) Klassen [und das Multithreading: Verwendungszwecke der Synchronisierungs Klassen](multithreading-when-to-use-the-synchronization-classes.md) Weitere Informationen zu diesen Objekten finden Sie unter [Synchronisierung](/windows/win32/Sync/synchronization) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Multithreading mit C++ und MFC](multithreading-with-cpp-and-mfc.md)
