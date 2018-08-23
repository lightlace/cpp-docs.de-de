---
title: 'Multithreading: Tipps Programmierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ad830117323aef807fcebc1ef61b4dfb1900bd9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591310"
---
# <a name="multithreading-programming-tips"></a>Multithreading: Tipps für die Programmierung
In Multithreadanwendungen müssen Sie beim Zugriff auf Daten größere Vorsicht walten lassen als in Singlethreadanwendungen. Da in Multithreadanwendungen mehrere unabhängige Ausführungspfade gleichzeitig verwendet werden, müssen die Algorithmen, die Daten oder beide darüber informiert sein, dass Daten möglicherweise von mehreren Threads gleichzeitig verwendet werden. In diesem Thema werden die Methoden beschrieben, mit denen potenzielle Probleme bei der Programmierung von Multithreadanwendungen mit Microsoft Foundation Class Library (MFC) vermieden werden können.  
  
- [Zugreifen auf Objekte von mehreren Threads](#_core_accessing_objects_from_multiple_threads)  
  
- [Zugriff auf MFC-Objekte durch MFC-fremde Threads](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
- [Windows-Handlezuordnungen](#_core_windows_handle_maps)  
  
- [Kommunikation zwischen Threads](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a> Zugreifen auf Objekte von mehreren Threads  
 
Aus Gründen der Leistung und des Umfangs sind MFC-Objekte auf Objektebene nicht threadsicher, auf Klassenebene hingegen schon. Dies bedeutet, dass zwei separate Threads zwei unterschiedliche `CString`-Objekte bearbeiten können, dasselbe `CString`-Objekt jedoch nicht von zwei Threads bearbeitet werden kann. Wenn es unumgänglich ist, dass mehrere Threads dasselbe Objekt bearbeiten, nutzen Sie die entsprechenden Win32-Synchronisierungsmechanismen (z. B. kritische Abschnitte), um Zugriffe dieser Art sicher zu gestalten. Weitere Informationen über kritische Abschnitte und andere verwandte Objekte finden Sie unter [Synchronisierung](http://msdn.microsoft.com/library/windows/desktop/ms686353) im Windows SDK.  
  
In der Klassenbibliothek werden kritische Abschnitte intern zum Schutz globaler Datenstrukturen verwendet. Diese Datenstrukturen werden z. B. von der Debugspeicherbelegung verwendet.  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> Zugriff auf MFC-Objekte durch MFC-fremde Threads  
 
Wenn Sie eine Multithreadanwendung, die einen Thread auf eine Weise verfügen als mithilfe von erstellt eine [CWinThread](../mfc/reference/cwinthread-class.md) Objekt, Sie können nicht auf andere MFC-Objekte zugreifen, von diesem Thread aus. Also, wenn Sie ein MFC-Objekt von einem sekundären Thread zugreifen möchten, Sie müssen zur Erstellung dieses Threads mit einer der Methoden aus [Multithreading: Erstellen von Benutzeroberflächenthreads](../parallel/multithreading-creating-user-interface-threads.md) oder [Multithreading: Erstellen von Arbeitsthreads](../parallel/multithreading-creating-worker-threads.md). Nur mithilfe dieser Methoden kann die Klassenbibliothek die internen Variablen initialisieren, die zur Behandlung von Multithreadanwendungen erforderlich sind.  
  
##  <a name="_core_windows_handle_maps"></a> Windows-Handlezuordnungen  
 
Grundsätzlich kann ein Thread nur auf die von ihm erstellten MFC-Objekte zugreifen. Der Grund hierfür ist, dass temporäre und permanente Windows-Handlezuordnungen im threadlokalen Speicher verwaltet werden. Auf diese Weise soll der gleichzeitige Zugriff von mehreren Threads aus verhindert werden. Ein Arbeitsthread kann z. B. keine Berechnung durchführen und anschließend die `UpdateAllViews`-Memberfunktion eines Dokuments aufrufen, um die Fenster zu ändern, die Ansichten der neuen Daten enthalten. Dies wirkt sich nicht, da die Zuordnung von `CWnd` Objekte HWNDs wird lokal auf dem primären Thread. Dies bedeutet, dass ein bestimmter Thread möglicherweise eine Zuordnung eines Windows-Handles zu einem C++-Objekt aufweist, ein anderer Thread dasselbe Handle jedoch unter Umständen einem anderen C++-Objekt zuordnet. Änderungen, die in einem Thread vorgenommen wurden, werden in einem anderen Thread nicht widergespiegelt.  
  
Es gibt verschiedene Methoden zur Umgehung dieses Problems: Die erste ist Übergabe individuellen Handles (z. B. ein HWND) anstelle der C++-Objekte an den Arbeitsthread. Der Arbeitsthread fügt anschließend diese Objekte seiner temporären Zuordnung hinzu, indem er die entsprechende `FromHandle`-Memberfunktion aufruft. Sie könnten auch das Objekt des Threads permanenten Zuordnung hinzufügen, durch den Aufruf `Attach`, aber dies sollte erfolgen nur, wenn Sie garantiert, dass das Objekt länger als der Thread vorhanden ist.  
  
Erstellen neue benutzerdefinierte Meldungen für die verschiedenen Aufgaben den Arbeitsthreads durchgeführt werden, und diese Nachrichten an das Hauptfenster der Anwendung senden, eine andere Methode ist mit `::PostMessage`. Diese Kommunikationsmethode ist mit dem Informationsaustausch zwischen zwei Anwendungen vergleichbar; der Unterschied besteht darin, dass beide Threads im selben Adressbereich ausgeführt werden.  
  
Weitere Informationen über Handlezuordnungen finden Sie unter [technischer Hinweis 3](../mfc/tn003-mapping-of-windows-handles-to-objects.md). Weitere Informationen über den lokalen Threadspeicher finden Sie unter [threadlokalen Speicher](http://msdn.microsoft.com/library/windows/desktop/ms686749) und [Using Thread Local Storage](http://msdn.microsoft.com/library/windows/desktop/ms686991) im Windows SDK.  
  
##  <a name="_core_communicating_between_threads"></a> Kommunikation zwischen Threads  
 
MFC enthält eine Anzahl von Klassen, die es Threads ermöglichen, den Zugriff auf Objekte zu synchronisieren und so die Threadsicherheit aufrechtzuerhalten. Verwendung dieser Klassen finden Sie im [Multithreading: Gewusst wie: der Synchronisierungsklassen](../parallel/multithreading-how-to-use-the-synchronization-classes.md) und [Multithreading: Wenn der Synchronisierungsklassen](../parallel/multithreading-when-to-use-the-synchronization-classes.md). Weitere Informationen zu diesen Objekten finden Sie unter [Synchronisierung](http://msdn.microsoft.com/library/windows/desktop/ms686353) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  

[Multithreading mit C++ und MFC](../parallel/multithreading-with-cpp-and-mfc.md)