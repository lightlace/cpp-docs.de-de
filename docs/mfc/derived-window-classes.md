---
title: "Abgeleitete Fensterklassen"
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
  - "Klassen [C++], Abgeleitet"
  - "CWnd-Klasse, Klassen, die abgeleitet sind aus"
  - "Abgeleitete Klassen, Fensterklassen"
  - "Hierarchien, Fensterklassen"
  - "Fensterklassenhierarchie"
  - "Fensterklassen, Abgeleitet"
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Abgeleitete Fensterklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Fenster direkt aus [CWnd](../mfc/reference/cwnd-class.md) erstellen, oder Sie leiten neue Fensterklassen von `CWnd` ab.  Im Allgemeinen erstellen Sie eigene, benutzerdefinierte Fenster auf diese Weise.  Allerdings werden die meisten Fenster, die in einem Frameworkprogramm verwendet werden, stattdessen aus einer der von MFC bereitgestellten, von `CWnd` abgeleiteten Rahmenfensterklassen erstellt.  
  
## Klassen für Rahmenfenster  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Wird für SDI\-Rahmenfenster verwendet, um ein einzelnes Dokument und dessen Ansicht zu gestalten.  Das Rahmenfenster ist sowohl das Hauptrahmenfenster für die Anwendung als auch das Rahmenfenster für das aktuelle Dokument.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Wird als Hauptrahmenfenster für MDI\-Anwendungen verwendet.  Das Hauptrahmenfenster ist ein Container für alle MDI\-Dokumentfenster und gibt seine Menüleiste für diese frei.  Ein MDI\-Rahmenfenster ist ein Fenster der obersten Ebene, das auf dem Desktop angezeigt wird.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Wird für einzelne Dokumente verwendet, die in einem MDI\-Hauptrahmenfenster geöffnet werden.  Jedes Dokument und seine Ansicht werden durch ein untergeordnetes MDI\-Rahmenfenster eingerahmt, das im MDI\-Hauptrahmenfenster enthalten ist.  Ein untergeordnetes MDI\-Fenster sieht einem typischen Rahmenfenster sehr ähnlich. Es befindet sich aber nicht auf dem Desktop, sondern bleibt in einem MDI\-Rahmenfenster.  Dem untergeordneten MDI\-Fenster fehlt allerdings eine eigene Menüleiste, sodass es die Menüleiste des MDI\-Rahmenfensters mitverwenden muss, in dem es enthalten ist.  
  
 Weitere Informationen finden Sie unter [Rahmenfenster](../mfc/frame-windows.md).  
  
## Andere Fensterklassen, die von "CWnd" abgeleitet werden  
 Zusätzlich zu den Rahmenfenstern werden mehrere andere Hauptkategorien von Fenstern von `CWnd` abgeleitet:  
  
 *Ansichten*  
 Ansichten werden mit der von der `CWnd`\-Klasse abgeleiteten [CView](../mfc/reference/cview-class.md)\-Klasse erstellt \(oder mit einer ihrer abgeleiteten Klassen\).  Eine Ansicht wird an ein Dokument angefügt und dient als Vermittler zwischen dem Dokument und dem Benutzer.  Eine Ansicht ist ein untergeordnetes Fenster \(kein untergeordnetes MDI\-Fenster\), das normalerweise den Clientbereich eines SDI\-Rahmenfensters oder eines untergeordneten MDI\-Rahmenfensters ausfüllt \(oder den Teil des Clientbereichs, der nicht von einer Symbolleiste und\/oder einer Statusleiste abgedeckt ist\).  
  
 *Dialogfelder*  
 Dialogfelder werden mithilfe der von `CWnd` abgeleiteten Klasse [CDialog](../mfc/reference/cdialog-class.md) erstellt.  
  
 *Formulare*  
 Formularansichten auf Grundlage von Dialogfeld\-Vorlagenressourcen, zum Beispiel Dialogfelder, werden mithilfe der Klassen [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) erstellt.  
  
 *Steuerelemente*  
 Steuerelemente wie Schaltflächen, Listenfelder und Kombinationsfelder werden mithilfe anderer Klassen erstellt, die von `CWnd` abgeleitet werden.  Weitere Informationen erhalten Sie in den [Themen zu Steuerelementen](../mfc/controls-mfc.md).  
  
 *Steuerleisten*  
 Untergeordnete Fenster, die Steuerelemente enthalten.  Dazu zählen beispielsweise Symbolleisten und Statusleisten.  Weitere Informationen erhalten Sie unter [Steuerleisten](../mfc/control-bars.md).  
  
## Fensterklassenhierarchie  
 Sehen Sie sich hierzu das [MFC\-Hierarchiediagramm](../mfc/hierarchy-chart.md) in der *MFC\-Referenz* an.  Ansichten werden unter [Dokument\-\/Ansichtarchitektur](../mfc/document-view-architecture.md) erläutert.  Dialogfelder werden unter [Dialogfelder](../mfc/dialog-boxes.md) erläutert.  
  
## Erstellen eigener Fensterklassen für spezielle Zwecke  
 Neben den Fensterklassen, die von der Klassenbibliothek bereitgestellt werden, benötigen Sie möglicherweise untergeordnete Fenster für besondere Zwecke.  Um ein solches Fenster zu erzeugen, erstellen Sie eine eigene, von [CWnd](../mfc/reference/cwnd-class.md) abgeleitete Klasse als untergeordnetes Fenster von einem Frame oder einer Ansicht.  Bedenken Sie, dass das Framework den Umfang des Clientbereichs von einem Dokumentrahmenfenster verwaltet.  Die Großteil des Clientbereichs wird durch eine Ansicht verwaltet, aber andere Fenster, z. B. Steuerleisten oder eigene, benutzerdefinierte Fenster, können sich den Platz mit der Ansicht teilen.  Sie müssen möglicherweise mit den Mechanismen in den Klassen [CView](../mfc/reference/cview-class.md) und [CControlBar](../mfc/reference/ccontrolbar-class.md) interagieren, um untergeordnete Fenster im Clientbereich eines Rahmenfensters zu positionieren.  
  
 Unter [Erstellen von Fenstern](../mfc/creating-windows.md) finden Sie eine Erläuterung zur Erstellung von Fensterobjekten und den Fenstern, die sie verwalten.  
  
## Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)