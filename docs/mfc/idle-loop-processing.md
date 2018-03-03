---
title: Leerlaufschleifen-Verarbeitung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, background processing
- PeekMessage method [MFC], elsewhere than message loop
- PeekMessage method [MFC]
- MFC, messages
- messages [MFC], loops
- OnIdle method [MFC]
- processing [MFC], background
- idle loop processing [MFC]
- idle processing [MFC]
- threading [MFC], alternatives to multithreading
- processing, during idle loop
- processing [MFC]
- background processing [MFC]
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: baabba60ffaf886b7a34acfbff5b923a4495fa1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="idle-loop-processing"></a>Leerlaufschleifen-Verarbeitung
Viele Anwendungen führt langwierige Verarbeitung "in Hintergrund" In einigen Fällen geben Leistungsaspekte vor, die Verwendung von multithreading für derartige Schritte. Threads verursachen zusätzlichen, damit sie für einfache Aufgaben wie z. B. die Zeit im Leerlauf Arbeit nicht, die MFC empfohlen werden in der [OnIdle](../mfc/reference/cwinthread-class.md#onidle) Funktion. Dieser Artikel konzentriert sich auf die leerlaufverarbeitung. Weitere Informationen zu multithreading, finden Sie unter [Themen zu Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Einige Arten von Verarbeitung im Hintergrund werden entsprechend in Intervallen durchgeführt, die der Benutzer andernfalls nicht Interaktion mit der Anwendung verwendet wird. In einer Anwendung, die für das Betriebssystem Microsoft Windows entwickelt wurde kann eine Anwendung leerlaufzeitverarbeitung ausführen, und teilen Sie einen langwierigen Prozess in vielen kleinen Fragmenten. Nach der Verarbeitung jedes Fragment an, die Anwendung die Steuerung der Ausführung mit Windows ergibt eine [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Schleife.  
  
 Dieser Artikel beschreibt die zwei Möglichkeiten, um die Verarbeitung in der Anwendung im Leerlauf:  
  
-   Mit **PeekMessage** in MFC Haupt-Nachrichtenschleife.  
  
-   Einbetten von einem anderen **PeekMessage** Schleife woanders in der Anwendung.  
  
##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a>PeekMessage in der Nachrichtenschleife MFC  
 In einer Anwendung, die mit MFC entwickelt wurde, wurde die Hauptnachricht eine Schleife in der `CWinThread` Klasse enthält eine Nachrichtenschleife, die Aufrufe der [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Win32-API. Diese Schleife auch Aufrufe der `OnIdle` Memberfunktion von `CWinThread` zwischen Nachrichten. Eine Anwendung kann in diesem Zeitraum im Leerlauf Nachrichten verarbeiten, durch Überschreiben der `OnIdle` Funktion.  
  
> [!NOTE]
>  **Führen Sie**, `OnIdle`, und bestimmte weitere Memberfunktionen sind nun Elemente der Klasse `CWinThread` anstatt der Klasse `CWinApp`. `CWinApp` wird von `CWinThread` abgeleitet.  
  
 Weitere Informationen zur Ausführung im Leerlauf Verarbeitung finden Sie unter [OnIdle](../mfc/reference/cwinthread-class.md#onidle) in der *MFC-Referenz*.  
  
##  <a name="_core_peekmessage_elsewhere_in_your_application"></a>PeekMessage an anderer Stelle in der Anwendung  
 Eine andere Methode zum Ausführen der Verarbeitung in einer Anwendung im Leerlauf umfasst eine Nachrichtenschleife in eine Ihrer Funktionen einbetten. Diese Nachrichtenschleife ähnelt stark MFC Haupt-Meldungsschleife gefunden [Hauptmeldungsschleife](../mfc/reference/cwinthread-class.md#run). Bedeutet, dass solche Schleife in einer Anwendung, die mit MFC entwickelt wurde, die viele der gleichen Funktionen wie die Hauptnachrichtenschleife ausführen muss. Das folgende Codefragment veranschaulicht das Schreiben einer Nachrichtenschleife, die mit MFC kompatibel ist:  
  
 [!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]  
  
 Dieser Code, der in einer Funktion eingebettet Schleifen, solange es ist im Leerlauf verarbeiten müssen. Innerhalb der Schleife eine geschachtelte Schleife wiederholt aufgerufen **PeekMessage**. Solange dieser Aufruf einen Wert ungleich NULL zurückgibt, ruft die Schleife `CWinThread::PumpMessage` Durchführung normale Nachricht Übersetzung und verteilen. Obwohl `PumpMessage` ist nicht dokumentiert ist, können Sie den Quellcode in der Datei ThrdCore.Cpp im Verzeichnis \atlmfc\src\mfc der Visual C++-Installation überprüfen.  
  
 Einmal die innere Schleife beendet, die äußere Schleife führt leerlaufverarbeitung durch eine oder mehrere Aufrufe von `OnIdle`. Der erste Aufruf ist für MFC Zwecke. Sie können zusätzliche Aufrufe an `OnIdle` möchten eigene Verarbeitung im Hintergrund.  
  
 Weitere Informationen zur Ausführung im Leerlauf Verarbeitung finden Sie unter [OnIdle](../mfc/reference/cwinthread-class.md#onidle) in der Verweis auf die MFC-Bibliothek.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

