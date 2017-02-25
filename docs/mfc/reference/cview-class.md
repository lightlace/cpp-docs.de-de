---
title: "CView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Untergeordnete Fenster, Ansichten"
  - "CView class"
  - "document/view architecture"
  - "frame windows [C++], Ansichten"
  - "Eingabe, and view class"
  - "MDI [C++], view windows"
  - "Mehrere Ansichten"
  - "Seitenansicht, view windows"
  - "user input [C++], interpreting through view class"
  - "Ansichten [C++], view classes"
  - "windows [C++], Ansichten"
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die grundlegende Funktionalität für benutzerdefinierte Ansichtsklassen bereit.  
  
## Syntax  
  
```  
class AFX_NOVTABLE CView : public CWnd  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CView::CView](../Topic/CView::CView.md)|Erstellt ein `CView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CView::DoPreparePrinting](../Topic/CView::DoPreparePrinting.md)|Anzeigen\-Druckdialogfeldfeld und erstellt Druckergerätekontext; aufrufen, wenn die `OnPreparePrinting`\-Memberfunktion überschrieben wird.|  
|[CView::GetDocument](../Topic/CView::GetDocument.md)|Gibt das Dokument zurück, das mit der Ansicht zugeordnet ist.|  
|[CView::IsSelected](../Topic/CView::IsSelected.md)|Testet, ob ein Dokumentelement ausgewählt ist.  Erforderlich für OLE\-Unterstützung.|  
|[CView::OnDragEnter](../Topic/CView::OnDragEnter.md)|Aufgerufen, wenn ein Element zuerst in den Drag & Drop\-Bereich einer Ansicht gezogen wird.|  
|[CView::OnDragLeave](../Topic/CView::OnDragLeave.md)|Aufgerufen, wenn ein gezogenes Element den Drag & Drop\-Bereich einer Ansicht verlässt.|  
|[CView::OnDragOver](../Topic/CView::OnDragOver.md)|Aufgerufen, wenn ein Element über den Drag & Drop\-Bereich einer Ansicht gezogen wird.|  
|[CView::OnDragScroll](../Topic/CView::OnDragScroll.md)|Aufgerufen, um zu bestimmen, ob der Cursor im Bildlaufbereich des Fensters gezogen wird.|  
|[CView::OnDrop](../Topic/CView::OnDrop.md)|Aufgerufen, wenn ein Element in den Drag & Drop\-Bereich einer Ansicht gelöscht wurde, Standardhandler.|  
|[CView::OnDropEx](../Topic/CView::OnDropEx.md)|Aufgerufen, wenn ein Element in den Drag & Drop\-Bereich einer Ansicht gelöscht wurde, primärer Handler.|  
|[CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)|Aufgerufen, nachdem eine Ansicht erste angefügt zu einem Dokument ist.|  
|[CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md)|Aufgerufen, bevor die `OnDraw`\-Memberfunktion für Bildschirmanzeige oder die `OnPrint`\-Memberfunktion aufgerufen wird, wird für das Drucken oder Seitenansicht aufgerufen.|  
|[CView::OnScroll](../Topic/CView::OnScroll.md)|Aufgerufen, wenn OLE\-Elemente über den Rahmen der Ansicht hinaus gezogen werden.|  
|[CView::OnScrollBy](../Topic/CView::OnScrollBy.md)|Aufgerufen, wenn eine Ansicht, die aktive direkte OLE\-Elemente enthält, ein Bildlauf durchgeführt wird.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CView::OnActivateFrame](../Topic/CView::OnActivateFrame.md)|Aufgerufen, wenn das Rahmenfenster, das die Ansicht enthält, aktiviert oder deaktiviert ist.|  
|[CView::OnActivateView](../Topic/CView::OnActivateView.md)|Aufgerufen, wenn eine Ansicht aktiviert ist.|  
|[CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)|Aufgerufen, wenn ein Druckauftrag beginnt; Überschreiben Sie, um von Ressourcen des GDI \(Graphics Device Interface\) zuzuordnen.|  
|[CView::OnDraw](../Topic/CView::OnDraw.md)|Aufgerufen, um ein Bild des Dokuments für Bildschirmanzeige, Drucken oder Seitenansicht zu rendern.  Implementierung erforderlich.|  
|[CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md)|Aufgerufen, wenn ein Druckauftrag beendet wird, Überschreiben Sie, um von GDI\-Ressourcen freizugeben.|  
|[CView::OnEndPrintPreview](../Topic/CView::OnEndPrintPreview.md)|Aufgerufen, wenn Seitenansichtsmodus ausgestiegen wird.|  
|[CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)|Aufgerufen, bevor ein Dokument gedruckt oder in der Vorschau dargestellt wird, Überschreiben Sie, um des Druckdialogfeldfelds zu initialisieren.|  
|[CView::OnPrint](../Topic/CView::OnPrint.md)|Aufgerufen, um eine Seite des Dokuments gedruckt oder in der Vorschau anzeigen.|  
|[CView::OnUpdate](../Topic/CView::OnUpdate.md)|Aufgerufen, um eine Ansicht zu benachrichtigen, dass das Dokument geändert wurde.|  
  
