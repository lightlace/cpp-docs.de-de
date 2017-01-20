---
title: "Multithreading: Erstellen von Benutzeroberfl&#228;chenthreads"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CREATE_SUSPENDED"
  - "SECURITY_ATTRIBUTES"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Multithreading [C++], Benutzeroberflächenthreads"
  - "Threading [C++], Erstellen von Threads"
  - "Threading [C++], Benutzeroberflächenthreads"
  - "Threading [MFC], Benutzeroberflächenthreads"
  - "Benutzeroberflächenthreads [C++]"
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading: Erstellen von Benutzeroberfl&#228;chenthreads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Benutzeroberflächenthread wird normalerweise verwendet, um unabhängig von Threads, die derzeit andere Teile der Anwendung ausführen, Benutzereingaben zu behandeln und um auf vom Benutzer generierte Ereignisse zu reagieren.  Der Thread der Hauptanwendung, der in der von `CWinApp` abgeleiteten Klasse enthalten ist, ist bereits erstellt und wird automatisch gestartet.  In diesem Thema werden die notwendigen Schritte zur Erstellung zusätzlicher Benutzeroberflächenthreads beschrieben.  
  
 Der erste Schritt bei der Erstellung eines Benutzeroberflächenthreads ist die Ableitung einer Klasse von [CWinThread](../../mfc/reference/cwinthread-class.md).  Sie müssen diese Klasse mit dem [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md)\-Makro und dem [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md)\-Makro deklarieren und implementieren.  Die Klasse muss bestimmte Funktionen überschreiben und kann wiederum andere Funktionen überschreiben.  Diese Funktionen und ihre Aufgaben werden in der folgenden Tabelle erläutert.  
  
### Zu überschreibende Funktionen bei der Erstellung eines Benutzeroberflächenthreads  
  
|Funktion|Zweck|  
|--------------|-----------|  
|[ExitInstance](../Topic/CWinThread::ExitInstance.md)|Führt Aufräumarbeiten durch, wenn der Thread beendet wird.  Wird normalerweise überschrieben.|  
|[InitInstance](../Topic/CWinThread::InitInstance.md)|Führt die Instanzeninitialisierung des Threads durch.  Muss überschrieben werden.|  
|[OnIdle](../Topic/CWinThread::OnIdle.md)|Führt die threadspezifische Leerlaufzeitverarbeitung durch.  Wird normalerweise nicht überschrieben.|  
|[PreTranslateMessage](../Topic/CWinThread::PreTranslateMessage.md)|Filtert Meldungen, bevor diese an **TranslateMessage** und **DispatchMessage** gesendet werden.  Wird normalerweise nicht überschrieben.|  
|[ProcessWndProcException](../Topic/CWinThread::ProcessWndProcException.md)|Fängt unbehandelte Ausnahmen ab, die von den Meldungs\- und Befehlshandlern des Threads ausgelöst werden.  Wird normalerweise nicht überschrieben.|  
|[Run](../Topic/CWinThread::Run.md)|Steuerungsfunktion für den Thread.  Enthält die Meldungsverteilschleife.  Wird selten überschrieben.|  
  
 in MFC werden durch Parameterüberladung zwei Versionen von `AfxBeginThread` zur Verfügung gestellt: eine, die nur Arbeitsthreads erstellen kann, und eine, die Benutzeroberflächenthreads oder Arbeitsthreads erstellen kann.  Rufen Sie die zweite Überladung von [AfxBeginThread](../Topic/AfxBeginThread.md) zum Starten des Benutzeroberflächenthreads auf, und geben Sie folgende Informationen an:  
  
-   Die [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md) der Klasse, die Sie von `CWinThread` abgeleitet haben.  
  
-   \(Optional\) Die gewünschte Prioritätsebene  Standardmäßig ist normale Priorität eingestellt.  Weitere Informationen zu den verfügbaren Prioritätsebenen finden Sie im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] unter [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277).  
  
-   \(Optional\) Die gewünschte Stapelgröße für den Thread.  Standardmäßig wird die Größe des Erstellungsthreads verwendet.  
  
-   \(Optional\) **CREATE\_SUSPENDED**, wenn der Thread im unterbrochenen Zustand generiert werden soll  Standardmäßig ist **0** eingestellt; Sie können den Thread auch normal starten.  
  
-   \(Optional\) Die gewünschten Sicherheitsattribute  Standardmäßig werden dieselben Zugriffsrechte wie für den übergeordneten Thread verwendet.  Weitere Informationen zum Format dieser Sicherheitsinformationen finden Sie im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] unter [SECURITY\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560).  
  
 Von `AfxBeginThread` wird der Großteil der Arbeit für Sie übernommen:  Nach der Erstellung eines neuen Objekts einer Klasse wird es mit den von Ihnen zur Verfügung gestellten Informationen initialisiert; anschließend wird [CWinThread::CreateThread](../Topic/CWinThread::CreateThread.md) aufgerufen, um mit der Ausführung des Threads zu beginnen.  Während der gesamten Prozedur wird überprüft, ob alle Objekte ordnungsgemäß freigegeben werden, falls ein Teil des Erstellungsprozesses fehlschlagen sollte.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Multithreading: Beenden von Threads](../../parallel/multithreading-terminating-threads.md)  
  
-   [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md)  
  
-   [\<caps:sentence id\="tgt49" sentenceid\="d446961ca833a037f83b141ec4859428" class\="tgtSentence"\>Prozesse und Threads\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
## Siehe auch  
 [Multithreading mit C\+\+ und MFC](../../parallel/multithreading-with-cpp-and-mfc.md)