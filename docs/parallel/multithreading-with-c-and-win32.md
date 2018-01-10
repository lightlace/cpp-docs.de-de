---
title: Multithreading bei C und Win32 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 30c7833a4df80669b6223f1fe6b1ccceed0257cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-with-c-and-win32"></a>Multithreading bei C und Win32
Microsoft Visual C++ bietet Unterstützung zum Erstellen von Multithreadanwendungen mit Microsoft Windows: Windows XP, Windows 2000, Windows NT, Windows Me und Windows 98. Wenn Ihre Anwendung mehrere Aktivitäten verwalten muss, z. B. gleichzeitige Tastatur- und Mauseingaben, sollten Sie die Verwendung mehrerer Threads in Erwägung ziehen. Dabei verarbeitet ein Thread die Tastatureingabe, während ein zweiter Thread Mausaktivitäten filtert. Ein dritter Thread kann die Bildschirmanzeige auf Basis der Daten aus den Maus- und Tastaturthreads aktualisieren. Gleichzeitig können andere Threads auf Datenträgerdateien zugreifen oder Daten von einem Kommunikationsanschluss abrufen.  
  
 Visual C++ ermöglicht zwei Arten der Programmierung mit mehreren Threads: mit der MFC-Bibliothek (Microsoft Foundation Classes) oder der C-Laufzeitbibliothek und der Win32-API. Informationen zum Erstellen von Multithreadanwendungen mit MFC finden Sie unter [Multithreading mit C++ und MFC](../parallel/multithreading-with-cpp-and-mfc.md) nach dem Lesen der folgenden Themen über Multithreading in c  
  
 In diesen Themen werden die Funktionen von Visual C++ erläutert, die die Erstellung von Multithreadprogrammen unterstützen.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Was multithreading geht es um](../parallel/multithread-programs.md)  
  
-   [Bibliotheksunterstützung für multithreading](../parallel/library-support-for-multithreading.md)  
  
-   [Includedateien für multithreading](../parallel/include-files-for-multithreading.md)  
  
-   [C Run-Time Library-Funktionen zur Threadsteuerung](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [Beispiel-Multithreadprogramm C](../parallel/sample-multithread-c-program.md)  
  
-   [Schreiben von Win32-Multithreadprogrammen](../parallel/writing-a-multithreaded-win32-program.md)  
  
-   [Kompilieren und Binden von Multithreadprogrammen](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [Vermeiden von Problembereichen bei Multithreadprogrammen](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
-   [Lokaler Threadspeicher (TLS)](../parallel/thread-local-storage-tls.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreadingunterstützung für älteren Code (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)