## Hinweise  
 Eine Ansicht wird zu einem Dokument angefügt und fungiert als Mittler zwischen dem Dokument und den Benutzer: die Ansicht rendert ein Bild des Dokuments auf dem Bildschirm oder dem Drucker und interpretiert Benutzereingaben als Vorgänge nach dem Dokument.  
  
 Eine Ansicht ist ein untergeordnetes Element eines Rahmenfensters.  Mehr als eine Ansicht kann ein Rahmenfenster, wie im Fall eines Splitterfensters freigeben.  Die Beziehung zwischen einer Ansichtsklasse, einer Rahmenfensterklasse und einer Dokumentklasse wird durch ein `CDocTemplate`\-Objekt festgelegt.  Wenn der Benutzer ein neues oder vorhandenes Fenster geöffnet wird, erstellt das Framework eine neue Ansicht und fügt sie dem Dokument an.  
  
 Eine Ansicht kann nur einem Dokument angefügt werden, ein Dokument kann mehrere Ansichten haben, die unmittelbar darauf \- beispielsweise angefügt werden, wenn das Dokument in einem unterteilten oder in mehreren untergeordneten Fenstern in einer Anwendung \(Multiple Document Interface\) angezeigt wird.  Die Anwendung kann verschiedene Typen von Ansichten für einen bestimmten Typ des Dokuments unterstützen; beispielsweise kann ein Textverarbeitungsprogramm eine Ansicht des vollständigen Text eines Dokuments und eine Gliederungsansicht bereit, die nur die Abschnittsüberschriften anzeigt.  Diese verschiedenen Typen von Ansichten können in separate Rahmenfenster oder in separate Bereiche eines einzelnen Rahmenfensters platziert werden, wenn Sie ein Splitterfenster verwenden.  
  
 Eine Ansicht ist möglicherweise für das Behandeln mehrerer unterschiedlicher Typen Eingabe, wie Tastatureingabe verantwortlich, typisierte Maus oder Eingabe über Drag & Drop sowie Befehle von Menüs, \- Symbolleisten oder den Bildlaufleisten.  Eine Ansicht empfängt die Befehle, die durch das Rahmenfenster weitergeleitet werden.  Wenn die Ansicht keinen angegebenen Befehl verarbeitet, wird sie den Befehl an das zugeordnete Dokument weiter.  Wie alle Befehlsziele bearbeitet eine Ansicht Meldungen über eine Meldungszuordnung.  
  
 Die Ansicht ist zum Anzeigen und Ändern der Daten des Dokuments jedoch nicht für das Speichern sie verantwortlich.  Das Dokument stellt die Ansicht mit den notwendigen Informationen über seine Daten.  Sie können den Ansichtszugriff direkt lassen die Datenmember des Dokuments, oder Sie können Memberfunktionen in der Dokumentklasse für die Ansichtsklasse zum Aufruf bereitstellen.  
  
 Wenn die Daten eines Dokuments ändern, wird die Ansicht, die für die Änderungen zuständig ist in der Regel, die [CDocument::UpdateAllViews](../Topic/CDocument::UpdateAllViews.md)\-Funktion für das Dokument auf, das alle anderen Ansichten benachrichtigt, indem die `OnUpdate`\-Memberfunktion für jedes aufruft.  Die Standardimplementierung von `OnUpdate` macht den gesamten Clientbereich der Ansicht ungültig.  Sie können sie überschreiben, um nur diese Bereiche des Clientbereichs ungültig zu machen, die mit den geänderten Teile des Dokuments zuordnen.  
  
 Um `CView` zu verwenden, leiten Sie eine Klasse davon und implementieren Sie die `OnDraw`\-Memberfunktion um Bildschirmanzeige auszuführen.  Sie können `OnDraw` auch verwenden, um Drucken und Druckvorschau auszuführen.  Das Framework behandelt die Drucksschleife für das Drucken und das Vorschaufunktion des Dokuments.  
  
 Eine Ansicht bearbeitet Bildlaufleistenmeldungen mit den [CWnd::OnHScroll](../Topic/CWnd::OnHScroll.md) und [CWnd::OnVScroll](../Topic/CWnd::OnVScroll.md)\-Memberfunktionen.  Sie können BildlaufleistenNachrichtenverarbeitung in diesen Features implementieren, oder Sie können die `CView` abgeleitete Klasse [CScrollView](../../mfc/reference/cscrollview-class.md) verwenden, um einen Bildlauf für zu behandeln.  
  
 Neben `CScrollView` stellt Microsoft Foundation Class\-Bibliothek neun weitere Klassen, die von `CView` abgeleitet werden:  
  
