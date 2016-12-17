---
title: "CScrollView Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CScrollView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CScrollView class"
  - "scrolling views"
  - "Ansichten, Scrollen"
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CScrollView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CView](../../mfc/reference/cview-class.md) mit Bildlauffunktionen.  
  
## Syntax  
  
```  
class CScrollView : public CView  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CScrollView::CScrollView](../Topic/CScrollView::CScrollView.md)|Erstellt ein `CScrollView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CScrollView::CheckScrollBars](../Topic/CScrollView::CheckScrollBars.md)|Gibt an, ob die Bildlaufansicht horizontale und vertikale Bildlaufleisten.|  
|[CScrollView::FillOutsideRect](../Topic/CScrollView::FillOutsideRect.md)|Füllt den Bereich einer Ansicht durchführenden Bildlauf außerhalb des Bereichs aus.|  
|[CScrollView::GetDeviceScrollPosition](../Topic/CScrollView::GetDeviceScrollPosition.md)|Ruft die aktuelle Bildlaufposition in den Geräteeinheiten ab.|  
|[CScrollView::GetDeviceScrollSizes](../Topic/CScrollView::GetDeviceScrollSizes.md)|Ruft den aktuellen Zuordnungsmodus, die Gesamtgröße und die Zeile und die Seitengrößen der bildlauffähigen Ansicht ab.  Größen sind in den Geräteeinheiten.|  
|[CScrollView::GetScrollPosition](../Topic/CScrollView::GetScrollPosition.md)|Ruft die aktuelle Bildlaufposition in logischen Einheiten ab.|  
|[CScrollView::GetTotalSize](../Topic/CScrollView::GetTotalSize.md)|Ruft die Gesamtgröße der Bildlaufansicht in logische Einheiten ab.|  
|[CScrollView::ResizeParentToFit](../Topic/CScrollView::ResizeParentToFit.md)|Ruft die Größe der Ansicht, die Größe der Frame vorzuschreiben.|  
|[CScrollView::ScrollToPosition](../Topic/CScrollView::ScrollToPosition.md)|Führt die Ansicht zu einem bestimmten Punkt Bildlauf, der in logischen Einheiten angegeben ist.|  
|[CScrollView::SetScaleToFitSize](../Topic/CScrollView::SetScaleToFitSize.md)|Setzt die Bildlaufansicht in Skala\-zuAnpassung Modus.|  
|[CScrollView::SetScrollSizes](../Topic/CScrollView::SetScrollSizes.md)|Legt den Zuordnungsmodus der Bildlaufansicht, Gesamtgröße fest, und horizontaler und vertikaler Bildlauf\) liegt.|  
  
## Hinweise  
 Sie können Standardbildlauf behandeln sich in einer Klasse, die von `CView` abgeleitet wird, indem Sie die Meldung\-zugeordneten [OnHScroll](../Topic/CWnd::OnHScroll.md) und [OnVScroll](../Topic/CWnd::OnVScroll.md)\-Memberfunktionen überschreiben.  Die `CScrollView` fügt die folgenden Funktionen den `CView`\-Funktionen hinzu:  
  
-   Sie verwaltet Fenster und Viewportgrößen und \-Zuordnungsmodi.  
  
-   Sie führt automatisch als Reaktion auf Bildlaufleistenmeldungen aus.  
  
