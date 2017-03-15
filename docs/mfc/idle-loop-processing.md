---
title: "Leerlaufschleifen-Verarbeitung | Microsoft Docs"
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
  - "Hintergrundverarbeitung"
  - "Leerlaufschleifen-Verarbeitung"
  - "Leerlaufverarbeitung"
  - "Meldungen, Schleifen"
  - "MFC, Hintergrundverarbeitung"
  - "MFC, Meldungen"
  - "OnIdle-Methode"
  - "PeekMessage-Methode"
  - "PeekMessage-Methode, elsewhere than-Meldungsschleife"
  - "Verarbeiten"
  - "Verarbeiten, Hintergrund"
  - "Verarbeiten, während Leerlaufschleife"
  - "Threading [MFC], Alternativen zum Multithreading"
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Leerlaufschleifen-Verarbeitung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Viele Anwendungen führen das langwierige Verarbeitung "im Hintergrund" aus. Manchmal schreiben Leistungsüberlegungen mit Multithreading für diese Arbeit vor.  Threads werden zusätzliche Entwicklungsmehraufwand mit ein, sodass sie nicht für einfache Aufgaben wie die Leerlaufarbeit empfohlen, dass MFC in der [OnIdle](../Topic/CWinThread::OnIdle.md)\-Funktion ausführt.  Dieser Artikel beschreibt schwerpunktmäßig Leerlaufverarbeitung.  Weitere Informationen über Multithreading, finden Sie unter [Multithreading\-Themen](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Einige Arten Hintergrundverarbeitung sind entsprechend während der Zeitintervalle derjenigen, dass der Benutzer nicht andernfalls mit der Anwendung.  In Anwendungen, die für das Microsoft Windows\-Betriebssystem entwickelt wurde, kann eine Anwendung im Leerlauf ausführen, indem sie einen aufwändigen Prozess in viele kleine Fragmente verarbeitet, unterteilt.  Nachdem sie jedes Fragment verarbeitet hat, führt die Anwendung Ausführungssteuerung zu Windows mithilfe einer [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Schleife.  
  
 Dieser Artikel beschreibt zwei Möglichkeiten, Leerlaufverarbeitung in der Anwendung auszuführen:  
  
-   Die Verwendung von **PeekMessage** auf Hauptnachrichtenschleife MFC.  
  
-   Eine weitere **PeekMessage** Schleife in der Anwendung auf einbetten.  
  
##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a> PeekMessage in der MFC\-Nachrichtenschleife  
 In einer Anwendung, die mit MFC entwickelt wurde, enthält der Hauptnachrichtenschleife in der `CWinThread`\-Klasse eine Nachrichtenschleife, die die [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Win32\-API aufruft.  Die Schleife ruft außerdem die `OnIdle`\-Memberfunktion von `CWinThread` zwischen Meldungen auf.  Eine Anwendung kann Meldungen in der Leerlaufzeit verarbeiten, indem sie die `OnIdle`\-Funktion überschreibt.  
  
> [!NOTE]
>  **Ausführen**, `OnIdle` und bestimmte andere Memberfunktionen sind jetzt Member der Klasse `CWinThread` und der `CWinApp`\- Klasse.  `CWinApp` ist von `CWinThread` abgeleitet.  
  
 Weitere Informationen zum Ausführen von Leerlaufverarbeitung, finden Sie unter [OnIdle](../Topic/CWinThread::OnIdle.md) in der *MFC\-Referenz*.  
  
##  <a name="_core_peekmessage_elsewhere_in_your_application"></a> PeekMessage an anderer Stelle in der Anwendung  
 Eine weitere Methode zum Ausführen von Leerlaufverarbeitung in einer Anwendung, scrollen eine Nachrichtenschleife einzubetten in eine der Funktionen.  Diese Meldungsschleife entspricht Hauptnachrichtenschleife MFC, gefunden [CWinThread::Run](../Topic/CWinThread::Run.md) sehr ähnlich.  Das bedeutet, dass einer solchen Schleife in einer Anwendung, die mit MFC entwickelten, viele der gleichen Aufgaben wie der Hauptnachrichtenschleife ausführen muss.  Das folgende Codefragment veranschaulicht das Schreiben eine Nachrichtenschleife, die mit MFC ist kompatibel:  
  
 [!CODE [NVC_MFCDocView#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#8)]  
  
 Dieser Code, eingebettet in einer Funktion, Schleifen, solange die Leerlaufverarbeitung gibt, auszuführen.  Innerhalb dieser Schleife ruft eine geschachtelte Schleife wiederholt **PeekMessage** auf.  Solange dies Aufruf gibt einen Wert ungleich 0 \(null\), die `CWinThread::PumpMessage` \- Schleife aufruft, um die normale Meldungsübersetzung und \-c$weiterleiten auszuführen.  Obwohl `PumpMessage` nicht dokumentiert ist, können Sie den Quellcode in der Datei ThrdCore.Cpp im Verzeichnis \\atlmfc\\src\\mfc in der Visual C\+\+\-Installation überprüfen.  
  
 Sobald beendet die innere Schleife, die äußeren Schleife ausführt Leerlaufverarbeitung mit einem oder mehreren Aufrufen von `OnIdle`.  Der erste Aufruf ist zu Zwecken MFC.  Sie können zusätzliche Aufrufe eigene Hintergrundarbeit erledigen lassen `OnIdle`.  
  
 Weitere Informationen zum Ausführen von Leerlaufverarbeitung, finden Sie unter [OnIdle](../Topic/CWinThread::OnIdle.md) in der MFC\-Bibliotheksreferenz.  
  
## Siehe auch  
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)