-   [CCtrlView](../../mfc/reference/cctrlview-class.md), eine Ansicht, die die Verwendung der Dokument\-\/Ansichtarchitektur mit Struktur, Liste und Rich\-Edit\-Steuerelementen zulässig.  
  
-   [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), eine Ansicht, die Datenbankdatensätze in den Dialogfeld\-Steuerelemente anzeigt.  
  
-   [CEditView](../../mfc/reference/ceditview-class.md), eine Ansicht, die einen einfachen Text\-Editor mehrzeiligen bereitstellt.  Sie können ein `CEditView`\-Objekt als Steuerelement in einem Dialogfeld wie in einer Ansicht auf ein Dokument verwenden.  
  
-   [CFormView](../../mfc/reference/cformview-class.md), einer scrollbaren Ansicht, die Dialogfeld\-Steuerelemente enthält und auf Grundlage einer Dialogfeldvorlagen\-Ressource ist.  
  
-   [CListView](../../mfc/reference/clistview-class.md), eine Ansicht, die die Verwendung der Dokument\-\/Ansichtarchitektur mit Listen\-Steuerelementen zulässig.  
  
-   [CRecordView](../../mfc/reference/crecordview-class.md), eine Ansicht, die Datenbankdatensätze in den Dialogfeld\-Steuerelemente anzeigt.  
  
-   [CRichEditView](../../mfc/reference/cricheditview-class.md), eine Ansicht, die die Verwendung der Dokument\-\/Ansichtarchitektur mit Rich\-Edit\-Steuerelementen zulässig.  
  
-   [CScrollView](../../mfc/reference/cscrollview-class.md), eine Ansicht, die automatisch Bildlaufunterstützung bietet.  
  
-   [CTreeView](../../mfc/reference/ctreeview-class.md), eine Ansicht, die die Verwendung der Dokument\-\/Ansichtarchitektur mit Strukturansicht\-Steuerelementen zulässig.  
  
 Die `CView`\-Klasse verfügt auch über eine abgeleitete Implementierungsklasse, die **CPreviewView** genannt wird, die vom Framework verwendet wird, um das Drucksin der vorschau zeigen auszuführen.  Diese Klasse stellt Unterstützung für Funktionen, die dem Seitenansicht, wie eine Symbolleiste, eine von Einzel\- oder doppelseitige Vorschau und ein Zoomen h. eindeutig sind vergrößert das in der Vorschau gezeigte Bild.  Sie müssen nicht, um alle von CPreviewView Memberfunktionen aufzurufen oder überschreiben, es sei denn, die eigene Schnittstelle für Seitenansicht implementieren möchten \(beispielsweise, wenn Sie die Bearbeitung in der Seitenansicht unterstützen möchten\).  Weitere Informationen zur Verwendung von `CView`, finden Sie unter [Dokument\-\/Ansichtarchitektur](../../mfc/document-view-architecture.md) und [Drucken](../../mfc/printing.md).  Außerdem finden Sie unter [Technischer Hinweis 30](../../mfc/tn030-customizing-printing-and-print-preview.md) für weitere Details zum Anpassen der Seitenansicht.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CView`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC überprüft MDIDOCVW](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)   
 [CDC\-Klasse](../../mfc/reference/cdc-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)