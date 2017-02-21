---
title: "CWinThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinThread-Klasse"
  - "Threading [MFC], Erstellen von Threads"
  - "Threading [MFC], Sicherheit"
  - "Arbeitsthreads"
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CWinThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Ausführungsthread innerhalb einer Anwendung dar.  
  
## Syntax  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWinThread::CWinThread](../Topic/CWinThread::CWinThread.md)|Erstellt ein `CWinThread`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWinThread::CreateThread](../Topic/CWinThread::CreateThread.md)|Startet `CWinThread` Ausführung eines Objekts.|  
|[CWinThread::ExitInstance](../Topic/CWinThread::ExitInstance.md)|Überschreiben Sie, um zu bereinigen, wenn der Thread beendet wird.|  
|[CWinThread::GetMainWnd](../Topic/CWinThread::GetMainWnd.md)|Ruft einen Zeiger auf das Hauptfenster für den Thread ab.|  
|[CWinThread::GetThreadPriority](../Topic/CWinThread::GetThreadPriority.md)|Ruft die Priorität des aktuellen Threads ab.|  
|[CWinThread::InitInstance](../Topic/CWinThread::InitInstance.md)|Überschreiben Sie, um von Threadinstanzinitialisierung auszuführen.|  
|[CWinThread::IsIdleMessage](../Topic/CWinThread::IsIdleMessage.md)|Überprüfungen für Sondermeldungen.|  
|[CWinThread::OnIdle](../Topic/CWinThread::OnIdle.md)|Überschreiben Sie, um des threadspezifische Leerlaufverarbeitens auszuführen.|  
|[CWinThread::PostThreadMessage](../Topic/CWinThread::PostThreadMessage.md)|Sendet eine Nachricht an einen anderen `CWinThread`\-Objekt.|  
|[CWinThread::PreTranslateMessage](../Topic/CWinThread::PreTranslateMessage.md)|Filtert Meldungen, bevor sie an den Windows\-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) weitergeleitet werden.|  
|[CWinThread::ProcessMessageFilter](../Topic/CWinThread::ProcessMessageFilter.md)|Abfangbestimmte Meldungen, bevor die Anwendung erreichen.|  
|[CWinThread::ProcessWndProcException](../Topic/CWinThread::ProcessWndProcException.md)|Fängt alle Ausnahmen ab, die von der Meldung und von den Befehlshandlern Threads ausgelöst werden.|  
|[CWinThread::PumpMessage](../Topic/CWinThread::PumpMessage.md)|Enthält die Nachrichtenschleife des Threads.|  
|[CWinThread::ResumeThread](../Topic/CWinThread::ResumeThread.md)|Dekrementiert den Unterbrechungszähler eines Threads.|  
|[CWinThread::Run](../Topic/CWinThread::Run.md)|Steuerungsfunktion für Threads mit einer Nachrichtensystem.  Überschreiben Sie, um die standardmäßige Meldungsschleife anzupassen.|  
|[CWinThread::SetThreadPriority](../Topic/CWinThread::SetThreadPriority.md)|Legt die Priorität des aktuellen Threads fest.|  
|[CWinThread::SuspendThread](../Topic/CWinThread::SuspendThread.md)|Inkrementiert den Unterbrechungszähler eines Threads.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWinThread::operator HANDLE](../Topic/CWinThread::operator%20HANDLE.md)|Ruft das Handle des `CWinThread`\-Objekts ab.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CWinThread::m\_bAutoDelete](../Topic/CWinThread::m_bAutoDelete.md)|Gibt an, ob das Objekt der Threadbeendigung zerstört.|  
|[CWinThread::m\_hThread](../Topic/CWinThread::m_hThread.md)|Handle an den aktuellen Thread.|  
|[CWinThread::m\_nThreadID](../Topic/CWinThread::m_nThreadID.md)|ID des aktuellen Threads.|  
|[CWinThread::m\_pActiveWnd](../Topic/CWinThread::m_pActiveWnd.md)|Zeiger auf das Hauptfenster der Containeranwendung, wenn ein OLE\-Server direkt aktiviert ist.|  
|[CWinThread::m\_pMainWnd](../Topic/CWinThread::m_pMainWnd.md)|Hält einen Zeiger auf das Hauptfenster der Anwendung.|  
  
