---
title: "CSplitterWnd Class"
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
  - "CSplitterWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSplitterWnd class"
  - "dynamic splitter windows"
  - "Mehrere Ansichten"
  - "Splitterfenster"
  - "static splitter windows"
  - "Ansichten, Mehrere im Fenster"
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CSplitterWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität eines Splitterfensters bereit, das ein Fenster befindet, das mehrere Bereiche enthält.  
  
## Syntax  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSplitterWnd::CSplitterWnd](../Topic/CSplitterWnd::CSplitterWnd.md)|aufrufen, um `CSplitterWnd` eines Objekts zu erstellen.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSplitterWnd::ActivateNext](../Topic/CSplitterWnd::ActivateNext.md)|Führt den folgenden Bereich oder den vorherigen Bereichsbefehl aus.|  
|[CSplitterWnd::CanActivateNext](../Topic/CSplitterWnd::CanActivateNext.md)|Überprüft, festzustellen, ob der folgenden Bereich oder vorherige der Bereichsbefehl nur möglich ist.|  
|[CSplitterWnd::Create](../Topic/CSplitterWnd::Create.md)|aufrufen, um eines dynamischen Splitterfensters zu erstellen und auf den `CSplitterWnd`\-Objekt anzufügen.|  
|[CSplitterWnd::CreateScrollBarCtrl](../Topic/CSplitterWnd::CreateScrollBarCtrl.md)|Stellt ein freigegebenes ScrollBar\-Steuerelement erstellt.|  
|[CSplitterWnd::CreateStatic](../Topic/CSplitterWnd::CreateStatic.md)|aufrufen, um eines statischen Splitterfensters zu erstellen und auf den `CSplitterWnd`\-Objekt anzufügen.|  
|[CSplitterWnd::CreateView](../Topic/CSplitterWnd::CreateView.md)|aufrufen, um einen Bereich in einem unterteilten zu erstellen.|  
|[CSplitterWnd::DeleteColumn](../Topic/CSplitterWnd::DeleteColumn.md)|Löscht eine Spalte aus dem Splitterfenster.|  
|[CSplitterWnd::DeleteRow](../Topic/CSplitterWnd::DeleteRow.md)|Löscht eine Zeile aus dem Splitterfenster.|  
|[CSplitterWnd::DeleteView](../Topic/CSplitterWnd::DeleteView.md)|Löscht eine Ansicht im Splitterfenster.|  
|[CSplitterWnd::DoKeyboardSplit](../Topic/CSplitterWnd::DoKeyboardSplit.md)|Führt den geteilten Befehl der Tastatur, normalerweise "Fenster\-Teilung" aus.|  
|[CSplitterWnd::DoScroll](../Topic/CSplitterWnd::DoScroll.md)|Performs synchronisierte Bildlauf von geteilten Fenster.|  
|[CSplitterWnd::DoScrollBy](../Topic/CSplitterWnd::DoScrollBy.md)|Bildlaufgeteilte Vorschaufenster durch die angegebene Anzahl der Pixel.|  
|[CSplitterWnd::GetActivePane](../Topic/CSplitterWnd::GetActivePane.md)|Bestimmt den aktiven Bereich des Fokus oder aus der aktuellen Ansicht in der Rahmen.|  
|[CSplitterWnd::GetColumnCount](../Topic/CSplitterWnd::GetColumnCount.md)|Gibt die aktuelle Bereichsspaltenanzahl zurück.|  
|[CSplitterWnd::GetColumnInfo](../Topic/CSplitterWnd::GetColumnInfo.md)|Gibt Informationen über die angegebene Spalte zurück.|  
|[CSplitterWnd::GetPane](../Topic/CSplitterWnd::GetPane.md)|Gibt den Bereich an der angegebenen Zeile und an der Spalte zurück.|  
|[CSplitterWnd::GetRowCount](../Topic/CSplitterWnd::GetRowCount.md)|Gibt die aktuelle Bereichszeilenanzahl zurück.|  
|[CSplitterWnd::GetRowInfo](../Topic/CSplitterWnd::GetRowInfo.md)|Gibt Informationen über die angegebene Zeile zurück.|  
|[CSplitterWnd::GetScrollStyle](../Topic/CSplitterWnd::GetScrollStyle.md)|Gibt das freigegebene Bildlaufleistenformat zurück.|  
|[CSplitterWnd::IdFromRowCol](../Topic/CSplitterWnd::IdFromRowCol.md)|Gibt die ID des untergeordneten Fensters des Bereichs an der angegebenen Zeile und an der Spalte zurück.|  
|[CSplitterWnd::IsChildPane](../Topic/CSplitterWnd::IsChildPane.md)|So bestimmen Sie, ob Aufruf, das Fenster gerade ein untergeordneter Bereich dieses Splitterfensters ist.|  
|[CSplitterWnd::IsTracking](../Topic/CSplitterWnd::IsTracking.md)|Bestimmt, ob gerade Splitterleiste bewegt wird.|  
|[CSplitterWnd::RecalcLayout](../Topic/CSplitterWnd::RecalcLayout.md)|aufrufen, um des Splitterfensters nach der Anpassen der Zeilen\- oder Spaltengröße erneut anzuzeigen.|  
|[CSplitterWnd::SetActivePane](../Topic/CSplitterWnd::SetActivePane.md)|Legt einen Bereich fest, um das aktive im Rahmen zu sein.|  
|[CSplitterWnd::SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md)|aufrufen, um die angegebenen Spalteninformationen festzulegen.|  
|[CSplitterWnd::SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md)|aufrufen, um die angegebenen Zeileninformationen festzulegen.|  
|[CSplitterWnd::SetScrollStyle](../Topic/CSplitterWnd::SetScrollStyle.md)|Gibt das neue Bildlaufleistenformat für die freigegebene Bildlaufleistenunterstützung des Splitterfensters an.|  
|[CSplitterWnd::SplitColumn](../Topic/CSplitterWnd::SplitColumn.md)|Gibt an, wo ein Rahmenfenster sich vertikal teilt.|  
|[CSplitterWnd::SplitRow](../Topic/CSplitterWnd::SplitRow.md)|Gibt an, wo ein Rahmenfenster sich horizontal teilt.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSplitterWnd::OnDraw](../Topic/CSplitterWnd::OnDraw.md)|Aufgerufen vom Framework, um das Splitterfenster zu zeichnen.|  
|[CSplitterWnd::OnDrawSplitter](../Topic/CSplitterWnd::OnDrawSplitter.md)|Gibt ein Bild eines geteilten Fenster.|  
|[CSplitterWnd::OnInvertTracker](../Topic/CSplitterWnd::OnInvertTracker.md)|Gibt das Bild eines geteilten Fenster, dieselbe Größe und die Form als das Rahmenfenster zu sein.|  
  
