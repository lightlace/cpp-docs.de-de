---
title: Multithreadingunterstützung für älteren Code (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b1b301186036460acc07a526267503da8b97678
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "43132101"
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Multithreadingunterstützung für älteren Code (Visual C++)
Mit Visual C++ können mehrere parallele Ausführungsthreads gleichzeitig ausgeführt werden. Mit Multithreading können Sie Aufgaben im Hintergrund starten, gleichzeitige Eingabestreams sowie eine Benutzeroberfläche verwalten u. v. m.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 
[Multithreading bei C und Win32](multithreading-with-c-and-win32.md)  
Bietet Unterstützung beim Erstellen von Multithreadanwendungen mit Microsoft Windows.  
  
[Multithreading mit C++ und MFC](multithreading-with-cpp-and-mfc.md)  
Definiert Prozesse und Threads und erörtert, wie Multithreading in MFC gehandhabt wird.  
  
[Multithreading und Gebietsschemas](multithreading-and-locales.md)  
Erläutert Probleme, die auftreten, wenn Sie die Gebietsschema-Funktionen von C-Laufzeitbibliothek und C++-Standardbibliothek in einer Multithreadanwendung zu verwenden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 
[CWinThread](../mfc/reference/cwinthread-class.md)  
Stellt einen Ausführungsthread innerhalb einer Anwendung dar.  
  
[CSyncObject](../mfc/reference/csyncobject-class.md)  
Beschreibt eine reine virtuelle Klasse, die die Funktionalität bereitstellt, die alle Synchronisierungsobjekte in Win32 gemeinsam haben.  
  
[CSemaphore](../mfc/reference/csemaphore-class.md)  
Stellt eine Semaphore dar - ein Synchronisierungsobjekt, das einer begrenzten Anzahl von Threads in einem oder mehreren Prozessen den Zugriff auf eine Ressource ermöglicht.  
  
[CMutex](../mfc/reference/cmutex-class.md)  
Stellt einen Mutex dar – ein Synchronisierungsobjekt, das Threads den einander ausschließenden Zugriff auf eine Ressource ermöglicht.  
  
[CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
Stellt einen kritischen Abschnitt dar - ein Synchronisierungsobjekt, das jeweils einem Thread den Zugriff auf eine Ressource oder einen Codeabschnitt ermöglicht.  
  
[CEvent](../mfc/reference/cevent-class.md)  
Stellt ein Ereignis dar - ein Synchronisierungsobjekt, das es einem Thread ermöglicht, einen anderen darüber zu benachrichtigen, dass ein Ereignis aufgetreten ist.  
  
[CMultiLock](../mfc/reference/cmultilock-class.md)  
Stellt den Mechanismus zur Zugriffssteuerung dar, mit dessen Hilfe der Zugriff auf Ressourcen in einem Multithreadprogramm gesteuert wird.  
  
[CSingleLock](../mfc/reference/csinglelock-class.md)  
Stellt den Mechanismus zur Zugriffssteuerung dar, mit dessen Hilfe der Zugriff auf Ressourcen in einem Multithreadprogramm gesteuert wird.  