## Hinweise  
 Der Hauptthread der Ausführung wird normalerweise von einem Objekt bereitgestellt, das von abgeleitet wird, `CWinApp``CWinApp` wird von `CWinThread` abgeleitet.  Zusätzliche `CWinThread`\-Objekte können mehrere Threads innerhalb einer angegebenen Anwendung.  
  
 Es gibt zwei allgemeine Typen von Threads, die `CWinThread` unterstützt: Arbeitsthreads und Benutzeroberflächenthreads.  Arbeitsthreads haben keine Haupt\-Meldungsverteilschleife: beispielsweise ein Thread, der Hintergrundberechnungen in einer Arbeitsblatt\-Anwendung ausführt.  Benutzeroberflächenthreads verfügen die Meldungen einer Meldungsverteilschleife und des Prozesses, die vom System empfangen werden.  [CWinApp](../../mfc/reference/cwinapp-class.md) und Klassen, die davon abgeleitet werden, sind Beispiele von Benutzeroberflächenthreads.  Andere Benutzeroberflächenthreads können direkt aus `CWinThread` auch abgeleitet werden.  
  
 Objekte der Klasse `CWinThread` sind in der Regel während der Dauer des Threads.  Um dieses Verhalten zu ändern, legen Sie [m\_bAutoDelete](../Topic/CWinThread::m_bAutoDelete.md) zu **FALSE** fest.  
  
 Die `CWinThread`\-Klasse ist erforderlich, um den Code und MFC vollständig threadsicher zu machen.  Die lokalen Daten, die vom Framework verwendet werden, um threadspezifische Informationen beizubehalten, werden durch `CWinThread`\-Objekte verwaltet.  Daher muss Abhängigkeit auf `CWinThread`, von lokalen Daten zu bearbeiten, jeder Thread, der MFC verwendet, von MFC erstellt werden.  Beispielsweise kann ein Thread, der durch die Laufzeitfunktion [\_beginthread\-Funktion, \_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) erstellt wird, kein MFC APIs verwenden.  
  
 Um einen Thread zu erstellen, rufen Sie [AfxBeginThread](../Topic/AfxBeginThread.md) auf.  Es gibt zwei Formen, je nachdem, ob Sie einen Arbeits\- oder einen Benutzeroberflächenthread soll.  Wenn Sie einen Benutzeroberflächenthread möchten, führen Sie auf `AfxBeginThread` einen Zeiger auf `CRuntimeClass` aus dem `CWinThread` von abgeleitete Klasse.  Wenn Sie einen Arbeitsthread erstellen möchten, führen Sie auf `AfxBeginThread` einen Zeiger an die Steuerungsfunktion und den Parameter an die Steuerungsfunktion.  Für beide Arbeitsthreads und Benutzeroberflächenthreads können optionale Parameter angeben, die Priorität, Stapelgröße, Erstellungsflags und Sicherheitsattribute ändern.  `AfxBeginThread` gibt einen Zeiger auf dem neuen `CWinThread`\-Objekt zurück.  
  
 Anstatt, `AfxBeginThread` aufzurufen, können Sie `CWinThread` erstellen von abgeleitetes Objekt und `CreateThread` dann aufrufen.  Dieses zweistufige Bauverfahren ist hilfreich, wenn Sie das `CWinThread`\-Objekt zwischen aufeinander folgender Erstellung und Verlassen von Threadausführungen wiederverwenden möchten.  
  
 Weitere Informationen zu `CWinThread`, finden Sie in Artikel [Multithreading in C\+\+ und MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Multithreading: Erstellen von Benutzeroberflächenthreads](../../parallel/multithreading-creating-user-interface-threads.md), [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md) und [Multithreading: Erstellen der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)