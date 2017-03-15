---
title: "Multithreading bei C und Win32 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Multithreading [C++], C und Win32"
  - "Threading [C]"
  - "Threading [C++], C und Win32"
  - "Visual C, Multithreading"
  - "Win32 [C++], Multithreading"
  - "Win32-Anwendungen [C++], Multithreading"
  - "Windows-API [C++], Multithreading"
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Multithreading bei C und Win32
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Visual C\+\+ bietet Unterstützung für die Entwicklung von Multithreadanwendungen mit Microsoft Windows: Windows XP, Windows 2000, Windows NT, Windows Me und Windows 98.  Wenn Ihre Anwendung mehrere Aktivitäten verwalten muss, z. B. gleichzeitige Tastatur\- und Mauseingaben, sollten Sie die Verwendung mehrerer Threads in Erwägung ziehen.  Dabei verarbeitet ein Thread die Tastatureingabe, während ein zweiter Thread Mausaktivitäten filtert.  Ein dritter Thread kann die Bildschirmanzeige auf Basis der Daten aus den Maus\- und Tastaturthreads aktualisieren.  Gleichzeitig können andere Threads auf Datenträgerdateien zugreifen oder Daten von einem Kommunikationsanschluss abrufen.  
  
 Visual C\+\+ ermöglicht zwei Arten der Programmierung mit mehreren Threads: mit der MFC\-Bibliothek \(Microsoft Foundation Classes\) oder der C\-Laufzeitbibliothek und der Win32\-API.  Wenn Sie die folgenden Themen über Multithreading in C gelesen haben, finden Sie weitere Informationen über das Erstellen von Multithreadanwendungen mit MFC unter [Multithreading mit C\+\+ und MFC](../parallel/multithreading-with-cpp-and-mfc.md).  
  
 In diesen Themen werden die Features von Visual C\+\+ erläutert, die die Erstellung von Multithreadprogrammen unterstützen.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Multithreadprogramme](../parallel/multithread-programs.md)  
  
-   [Bibliotheksunterstützung für Multithreading](../parallel/library-support-for-multithreading.md)  
  
-   [Includedateien für Multithreading](../parallel/include-files-for-multithreading.md)  
  
-   [Funktionen der C\-Laufzeitbibliothek zur Threadsteuerung](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [Beispiel für ein C\-Multithreadprogramm](../parallel/sample-multithread-c-program.md)  
  
-   [Schreiben von Win32\-Multithreadprogrammen](../parallel/writing-a-multithreaded-win32-program.md)  
  
-   [Kompilieren und Binden von Multithreadprogrammen](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [Vermeiden von Problembereichen bei Multithreadprogrammen](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
-   [Lokaler Threadspeicher \(TLS\)](../parallel/thread-local-storage-tls.md)  
  
## Siehe auch  
 [Multithreadingunterstützung für älteren Code \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)