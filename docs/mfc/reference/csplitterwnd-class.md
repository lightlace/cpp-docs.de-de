---
title: CSplitterWnd Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSplitterWnd
- AFXEXT/CSplitterWnd
- AFXEXT/CSplitterWnd::CSplitterWnd
- AFXEXT/CSplitterWnd::ActivateNext
- AFXEXT/CSplitterWnd::CanActivateNext
- AFXEXT/CSplitterWnd::Create
- AFXEXT/CSplitterWnd::CreateScrollBarCtrl
- AFXEXT/CSplitterWnd::CreateStatic
- AFXEXT/CSplitterWnd::CreateView
- AFXEXT/CSplitterWnd::DeleteColumn
- AFXEXT/CSplitterWnd::DeleteRow
- AFXEXT/CSplitterWnd::DeleteView
- AFXEXT/CSplitterWnd::DoKeyboardSplit
- AFXEXT/CSplitterWnd::DoScroll
- AFXEXT/CSplitterWnd::DoScrollBy
- AFXEXT/CSplitterWnd::GetActivePane
- AFXEXT/CSplitterWnd::GetColumnCount
- AFXEXT/CSplitterWnd::GetColumnInfo
- AFXEXT/CSplitterWnd::GetPane
- AFXEXT/CSplitterWnd::GetRowCount
- AFXEXT/CSplitterWnd::GetRowInfo
- AFXEXT/CSplitterWnd::GetScrollStyle
- AFXEXT/CSplitterWnd::IdFromRowCol
- AFXEXT/CSplitterWnd::IsChildPane
- AFXEXT/CSplitterWnd::IsTracking
- AFXEXT/CSplitterWnd::RecalcLayout
- AFXEXT/CSplitterWnd::SetActivePane
- AFXEXT/CSplitterWnd::SetColumnInfo
- AFXEXT/CSplitterWnd::SetRowInfo
- AFXEXT/CSplitterWnd::SetScrollStyle
- AFXEXT/CSplitterWnd::SplitColumn
- AFXEXT/CSplitterWnd::SplitRow
- AFXEXT/CSplitterWnd::OnDraw
- AFXEXT/CSplitterWnd::OnDrawSplitter
- AFXEXT/CSplitterWnd::OnInvertTracker
dev_langs:
- C++
helpviewer_keywords:
- CSplitterWnd [MFC], CSplitterWnd
- CSplitterWnd [MFC], ActivateNext
- CSplitterWnd [MFC], CanActivateNext
- CSplitterWnd [MFC], Create
- CSplitterWnd [MFC], CreateScrollBarCtrl
- CSplitterWnd [MFC], CreateStatic
- CSplitterWnd [MFC], CreateView
- CSplitterWnd [MFC], DeleteColumn
- CSplitterWnd [MFC], DeleteRow
- CSplitterWnd [MFC], DeleteView
- CSplitterWnd [MFC], DoKeyboardSplit
- CSplitterWnd [MFC], DoScroll
- CSplitterWnd [MFC], DoScrollBy
- CSplitterWnd [MFC], GetActivePane
- CSplitterWnd [MFC], GetColumnCount
- CSplitterWnd [MFC], GetColumnInfo
- CSplitterWnd [MFC], GetPane
- CSplitterWnd [MFC], GetRowCount
- CSplitterWnd [MFC], GetRowInfo
- CSplitterWnd [MFC], GetScrollStyle
- CSplitterWnd [MFC], IdFromRowCol
- CSplitterWnd [MFC], IsChildPane
- CSplitterWnd [MFC], IsTracking
- CSplitterWnd [MFC], RecalcLayout
- CSplitterWnd [MFC], SetActivePane
- CSplitterWnd [MFC], SetColumnInfo
- CSplitterWnd [MFC], SetRowInfo
- CSplitterWnd [MFC], SetScrollStyle
- CSplitterWnd [MFC], SplitColumn
- CSplitterWnd [MFC], SplitRow
- CSplitterWnd [MFC], OnDraw
- CSplitterWnd [MFC], OnDrawSplitter
- CSplitterWnd [MFC], OnInvertTracker
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 071eaeef6fbdbe4967d184936f5fb7bffb7786b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377848"
---
# <a name="csplitterwnd-class"></a>CSplitterWnd-Klasse
Stellt die Funktionalität eines unterteilten Fensters bereit. Dabei handelt es sich um ein Fenster, das mehrere Bereiche enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|Der Aufruf zum Erstellen einer `CSplitterWnd` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitterWnd::ActivateNext](#activatenext)|Führt den nächsten oder vorherigen Bereich-Befehl.|  
|[CSplitterWnd::CanActivateNext](#canactivatenext)|Überprüft, um festzustellen, ob der Befehl nächsten oder vorherigen Bereich derzeit möglich ist.|  
|[Splitterfenstern](#create)|Aufruf an ein dynamisches Splitterfenster wird erstellt und angefügt, die `CSplitterWnd` Objekt.|  
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|Erstellt eine freigegebene Bildlaufleisten-Steuerelement.|  
|[CSplitterWnd::CreateStatic](#createstatic)|Aufruf an ein statisches Splitterfenster wird erstellt und angefügt, die `CSplitterWnd` Objekt.|  
|[CSplitterWnd:: CreateView-Funktion](#createview)|So erstellen Sie einen Bereich in einem Splitterfenster aufrufen.|  
|[CSplitterWnd::DeleteColumn](#deletecolumn)|Löscht eine Spalte aus der unterteiltes Fenster an.|  
|[CSplitterWnd::DeleteRow](#deleterow)|Löscht eine Zeile aus der unterteiltes Fenster.|  
|[CSplitterWnd::DeleteView](#deleteview)|Löscht eine Ansicht aus der unterteiltes Fenster an.|  
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|Führt die Tastatur split-Befehl, in der Regel "Fenster teilen."|  
|[CSplitterWnd::DoScroll](#doscroll)|Führt die synchronisierten Bildlauf bei der Split-Windows.|  
|[CSplitterWnd::DoScrollBy](#doscrollby)|Scrollt geteilte Fenster durch eine angegebene Anzahl von Pixeln.|  
|[CSplitterWnd::GetActivePane](#getactivepane)|Bestimmt den aktiven Bereich den Fokus oder die aktive Ansicht im Frame.|  
|[CSplitterWnd::GetColumnCount](#getcolumncount)|Gibt die aktuelle Anzahl der Spalten im Bereich zurück.|  
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|Gibt Informationen zu der angegebenen Spalte zurück.|  
|[CSplitterWnd::GetPane](#getpane)|Gibt den Bereich in der angegebenen Zeile und Spalte zurück.|  
|[CSplitterWnd::GetRowCount](#getrowcount)|Gibt den aktuellen Bereich Zeilenanzahl zurück.|  
|[CSplitterWnd::GetRowInfo](#getrowinfo)|Gibt Informationen zu der angegebenen Zeile zurück.|  
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|Gibt den Schriftschnitt freigegebenen Bildlaufleiste.|  
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|Gibt das untergeordnete Fenster-ID des Bereichs in der angegebenen Zeile und Spalte zurück.|  
|[CSplitterWnd::IsChildPane](#ischildpane)|Aufruf, um zu bestimmen, ob das Fenster derzeit einen untergeordneten Bereich dieser unterteiltes Fenster ist.|  
|[CSplitterWnd::IsTracking](#istracking)|Bestimmt, ob die Teilerleiste gerade verschoben wird.|  
|[CSplitterWnd::RecalcLayout](#recalclayout)|Rufen Sie auf, um die unterteiltes Fenster anzuzeigen, nach der Zeile oder Spalte Größe anpassen.|  
|[CSplitterWnd::SetActivePane](#setactivepane)|Legt einen Bereich auf die aktive im Frame fest.|  
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|Rufen Sie Informationen über die angegebene Spalte festgelegt.|  
|[CSplitterWnd::SetRowInfo](#setrowinfo)|Rufen Sie Informationen über die angegebene Zeile festgelegt.|  
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|Gibt an, dass die neue Bildlaufleisten-Formatvorlage für die unterteiltes Fenster Bildlaufleisten-Unterstützung freigegeben.|  
|[CSplitterWnd::SplitColumn](#splitcolumn)|Gibt an, in einem Rahmenfenster vertikal geteilt.|  
|[CSplitterWnd::SplitRow](#splitrow)|Gibt an, in dem ein Rahmenfenster horizontal aufgeteilt wird.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitterWnd::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework Splitterfensters gezeichnet werden soll.|  
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|Rendert ein Bild von einem geteilten Fenster an.|  
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|Rendert das Image von einem geteilten Fenster die gleiche Größe und Form als das Rahmenfenster sein.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Bereich ist in der Regel ein anwendungsspezifisches Objekt abgeleitet [CView](../../mfc/reference/cview-class.md), aber es kann eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das über die entsprechenden untergeordneten Fenster ID verfügt  
  
 Ein `CSplitterWnd` -Objekt ist in der Regel in einem übergeordneten eingebettet [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) Objekt. Erstellen einer `CSplitterWnd` -Objekt mithilfe der folgenden Schritte aus:  
  
1.  Einbetten einer `CSplitterWnd` Membervariable in den übergeordneten Frame.  
  
2.  Überschreiben Sie des übergeordneten Frames [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) Memberfunktion.  
  
3.  Von der überschriebenen `OnCreateClient`, rufen Sie die [erstellen](#create) oder [CreateStatic](#createstatic) Memberfunktion von `CSplitterWnd`.  
  
 Rufen Sie die **erstellen** Memberfunktion versucht, ein dynamisches Splitterfenster erstellen. Ein dynamisches Splitterfenster wird in der Regel zu erstellen, führen Sie einen Bildlauf eine Anzahl von einzelnen Bereiche oder Ansichten des gleichen Dokuments verwendet. Das Framework erstellt automatisch einen ersten Bereich für den Splitter; Das Framework dann erstellt, ändert die Größe und verwirft zusätzliche Bereiche wie der Benutzer den Splitter Window-Steuerelementen.  
  
 Beim Aufruf **erstellen**, geben Sie eine minimale Zeile Zeilenhöhe und Spaltenbreite, mit denen bestimmt wird, wenn die Bereiche zu klein, um vollständig angezeigt sind. Nach dem Aufruf **erstellen**, können Sie durch Aufrufen dieser Mindestwerte Anpassen der [SetColumnInfo](#setcolumninfo) und [SetRowInfo](#setrowinfo) Memberfunktionen.  
  
 Verwenden Sie auch die `SetColumnInfo` und `SetRowInfo` Memberfunktionen einer "ideale" Breite für eine Spalte und "optimale" Höhe für eine Zeile fest. Wenn das Framework ein unterteiltes Fenster angezeigt wird, wird zuerst den übergeordneten Frame, klicken Sie dann die unterteiltes Fenster angezeigt. Das Framework angeordnet klicken Sie dann auf die Bereiche in Spalten und Zeilen gemäß ihrer idealen Dimensionen, die von der linken oberen Ecke auf der unteren rechten Ecke des Clientbereichs des Splitterfensters zu arbeiten.  
  
 Alle Bereiche in ein dynamisches Splitterfenster müssen der gleichen Klasse sein. Vertraute Anwendungen, die Unterstützung von dynamischen Splitterfenstern gehören Microsoft Word und Microsoft Excel.  
  
 Verwenden der `CreateStatic` Memberfunktion versucht, ein statisches Splitterfenster erstellen. Der Benutzer kann nur die Größe der Bereiche in einem statischen Splitter Fenster, nicht deren Anzahl oder Reihenfolge ändern.  
  
 Bei der Erstellung des statischen Splitters, müssen Sie insbesondere alle statischen Splitters des Bereiche erstellen. Stellen Sie sicher, dass Sie alle Bereiche vor des übergeordneten Frames erstellen `OnCreateClient` Member-Funktion gibt oder das Framework wird das Fenster nicht richtig angezeigt.  
  
 Die `CreateStatic` Memberfunktion wird automatisch einen statischen Splitter mit einem minimalen Zeile Zeilenhöhe und Spaltenbreite 0 initialisiert. Nach dem Aufruf **erstellen**, passen Sie diese Mindestwerte durch Aufrufen der [SetColumnInfo](#setcolumninfo) und [SetRowInfo](#setrowinfo) Memberfunktionen. Verwenden Sie auch `SetColumnInfo` und `SetRowInfo` nach dem Aufruf `CreateStatic` an, dass die gewünschte ideal Bereich Dimensionen.  
  
 Die einzelnen Bereiche eines statischen Splitters gehören häufig zu verschiedenen Klassen. Beispiele für statisches Splitterfenster finden Sie in der Grafik-Editor und die Windows-Manager für Dateiserver.  
  
 Ein unterteiltes Fenster unterstützt spezielle Bildlaufleisten (abgesehen von den Bildlaufleisten, die Bereiche verfügen können). Diese Bildlaufleisten sind untergeordnete Elemente der `CSplitterWnd` -Objekt und gemeinsam mit den Bereichen.  
  
 Sie erstellen diese spezielle Bildlaufleisten, bei der Erstellung des Splitterfensters. Z. B. eine `CSplitterWnd` , besitzt eine Zeile, die zwei Spalten und die **WS_VSCROLL** Stil zeigt eine vertikale Bildlaufleiste angezeigt, die von den beiden Bereichen gemeinsam verwendet wird. Wenn der Benutzer die Bildlaufleiste bewegt `WM_VSCROLL` Nachrichten an beide Bereiche gesendet werden. Wenn die Bereiche die Bildlaufleisten-Position festgelegt, wird die freigegebene Bildlaufleiste festgelegt.  
  
 Weitere Informationen über Splitterfenster finden Sie unter:  
  
- [Technischer Hinweis 29](../../mfc/tn029-splitter-windows.md)  
  
-   Knowledge Base-Artikel Q262024: So wird's gemacht: verwenden CPropertySheet als einen untergeordneten CSplitterWnd  
  
 Weitere Informationen zum Erstellen von dynamischen Splitterfenstern finden Sie unter:  
  
-   MFC-Beispiel [Scribble](../../visual-cpp-samples.md)  
  
-   MFC-Beispiel [VIEWEX](../../visual-cpp-samples.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="activatenext"></a>  CSplitterWnd::ActivateNext  
 Vom Framework aufgerufen wird, den nächsten oder vorherigen Bereich-Befehl auszuführen.  
  
```  
virtual void ActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bPrev`  
 Gibt an, welches Fenster zu aktivieren. **"True"** für vorherige; **"False"** für weiter.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist ein auf hoher Ebene Befehl, mit dem die [CView](../../mfc/reference/cview-class.md) Klasse für die Delegierung an die `CSplitterWnd` Implementierung.  
  
##  <a name="canactivatenext"></a>  CSplitterWnd::CanActivateNext  
 Vom Framework aufgerufen wird, überprüfen, wenn der Befehl zum nächsten oder vorherigen Bereich derzeit möglich ist.  
  
```  
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bPrev`  
 Gibt an, welches Fenster zu aktivieren. **"True"** für vorherige; **"False"** für weiter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist ein auf hoher Ebene Befehl, mit dem die [CView](../../mfc/reference/cview-class.md) Klasse für die Delegierung an die `CSplitterWnd` Implementierung.  
  
##  <a name="create"></a>  Splitterfenstern  
 Um ein dynamisches Splitterfenster zu erstellen, rufen Sie die **erstellen** Memberfunktion.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    int nMaxRows,  
    int nMaxCols,  
    SIZE sizeMin,  
    CCreateContext* pContext,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_HSCROLL | WS_VSCROLL | SPLS_DYNAMIC_SPLIT,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Der übergeordnete Rahmenfenster des Splitterfensters.  
  
 *nMaxRows*  
 Die maximale Anzahl der Zeilen in der unterteiltes Fenster. Dieser Wert darf maximal 2.  
  
 *nMaxCols*  
 Die maximale Anzahl der Spalten in der unterteiltes Fenster. Dieser Wert darf maximal 2.  
  
 `sizeMin`  
 Gibt die minimale Größe, die bei der ein Bereich angezeigt werden kann.  
  
 `pContext`  
 Ein Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Struktur. In den meisten Fällen kann dies die `pContext` an der übergeordneten Rahmenfensters übergeben.  
  
 `dwStyle`  
 Gibt den Fensterstil.  
  
 `nID`  
 Die untergeordneten Fenster-ID des Fensters. Die ID kann **AFX_IDW_PANE_FIRST** , sofern Splitterfensters in einem anderen unterteiltes Fenster geschachtelt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie können Einbetten einer `CSplitterWnd` in einem übergeordneten [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) Objekt, indem Sie folgende Schritte ausführen:  
  
1.  Einbetten einer `CSplitterWnd` Membervariable in den übergeordneten Frame.  
  
2.  Überschreiben Sie des übergeordneten Frames [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) Memberfunktion.  
  
3.  Rufen Sie die **erstellen** Memberfunktion, die von der überschriebenen `OnCreateClient`.  
  
 Wenn Sie ein unterteiltes-Fenster innerhalb eines übergeordneten Frames erstellen, übergeben Sie des übergeordneten Frames `pContext` Splitterfensters Parameter. Dieser Parameter kann, andernfalls **NULL**.  
  
 Die Anfangszeile minimale Zeilenhöhe und Spaltenbreite für ein dynamisches Splitterfenster werden festgelegt, indem die `sizeMin` Parameter. Dieser Mindestwerte, die bestimmen, ob ein Bereich in seiner Gesamtheit anzuzeigenden zu klein ist, können geändert werden, mit der [SetRowInfo](#setrowinfo) und [SetColumnInfo](#setcolumninfo) Memberfunktionen.  
  
 Weitere Informationen über dynamische Splitterfenster finden Sie unter "Splitterfenster" im Artikel [mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md), [technischen Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` -Klassenübersicht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]  
  
##  <a name="createscrollbarctrl"></a>  CSplitterWnd::CreateScrollBarCtrl  
 Wird aufgerufen, durch das Framework zum Erstellen einer freigegebenen Bildlaufleisten-Steuerelement.  
  
```  
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt den Fensterstil.  
  
 `nID`  
 Die untergeordneten Fenster-ID des Fensters. Die ID kann **AFX_IDW_PANE_FIRST** , sofern Splitterfensters in einem anderen unterteiltes Fenster geschachtelt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie `CreateScrollBarCtrl` enthalten zusätzliche Steuerelemente neben einer Bildlaufleiste. Das Standardverhalten besteht darin normalen Windows-Bildlaufleisten-Steuerelemente zu erstellen.  
  
##  <a name="createstatic"></a>  CSplitterWnd::CreateStatic  
 Um ein statisches Splitterfenster zu erstellen, rufen Sie die `CreateStatic` Memberfunktion.  
  
```  
virtual BOOL CreateStatic(
    CWnd* pParentWnd,  
    int nRows,  
    int nCols,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Der übergeordnete Rahmenfenster des Splitterfensters.  
  
 `nRows`  
 Die Anzahl von Zeilen. Dieser Wert darf 16 nicht überschreiten.  
  
 *nCols*  
 Die Anzahl von Spalten. Dieser Wert darf 16 nicht überschreiten.  
  
 `dwStyle`  
 Gibt den Fensterstil.  
  
 `nID`  
 Die untergeordneten Fenster-ID des Fensters. Die ID kann **AFX_IDW_PANE_FIRST** , sofern Splitterfensters in einem anderen unterteiltes Fenster geschachtelt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ein `CSplitterWnd` ist in der Regel in einem übergeordneten eingebettet `CFrameWnd` oder [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) Objekt, indem Sie folgende Schritte ausführen:  
  
1.  Einbetten einer `CSplitterWnd` Membervariable in den übergeordneten Frame.  
  
2.  Überschreiben Sie des übergeordneten Frames `OnCreateClient` Memberfunktion.  
  
3.  Rufen Sie die `CreateStatic` Memberfunktion, die von der überschriebenen [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient).  
  
 Ein statisches Splitterfenster enthält eine feste Anzahl von Bereichen, häufig aus verschiedenen Klassen.  
  
 Wenn Sie ein statisches Splitterfenster erstellen, müssen Sie alle Bereiche gleichzeitig erstellen. Die [CreateView](#createview) Memberfunktion wird in der Regel für diesen Zweck verwendet, aber Sie können auch andere Nonview Klassen erstellen.  
  
 Die Anfangszeile minimale Zeilenhöhe und Spaltenbreite für ein statisches Splitterfenster ist 0. Dieser Mindestwerte, die bestimmen, wenn ein Bereich in seiner Gesamtheit dargestellt werden zu klein ist, können geändert werden, mit der [SetRowInfo](#setrowinfo) und [SetColumnInfo](#setcolumninfo) Memberfunktionen.  
  
 Um ein statisches Splitterfenster Bildlaufleisten hinzuzufügen, fügen die **WS_HSCROLL** und **WS_VSCROLL** Stile auf `dwStyle`.  
  
 Finden Sie unter "Splitterfenster" im Artikel [mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md), [technischen Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` für Weitere Informationen über die statisches Splitterfenster-Klassenübersicht.  
  
##  <a name="createview"></a>  CSplitterWnd:: CreateView-Funktion  
 Die Bereiche für ein statisches Splitterfenster wird erstellt.  
  
```  
virtual BOOL CreateView(
    int row,  
    int col,  
    CRuntimeClass* pViewClass,  
    SIZE sizeInit,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Parameter  
 `row`  
 Gibt die Zeile Splitter Fenster, in das die neue Ansicht eingefügt werden soll.  
  
 `col`  
 Gibt die Spalte Splitter Fenster, in das die neue Ansicht eingefügt werden soll.  
  
 `pViewClass`  
 Gibt an, die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) der neuen Sicht.  
  
 *sizeInit*  
 Gibt die Anfangsgröße der neuen Sicht an.  
  
 `pContext`  
 Ein Zeiger auf einen erstellen-Kontext verwendet, um die Ansicht zu erstellen (in der Regel die `pContext` an des übergeordneten Frames außer Kraft gesetzte übergeben [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) Memberfunktion, die in der Splitterfensters erstellt wird).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Alle Bereiche der ein statisches Splitterfenster müssen erstellt werden, bevor das Framework den Splitter wird angezeigt.  
  
 Das Framework ruft auch diese Memberfunktion zum neuen Bereiche zu erstellen, wenn der Benutzer ein dynamisches Splitterfenster einen Bereich, Zeile oder Spalte geteilt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]  
  
##  <a name="csplitterwnd"></a>  CSplitterWnd::CSplitterWnd  
 Der Aufruf zum Erstellen einer `CSplitterWnd` Objekt.  
  
```  
CSplitterWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CSplitterWnd` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor erstellt die `CSplitterWnd` Objekt, und rufen Sie anschließend die [erstellen](#create) Memberfunktion, die die unterteiltes Fenster erstellt, und fügt es der `CSplitterWnd` Objekt.  
  
##  <a name="deletecolumn"></a>  CSplitterWnd::DeleteColumn  
 Löscht eine Spalte aus der unterteiltes Fenster an.  
  
```  
virtual void DeleteColumn(int colDelete);
```  
  
### <a name="parameters"></a>Parameter  
 *colDelete*  
 Gibt die Spalte gelöscht werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird vom Framework zum Implementieren der Logik des dynamischen Splitterfensters aufgerufen (d. h., wenn das Splitterfenster verfügt über die **SPLS_DYNAMIC_SPLIT** Stil). Sie können angepasst werden, zusammen mit der virtuellen Funktion [CreateView](#createview), um erweiterte dynamischen Splitterfenstern zu implementieren.  
  
##  <a name="deleterow"></a>  CSplitterWnd::DeleteRow  
 Löscht eine Zeile aus der unterteiltes Fenster.  
  
```  
virtual void DeleteRow(int rowDelete);
```  
  
### <a name="parameters"></a>Parameter  
 *rowDelete*  
 Gibt die zu löschende Zeile.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird vom Framework zum Implementieren der Logik des dynamischen Splitterfensters aufgerufen (d. h., wenn das Splitterfenster verfügt über die **SPLS_DYNAMIC_SPLIT** Stil). Sie können angepasst werden, zusammen mit der virtuellen Funktion [CreateView](#createview), um erweiterte dynamischen Splitterfenstern zu implementieren.  
  
##  <a name="deleteview"></a>  CSplitterWnd::DeleteView  
 Löscht eine Ansicht aus der unterteiltes Fenster an.  
  
```  
virtual void DeleteView(
    int row,  
    int col);
```  
  
### <a name="parameters"></a>Parameter  
 `row`  
 Gibt die Splitter Fenster Zeile, an dem die Sicht zu löschen.  
  
 `col`  
 Gibt die Splitter Fenster-Spalte, an dem die Sicht zu löschen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die aktive Ansicht gelöscht wird, wird die nächste Ansicht aktiviert werden. Die Standardimplementierung geht davon aus, die Sicht werden automatisch löschen [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy).  
  
 Diese Memberfunktion wird vom Framework zum Implementieren der Logik des dynamischen Splitterfensters aufgerufen (d. h., wenn das Splitterfenster verfügt über die **SPLS_DYNAMIC_SPLIT** Stil). Sie können angepasst werden, zusammen mit der virtuellen Funktion [CreateView](#createview), um erweiterte dynamischen Splitterfenstern zu implementieren.  
  
##  <a name="dokeyboardsplit"></a>  CSplitterWnd::DoKeyboardSplit  
 Führt die Tastatur split-Befehl, in der Regel "Fenster teilen."  
  
```  
virtual BOOL DoKeyboardSplit();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist ein auf hoher Ebene Befehl, mit dem die [CView](../../mfc/reference/cview-class.md) Klasse für die Delegierung an die `CSplitterWnd` Implementierung.  
  
##  <a name="doscroll"></a>  CSplitterWnd::DoScroll  
 Führt die synchronisierten Bildlauf bei der Split-Windows.  
  
```  
virtual BOOL DoScroll(
    CView* pViewFrom,  
    UINT nScrollCode,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pViewFrom`  
 Ein Zeiger auf die Sicht aus der Durchführen eines Bildlaufs Nachricht stammt.  
  
 `nScrollCode`  
 Ein Bildlaufleisten-Code, der den Benutzer angibt, der Anforderung Bildlauf. Dieser Parameter besteht aus zwei Teilen: ein niederwertige Byte ist, die den Typ des horizontalen Bildlauf auftritt bestimmt wird, und ein höherwertige Byte ist, die festlegt, den Typ des vertikalen Bildlauf auftritt:  
  
- **SB_BOTTOM** führt einen Bildlauf nach unten.  
  
- **SB_LINEDOWN** führt einen Bildlauf eine Zeile nach unten.  
  
- **SB_LINEUP** führt einen Bildlauf eine Zeile einrichten.  
  
- **SB_PAGEDOWN** führt einen Bildlauf eine Seite nach unten.  
  
- **SB_PAGEUP** führt einen Bildlauf eine Seite einrichten.  
  
- **SB_TOP** führt einen Bildlauf nach oben.  
  
 `bDoScroll`  
 Bestimmt, ob die angegebene Aktion durchführen eines Bildlaufs ausgeführt wird. Wenn `bDoScroll` ist **"true"** (d. h., wenn ein untergeordnetes Fenster vorhanden ist und die Fenster teilen ein Bildlaufbereichs einen haben), und klicken Sie dann die angegebene Aktion durchführen eines Bildlaufs; Wenn stattfinden kann `bDoScroll` ist **"false"** (d. h. wenn keine untergeordneten Fenster vorhanden ist, oder die geteilten Ansichten haben keine Bildlaufleisten-Bereich), und klicken Sie dann einen Bildlauf nicht auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Durchführen eines Bildlaufs ungleich NULL, wenn synchronisiert auftritt. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird aufgerufen, durch das Framework auszuführenden synchronisierte Bildlauf bei der Teilung Windows, wenn die Sicht eine Scroll-Nachricht empfängt. Überschreiben Sie, um eine Aktion vom Benutzer erforderlich, bevor synchronisierte Bildlauf zulässig ist.  
  
##  <a name="doscrollby"></a>  CSplitterWnd::DoScrollBy  
 Scrollt geteilte Fenster durch eine angegebene Anzahl von Pixeln.  
  
```  
virtual BOOL DoScrollBy(
    CView* pViewFrom,  
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pViewFrom`  
 Ein Zeiger auf die Sicht aus der Durchführen eines Bildlaufs Nachricht stammt.  
  
 `sizeScroll`  
 Anzahl der Pixel horizontal und vertikal angezeigt werden.  
  
 bDoScroll  
 Bestimmt, ob die angegebene Aktion durchführen eines Bildlaufs ausgeführt wird. Wenn `bDoScroll` ist **"true"** (d. h., wenn ein untergeordnetes Fenster vorhanden ist und die Fenster teilen ein Bildlaufbereichs einen haben), und klicken Sie dann die angegebene Aktion durchführen eines Bildlaufs; Wenn stattfinden kann `bDoScroll` ist **"false"** (d. h. wenn keine untergeordneten Fenster vorhanden ist, oder die geteilten Ansichten haben keine Bildlaufleisten-Bereich), und klicken Sie dann einen Bildlauf nicht auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Durchführen eines Bildlaufs ungleich NULL, wenn synchronisiert auftritt. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion vom Framework als Antwort auf eine Nachricht Scroll aufgerufen wird, ausführen synchronisiert der geteilten Fenster erheben, in Pixel, angegeben durch Scrollen `sizeScroll`. Positive Werte geben einen Bildlauf nach unten und rechts; negative Werte geben Sie einen Bildlauf nach oben und nach links an.  
  
 Überschreiben Sie, um eine Aktion vom Benutzer zuzulassen Bildlauf erfordern.  
  
##  <a name="getactivepane"></a>  CSplitterWnd::GetActivePane  
 Bestimmt den aktiven Bereich den Fokus oder die aktive Ansicht im Frame.  
  
```  
virtual CWnd* GetActivePane(
    int* pRow = NULL,  
    int* pCol = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pRow`  
 Ein Zeiger auf ein **Int** zum Abrufen der Zeilennummer im aktiven Bereich.  
  
 `pCol`  
 Ein Zeiger auf ein **Int** die Spaltennummer des aktiven Bereichs abgerufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktiven Bereich. **NULL** Wenn keine aktiven Bereich vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird durch das Framework, um zu bestimmen, den aktiven Bereich in einem Splitterfenster aufgerufen. Überschreiben Sie, um eine Aktion vom Benutzer vor dem Abrufen des aktiven Bereichs erforderlich ist.  
  
##  <a name="getcolumncount"></a>  CSplitterWnd::GetColumnCount  
 Gibt die aktuelle Anzahl der Spalten im Bereich zurück.  
  
```  
int GetColumnCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktuelle Anzahl der Spalten in der Splitter zurück. Ein statischer Splitter werden dadurch auch die maximale Anzahl von Spalten.  
  
##  <a name="getcolumninfo"></a>  CSplitterWnd::GetColumnInfo  
 Gibt Informationen zu der angegebenen Spalte zurück.  
  
```  
void GetColumnInfo(
    int col,  
    int& cxCur,  
    int& cxMin) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `col`  
 Gibt eine Spalte an.  
  
 *cxCur*  
 Ein Verweis auf eine `int` auf die aktuelle Breite der Spalte festgelegt werden.  
  
 `cxMin`  
 Ein Verweis auf eine `int` auf die aktuelle minimale Breite der Spalte festgelegt werden.  
  
##  <a name="getpane"></a>  CSplitterWnd::GetPane  
 Gibt den Bereich in der angegebenen Zeile und Spalte zurück.  
  
```  
CWnd* GetPane(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `row`  
 Gibt eine Zeile an.  
  
 `col`  
 Gibt eine Spalte an.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Bereich in der angegebenen Zeile und Spalte zurück. Der zurückgegebene Bereich ist in der Regel eine [CView](../../mfc/reference/cview-class.md)-Klasse.  
  
##  <a name="getrowcount"></a>  CSplitterWnd::GetRowCount  
 Gibt den aktuellen Bereich Zeilenanzahl zurück.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktuelle Anzahl der Zeilen in der unterteiltes Fenster zurück. Für ein statisches Splitterfenster wird dies auch die maximale Anzahl von Zeilen sein.  
  
##  <a name="getrowinfo"></a>  CSplitterWnd::GetRowInfo  
 Gibt Informationen zu der angegebenen Zeile zurück.  
  
```  
void GetRowInfo(
    int row,  
    int& cyCur,  
    int& cyMin) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `row`  
 Gibt eine Zeile an.  
  
 `cyCur`  
 Ein Verweis auf `int` auf der aktuellen Höhe der Zeile in Pixel festgelegt werden.  
  
 `cyMin`  
 Ein Verweis auf `int` auf die aktuelle Mindesthöhe der Zeile in Pixel festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion zum Abrufen von Informationen zu der angegebenen Zeile an. Die `cyCur` Parameter mit der aktuellen Höhe der angegebenen Zeile gefüllt ist und `cyMin` mit die Mindesthöhe der Zeile gefüllt ist.  
  
##  <a name="getscrollstyle"></a>  CSplitterWnd::GetScrollStyle  
 Gibt den Schriftschnitt freigegebenen Bildlaufleiste für das Splitterfenster.  
  
```  
DWORD GetScrollStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine oder mehrere der folgenden Windows style Flags, die bei Erfolg:  
  
- **WS_HSCROLL** Wenn Splitters derzeit freigegebenen horizontale Bildlaufleisten verwaltet.  
  
- **WS_VSCROLL** Wenn Splitters derzeit freigegebenen vertikalen Schiebeleisten verwaltet.  
  
 Wenn 0 (null), Splitterfensters kein derzeit freigegebenen Bildlaufleisten verwaltet werden.  
  
##  <a name="idfromrowcol"></a>  CSplitterWnd::IdFromRowCol  
 Ruft das untergeordnete Fenster-ID für den Bereich in der angegebenen Zeile und Spalte ab.  
  
```  
int IdFromRowCol(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `row`  
 Gibt die Zeile der Splitter-Fenster.  
  
 `col`  
 Gibt die Spalte der Splitter-Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Die untergeordneten Fenster-ID für den Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion dient zum Erstellen von Nonviews als Bereiche und kann aufgerufen werden, bevor Sie der Bereich vorhanden ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]  
  
##  <a name="ischildpane"></a>  CSplitterWnd::IsChildPane  
 Bestimmt, ob `pWnd` ist derzeit ein untergeordneten Bereich dieser unterteiltes Fenster.  
  
```  
BOOL IsChildPane(
    CWnd* pWnd,  
    int* pRow,  
    int* pCol);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) Objekt, das getestet werden.  
  
 `pRow`  
 Ein Zeiger auf ein `int` in dem die Nummer der Zeile gespeichert.  
  
 `pCol`  
 Ein Zeiger auf ein `int` in der eine Spaltennummer gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL `pWnd` ist derzeit ein untergeordneten Bereich dieses Fensters Splitter und `pRow` und `pCol` werden sich die Position des Bereichs in Splitterfensters gefüllt. Wenn `pWnd` ist es sich nicht um ein untergeordneten Bereich dieses Fensters Splitter wird 0 zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 In Visual C++-Versionen vor 6.0 wurde diese Funktion als definiert.  
  
 `BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`  
  
 Diese Version ist jetzt veraltet und sollte nicht verwendet werden.  
  
##  <a name="istracking"></a>  CSplitterWnd::IsTracking  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Teilerleiste in das Fenster derzeit verschoben wird.  
  
```  
BOOL IsTracking();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Splitter-Vorgang ausgeführt wird; andernfalls 0.  
  
##  <a name="ondrawsplitter"></a>  CSplitterWnd::OnDrawSplitter  
 Rendert ein Bild von einem geteilten Fenster an.  
  
```  
virtual void OnDrawSplitter(
    CDC* pDC,  
    ESplitType nType,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Gerätekontext, in dem gezeichnet werden soll. Wenn `pDC` ist **NULL**, klicken Sie dann [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) aufgerufen wird und keine Aufteilung Fensters gezeichnet wird.  
  
 `nType`  
 Der Wert der **Enum ESplitType**, kann die eines der folgenden sein:  
  
- **SplitBox** Splitters ziehen Sie das Feld.  
  
- `splitBar` Die Leiste, die zwischen den zwei Teilfenstern angezeigt wird.  
  
- **SplitIntersection** die Schnittmenge der geteilten Fenster. Dieses Element wird nicht aufgerufen werden, wenn auf Windows 95-und Windows 98 ausgeführt wird.  
  
- **SplitBorder** Fensterrahmen teilen.  
  
 `rect`  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Größe und Form des Windows-Teilung angibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird vom Framework zu zeichnen, und geben Sie die genaue Merkmale eines unterteilten Fensters aufgerufen. Überschreiben Sie `OnDrawSplitter` für die erweiterte Anpassung von der Bilder für die verschiedenen Grafikkomponenten eines unterteilten Fensters. Der Standard-Bilder ähnelt des Splitters in Microsoft Works für Windows oder Microsoft Windows 95-und Windows 98, insofern, dass die Schnittmengen der Splitter Balken miteinander vermischt werden.  
  
 Weitere Informationen über dynamische Splitterfenster finden Sie unter "Splitterfenster" im Artikel [mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md), [technischen Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` -Klassenübersicht.  
  
##  <a name="oninverttracker"></a>  CSplitterWnd::OnInvertTracker  
 Rendert das Image von einem geteilten Fenster die gleiche Größe und Form als das Rahmenfenster sein.  
  
```  
virtual void OnInvertTracker(const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Ein Verweis auf eine `CRect` -Objekt, das Überwachungsprofil Rechteck angibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird vom Framework aufgerufen, während der Größenänderung des Splitterfenstern. Überschreiben Sie `OnInvertTracker` für die erweiterte Anpassung von der Bilder des Splitterfensters. Der Standard-Bilder ähnelt des Splitters in Microsoft Works für Windows oder Microsoft Windows 95-und Windows 98, insofern, dass die Schnittmengen der Splitter Balken miteinander vermischt werden.  
  
 Weitere Informationen über dynamische Splitterfenster finden Sie unter "Splitterfenster" im Artikel [mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md), [technischen Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` -Klassenübersicht.  
  
##  <a name="recalclayout"></a>  CSplitterWnd::RecalcLayout  
 Rufen Sie auf, um die unterteiltes Fenster anzuzeigen, nach der Zeile oder Spalte Größe anpassen.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion zum Splitterfensters ordnungsgemäß anzuzeigen, nachdem Sie die Zeilen- und Größen mit eingestellt haben die [SetRowInfo](#setrowinfo) und [SetColumnInfo](#setcolumninfo) Memberfunktionen. Wenn Sie Zeilen- und Größen als Teil des Erstellungsprozesses ändern, bevor die unterteiltes Fenster sichtbar ist, ist es nicht erforderlich, diese Memberfunktion aufrufen.  
  
 Das Framework ruft diese Memberfunktion auf, wenn der Benutzer ändert die Größe der unterteiltes Fenster oder eine Teilung verschiebt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CSplitterWnd::SetColumnInfo](#setcolumninfo).  
  
##  <a name="setactivepane"></a>  CSplitterWnd::SetActivePane  
 Legt einen Bereich auf die aktive im Frame fest.  
  
```  
virtual void SetActivePane(
    int row,  
    int col,  
    CWnd* pWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `row`  
 Wenn `pWnd` ist **NULL**, gibt die Zeile im Bereich, die aktiv sind.  
  
 `col`  
 Wenn `pWnd` ist **NULL**, gibt die Spalte in den Bereich, die aktiv sind.  
  
 `pWnd`  
 Ein Zeiger auf eine `CWnd` Objekt. Wenn **NULL**, dem Bereich gemäß `row` und `col` aktiv festgelegt ist. Wenn dies nicht der **NULL**, gibt der Bereich, der aktiv festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird aufgerufen, durch das Framework einen Bereich als aktiv festlegen, wenn der Benutzer den Fokus auf einen Bereich innerhalb der Frame-Fensters ändert. Sie können explizit aufrufen, `SetActivePane` so ändern Sie den Fokus auf die angegebene Ansicht.  
  
 Geben Sie im Bereich durch die Bereitstellung von Zeile und Spalte **oder** durch die Bereitstellung `pWnd`.  
  
##  <a name="setcolumninfo"></a>  CSplitterWnd::SetColumnInfo  
 Rufen Sie Informationen über die angegebene Spalte festgelegt.  
  
```  
void SetColumnInfo(
    int col,  
    int cxIdeal,  
    int cxMin);
```  
  
### <a name="parameters"></a>Parameter  
 `col`  
 Gibt eine Spalte der Splitter-Fenster.  
  
 *cxIdeal*  
 Gibt eine ideale Breite der Spalte der Splitter-Fenster in Pixel an.  
  
 `cxMin`  
 Gibt eine minimale Breite der Spalte der Splitter Fenster in Pixel an.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um eine neue minimale Breite und die ideale Breite für eine Spalte festzulegen. Der minimale Wert der Spalte bestimmt, wenn die Spalte zu klein, um vollständig angezeigt werden kann.  
  
 Wenn das Framework Splitterfensters angezeigt wird, ordnet es die Bereiche in Spalten und Zeilen gemäß ihrer idealen Dimensionen, die von der linken oberen Ecke auf der unteren rechten Ecke des Clientbereichs des Splitterfensters arbeiten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]  
  
##  <a name="setrowinfo"></a>  CSplitterWnd::SetRowInfo  
 Rufen Sie Informationen über die angegebene Zeile festgelegt.  
  
```  
void SetRowInfo(
    int row,  
    int cyIdeal,  
    int cyMin);
```  
  
### <a name="parameters"></a>Parameter  
 `row`  
 Gibt eine Zeile der Splitter-Fenster an.  
  
 *cyIdeal*  
 Gibt eine ideale Höhe der Zeile der Splitter-Fenster in Pixel an.  
  
 `cyMin`  
 Gibt eine minimale Höhe der Zeile der Splitter-Fenster in Pixel an.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um eine neue minimale Höhe und die ideale Höhe einer Zeile festzulegen. Der Mindestwert für die Zeile wird bestimmt, wenn die Zeile zu klein, um vollständig angezeigt werden kann.  
  
 Wenn das Framework Splitterfensters angezeigt wird, ordnet es die Bereiche in Spalten und Zeilen gemäß ihrer idealen Dimensionen, die von der linken oberen Ecke auf der unteren rechten Ecke des Clientbereichs des Splitterfensters arbeiten.  
  
##  <a name="setscrollstyle"></a>  CSplitterWnd::SetScrollStyle  
 Gibt an, dass die neue Scroll Formatvorlage für die unterteiltes Fenster Bildlaufleisten-Unterstützung freigegeben.  
  
```  
void SetScrollStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Die neue Scroll Formatvorlage für die unterteiltes Fenster freigegebene Bildlaufleisten-Unterstützung, die der folgenden Werte sind möglich:  
  
- **WS_HSCROLL** erstellen/anzeigen horizontaler freigegebene Bildlaufleisten.  
  
- **WS_VSCROLL** erstellen/anzeigen vertikaler freigegebene Bildlaufleisten.  
  
### <a name="remarks"></a>Hinweise  
 Nach der Erstellung einer Bildlaufleiste ist es, werden nicht zerstört selbst wenn `SetScrollStyle` aufgerufen wird, ohne diesen Stil; stattdessen diese Bildlaufleisten werden ausgeblendet. Dadurch wird die Bildlaufleisten, um ihren Zustand zu beizubehalten, auch wenn sie ausgeblendet sind. Nach dem Aufruf `SetScrollStyle` es ist erforderlich, rufen Sie [RecalcLayout](#recalclayout) für alle Änderungen wirksam werden.  
  
##  <a name="splitcolumn"></a>  CSplitterWnd::SplitColumn  
 Gibt an, in einem Rahmenfenster vertikal geteilt.  
  
```  
virtual BOOL SplitColumn(int cxBefore);
```  
  
### <a name="parameters"></a>Parameter  
 *cxBefore*  
 Die Position in Pixel, die vor denen die Teilung auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird aufgerufen, wenn eine vertikale unterteiltes Fenster erstellt wird. `SplitColumn` Gibt den Standardspeicherort, wo die Teilung auftritt.  
  
 `SplitColumn` durch das Framework zum Implementieren der Logik des dynamischen Splitterfensters aufgerufen wird (d. h., wenn das Splitterfenster verfügt über die **SPLS_DYNAMIC_SPLIT** Stil). Sie können angepasst werden, zusammen mit der virtuellen Funktion [CreateView](#createview), um erweiterte dynamischen Splitterfenstern zu implementieren.  
  
##  <a name="splitrow"></a>  CSplitterWnd::SplitRow  
 Gibt an, in dem ein Rahmenfenster horizontal aufgeteilt wird.  
  
```  
virtual BOOL SplitRow(int cyBefore);
```  
  
### <a name="parameters"></a>Parameter  
 *cyBefore*  
 Die Position in Pixel, die vor denen die Teilung auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird aufgerufen, wenn ein horizontaler unterteiltes Fenster erstellt wird. `SplitRow` Gibt den Standardspeicherort, wo die Teilung auftritt.  
  
 `SplitRow` durch das Framework zum Implementieren der Logik des dynamischen Splitterfensters aufgerufen wird (d. h., wenn das Splitterfenster verfügt über die **SPLS_DYNAMIC_SPLIT** Stil). Sie können angepasst werden, zusammen mit der virtuellen Funktion [CreateView](#createview), um erweiterte dynamischen Splitterfenstern zu implementieren.  
  
##  <a name="ondraw"></a>  CSplitterWnd::OnDraw  
 Wird aufgerufen, durch das Framework Splitterfensters gezeichnet werden soll.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel VIEWEX](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)