## Hinweise  
 Ein Bereich ist normalerweise ein anwendungsspezifisches Objekt, das von [CView](../../mfc/reference/cview-class.md) abgeleitet wird, kann jedoch jedes [CWnd](../../mfc/reference/cwnd-class.md)\-Objekt sein, das die entsprechende ID des untergeordneten Fensters wurde  
  
 Ein Objekt `CSplitterWnd` wird normalerweise in einem übergeordneten [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)\-Objekt eingebettet.  Erstellen Sie ein Objekt `CSplitterWnd` mithilfe der folgenden Schritte:  
  
1.  Betten Sie eine `CSplitterWnd`\-Membervariable in übergeordneten Frames ein.  
  
2.  Überschreiben Sie die Elemente [CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md)\-Memberfunktion der Rahmen.  
  
3.  Aus überschriebenen `OnCreateClient` rufen Sie die [Erstellen Sie](../Topic/CSplitterWnd::Create.md) oder [CreateStatic](../Topic/CSplitterWnd::CreateStatic.md)\-Memberfunktion der `CSplitterWnd` auf.  
  
 Rufen Sie die **Create**\-Memberfunktion auf, um ein dynamisches Splitterfenster zu erstellen.  Ein dynamisches Splitterfenster wird normalerweise verwendet, um einzelne oder mehrere Bereiche, Ansichten desselben Dokuments zu erstellen und zu wechseln.  Das Framework stellt automatisch einen Anfangsbereich für den Splitter generiert; stellt das Framework erstellt, ändert Größe und verwirft weitere Bereiche, während der Benutzer die Reguliervorrichtungen des Splitterfensters bedient.  
  
 Wenn Sie **Create** aufrufen, geben Sie eine minimale Zeilenhöhe und eine Spaltenbreite an, die bestimmen, wann die Bereiche zu klein sind, vollständig angezeigt werden.  Nachdem Sie **Create** aufrufen, können Sie diese Minima anpassen, indem Sie die [SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) und [SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md)\-Memberfunktionen aufrufen.  
  
 Verwenden Sie auch die `SetColumnInfo` und `SetRowInfo`\-Memberfunktionen, um eine ideale "" Breite für eine Spalte" und "ideale Höhe für eine Zeile festzulegen.  Wenn das Framework ein Splitterfenster anzeigt, wird zuerst die übergeordneten Frames, dann das Splitterfenster an.  Das Framework legt dann die Bereiche in den Spalten und Zeilen nach ihren idealen Dimensionen aus und funktioniert von der linken oberen Ecke der rechten unteren Ecke des Clientbereichs des Splitterfensters.  
  
 Alle Bereiche in einem dynamischen Splitterfenster müssen von derselben Klasse sein.  Vertraute Anwendungen, die dynamische Splitterfenster unterstützen, gehören Microsoft Word und Microsoft Excel.  
  
 Verwenden Sie die `CreateStatic`\-Memberfunktion, um ein statisches Splitterfenster zu erstellen.  Der Benutzer kann nur die Größe der Bereiche in einem statischen Splitterfenster ändern, nicht die Anzahl oder Reihenfolge.  
  
 Sie müssen die statischen Splitters speziell erstellen Bereiche des gesamten, wenn Sie den statischen Splitter erstellen.  Stellen Sie sicher, dass alle Bereiche, bevor die Elemente `OnCreateClient`\-Memberfunktion der Rahmen zurückgibt, oder das Framework erstellen anzeigt das Fenster nicht ordnungsgemäß.  
  
 Die `CreateStatic`\-Memberfunktion initialisiert automatisch einen statischen Splitter mit einer minimalen Zeilenhöhe und einer Spaltenbreite von 0.  Nachdem Sie **Create** aufrufen, passen Sie diese Minima, indem Sie die [SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) und [SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md)\-Memberfunktionen aufrufen.  Verwenden Sie auch `SetColumnInfo` und `SetRowInfo`, nachdem Sie `CreateStatic` aufrufen, um anzugeben, der gewünschten ideale Bereichsdimensionen.  
  
 Die einzelnen Bereiche eines statischen Splitters gehören häufig verschiedenen Klassen.  Beispiele für statische Splitterfenster finden Sie im Grafik\-Editor und den Windows\-Datei\-Manager.  
  
 Ein Splitterfenster unterstützt spezielle Bildlaufleisten \(abgesehen von den Bildlaufleisten, die Bereiche möglicherweise haben\).  Diese Bildlaufleisten sind untergeordnete Elemente des Objekts `CSplitterWnd` und mit den Bereichen freigegeben.  
  
 Sie erstellen diese speziellen Bildlaufleisten, wenn Sie das Splitterfenster erstellen.  Beispielsweise enthalten `CSplitterWnd`, die eine Zeile enthält, zwei Spalten und das **WS\_VSCROLL** Format eine vertikale Bildlaufleiste an, die durch die zwei Bereiche freigegeben wird.  Wenn der Benutzer die Bildlaufleiste bewegt, werden `WM_VSCROLL` Meldungen zu beiden Bereichen gesendet.  Wenn die Bereiche die Bildlaufleistenposition festlegen, wird die freigegebene Bildlaufleiste festgelegt.  
  
 Weitere Informationen über Splitterfenster finden Sie unter:  
  
-   [Technischer Hinweis 29](../../mfc/tn029-splitter-windows.md)  
  
-   Knowledge Base\-Artikel Q262024: HOWTO: Verwendung CPropertySheet als untergeordnetes Element von CSplitterWnd  
  
 Weitere Informationen dazu, wie dynamische Splitterfenster, finden Sie unter:  
  
-   MFC\-Beispiel [Scribble](../../top/visual-cpp-samples.md)  
  
-   [VIEWEX](../../top/visual-cpp-samples.md) MFC\-Beispiel.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## Anforderungen  
 **Header:**  afxext.h  
  
## Siehe auch  
 [MFC\-Beispiel VIEWEX](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)