---
title: "Multithreading: Tipps f&#252;r die Programmierung"
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
  - "Zugriffssteuerung [C++], Multithreading"
  - "Kommunikation [C++], Zwischen Threads"
  - "Kritische Abschnitte [C++]"
  - "Handlezuordnungen [C++]"
  - "Multithreading [C++], Programmiertipps"
  - "MFC-fremde Threads [C++]"
  - "Objekte [C++], Mehrere Threads und"
  - "[C++]-Programmierung, Multithread"
  - "Synchronisierung [C++], Multithreading"
  - "Threading [C++], Bewährte Methoden"
  - "Threading [MFC], Programmiertipps"
  - "Problembehandlung [C++], Multithreading"
  - "Windows-Handlezuordnungen [C++]"
ms.assetid: ad14cc70-c91c-4c24-942f-13a75e58bf8a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading: Tipps f&#252;r die Programmierung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In Multithreadanwendungen müssen Sie beim Zugriff auf Daten größere Vorsicht walten lassen als in Singlethreadanwendungen.  Da in Multithreadanwendungen mehrere unabhängige Ausführungspfade gleichzeitig verwendet werden, müssen die Algorithmen, die Daten oder beide darüber informiert sein, dass Daten möglicherweise von mehreren Threads gleichzeitig verwendet werden.  In diesem Thema werden die Methoden beschrieben, mit denen potenzielle Probleme bei der Programmierung von Multithreadanwendungen mit Microsoft Foundation Class Library \(MFC\) vermieden werden können.  
  
-   [Zugriff auf Objekte durch mehrere Threads](#_core_accessing_objects_from_multiple_threads)  
  
-   [Zugriff auf MFC\-Objekte durch MFC\-fremde Threads](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
-   [Windows\-Handlezuordnungen](#_core_windows_handle_maps)  
  
-   [Kommunikation zwischen Threads](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a> Zugriff auf Objekte durch mehrere Threads  
 Aus Gründen der Leistung und des Umfangs sind MFC\-Objekte auf Objektebene nicht threadsicher, auf Klassenebene hingegen schon.  Dies bedeutet, dass zwei separate Threads zwei unterschiedliche `CString`\-Objekte bearbeiten können, dasselbe `CString`\-Objekt jedoch nicht von zwei Threads bearbeitet werden kann.  Wenn es unumgänglich ist, dass mehrere Threads dasselbe Objekt bearbeiten, nutzen Sie die entsprechenden Win32\-Synchronisierungsmechanismen \(z. B. kritische Abschnitte\), um Zugriffe dieser Art sicher zu gestalten.  Weitere Informationen über kritische Abschnitte und andere verwandte Objekte finden Sie im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] unter [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353).  
  
 In der Klassenbibliothek werden kritische Abschnitte intern zum Schutz globaler Datenstrukturen verwendet. Diese Datenstrukturen werden z. B. von der Debugspeicherbelegung verwendet.  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> Zugriff auf MFC\-Objekte durch MFC\-fremde Threads  
 Wenn Sie mit einer Multithreadanwendung arbeiten, in der ein Thread nicht mithilfe eines [CWinThread](../../mfc/reference/cwinthread-class.md)\-Objekts erstellt wird, ist der Zugriff auf andere MFC\-Objekte von diesem Thread aus nicht möglich.  Wenn Sie also von einem sekundären Thread aus auf ein beliebiges MFC\-Objekt zugreifen möchten, müssen Sie zur Erstellung dieses Threads eine der Methoden verwenden, die im Thema [Multithreading: Erstellen von Benutzeroberflächenthreads](../../parallel/multithreading-creating-user-interface-threads.md) bzw. [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md) beschrieben werden.  Nur mithilfe dieser Methoden kann die Klassenbibliothek die internen Variablen initialisieren, die zur Behandlung von Multithreadanwendungen erforderlich sind.  
  
##  <a name="_core_windows_handle_maps"></a> Windows\-Handlezuordnungen  
 Grundsätzlich kann ein Thread nur auf die von ihm erstellten MFC\-Objekte zugreifen.  Der Grund hierfür ist, dass temporäre und permanente Windows\-Handlezuordnungen im lokalen Threadspeicher verwaltet werden. Auf diese Weise soll der gleichzeitige Zugriff von mehreren Threads aus verhindert werden.  Ein Arbeitsthread kann z. B. keine Berechnung durchführen und anschließend die `UpdateAllViews`\-Memberfunktion eines Dokuments aufrufen, um die Fenster zu ändern, die Ansichten der neuen Daten enthalten.  Dies hat keinerlei Auswirkung, da sich die Zuordnung von `CWnd`\-Objekten zu `HWND`s lediglich auf den primären Thread bezieht.  Dies bedeutet, dass ein bestimmter Thread möglicherweise eine Zuordnung eines Windows\-Handles zu einem C\+\+\-Objekt aufweist, ein anderer Thread dasselbe Handle jedoch unter Umständen einem anderen C\+\+\-Objekt zuordnet.  Änderungen, die in einem Thread vorgenommen wurden, werden in einem anderen Thread nicht widergespiegelt.  
  
 Es gibt verschiedene Methoden zur Umgehung dieses Problems:  Die erste Methode ist die Übergabe eines individuellen Handles \(z. B. `HWND`\) an den Arbeitsthread, anstelle von C\+\+\-Objekten.  Der Arbeitsthread fügt anschließend diese Objekte seiner temporären Zuordnung hinzu, indem er die entsprechende `FromHandle`\-Memberfunktion aufruft.  Sie haben auch die Möglichkeit, das Objekt der permanenten Zuordnung des Threads durch Aufruf von **Attach** hinzuzufügen; dies sollten Sie jedoch nur tun, wenn Sie mit absoluter Sicherheit wissen, dass das Objekt länger als der Thread vorhanden sein wird.  
  
 Sie können auch neue benutzerdefinierte Meldungen erstellen, die den unterschiedlichen Aufgaben entsprechen, die von den Arbeitsthreads durchgeführt werden, und diese Meldungen mit **::PostMessage** im Hauptfenster der Anwendung bereitstellen.  Diese Kommunikationsmethode ist mit dem Informationsaustausch zwischen zwei Anwendungen vergleichbar; der Unterschied besteht darin, dass beide Threads im selben Adressbereich ausgeführt werden.  
  
 Weitere Informationen über Handlezuordnungen finden Sie unter [Technischer Hinweis 3](../../mfc/tn003-mapping-of-windows-handles-to-objects.md).  Weitere Informationen über den lokalen Threadspeicher finden Sie im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] unter [Thread Local Storage](http://msdn.microsoft.com/library/windows/desktop/ms686749) und [Using Thread Local Storage](http://msdn.microsoft.com/library/windows/desktop/ms686991).  
  
##  <a name="_core_communicating_between_threads"></a> Kommunikation zwischen Threads  
 MFC enthält eine Anzahl von Klassen, die es Threads ermöglichen, den Zugriff auf Objekte zu synchronisieren und so die Threadsicherheit aufrechtzuerhalten.  Die Verwendung dieser Klassen wird in den Themen [Multithreading: Verwendungsweise der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md) und [Multithreading: Verwendungsmöglichkeiten der Synchronisierungsklassen](../../parallel/multithreading-when-to-use-the-synchronization-classes.md) erläutert.  Weitere Informationen über diese Objekte finden Sie im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] unter [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353).  
  
## Siehe auch  
 [Multithreading mit C\+\+ und MFC](../../parallel/multithreading-with-cpp-and-mfc.md)