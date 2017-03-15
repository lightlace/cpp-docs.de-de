---
title: "Beziehungen zwischen MFC-Objekten | Microsoft Docs"
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
  - "MFC-Objektbeziehungen"
  - "MFC, Beziehungen zwischen Schlüsselobjekten"
  - "Objekte [C++], Beziehungen"
  - "Beziehungen, MFC-Objekte"
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Beziehungen zwischen MFC-Objekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zur einfacheren Ausgabe den Dokument\/Ansichts\-Erstellungsprozess in Perspektive, berücksichtigen ein Programm ein: ein Dokument, das Rahmenfenster, das verwendet wurden, um die Ansicht zu enthalten, und die Ansicht sind im Dokument auf.  
  
-   Ein Dokument wird eine Liste der Ansichten dieses Dokuments und des Zeigers die Normal\-Vorlage, die das Dokument erstellt.  
  
-   Eine Ansicht enthält einen Zeiger auf das Dokument und ein untergeordnetes Element des übergeordneten Rahmenfensters.  
  
-   Ein Dokumentrahmenfenster enthält einen Zeiger auf die aktuelle aktive Ansicht.  
  
-   Die Normal\-Vorlage wird eine Liste der geöffneten Dokumente.  
  
-   Die Anwendung wird eine Liste der Dokumentvorlagen.  
  
-   Windows werden alle geöffneten Fenster stets, sodass es diese Nachrichten zu senden.  
  
 Diese Beziehungen werden während der Ansichts\-Erstellung Dokument\/festgelegt.  Die folgende Tabelle zeigt, wie Objekte in einem ausgeführten Programm auf andere Objekte zugreifen können.  Jedes beliebige Objekt kann einen Zeiger auf das Anwendungsobjekt erhalten, indem es die globale [AfxGetApp](../Topic/AfxGetApp.md)\- Funktion aufruft.  
  
### erhalten zu anderen Objekten in der Anwendung  
  
|Vom Objekt|Wie Sie auf andere Objekte zugreift|  
|----------------|-----------------------------------------|  
|Document|Verwenden Sie [GetFirstViewPosition](../Topic/CDocument::GetFirstViewPosition.md) und [GetNextView](../Topic/CDocument::GetNextView.md), um auf die Ansichtsliste des Dokuments zugreifen.<br /><br /> Aufruf [GetDocTemplate](../Topic/CDocument::GetDocTemplate.md), um der Normal\-Vorlage abzurufen.|  
|Ansicht|Aufruf [GetDocument](../Topic/CView::GetDocument.md), z des Dokuments abzurufen.<br /><br /> Aufruf [GetParentFrame](../Topic/CWnd::GetParentFrame.md), z des Rahmenfensters abzurufen.|  
|Dokumentrahmenfenster|Aufruf [GetActiveView](../Topic/CFrameWnd::GetActiveView.md), um die aktuelle Ansicht abzurufen.<br /><br /> Rufen Sie [GetActiveDocument](../Topic/CFrameWnd::GetActiveDocument.md) auf, um das Dokument zu, das der aktuellen Ansicht angefügt wird.|  
|MDI\-Rahmenfenster|Rufen Sie [MDIGetActive](../Topic/CMDIFrameWnd::MDIGetActive.md) auf, um aktive [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) nur abzurufen.|  
  
 Normalerweise verfügt eine Ansicht ein Rahmenfenster, aber manchmal, wie in den Splitterfenstern, enthält das gleiche Rahmenfenster mehrere Ansichten.  Das Rahmenfenster enthält einen Zeiger zur derzeit aktive Ansicht; der Zeiger wird aktualisiert, wenn eine andere Ansicht aktiviert ist.  
  
> [!NOTE]
>  Ein Zeiger auf das Hauptrahmenfenster wird [m\_pMainWnd](../Topic/CWinThread::m_pMainWnd.md) in der Membervariable des DLL\-Anwendungsobjekts gespeichert.  Ein Aufruf von `OnFileNew` in der Überschreibung der `InitInstance`\-Memberfunktion von `CWinApp` wird die `m_pMainWnd` für Sie fest.  Wenn Sie `OnFileNew` aufrufen, müssen Sie den Wert der Variablen in `InitInstance` selbst festlegen. Anwendungen kann \(SDI\-COM\-Komponente \(Server\) Legen die Variable nicht fest, wenn \/Embedding in der Befehlszeile.\) Beachten Sie, dass `m_pMainWnd` jetzt der Klasse `CWinThread` und nicht `CWinApp` ist.  
  
## Siehe auch  
 [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)   
 [Erstellen von Dokument\/Ansicht](../mfc/document-view-creation.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)