-   Sie führt automatisch als Reaktion auf Meldungen auf der Tastatur, einer NichtBildlauf Maus oder vom IntelliMouse\-Rad aus.  
  
 Um auf Meldungen von der Tastatur automatisch wechseln, eine WM\_KEYDOWN\-Meldung und Test für VK\_DOWN, VK\_PREV und Aufruf [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597) hinzufügen.  
  
 Sie können Mausradbildlauf behandeln den, indem Sie die Meldung\-zugeordneten [OnMouseWheel](../Topic/CWnd::OnMouseWheel.md) und [OnRegisteredMouseWheel](../Topic/CWnd::OnRegisteredMouseWheel.md)\-Memberfunktionen überschreiben.  Obwohl sie für `CScrollView` sind, unterstützen diese Memberfunktionen das empfohlene Verhalten für [WM\_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617), die Mausraddrehungsmeldung.  
  
 Um einen automatischen Bildlauf zu nutzen, leiten Sie die Ansichtsklasse von `CScrollView` anstelle von `CView`.  Wenn die Ansicht zuerst erstellt wird, wenn Sie die Größe der bildlauffähigen Ansicht basierend auf der Größe des Dokuments berechnen möchten, rufen Sie die `SetScrollSizes`\-Memberfunktion von der Überschreibung entweder von [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) oder von [CView::OnUpdate](../Topic/CView::OnUpdate.md) auf.  \(Sie müssen einen eigenen Code schreiben, um die Größe des Dokuments abfragen.  Ein Beispiel finden Sie unter [Sie Kritzeln Beispiel](../../top/visual-cpp-samples.md).\)  
  
 Der Aufruf der Memberfunktion `SetScrollSizes` legt den Zuordnungsmodus der Ansicht, die gesamten Dimensionen der Bildlaufansicht und die Mengen fest, um horizontal und vertikal liegen.  Alle Größen sind in logischen Einheiten.  Die logische Größe der Ansicht wird normalerweise von den Daten berechnet, die im Dokument gespeichert, sondern in einigen Fällen können Sie eine feste Größe angeben.  Beispiele beider Ansätze finden Sie unter [CScrollView::SetScrollSizes](../Topic/CScrollView::SetScrollSizes.md).  
  
 Sie geben die Mengen an, um in logischen Einheiten horizontal und vertikal liegen.  Standardmäßig wird der Benutzer auf einen Schaft für Bildlaufleiste außerhalb des Bildlauffelds klickt, führt `CScrollView` eine "Seite" Bildlauf. Wenn der Benutzer auf einen Bildlaufpfeil an jedem Ende einer Bildlaufleiste klickt, führt `CScrollView` eine Zeile "." Bildlauf Standardmäßig ist eine Seite 1\/10 der Gesamtgröße der Ansicht; ist eine Zeile 1\/10 der Seitengröße.  Überschreiben Sie diese Standardwerte, indem Sie Sondergrößen in der `SetScrollSizes`\-Memberfunktion übergeben.  Beispielsweise könnten Sie die horizontale Größe zu einem Bruchteil der Breite der Gesamtgröße und die vertikale Größe der Höhe einer Zeile in der aktuellen Schriftart fest.  
  
 Anstelle des Bildlaufs kann `CScrollView` die Ansicht der Größe des aktiven Fensters automatisch skalieren.  In diesem Modus hat die Ansicht keine Bildlaufleisten und logische Ansicht wird gestreckt oder verkleinert wird, um den Clientbereich des Fensters genau zu passen.  Um diese Skala\-zuAnpassung Funktion zu verwenden, erhalten Sie [CScrollView::SetScaleToFitSize](../Topic/CScrollView::SetScaleToFitSize.md) auf.  \(Abrufen `SetScaleToFitSize` oder `SetScrollSizes`, jedoch nicht beide\) auf.  
  
 Bevor die `OnDraw`\-Memberfunktion der abgeleiteten Ansichtsklasse aufgerufen wird, stellt `CScrollView` automatisch den Viewportursprung auf das `CPaintDC` Gerätekontextobjekt ein, das er zu `OnDraw` führt.  
  
 Um den Viewportursprung auf das Bildlauffenster anzuhalten, überschreibt `CScrollView`[CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md).  Diese Anpassung ist für den `CPaintDC` Gerätekontext automatisch, den `CScrollView` zu `OnDraw` führt, aber Sie müssen aufrufen **CScrollView::OnPrepareDC** sich für alle anderen Gerätekontexte, die Sie verwenden, wie `CClientDC`.  Sie können **CScrollView::OnPrepareDC** überschreiben, um den Stift, Hintergrundfarbe und andere Zeichnungsattribute festzulegen, jedoch die Basisklasse auf, um Skalierung auszuführen.  
  
 Bildlaufleisten können in drei Stellen relativ zu einer Ansicht, wie in den folgenden Fällen dargestellt:  
  
-   Standardfensterstilbildlaufleisten können für die Ansicht mit **WS\_HSCROLL** und **WS\_VSCROLL**[Windows\-Formate](../../mfc/reference/window-styles.md) festgelegt werden.  
  
-   ScrollBar\-Steuerelementen können auf Frames ebenfalls hinzugefügt werden, die die Ansicht enthalten, in diesem Fall das Framework `WM_HSCROLL` und `WM_VSCROLL` Meldungen vom Rahmenfenster an nur weiterleitet aktive Ansicht.  
  
-   Das Framework führt auch Bildlaufmeldungen von einem `CSplitterWnd` Splitter\-Steuerelement an das derzeit aktive Splitterbereich beibehalten \(eine Ansicht\).  Wenn es in [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) mit freigegebenen Bildlaufleisten platziert wird, wird ein `CScrollView`\-Objekt die freigegebenen, anstatt einen eigenen erstellen.  
  
 Weitere Informationen zur Verwendung von `CScrollView`, finden Sie unter [Dokument\-\/Ansichtarchitektur](../../mfc/document-view-architecture.md) und [Abgeleitete Ansichtsklassen verfügbar in MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CScrollView`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC Sampling DIBLOOK](../../top/visual-cpp-samples.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)