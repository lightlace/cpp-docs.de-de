---
title: "Multithreadingunterstützung für älteren Code (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d949c1ff19be6f3b89673753fdaccc2996bbef36
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Multithreadingunterstützung für älteren Code (Visual C++)
Mit Visual C++ können mehrere parallele Ausführungsthreads gleichzeitig ausgeführt werden. Mit Multithreading können Sie Tasks im Hintergrund starten, gleichzeitige Eingabestreams sowie eine Benutzeroberfläche verwalten u. v. m.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)  
 Bietet Unterstützung beim Erstellen von Multithreadanwendungen mit Microsoft Windows.  
  
 [Multithreading mit C++ und MFC](../parallel/multithreading-with-cpp-and-mfc.md)  
 Definiert Prozesse und Threads und erörtert, wie Multithreading in MFC gehandhabt wird.  
  
 [Multithreading und Gebietsschemas](../parallel/multithreading-and-locales.md)  
 Erläutert Probleme, die auftreten, wenn die Gebietsschema-Funktionen der C-Laufzeitbibliothek und der C++-Standardbibliothek in einer Multithreadanwendung zu verwenden.  
  
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
  
 [(NOTINBUILD) Methodiken der Visual C++-Programmierung](http://msdn.microsoft.com/en-us/0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Enthält Links zu Themen, die grundlegende Informationen über Visual C++-Bibliotheken bieten, sowie zu Themen, in denen unterschiedliche Codierungstechnologien und -verfahren erläutert werden.