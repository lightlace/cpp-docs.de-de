---
title: CSplitterWnd-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: 065735c13a3e763208142eb6bc989d3a496221f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323816"
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
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|Aufruf zum Erstellen einer `CSplitterWnd` Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSplitterWnd::ActivateNext](#activatenext)|Führt den Befehl zum nächsten oder vorherigen Bereich.|
|[CSplitterWnd::CanActivateNext](#canactivatenext)|Überprüft, um festzustellen, ob es sich bei der nächsten oder vorherigen Bereich Befehl derzeit möglich ist.|
|[CSplitterWnd::Create](#create)|Aufruf erstellen ein dynamisches Teilungsfenster und fügen Sie ihn auf die `CSplitterWnd` Objekt.|
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|Erstellt ein freigegebenes Bildlaufleistensteuerelement an.|
|[CSplitterWnd::CreateStatic](#createstatic)|Aufruf erstellen ein statisches Splitterfenster, und fügen Sie ihn auf die `CSplitterWnd` Objekt.|
|[CSplitterWnd::CreateView](#createview)|Rufen Sie auf, um einen Bereich in einem Splitterfenster zu erstellen.|
|[CSplitterWnd::DeleteColumn](#deletecolumn)|Löscht eine Spalte aus der Teilungsfenster.|
|[CSplitterWnd::DeleteRow](#deleterow)|Löscht eine Zeile aus Teilungsfenster.|
|[CSplitterWnd::DeleteView](#deleteview)|Löscht eine Ansicht aus Teilungsfenster.|
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|Führt den Tastaturteilbefehl aus, in der Regel "Window Split."|
|[CSplitterWnd::DoScroll](#doscroll)|Führt die synchronisierten Bildlauf in Teilfenstern aus.|
|[CSplitterWnd::DoScrollBy](#doscrollby)|Führt einen Bildlauf in Teilfenstern eine angegebene Anzahl von Pixeln.|
|[CSplitterWnd::GetActivePane](#getactivepane)|Bestimmt den aktiven Bereich im Fokus oder der aktiven Ansicht im Rahmen fest.|
|[CSplitterWnd::GetColumnCount](#getcolumncount)|Gibt die aktuelle Anzahl der Spalten im Bereich zurück.|
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|Gibt Informationen über die angegebene Spalte zurück.|
|[CSplitterWnd::GetPane](#getpane)|Gibt den Bereich in der angegebenen Zeile und Spalte zurück.|
|[CSplitterWnd::GetRowCount](#getrowcount)|Gibt die Anzahl der aktuelle Bereich Zeilen zurück.|
|[CSplitterWnd::GetRowInfo](#getrowinfo)|Gibt Informationen über die angegebene Zeile zurück.|
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|Gibt den gemeinsam genutzten Bildlaufleisten-Format zurück.|
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|Gibt das untergeordnete Fenster-ID des Bereichs in der angegebenen Zeile und Spalte zurück.|
|[CSplitterWnd::IsChildPane](#ischildpane)|Aufruf, um zu bestimmen, ob das Fenster derzeit einen untergeordneten Bereich Splitter im Fenster ist.|
|[CSplitterWnd::IsTracking](#istracking)|Bestimmt, ob der Teilerleiste gerade verschoben wird.|
|[CSplitterWnd::RecalcLayout](#recalclayout)|Rufen Sie auf, um die erneute Anzeige der Teilungsfenster. nach der Zeile oder Spalte Größe anpassen.|
|[CSplitterWnd::SetActivePane](#setactivepane)|Legt einen Bereich auf die aktiven im Rahmen fest.|
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|Rufen Sie die Informationen für die angegebene Spalte festgelegt.|
|[CSplitterWnd::SetRowInfo](#setrowinfo)|Rufen Sie die Informationen für die angegebene Zeile festgelegt.|
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|Gibt an, dass die neue Bildlaufleisten-Formatvorlage für des Splitter-Fensters Bildlaufleisten-Unterstützung freigegeben.|
|[CSplitterWnd::SplitColumn](#splitcolumn)|Gibt an, ob ein Rahmenfenster vertikal aufgeteilt wird.|
|[CSplitterWnd::SplitRow](#splitrow)|Gibt an, ob ein Rahmenfenster horizontal aufgeteilt wird.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSplitterWnd::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework das Splitterfenster gezeichnet werden soll.|
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|Rendert das Bild eines Teilfensters.|
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|Rendert das Bild eines Teilfensters gleicher Größe und Form als das Rahmenfenster sein.|

## <a name="remarks"></a>Hinweise

Ein Bereich ist in der Regel ein anwendungsspezifisches Objekt abgeleitet [CView](../../mfc/reference/cview-class.md), aber es kann sein, alle [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das die entsprechenden untergeordneten Fenster-ID verfügt.

Ein `CSplitterWnd` -Objekt ist in der Regel in einem übergeordneten eingebettet [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) Objekt. Erstellen Sie eine `CSplitterWnd` -Objekt mithilfe der folgenden Schritte aus:

1. Einbetten einer `CSplitterWnd` Membervariable in übergeordneten Rahmens.

2. Überschreiben des übergeordneten Rahmens [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) Member-Funktion.

3. Von in der überschriebenen `OnCreateClient`, rufen Sie die [erstellen](#create) oder [CreateStatic](#createstatic) Memberfunktion `CSplitterWnd`.

Rufen Sie die `Create` Memberfunktion versucht, ein dynamisches Teilungsfenster erstellen. Ein dynamisches Splitterfenster wird in der Regel verwendet, erstellen und führen Sie einen Bildlauf eine Anzahl der einzelnen Bereiche oder Ansichten des gleichen Dokuments. Das Framework erstellt automatisch einen anfängliche Bereich für den Splitter; Das Framework dann erstellt, ändert die Größe und verwirft zusätzlichen Bereichen wie der Benutzer das Splitter-Window-Steuerelemente.

Beim Aufruf `Create`, Sie geben eine minimale Zeilengröße Zeilenhöhe und Spaltenbreite, die bestimmen, wenn die Bereiche vollständig angezeigt werden zu klein sind. Nach dem Aufruf von `Create`, Sie können diese Mindestwerte anpassen, durch den Aufruf der [SetColumnInfo](#setcolumninfo) und [SetRowInfo](#setrowinfo) Memberfunktionen.

Verwenden Sie auch die `SetColumnInfo` und `SetRowInfo` Memberfunktionen zum Festlegen der Breite einer "ideale" für eine Spalte und "ideale" Höhe für eine Zeile. Wenn das Framework ein unterteilten Fensters angezeigt wird, wird zuerst der übergeordneten Rahmen, klicken Sie dann das Splitterfenster angezeigt. Das Framework ordnet anschließend die Bereiche in Spalten und Zeilen gemäß ihrer idealen Dimensionen, die von der linken oberen Ecke in die unteren rechten Ecke des Clientbereichs des Fensters Splitter arbeiten.

Alle Bereiche in ein dynamisches Teilungsfenster müssen derselben Klasse sein. Vertraute Anwendungen mit Unterstützung für dynamische Splitterfenster enthalten Microsoft Word und Microsoft Excel.

Verwenden der `CreateStatic` Memberfunktion versucht, ein statisches Splitterfenster zu erstellen. Der Benutzer kann nur die Größe der Bereiche in eine statische Aufteilung Fenster, nicht deren Anzahl oder Reihenfolge ändern.

Sie müssen insbesondere alle die statische Aufteilung der Bereiche erstellen, bei der Erstellung statischen Splitters. Stellen Sie sicher, dass die Erstellung aller Bereiche vor dem des übergeordneten Rahmens `OnCreateClient` Member-Funktion gibt, oder das Framework wird das Fenster nicht richtig angezeigt.

Die `CreateStatic` Memberfunktion wird automatisch einen statischen Splitter mit einem Mindesthöhe der Zeile Zeilenhöhe und Spaltenbreite 0 initialisiert. Nach dem Aufruf von `Create`, passen Sie diese Mindestwerte durch Aufrufen der [SetColumnInfo](#setcolumninfo) und [SetRowInfo](#setrowinfo) Memberfunktionen. Auch `SetColumnInfo` und `SetRowInfo` nach dem Aufruf von `CreateStatic` an die gewünschte ideal Bereich Dimensionen.

Die einzelnen Bereiche eines statischen Splitters gehören häufig verschiedene Klassen an. Beispiele für statisches Splitterfenster finden Sie in der Grafik-Editor und den Windows-Datei-Manager.

Ein Teilungsfenster unterstützt spezielle Bildlaufleisten (abgesehen von den Bildlaufleisten, die möglicherweise Bereiche). Diese Bildlaufleisten sind untergeordnete Elemente von der `CSplitterWnd` Objekt aus, und die Bereiche freigegeben wurden.

Sie erstellen diese spezielle Bildlaufleisten, bei der Erstellung von Teilungsfenster. Z. B. eine `CSplitterWnd` , besitzt eine Zeile, die zwei Spalten und der Stil WS_VSCROLL zeigt eine vertikale Bildlaufleiste angezeigt, die von den beiden Fenstern gemeinsam verwendet wird. Wenn der Benutzer die Schiebeleiste verschoben wird, werden die WM_VSCROLL-Meldungen an beider Bereiche gesendet. Wenn die Bereiche die Bildlaufleisten-Position festgelegt, wird die freigegebene Bildlaufleiste festgelegt.

Weitere Informationen über Splitterfenster, finden Sie unter [technischen Hinweis 29](../../mfc/tn029-splitter-windows.md).

Weitere Informationen zum Erstellen von dynamischen Splitterfenstern finden Sie unter:

- MFC-Beispiel [Scribble](../../overview/visual-cpp-samples.md)

- MFC-Beispiel [VIEWEX](../../overview/visual-cpp-samples.md).

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

*bPrev*<br/>
Gibt an, welches Fenster aktivieren. **"True"** für vorherige; **"False"** für weiter.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist ein auf hoher Ebene Befehl, mit dem die [CView](../../mfc/reference/cview-class.md) Klasse für die Delegierung an die `CSplitterWnd` Implementierung.

##  <a name="canactivatenext"></a>  CSplitterWnd::CanActivateNext

Wird aufgerufen, durch das Framework, um zu überprüfen, um festzustellen, ob es sich bei der nächsten oder vorherigen Bereich Befehl derzeit möglich ist.

```
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>Parameter

*bPrev*<br/>
Gibt an, welches Fenster aktivieren. **"True"** für vorherige; **"False"** für weiter.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist ein auf hoher Ebene Befehl, mit dem die [CView](../../mfc/reference/cview-class.md) Klasse für die Delegierung an die `CSplitterWnd` Implementierung.

##  <a name="create"></a>  Splitterfenstern

Um ein dynamisches Teilungsfenster erstellen möchten, rufen die `Create` Member-Funktion.

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

*pParentWnd*<br/>
Das übergeordnete Rahmenfenster des Splitterfensters.

*nMaxRows*<br/>
Die maximale Anzahl der Zeilen im Teilungsfenster. Dieser Wert darf 2 nicht überschreiten.

*nMaxCols*<br/>
Die maximale Anzahl der Spalten im Teilungsfenster. Dieser Wert darf 2 nicht überschreiten.

*sizeMin*<br/>
Gibt die minimale Größe, an der ein Bereich angezeigt werden kann.

*pContext*<br/>
Ein Zeiger auf eine [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) Struktur. Dies kann in den meisten Fällen werden die *"pContext"* an den übergeordneten Rahmenfensters übergeben.

*dwStyle*<br/>
Gibt den Fensterstil an.

*nID*<br/>
Die untergeordnete Fenster-ID des Fensters. Die ID kann AFX_IDW_PANE_FIRST sein, es sei denn, Teilungsfenster. in einem anderen Teilungsfenster geschachtelt ist.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sie können einbetten, eine `CSplitterWnd` in einem übergeordneten [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) Objekt, indem Sie die folgenden Schritte aus:

1. Einbetten einer `CSplitterWnd` Membervariable in übergeordneten Rahmens.

1. Überschreiben des übergeordneten Rahmens [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) Member-Funktion.

1. Rufen Sie die `Create` Memberfunktionen aus der überschriebenen `OnCreateClient`.

Bei der Erstellung eines unterteilten Fensters aus innerhalb eines übergeordneten übergeben des übergeordneten Rahmens *"pContext"* Parameter Teilungsfenster. Andernfalls kann dieser Parameter NULL sein.

Die anfängliche minimale Zeilengröße Zeilenhöhe und Spaltenbreite des ein dynamisches Teilungsfenster werden festgelegt, indem die *SizeMin* Parameter. Diese Mindestwerte, die bestimmen, ob es sich bei ein Bereich zu klein, um eine vollständige Beispieldatei gezeigt werden wird, können geändert werden, mit der [SetRowInfo](#setrowinfo) und [SetColumnInfo](#setcolumninfo) Memberfunktionen.

Weitere Informationen über dynamische Splitterfenster, finden Sie unter "Windows Splitter" in diesem Artikel [mehrere Dokumenttypen, Ansichten und Frame Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [technischen Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` Übersicht über die Klasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]

##  <a name="createscrollbarctrl"></a>  CSplitterWnd::CreateScrollBarCtrl

Wird aufgerufen, durch das Framework um ein freigegebenes Bildlaufleistensteuerelement zu erstellen.

```
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt den Fensterstil an.

*nID*<br/>
Die untergeordnete Fenster-ID des Fensters. Die ID kann AFX_IDW_PANE_FIRST sein, es sei denn, Teilungsfenster. in einem anderen Teilungsfenster geschachtelt ist.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Außer Kraft setzen `CreateScrollBarCtrl` sollen zusätzliche Steuerelemente neben einer Bildlaufleiste. Das Standardverhalten ist die Erstellung der normalen Windows-Schiebeleisten-Steuerelemente.

##  <a name="createstatic"></a>  CSplitterWnd::CreateStatic

Um ein statisches Splitterfenster zu erstellen, rufen die `CreateStatic` Member-Funktion.

```
virtual BOOL CreateStatic(
    CWnd* pParentWnd,
    int nRows,
    int nCols,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Das übergeordnete Rahmenfenster des Splitterfensters.

*nRows*<br/>
Die Anzahl von Zeilen. Dieser Wert darf 16 nicht überschreiten.

*nCols*<br/>
Die Anzahl von Spalten. Dieser Wert darf 16 nicht überschreiten.

*dwStyle*<br/>
Gibt den Fensterstil an.

*nID*<br/>
Die untergeordnete Fenster-ID des Fensters. Die ID kann AFX_IDW_PANE_FIRST sein, es sei denn, Teilungsfenster. in einem anderen Teilungsfenster geschachtelt ist.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Ein `CSplitterWnd` ist in der Regel in einem übergeordneten eingebettet `CFrameWnd` oder [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) Objekt, indem Sie die folgenden Schritte aus:

1. Einbetten einer `CSplitterWnd` Membervariable in übergeordneten Rahmens.

1. Überschreiben des übergeordneten Rahmens `OnCreateClient` Member-Funktion.

1. Rufen Sie die `CreateStatic` Memberfunktionen aus der überschriebenen [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient).

Ein statisches Splitterfenster enthält eine feste Anzahl von Bereichen, häufig aus verschiedenen Klassen.

Wenn Sie ein statisches Splitterfenster erstellen, müssen Sie alle Bereiche gleichzeitig erstellen. Die ["CreateView"](#createview) Member-Funktion in der Regel für diesen Zweck verwendet wird, aber Sie können auch andere Nonview Klassen erstellen.

Die anfängliche minimale Zeilengröße Zeilenhöhe und Spaltenbreite für die ein statisches Splitterfenster ist 0. Diese Mindestwerte, die festzulegen, wann ein Bereich zu klein, um eine vollständige Beispieldatei gezeigt werden, können geändert werden, mit der [SetRowInfo](#setrowinfo) und [SetColumnInfo](#setcolumninfo) Memberfunktionen.

Um ein statisches Splitterfenster Bildlaufleisten hinzuzufügen, fügen Sie die Stile, und WS_HSCROLL WS_VSCROLL, *DwStyle*.

Finden Sie im Artikel unter "Windows Splitter" [mehrere Dokumenttypen, Ansichten und Frame Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [technischen Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` Klassenübersicht Weitere Informationen zu statischen Splitterfenstern.

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

*row*<br/>
Gibt die Zeile des Splitter-Fenster in der die neue Ansicht platziert werden soll.

*col*<br/>
Gibt die Spalte Splitter-Fenster, in dem die neue Ansicht platziert werden soll.

*pViewClass*<br/>
Gibt an, die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) der neuen Ansicht.

*sizeInit*<br/>
Gibt die Anfangsgröße der neuen Ansicht an.

*pContext*<br/>
Ein Zeiger auf einen erstellen-Kontext verwendet, um die Ansicht zu erstellen (in der Regel die *"pContext"* übergebenen des übergeordneten Rahmens außer Kraft gesetzte [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) Memberfunktion in der Teilungsfenster. erstellt wird).

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Alle Bereiche der ein statisches Splitterfenster müssen erstellt werden, bevor das Framework den Splitter wird angezeigt.

Das Framework ruft auch diese Member-Funktion, um neue Bereiche zu erstellen, wenn der Benutzer des ein dynamisches Teilungsfenster ein Bereich, Zeile oder Spalte geteilt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]

##  <a name="csplitterwnd"></a>  CSplitterWnd::CSplitterWnd

Aufruf zum Erstellen einer `CSplitterWnd` Objekt.

```
CSplitterWnd();
```

### <a name="remarks"></a>Hinweise

Erstellen einer `CSplitterWnd` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor, der erstellt das `CSplitterWnd` Objekt aus, und rufen Sie dann die [erstellen](#create) Memberfunktion, die Teilungsfenster erstellt und fügt es der `CSplitterWnd` Objekt.

##  <a name="deletecolumn"></a>  CSplitterWnd::DeleteColumn

Löscht eine Spalte aus der Teilungsfenster.

```
virtual void DeleteColumn(int colDelete);
```

### <a name="parameters"></a>Parameter

*colDelete*<br/>
Gibt die Spalte gelöscht werden soll.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird von dem Framework, die die Logik der dynamisches Teilungsfenster implementieren (d.h., wenn Teilungsfenster styl SPLS_DYNAMIC_SPLIT hat) aufgerufen. Sie können angepasst werden, zusammen mit der virtuellen Funktion ["CreateView"](#createview), um erweiterte dynamischen Splitterfenstern zu implementieren.

##  <a name="deleterow"></a>  CSplitterWnd::DeleteRow

Löscht eine Zeile aus Teilungsfenster.

```
virtual void DeleteRow(int rowDelete);
```

### <a name="parameters"></a>Parameter

*rowDelete*<br/>
Gibt die Zeile gelöscht werden soll.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird von dem Framework, die die Logik der dynamisches Teilungsfenster implementieren (d.h., wenn Teilungsfenster styl SPLS_DYNAMIC_SPLIT hat) aufgerufen. Sie können angepasst werden, zusammen mit der virtuellen Funktion ["CreateView"](#createview), um erweiterte dynamischen Splitterfenstern zu implementieren.

##  <a name="deleteview"></a>  CSplitterWnd::DeleteView

Löscht eine Ansicht aus Teilungsfenster.

```
virtual void DeleteView(
    int row,
    int col);
```

### <a name="parameters"></a>Parameter

*row*<br/>
Gibt die Zeile des Splitter-Fenster, die Ansicht zu löschen.

*col*<br/>
Gibt die Spalte des Splitter-Fenster, die Ansicht zu löschen.

### <a name="remarks"></a>Hinweise

Wenn die aktive Ansicht gelöscht wird, wird die nächste Ansicht aktiv. Die Standardimplementierung geht davon aus, die Sicht werden automatisch löschen [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy).

Diese Memberfunktion wird von dem Framework, die die Logik der dynamisches Teilungsfenster implementieren (d.h., wenn Teilungsfenster styl SPLS_DYNAMIC_SPLIT hat) aufgerufen. Sie können angepasst werden, zusammen mit der virtuellen Funktion ["CreateView"](#createview), um erweiterte dynamischen Splitterfenstern zu implementieren.

##  <a name="dokeyboardsplit"></a>  CSplitterWnd::DoKeyboardSplit

Führt den Tastaturteilbefehl aus, in der Regel "Window Split."

```
virtual BOOL DoKeyboardSplit();
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist ein auf hoher Ebene Befehl, mit dem die [CView](../../mfc/reference/cview-class.md) Klasse für die Delegierung an die `CSplitterWnd` Implementierung.

##  <a name="doscroll"></a>  CSplitterWnd::DoScroll

Führt die synchronisierten Bildlauf in Teilfenstern aus.

```
virtual BOOL DoScroll(
    CView* pViewFrom,
    UINT nScrollCode,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parameter

*pViewFrom*<br/>
Ein Zeiger auf die Ansicht aus der die Bildlauf Nachricht stammt.

*nScrollCode*<br/>
Ein Schiebeleisten-Code, der der Benutzer zeigt an, die Anforderung Bildlauf. Dieser Parameter besteht aus zwei Teilen: ein niederwertigen Byte ist, der bestimmt, den Typ der horizontalen Bildlauf auftritt, und ein höherwertige Byte ist, der bestimmt, den Typ des vertikalen Bildlauf auftritt:

    - SB_BOTTOM führt einen Bildlauf nach unten.

    - SB_LINEDOWN führt einen Bildlauf eine Zeile nach unten.

    - SB_LINEUP führt einen Bildlauf eine Zeile nach oben.

    - SB_PAGEDOWN führt einen Bildlauf eine Seite nach unten.

    - SB_PAGEUP führt einen Bildlauf eine Seite nach oben.

    - SB_TOP führt einen Bildlauf nach oben.

*bDoScroll*<br/>
Bestimmt, ob der Bildlauf angegebene Aktion ausgeführt wird. Wenn *bDoScroll* ist "true" (d. h., wenn ein untergeordnetes Fenster vorhanden ist, und wenn auf die Split-Fenster scrollen), und klicken Sie dann die angegebene Aktion für die fortlaufenden; stattfinden kann Wenn *bDoScroll* ist "false", (d. h., wenn keine untergeordneten Fenster vorhanden ist, oder die geteilten Ansichten haben keine scrollbereich), und klicken Sie dann einen Bildlauf nicht auftritt.

### <a name="return-value"></a>Rückgabewert

Durchführen eines Bildlaufs ungleich NULL, wenn synchronisiert auftritt. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird aufgerufen, durch das Framework zum Ausführen der synchronisierten Bildlauf in Teilfenstern aus. wenn die Sicht eine Scroll-Nachricht empfängt. Überschreiben Sie, um eine Aktion durch den Benutzer erfordern, bevor synchronisierten Bildlauf zulässig ist.

##  <a name="doscrollby"></a>  CSplitterWnd::DoScrollBy

Führt einen Bildlauf in Teilfenstern eine angegebene Anzahl von Pixeln.

```
virtual BOOL DoScrollBy(
    CView* pViewFrom,
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parameter

*pViewFrom*<br/>
Ein Zeiger auf die Ansicht aus der die Bildlauf Nachricht stammt.

*sizeScroll*<br/>
Die Anzahl der Pixel, die horizontal und vertikal gescrollt werden.

*bDoScroll*<br/>
Bestimmt, ob der Bildlauf angegebene Aktion ausgeführt wird. Wenn *bDoScroll* ist "true" (d. h., wenn ein untergeordnetes Fenster vorhanden ist, und wenn auf die Split-Fenster scrollen), und klicken Sie dann die angegebene Aktion für die fortlaufenden; stattfinden kann Wenn *bDoScroll* ist "false", (d. h., wenn keine untergeordneten Fenster vorhanden ist, oder die geteilten Ansichten haben keine scrollbereich), und klicken Sie dann einen Bildlauf nicht auftritt.

### <a name="return-value"></a>Rückgabewert

Durchführen eines Bildlaufs ungleich NULL, wenn synchronisiert auftritt. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird aufgerufen, durch das Framework als Reaktion auf eine Nachricht scrollen, auszuführenden synchronisiert Bildlauf in Teilfenstern aus der um den Betrag an, in Pixel, angegeben durch *SizeScroll*. Positive Werte geben an, einen Bildlauf nach unten und nach rechts; negative Werte geben an, ein diagonaler Bildlauf nach oben auf der linken Seite.

Überschreiben Sie, um eine Aktion durch den Benutzer vor führen Sie einen Bildlauf erfordern.

##  <a name="getactivepane"></a>  CSplitterWnd::GetActivePane

Bestimmt den aktiven Bereich im Fokus oder der aktiven Ansicht im Rahmen fest.

```
virtual CWnd* GetActivePane(
    int* pRow = NULL,
    int* pCol = NULL);
```

### <a name="parameters"></a>Parameter

*pRow*<br/>
Ein Zeiger auf ein **Int** die Zeilennummer des aktiven Bereichs abrufen.

*pCol*<br/>
Ein Zeiger auf ein **Int** die Spaltennummer des aktiven Bereichs abrufen.

### <a name="return-value"></a>Rückgabewert

Zeiger auf den aktiven Bereich. NULL, wenn kein aktiver Bereich vorhanden ist.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird durch das Framework, um zu bestimmen, den aktiven Bereich in einem Splitterfenster aufgerufen. Überschreiben Sie, um eine Aktion durch den Benutzer vor dem Abrufen des aktiven Bereichs erforderlich.

##  <a name="getcolumncount"></a>  CSplitterWnd::GetColumnCount

Gibt die aktuelle Anzahl der Spalten im Bereich zurück.

```
int GetColumnCount() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die aktuelle Anzahl der Spalten in der Aufteilung zurück. Ein statischer Splitter werden dadurch auch die maximale Anzahl von Spalten.

##  <a name="getcolumninfo"></a>  CSplitterWnd::GetColumnInfo

Gibt Informationen über die angegebene Spalte zurück.

```
void GetColumnInfo(
    int col,
    int& cxCur,
    int& cxMin) const;
```

### <a name="parameters"></a>Parameter

*col*<br/>
Gibt eine Spalte.

*cxCur*<br/>
Ein Verweis auf ein **Int** auf die aktuelle Breite der Spalte festgelegt werden.

*cxMin*<br/>
Ein Verweis auf ein **Int** auf die aktuelle minimale Breite der Spalte festgelegt werden.

##  <a name="getpane"></a>  CSplitterWnd::GetPane

Gibt den Bereich in der angegebenen Zeile und Spalte zurück.

```
CWnd* GetPane(
    int row,
    int col) const;
```

### <a name="parameters"></a>Parameter

*row*<br/>
Gibt eine Zeile an.

*col*<br/>
Gibt eine Spalte.

### <a name="return-value"></a>Rückgabewert

Gibt den Bereich in der angegebenen Zeile und Spalte zurück. Der zurückgegebene Bereich ist in der Regel eine [CView](../../mfc/reference/cview-class.md)-abgeleitete Klasse.

##  <a name="getrowcount"></a>  CSplitterWnd::GetRowCount

Gibt die Anzahl der aktuelle Bereich Zeilen zurück.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die aktuelle Anzahl der Zeilen in einem Splitterfenster zurück. Für ein statisches Splitterfenster wird dies auch die maximale Anzahl der Zeilen sein.

##  <a name="getrowinfo"></a>  CSplitterWnd::GetRowInfo

Gibt Informationen über die angegebene Zeile zurück.

```
void GetRowInfo(
    int row,
    int& cyCur,
    int& cyMin) const;
```

### <a name="parameters"></a>Parameter

*row*<br/>
Gibt eine Zeile an.

*cyCur*<br/>
Ein Verweis auf **Int** auf der aktuellen Höhe der Zeile in Pixel festgelegt werden.

*cyMin*<br/>
Ein Verweis auf **Int** auf die aktuelle Mindesthöhe der Zeile in Pixel festgelegt werden.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion zum Abrufen von Informationen zu der angegebenen Zeile. Die *CyCur* Parameter mit der aktuellen Höhe der angegebenen Zeile gefüllt und *CyMin* mit die Mindesthöhe der Zeile gefüllt ist.

##  <a name="getscrollstyle"></a>  CSplitterWnd::GetScrollStyle

Gibt den freigegebenen Bildlaufleisten-Format für das Splitterfenster zurück.

```
DWORD GetScrollStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Eine oder mehrere der folgenden Fenster style Flags, die im Erfolgsfall:

    - WS_HSCROLL, wenn von der Splitter derzeit verwaltet freigegeben horizontale Scrollleisten auf.

    - WS_VSCROLL, wenn von der Splitter derzeit verwaltet gemeinsam vertikale Bildlaufleisten verwendet.

Bei NULL verwaltet Teilungsfenster. alle freigegebenen Bildlaufleisten nicht aktuell.

##  <a name="idfromrowcol"></a>  CSplitterWnd::IdFromRowCol

Ruft das untergeordnete Fenster-ID für den Bereich in der angegebenen Zeile und Spalte ab.

```
int IdFromRowCol(
    int row,
    int col) const;
```

### <a name="parameters"></a>Parameter

*row*<br/>
Gibt die Zeile der Splitter-Fenster.

*col*<br/>
Gibt die Spalte der Splitter-Fenster.

### <a name="return-value"></a>Rückgabewert

Die untergeordnete Fenster-ID für den Bereich.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird zum Erstellen von Nonviews wie Bereiche verwendet und kann aufgerufen werden, bevor Sie im Bereich vorhanden ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]

##  <a name="ischildpane"></a>  CSplitterWnd::IsChildPane

Bestimmt, ob *aufnehmen* befindet sich derzeit ein untergeordneter Bereich Splitter im Fenster.

```
BOOL IsChildPane(
    CWnd* pWnd,
    int* pRow,
    int* pCol);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) zu testende Objekt.

*pRow*<br/>
Ein Zeiger auf ein **Int** in dem die Nummer der Zeile gespeichert.

*pCol*<br/>
Ein Zeiger auf ein **Int** in dem Sie die Nummer einer Spalte zu speichern.

### <a name="return-value"></a>Rückgabewert

Wert ungleich NULL *aufnehmen* befindet sich derzeit um ein untergeordneten Bereich dieses Splitters-Fensters, und *pRow* und *pCol* werden mit der Position des Bereichs im Teilungsfenster gefüllt. Wenn *aufnehmen* ist es sich nicht um ein untergeordneten Bereich dieses Splitters-Fensters, wird 0 zurückgegeben.

### <a name="remarks"></a>Hinweise

In Visual C++-Versionen vor 6.0 wurde diese Funktion als definiert.

`BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`

Diese Version ist jetzt veraltet und sollte nicht verwendet werden.

##  <a name="istracking"></a>  CSplitterWnd::IsTracking

Rufen Sie diese Memberfunktion, um festzustellen, ob die Teilerleiste im Fenster gerade verschoben wird.

```
BOOL IsTracking();
```

### <a name="return-value"></a>Rückgabewert

Legen Sie ungleich NULL, wenn es sich bei ein Splitter-Vorgang ausgeführt wird; andernfalls 0.

##  <a name="ondrawsplitter"></a>  CSplitterWnd::OnDrawSplitter

Rendert das Bild eines Teilfensters.

```
virtual void OnDrawSplitter(
    CDC* pDC,
    ESplitType nType,
    const CRect& rect);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Ein Zeiger auf den Gerätekontext, in dem gezeichnet werden soll. Wenn *pDC* NULL ist, klicken Sie dann [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) wird aufgerufen, durch das Framework und keine geteilten Fensters gezeichnet wird.

*nType*<br/>
Der Wert der `enum ESplitType`, stehen die folgenden:

    - `splitBox` Das Feld für den Splitter-ziehen.

    - `splitBar` Die Leiste, die zwischen den zwei Split-Fenstern angezeigt wird.

    - `splitIntersection` Die Schnittmenge der Teilfenstern aus. Dieses Element wird nicht aufgerufen werden, wenn auf Windows 95-und Windows 98 ausgeführt.

    - `splitBorder` Der Fensterrahmen "Split".

*rect*<br/>
Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Größe und Form der Teilfenstern angibt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird von dem Framework, zeichnen, und geben Sie die genaue Merkmale eines unterteilten Fensters aufgerufen. Außer Kraft setzen `OnDrawSplitter` für die erweiterte Anpassung von der Bilder für die verschiedenen grafischen Komponenten eines unterteilten Fensters. Die Standard-Bilder ähnelt den Splitter im Microsoft Works für Windows oder Microsoft Windows 95/98, darin, dass die Schnittpunkte den Teilerleisten gemischt werden.

Weitere Informationen über dynamische Splitterfenster, finden Sie unter "Windows Splitter" in diesem Artikel [mehrere Dokumenttypen, Ansichten und Frame Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [technischen Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` Übersicht über die Klasse.

##  <a name="oninverttracker"></a>  CSplitterWnd::OnInvertTracker

Rendert das Bild eines Teilfensters gleicher Größe und Form als das Rahmenfenster sein.

```
virtual void OnInvertTracker(const CRect& rect);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
Ein Verweis auf eine `CRect` Objekt, das das Rechteck Überwachung angibt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird vom Framework aufgerufen, während der Größenänderung von Aufteilungen. Außer Kraft setzen `OnInvertTracker` für die erweiterte Anpassung von der Bilder des Splitterfensters. Die Standard-Bilder ähnelt den Splitter im Microsoft Works für Windows oder Microsoft Windows 95/98, darin, dass die Schnittpunkte den Teilerleisten gemischt werden.

Weitere Informationen über dynamische Splitterfenster, finden Sie unter "Windows Splitter" in diesem Artikel [mehrere Dokumenttypen, Ansichten und Frame Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [technischen Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` Übersicht über die Klasse.

##  <a name="recalclayout"></a>  CSplitterWnd::RecalcLayout

Rufen Sie auf, um die erneute Anzeige der Teilungsfenster. nach der Zeile oder Spalte Größe anpassen.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion auf, um ordnungsgemäß Teilungsfenster erneut anzuzeigen, nachdem Sie die Zeilen- und Größen mit eingestellt haben die [SetRowInfo](#setrowinfo) und [SetColumnInfo](#setcolumninfo) Memberfunktionen. Wenn Sie im Rahmen des Erstellungsprozesses des Größen von Zeilen und Spalten ändern, bevor das Splitterfenster sichtbar ist, ist es nicht erforderlich, diese Memberfunktion aufrufen.

Das Framework ruft diese Memberfunktion auf, wenn der Benutzer ändert die Größe der Teilungsfenster oder eine Teilung verschiebt.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CSplitterWnd::SetColumnInfo](#setcolumninfo).

##  <a name="setactivepane"></a>  CSplitterWnd::SetActivePane

Legt einen Bereich auf die aktiven im Rahmen fest.

```
virtual void SetActivePane(
    int row,
    int col,
    CWnd* pWnd = NULL);
```

### <a name="parameters"></a>Parameter

*row*<br/>
Wenn *aufnehmen* NULL ist, gibt die Zeile im Bereich, der aktiv sein werden.

*col*<br/>
Wenn *aufnehmen* NULL ist, gibt die Spalte im Bereich, der aktiv sein werden.

*pWnd*<br/>
Ein Zeiger auf ein `CWnd` -Objekt. Wenn der Wert NULL ist, im Bereich gemäß *Zeile* und *Col* aktiv festgelegt ist. Falls ungleich NULL, gibt den Bereich, der aktiv festgelegt ist.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird aufgerufen, durch das Framework einen Bereich als aktiv festlegen, wenn der Benutzer den Fokus auf einen Bereich innerhalb der Frame-Fensters ändert. Sie können explizit aufrufen, `SetActivePane` so ändern Sie den Fokus auf die angegebene Ansicht.

Bereich angeben, indem Sie entweder Zeile und Spalte **oder** durch die Bereitstellung *aufnehmen*.

##  <a name="setcolumninfo"></a>  CSplitterWnd::SetColumnInfo

Rufen Sie die Informationen für die angegebene Spalte festgelegt.

```
void SetColumnInfo(
    int col,
    int cxIdeal,
    int cxMin);
```

### <a name="parameters"></a>Parameter

*col*<br/>
Gibt eine Spalte der Splitter-Fenster.

*cxIdeal*<br/>
Gibt eine ideale Breite der Spalte der Splitter-Fenster in Pixel an.

*cxMin*<br/>
Gibt eine minimale Breite für die Spalte der Splitter-Fensters in Pixel an.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion, um eine neue minimale Breite und die ideale Breite für eine Spalte zu festzulegen. Der Mindestwert für die Spalte bestimmt, wann die Spalte zu klein, um vollständig angezeigt werden.

Wenn das Framework das Splitterfenster angezeigt wird, ordnet es die Bereiche in Spalten und Zeilen gemäß ihrer idealen Dimensionen, die von der linken oberen Ecke in die unteren rechten Ecke des Clientbereichs des Fensters Splitter arbeiten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]

##  <a name="setrowinfo"></a>  CSplitterWnd::SetRowInfo

Rufen Sie die Informationen für die angegebene Zeile festgelegt.

```
void SetRowInfo(
    int row,
    int cyIdeal,
    int cyMin);
```

### <a name="parameters"></a>Parameter

*row*<br/>
Gibt eine Zeile der Splitter-Fenster an.

*cyIdeal*<br/>
Gibt eine ideale Höhe der Zeile der Splitter-Fenster in Pixel an.

*cyMin*<br/>
Gibt eine minimale Höhe für die Zeile der Splitter-Fensters in Pixel an.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion, um eine neue minimale Höhe und die optimale Höhe für eine Zeile festzulegen. Der Mindestwert für die Zeile bestimmt, wann die Zeile zu klein, um vollständig angezeigt werden.

Wenn das Framework das Splitterfenster angezeigt wird, ordnet es die Bereiche in Spalten und Zeilen gemäß ihrer idealen Dimensionen, die von der linken oberen Ecke in die unteren rechten Ecke des Clientbereichs des Fensters Splitter arbeiten.

##  <a name="setscrollstyle"></a>  CSplitterWnd::SetScrollStyle

Gibt an, dass die neue Scroll-Formatvorlage für des Splitter-Fensters Bildlaufleisten-Unterstützung freigegeben.

```
void SetScrollStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Die neue Scroll-Formatvorlage für des Splitter-Fensters freigegebene Bildlaufleisten-Unterstützung, die der folgenden Werte sind möglich:

- WS_HSCROLL erstellen/horizontale freigegebenen Bildlaufleisten anzeigen.

- WS_VSCROLL erstellen/vertikale freigegebenen Bildlaufleisten anzeigen.

### <a name="remarks"></a>Hinweise

Nach der Erstellung einer Bildlaufleiste ist es wird nicht zerstört, wenn `SetScrollStyle` aufgerufen wird, ohne diesen Stil; stattdessen werden die Bildlaufleiste ausgeblendet. Dadurch wird die Bildlaufleisten, um den Zustand beibehalten, auch wenn sie ausgeblendet sind. Nach dem Aufruf `SetScrollStyle` ist es notwendig, [RecalcLayout](#recalclayout) für alle Änderungen wirksam werden.

##  <a name="splitcolumn"></a>  CSplitterWnd::SplitColumn

Gibt an, ob ein Rahmenfenster vertikal aufgeteilt wird.

```
virtual BOOL SplitColumn(int cxBefore);
```

### <a name="parameters"></a>Parameter

*cxBefore*<br/>
Die Position in Pixel, die vor denen die Teilung auftritt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird immer dann aufgerufen, wenn ein Fenster für die vertikale Aufteilung erstellt wird. `SplitColumn` Gibt den Standardspeicherort, wo die Teilung auftritt.

`SplitColumn` wird aufgerufen, durch das Framework die Logik der dynamisches Teilungsfenster implementieren (d.h., wenn Teilungsfenster styl SPLS_DYNAMIC_SPLIT hat). Sie können angepasst werden, zusammen mit der virtuellen Funktion ["CreateView"](#createview), um erweiterte dynamischen Splitterfenstern zu implementieren.

##  <a name="splitrow"></a>  CSplitterWnd::SplitRow

Gibt an, ob ein Rahmenfenster horizontal aufgeteilt wird.

```
virtual BOOL SplitRow(int cyBefore);
```

### <a name="parameters"></a>Parameter

*cyBefore*<br/>
Die Position in Pixel, die vor denen die Teilung auftritt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird aufgerufen, wenn es sich bei einem horizontalen Aufteilung Fenster erstellt wird. `SplitRow` Gibt den Standardspeicherort, wo die Teilung auftritt.

`SplitRow` wird aufgerufen, durch das Framework die Logik der dynamisches Teilungsfenster implementieren (d.h., wenn Teilungsfenster styl SPLS_DYNAMIC_SPLIT hat). Sie können angepasst werden, zusammen mit der virtuellen Funktion ["CreateView"](#createview), um erweiterte dynamischen Splitterfenstern zu implementieren.

##  <a name="ondraw"></a>  CSplitterWnd::OnDraw

Wird aufgerufen, durch das Framework das Splitterfenster gezeichnet werden soll.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Ein Zeiger zu einem Gerätekontext.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)
