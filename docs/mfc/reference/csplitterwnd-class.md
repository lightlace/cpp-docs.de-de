---
title: CSplitterWnd Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitterWnd
dev_langs:
- C++
helpviewer_keywords:
- static splitter windows
- multiple views
- splitter windows
- views, multiple per frame
- dynamic splitter windows
- CSplitterWnd class
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d015aa604c5394ccbe8c7471b70c84763cc00a5b
ms.lasthandoff: 02/24/2017

---
# <a name="csplitterwnd-class"></a>CSplitterWnd-Klasse
Stellt die Funktionalität eines unterteilten Fensters bereit. Dabei handelt es sich um ein Fenster, das mehrere Bereiche enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|Aufruf zum Erstellen einer `CSplitterWnd` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitterWnd::ActivateNext](#activatenext)|Führt den Befehl zum nächsten Bereich oder vorherigen Bereich.|  
|[CSplitterWnd::CanActivateNext](#canactivatenext)|Überprüft, um festzustellen, ob der Befehl im nächsten oder vorherigen Bereich derzeit möglich ist.|  
|[Splitterfenstern](#create)|Aufruf von ein dynamisches unterteiltes Fenster erstellen und Anfügen an die `CSplitterWnd` Objekt.|  
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|Erstellt eine freigegebene Bildlaufleisten-Steuerelements.|  
|[CSplitterWnd::CreateStatic](#createstatic)|Aufruf an ein statisches Splitterfenster erstellen und Anfügen an die `CSplitterWnd` Objekt.|  
|[CSplitterWnd:: CreateView-Funktion](#createview)|Rufen Sie einen Bereich in einem unterteilten Fenster zu erstellen.|  
|[CSplitterWnd::DeleteColumn](#deletecolumn)|Löscht eine Spalte aus einem Splitterfenster..|  
|[CSplitterWnd::DeleteRow](#deleterow)|Löscht eine Zeile aus einem Splitterfenster..|  
|[CSplitterWnd::DeleteView](#deleteview)|Löscht eine Ansicht aus einem Splitterfenster..|  
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|Führt die Tastatur teilen, Befehl in der Regel "der Teilung."|  
|[CSplitterWnd::DoScroll](#doscroll)|Führt die Bildlauf in Teilfenstern synchronisiert.|  
|[CSplitterWnd::DoScrollBy](#doscrollby)|Führt einen Bildlauf geteilte Fenster, um eine angegebene Anzahl von Pixeln.|  
|[CSplitterWnd::GetActivePane](#getactivepane)|Bestimmt den aktiven Bereich im Fokus oder die aktive Ansicht im Frame.|  
|[CSplitterWnd::GetColumnCount](#getcolumncount)|Gibt die aktuelle Anzahl der Bereich-Spalte zurück.|  
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|Gibt Informationen über die angegebene Spalte zurück.|  
|[CSplitterWnd::GetPane](#getpane)|Gibt den Bereich in der angegebenen Zeile und Spalte zurück.|  
|[CSplitterWnd::GetRowCount](#getrowcount)|Gibt die Anzahl der aktuelle Bereich Zeilen zurück.|  
|[CSplitterWnd::GetRowInfo](#getrowinfo)|Gibt Informationen über die angegebene Zeile zurück.|  
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|Gibt den freigegebenen Bildlaufleisten-Format zurück.|  
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|Gibt das untergeordnete Fenster-ID des Bereichs in der angegebenen Zeile und Spalte zurück.|  
|[CSplitterWnd::IsChildPane](#ischildpane)|Rufen Sie auf, um zu bestimmen, ob das Fenster derzeit einen untergeordneten Bereich dieses Fensters Splitter ist.|  
|[CSplitterWnd::IsTracking](#istracking)|Bestimmt, ob die Teilerleiste gerade verschoben wird.|  
|[CSplitterWnd::RecalcLayout](#recalclayout)|Rufen Sie auf, um das Splitterfenster erneut anzuzeigen, nach der Zeile oder Spalte Größe anpassen.|  
|[CSplitterWnd::SetActivePane](#setactivepane)|Legt einen Bereich im Rahmen der aktiven vorhanden sein.|  
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|Rufen Sie die Informationen für die angegebene Spalte festgelegt.|  
|[CSplitterWnd::SetRowInfo](#setrowinfo)|Rufen Sie die Informationen für die angegebene Zeile festgelegt.|  
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|Gibt an, die neue Bildlaufleisten-Formatvorlage für des Splitter-Fensters Bildlaufleisten-Support freigegeben.|  
|[CSplitterWnd::SplitColumn](#splitcolumn)|Gibt an, ob ein Rahmenfenster vertikal aufgeteilt wird.|  
|[CSplitterWnd::SplitRow](#splitrow)|Gibt an, ob ein Rahmenfenster horizontal aufgeteilt wird.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitterWnd::OnDraw](#ondraw)|Vom Framework zum Zeichnen der unterteiltes Fenster aufgerufen.|  
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|Rendert ein Abbild von einem geteilten Fenster.|  
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|Rendert ein Teilfenster in der gleichen Größe und Form wie das Rahmenfenster werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Bereich ist in der Regel ein anwendungsspezifisches Objekt abgeleitet [CView](../../mfc/reference/cview-class.md), aber es kann eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das über die entsprechenden untergeordneten Fenster ID verfügt  
  
 Ein `CSplitterWnd` -Objekt ist in der Regel in einem übergeordneten Element eingebettet [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) Objekt. Erstellen Sie ein `CSplitterWnd` -Objekt mithilfe der folgenden Schritte aus:  
  
1.  Einbetten einer `CSplitterWnd` -Membervariable in den übergeordneten Frame.  
  
2.  Überschreiben des übergeordneten Rahmens [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) Member-Funktion.  
  
3.  Von der überschriebenen `OnCreateClient`, rufen Sie die [erstellen](#create) oder [CreateStatic](#createstatic) Memberfunktion der `CSplitterWnd`.  
  
 Rufen Sie die **erstellen** Member-Funktion, um ein dynamisches unterteiltes Fenster zu erstellen. Ein dynamisches Splitterfenster wird normalerweise verwendet, erstellen und eine Anzahl einzelner Bereiche oder Ansichten des gleichen Dokuments. Das Framework erstellt automatisch einen anfängliche Bereich für die Aufteilung. Das Framework dann erstellt, ändert und zusätzliche Bereiche wie der Benutzer den Splitter Fenstersteuerelemente verwirft.  
  
 Beim Aufruf von **erstellen**, Sie eine minimale Zeilengröße Zeilenhöhe und Spaltenbreite, die bestimmen, wann die Bereiche vollständig angezeigt werden zu klein sind, angeben. Nach dem Aufruf von **erstellen**, Sie können diese Mindestwerte anpassen, durch Aufrufen der [SetColumnInfo](#setcolumninfo) und [SetRowInfo](#setrowinfo) Memberfunktionen.  
  
 Verwenden Sie auch die `SetColumnInfo` und `SetRowInfo` Memberfunktionen Breite für eine Spalte, einer "ideal" und "ideal" Höhe für eine Zeile fest. Wenn das Framework ein unterteiltes Fenster angezeigt wird, wird zuerst den übergeordneten Frame, dann das Splitterfenster angezeigt. Das Framework ordnet dann die Bereiche in Spalten und Zeilen gemäß ihrer idealen Dimensionen, die von der linken oberen Ecke auf der unteren rechten Ecke des Clientbereichs des Fensters Splitter arbeiten.  
  
 Alle Bereiche in ein dynamisches Splitterfenster müssen derselben Klasse sein. Vertraute Programme, die dynamische Splitterfenster unterstützen umfassen Microsoft Word und Microsoft Excel.  
  
 Verwenden der `CreateStatic` Member-Funktion ein statisches Splitterfenster erstellen. Der Benutzer kann nur die Größe der Bereiche in einer statisch unterteiltes Fenster, nicht deren Anzahl oder Reihenfolge ändern.  
  
 Bei der Erstellung statischen Splitters, müssen Sie ausdrücklich alle statischen Splitters des Bereiche erstellen. Sicherstellen, dass Sie alle Bereiche vor des übergeordneten Frames erstellen `OnCreateClient` Member-Funktion zurückgegeben wird oder das Framework wird das Fenster nicht richtig angezeigt.  
  
 Die `CreateStatic` Memberfunktion automatisch einen statischen Splitter mit eine minimale Zeilengröße Zeilenhöhe und Spaltenbreite 0 initialisiert. Nach dem Aufruf von **erstellen**, passen Sie diese Mindestwerte durch Aufrufen der [SetColumnInfo](#setcolumninfo) und [SetRowInfo](#setrowinfo) Memberfunktionen. Verwenden Sie auch `SetColumnInfo` und `SetRowInfo` nach dem Aufruf von `CreateStatic` an, dass die gewünschten ideal Bereich Dimensionen.  
  
 Die einzelnen Bereiche eines statischen Splitters gehören häufig andere Klassen. Beispiele für statisches Splitterfenster finden Sie unter der Grafik-Editor und die Windows-Datei-Manager.  
  
 Ein unterteiltes Fenster unterstützt spezielle Bildlaufleisten (mit Ausnahme der Bildlaufleisten, die möglicherweise Bereiche). Diese Bildlaufleisten sind untergeordnete Elemente der `CSplitterWnd` -Objekt und die Bereiche freigegeben wurden.  
  
 Erstellen Sie diese spezielle Bildlaufleisten, wenn Sie das Splitterfenster erstellen. Z. B. eine `CSplitterWnd` , bei dem eine Zeile, zwei Spalten und die **WS_VSCROLL** wird eine vertikale Bildlaufleiste angezeigt, die die beiden Bereiche gemeinsam anzeigen. Wenn der Benutzer die Bildlaufleiste bewegt `WM_VSCROLL` zum beider Bereiche gesendet werden. Wenn die Bereiche die Bildlaufleisten-Position festgelegt, wird die freigegebene Bildlaufleiste festgelegt.  
  
 Weitere Informationen über Splitterfenster finden Sie unter:  
  
- [Der technische Hinweis 29](../../mfc/tn029-splitter-windows.md)  
  
-   Knowledge Base-Artikel Q262024: So wird's gemacht: verwenden CPropertySheet als eine untergeordnete CSplitterWnd  
  
 Weitere Informationen zum dynamischen Erstellen finden Sie unter:  
  
-   MFC-Beispiel [Scribble](../../visual-cpp-samples.md)  
  
-   MFC-Beispiel [Wahl](../../visual-cpp-samples.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="a-nameactivatenexta--csplitterwndactivatenext"></a><a name="activatenext"></a>CSplitterWnd::ActivateNext  
 Vom Framework aufgerufen wird, den nächsten Bereich oder vorherigen Bereich Befehl auszuführen.  
  
```  
virtual void ActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bPrev`  
 Gibt an, welche Fenster aktiviert wird. **TRUE** für vorherige; **FALSE** für weiter.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist ein auf hoher Ebene Befehl, mit dem die [CView](../../mfc/reference/cview-class.md) Klasse für die Delegierung an die `CSplitterWnd` Implementierung.  
  
##  <a name="a-namecanactivatenexta--csplitterwndcanactivatenext"></a><a name="canactivatenext"></a>CSplitterWnd::CanActivateNext  
 Vom Framework aufgerufen wird, überprüfen, wenn der Befehl im nächsten oder vorherigen Bereich derzeit möglich ist.  
  
```  
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bPrev`  
 Gibt an, welche Fenster aktiviert wird. **TRUE** für vorherige; **FALSE** für weiter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist ein auf hoher Ebene Befehl, mit dem die [CView](../../mfc/reference/cview-class.md) Klasse für die Delegierung an die `CSplitterWnd` Implementierung.  
  
##  <a name="a-namecreatea--csplitterwndcreate"></a><a name="create"></a>Splitterfenstern  
 Um ein dynamisches unterteiltes Fenster zu erstellen, rufen die **erstellen** Member-Funktion.  
  
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
 Die übergeordneten Rahmenfensters des Splitterfensters.  
  
 *nMaxRows*  
 Die maximale Anzahl von Zeilen in der unterteiltes Fenster. Dieser Wert darf maximal 2.  
  
 *nMaxCols*  
 Die maximale Anzahl von Spalten im Splitterfenster. Dieser Wert darf maximal 2.  
  
 `sizeMin`  
 Gibt die minimale Größe, bei der ein Fenster angezeigt werden kann.  
  
 `pContext`  
 Ein Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md) Struktur. In den meisten Fällen kann dies die `pContext` an der übergeordneten Rahmenfensters übergeben.  
  
 `dwStyle`  
 Gibt den Fensterstil.  
  
 `nID`  
 Die untergeordneten Fenster ID des Fensters. Die ID kann **AFX_IDW_PANE_FIRST** , sofern die unterteiltes Fenster in einer anderen Splitterfenster geschachtelt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie können einbetten ein `CSplitterWnd` in einem übergeordneten [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) Objekt, indem Sie die folgenden Schritte:  
  
1.  Einbetten einer `CSplitterWnd` -Membervariable in den übergeordneten Frame.  
  
2.  Überschreiben des übergeordneten Rahmens [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) Member-Funktion.  
  
3.  Rufen Sie die **erstellen** Member-Funktion von der überschriebenen `OnCreateClient`.  
  
 Wenn Sie von innerhalb eines übergeordneten Rahmens ein unterteiltes Fenster erstellen, übergeben Sie des übergeordneten Frames `pContext` Parameter für das Splitterfenster. Andernfalls kann dieser Parameter **NULL**.  
  
 Die Anfangszeile minimale Zeilenhöhe und Spaltenbreite für ein dynamisches unterteiltes Fenster werden durch Festlegen der `sizeMin` Parameter. Dieser Mindestwerte, die bestimmen, ob ein Bereich in ihrer Gesamtheit dargestellt werden zu klein ist, können geändert werden, mit der [SetRowInfo](#setrowinfo) und [SetColumnInfo](#setcolumninfo) Memberfunktionen.  
  
 Weitere Informationen über dynamische Splitterfenster, finden Sie unter "Splitterfenster" im Artikel [mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md), [Technische Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` Übersicht über die Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#125;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]  
  
##  <a name="a-namecreatescrollbarctrla--csplitterwndcreatescrollbarctrl"></a><a name="createscrollbarctrl"></a>CSplitterWnd::CreateScrollBarCtrl  
 Vom Framework zum Erstellen einer freigegebenen ScrollBar-Steuerelement aufgerufen.  
  
```  
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt den Fensterstil.  
  
 `nID`  
 Die untergeordneten Fenster ID des Fensters. Die ID kann **AFX_IDW_PANE_FIRST** , sofern die unterteiltes Fenster in einer anderen Splitterfenster geschachtelt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie `CreateScrollBarCtrl` um die zusätzlichen Steuerelemente neben einer Bildlaufleiste. Standardmäßig ist normale Windows-Bildlaufleisten-Steuerelemente zu erstellen.  
  
##  <a name="a-namecreatestatica--csplitterwndcreatestatic"></a><a name="createstatic"></a>CSplitterWnd::CreateStatic  
 Um ein statisches Splitterfenster zu erstellen, rufen Sie die `CreateStatic` -Memberfunktion.  
  
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
 Die übergeordneten Rahmenfensters des Splitterfensters.  
  
 `nRows`  
 Die Anzahl von Zeilen. Dieser Wert darf maximal 16.  
  
 *nCols*  
 Die Anzahl von Spalten. Dieser Wert darf maximal 16.  
  
 `dwStyle`  
 Gibt den Fensterstil.  
  
 `nID`  
 Die untergeordneten Fenster ID des Fensters. Die ID kann **AFX_IDW_PANE_FIRST** , sofern die unterteiltes Fenster in einer anderen Splitterfenster geschachtelt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ein `CSplitterWnd` ist in der Regel in einem übergeordneten Element eingebettet `CFrameWnd` oder [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) Objekt, indem Sie die folgenden Schritte:  
  
1.  Einbetten einer `CSplitterWnd` -Membervariable in den übergeordneten Frame.  
  
2.  Überschreiben des übergeordneten Rahmens `OnCreateClient` Member-Funktion.  
  
3.  Rufen Sie die `CreateStatic` Member-Funktion von der überschriebenen [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient).  
  
 Statisches Splitterfenster enthält eine feste Anzahl von Bereichen, die häufig von anderen Klassen.  
  
 Wenn Sie ein statisches Splitterfenster erstellen, müssen Sie alle Bereiche gleichzeitig erstellen. Die [CreateView](#createview) Member-Funktion wird in der Regel für diesen Zweck verwendet, aber Sie können auch andere Nonview-Klassen erstellen.  
  
 Die Anfangszeile minimale Zeilenhöhe und Spaltenbreite für ein statisches Splitterfenster ist 0. Dieser Mindestwerte, die ermitteln, wann ein Fenster zu klein, um vollständig angezeigt werden, können geändert werden, mit der [SetRowInfo](#setrowinfo) und [SetColumnInfo](#setcolumninfo) Memberfunktionen.  
  
 Um ein statisches Splitterfenster Bildlaufleisten hinzuzufügen, fügen die **WS_HSCROLL** und **WS_VSCROLL** Stile auf `dwStyle`.  
  
 Finden Sie im Artikel unter "Splitterfenster" [mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md), [Technische Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` Klassenübersicht Weitere statisches Splitterfenster.  
  
##  <a name="a-namecreateviewa--csplitterwndcreateview"></a><a name="createview"></a>CSplitterWnd:: CreateView-Funktion  
 Erstellt die Bereiche für ein statisches Splitterfenster.  
  
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
 Gibt die Zeile des Splitter-Fenster in das die neue Ansicht eingefügt werden soll.  
  
 `col`  
 Gibt die Spalte Splitter-Fenster, in das die neue Ansicht eingefügt werden soll.  
  
 `pViewClass`  
 Gibt die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) der neuen Ansicht.  
  
 *sizeInit*  
 Gibt die Anfangsgröße der neuen Ansicht.  
  
 `pContext`  
 Ein Zeiger auf eine Erstellung Kontext verwendet, um die Ansicht zu erstellen (in der Regel die `pContext` an des übergeordneten Frames außer Kraft gesetzte übergebenen [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) Member-Funktion, die in dem Splitterfenster erstellt wird).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Alle Bereiche der ein statisches Splitterfenster müssen erstellt werden, bevor das Framework den Splitter angezeigt.  
  
 Das Framework ruft auch diese Member-Funktion, um neue Bereiche zu erstellen, wenn der Benutzer ein dynamisches Teilfenster einen Bereich, Zeile oder Spalte geteilt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&4;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]  
  
##  <a name="a-namecsplitterwnda--csplitterwndcsplitterwnd"></a><a name="csplitterwnd"></a>CSplitterWnd::CSplitterWnd  
 Aufruf zum Erstellen einer `CSplitterWnd` Objekt.  
  
```  
CSplitterWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CSplitterWnd` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, der erstellt die `CSplitterWnd` -Objekt, und rufen Sie dann die [erstellen](#create) Memberfunktion, die die unterteiltes Fenster erstellt, und fügt es der `CSplitterWnd` Objekt.  
  
##  <a name="a-namedeletecolumna--csplitterwnddeletecolumn"></a><a name="deletecolumn"></a>CSplitterWnd::DeleteColumn  
 Löscht eine Spalte aus einem Splitterfenster..  
  
```  
virtual void DeleteColumn(int colDelete);
```  
  
### <a name="parameters"></a>Parameter  
 *colDelete*  
 Gibt die Spalte gelöscht werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird vom Framework zum Implementieren der Logik des Fensters dynamischen aufgerufen (d. h., wenn das Splitterfenster verfügt über die **SPLS_DYNAMIC_SPLIT** Stil). Sie können angepasst werden, zusammen mit der virtuellen Funktion [CreateView](#createview), um erweiterte dynamische Splitter zu implementieren.  
  
##  <a name="a-namedeleterowa--csplitterwnddeleterow"></a><a name="deleterow"></a>CSplitterWnd::DeleteRow  
 Löscht eine Zeile aus einem Splitterfenster..  
  
```  
virtual void DeleteRow(int rowDelete);
```  
  
### <a name="parameters"></a>Parameter  
 *rowDelete*  
 Gibt die Zeile gelöscht werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird vom Framework zum Implementieren der Logik des Fensters dynamischen aufgerufen (d. h., wenn das Splitterfenster verfügt über die **SPLS_DYNAMIC_SPLIT** Stil). Sie können angepasst werden, zusammen mit der virtuellen Funktion [CreateView](#createview), um erweiterte dynamische Splitter zu implementieren.  
  
##  <a name="a-namedeleteviewa--csplitterwnddeleteview"></a><a name="deleteview"></a>CSplitterWnd::DeleteView  
 Löscht eine Ansicht aus einem Splitterfenster..  
  
```  
virtual void DeleteView(
    int row,  
    int col);
```  
  
### <a name="parameters"></a>Parameter  
 `row`  
 Gibt die Zeile des Splitter-Fenster an, die Ansicht zu löschen.  
  
 `col`  
 Gibt die Spalte des Splitter-Fenster an, die Ansicht zu löschen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die aktive Ansicht gelöscht wird, wird die nächste Ansicht aktiviert. Die Standardimplementierung geht davon aus, wird die Ansicht automatisch löschen [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy).  
  
 Diese Member-Funktion wird vom Framework zum Implementieren der Logik des Fensters dynamischen aufgerufen (d. h., wenn das Splitterfenster verfügt über die **SPLS_DYNAMIC_SPLIT** Stil). Sie können angepasst werden, zusammen mit der virtuellen Funktion [CreateView](#createview), um erweiterte dynamische Splitter zu implementieren.  
  
##  <a name="a-namedokeyboardsplita--csplitterwnddokeyboardsplit"></a><a name="dokeyboardsplit"></a>CSplitterWnd::DoKeyboardSplit  
 Führt die Tastatur teilen, Befehl in der Regel "der Teilung."  
  
```  
virtual BOOL DoKeyboardSplit();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist ein auf hoher Ebene Befehl, mit dem die [CView](../../mfc/reference/cview-class.md) Klasse für die Delegierung an die `CSplitterWnd` Implementierung.  
  
##  <a name="a-namedoscrolla--csplitterwnddoscroll"></a><a name="doscroll"></a>CSplitterWnd::DoScroll  
 Führt die Bildlauf in Teilfenstern synchronisiert.  
  
```  
virtual BOOL DoScroll(
    CView* pViewFrom,  
    UINT nScrollCode,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pViewFrom`  
 Ein Zeiger auf die Ansicht aus der Scrollen Nachricht stammt.  
  
 `nScrollCode`  
 Ein Bildlaufleisten-Code, der den Benutzer angibt, der Anforderung Bildlauf. Dieser Parameter besteht aus zwei Teilen: ein niederwertigen Byte ist, die den Typ des horizontalen Bildlauf auftreten bestimmt wird, und ein höherwertige Byte ist, die vertikal scrollen auftreten bestimmt:  
  
- **SB_BOTTOM** führt einen Bildlauf nach unten.  
  
- **SB_LINEDOWN** verschiebt eine Zeile nach unten.  
  
- **SB_LINEUP** ein Bildlauf um eine Zeile durchgeführt.  
  
- **SB_PAGEDOWN** rollt eine Seite nach unten.  
  
- **SB_PAGEUP** ein Bildlauf um eine Seite durchgeführt.  
  
- **SB_TOP** führt einen Bildlauf nach oben.  
  
 `bDoScroll`  
 Bestimmt, ob die angegebene Bildlaufleiste Aktion ausgeführt wird. Wenn `bDoScroll` ist **TRUE** (d. h., wenn ein untergeordnetes Fenster vorhanden ist und wenn die geteilten Windows einen Bildlaufbereich), und die angegebene Aktion für die fortlaufende; Wenn stattfinden kann `bDoScroll` ist **FALSE** (d. h., wenn keine untergeordneten Fenster vorhanden ist, oder die geteilten Ansichten keine Bildlaufbereich haben), dann Bildlauf nicht auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Durchführen eines Bildlaufs ungleich NULL, wenn die Synchronisierung erfolgt. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird aufgerufen, durch das Framework synchronisierte Bildlauf Teilfenstern erhält die Ansicht eine Nachricht einen Bildlauf ausführen. Überschreiben Sie, um eine Aktion durch den Benutzer erfordern, bevor synchronisierte Bildlauf zulässig ist.  
  
##  <a name="a-namedoscrollbya--csplitterwnddoscrollby"></a><a name="doscrollby"></a>CSplitterWnd::DoScrollBy  
 Führt einen Bildlauf geteilte Fenster, um eine angegebene Anzahl von Pixeln.  
  
```  
virtual BOOL DoScrollBy(
    CView* pViewFrom,  
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pViewFrom`  
 Ein Zeiger auf die Ansicht aus der Scrollen Nachricht stammt.  
  
 `sizeScroll`  
 Anzahl der Pixel, um die horizontalen und vertikalen Bildlauf durchgeführt werden.  
  
 bDoScroll  
 Bestimmt, ob die angegebene Bildlaufleiste Aktion ausgeführt wird. Wenn `bDoScroll` ist **TRUE** (d. h., wenn ein untergeordnetes Fenster vorhanden ist und wenn die geteilten Windows einen Bildlaufbereich), und die angegebene Aktion für die fortlaufende; Wenn stattfinden kann `bDoScroll` ist **FALSE** (d. h., wenn keine untergeordneten Fenster vorhanden ist, oder die geteilten Ansichten keine Bildlaufbereich haben), dann Bildlauf nicht auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Durchführen eines Bildlaufs ungleich NULL, wenn die Synchronisierung erfolgt. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion vom Framework in die Antwort auf eine Bildlaufleiste aufgerufen wird, ausführen synchronisiert Bildlauf der geteilten Fenster Betrag in Pixel, angegeben durch `sizeScroll`. Positive Werte geben einen Bildlauf nach unten und rechts; negative Werte geben Sie einen Bildlauf nach oben und nach links an.  
  
 Überschreiben Sie, um eine Aktion seitens des Benutzers, ehe Sie einen Bildlauf erfordern.  
  
##  <a name="a-namegetactivepanea--csplitterwndgetactivepane"></a><a name="getactivepane"></a>CSplitterWnd::GetActivePane  
 Bestimmt den aktiven Bereich im Fokus oder die aktive Ansicht im Frame.  
  
```  
virtual CWnd* GetActivePane(
    int* pRow = NULL,  
    int* pCol = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pRow`  
 Ein Zeiger auf eine **Int** die Zeilennummer im aktiven Bereich abgerufen.  
  
 `pCol`  
 Ein Zeiger auf eine **Int** die Nummer der Spalte im aktiven Bereich abgerufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktiven Bereich. **NULL** Wenn keine aktiven Bereich vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird vom Framework bestimmen den aktiven Bereich in einem unterteilten Fenster aufgerufen. Überschreiben Sie, um eine Aktion durch den Benutzer vor dem Abrufen des aktiven Bereichs erfordern.  
  
##  <a name="a-namegetcolumncounta--csplitterwndgetcolumncount"></a><a name="getcolumncount"></a>CSplitterWnd::GetColumnCount  
 Gibt die aktuelle Anzahl der Bereich-Spalte zurück.  
  
```  
int GetColumnCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktuelle Anzahl der Spalten in der Splitter zurück. Ein statischer Splitter werden dadurch auch die maximale Anzahl von Spalten.  
  
##  <a name="a-namegetcolumninfoa--csplitterwndgetcolumninfo"></a><a name="getcolumninfo"></a>CSplitterWnd::GetColumnInfo  
 Gibt Informationen über die angegebene Spalte zurück.  
  
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
 Ein Verweis auf eine `int` minimale Breite der Spalte festgelegt werden.  
  
##  <a name="a-namegetpanea--csplitterwndgetpane"></a><a name="getpane"></a>CSplitterWnd::GetPane  
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
 Gibt den Bereich in der angegebenen Zeile und Spalte zurück. Der zurückgegebene Bereich ist in der Regel eine [CView](../../mfc/reference/cview-class.md)-abgeleiteten Klasse.  
  
##  <a name="a-namegetrowcounta--csplitterwndgetrowcount"></a><a name="getrowcount"></a>CSplitterWnd::GetRowCount  
 Gibt die Anzahl der aktuelle Bereich Zeilen zurück.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktuelle Anzahl der Zeilen in der unterteiltes Fenster zurück. Für ein statisches Teilfenster wird dies auch die maximale Anzahl von Zeilen sein.  
  
##  <a name="a-namegetrowinfoa--csplitterwndgetrowinfo"></a><a name="getrowinfo"></a>CSplitterWnd::GetRowInfo  
 Gibt Informationen über die angegebene Zeile zurück.  
  
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
 Ein Verweis auf `int` auf die aktuelle Höhe der Zeile in Pixel festgelegt werden.  
  
 `cyMin`  
 Ein Verweis auf `int` auf die aktuelle Mindesthöhe der Zeile in Pixel festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion zum Abrufen von Informationen über die angegebene Zeile. Die `cyCur` Parameter wird mit der aktuellen Höhe der angegebenen Zeile gefüllt und `cyMin` mit die Mindesthöhe der Zeile gefüllt.  
  
##  <a name="a-namegetscrollstylea--csplitterwndgetscrollstyle"></a><a name="getscrollstyle"></a>CSplitterWnd::GetScrollStyle  
 Gibt den freigegebenen Bildlaufleisten-Stil für das Splitterfenster zurück.  
  
```  
DWORD GetScrollStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine oder mehrere der folgenden Fenster formatieren Flags, die bei Erfolg:  
  
- **WS_HSCROLL** Wenn der Splitter gerade freigegebene horizontale Bildlaufleisten verwaltet.  
  
- **WS_VSCROLL** Wenn der Splitter gerade freigegebene vertikalen Schiebeleisten verwaltet.  
  
 Wenn&0; (null), verwaltet die Splitterfenster freigegebenen Bildlaufleisten nicht aktuell.  
  
##  <a name="a-nameidfromrowcola--csplitterwndidfromrowcol"></a><a name="idfromrowcol"></a>CSplitterWnd::IdFromRowCol  
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
 Diese Member-Funktion dient zum Erstellen von Nonviews als Bereiche und kann aufgerufen werden, bevor Bereich vorhanden ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&5;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]  
  
##  <a name="a-nameischildpanea--csplitterwndischildpane"></a><a name="ischildpane"></a>CSplitterWnd::IsChildPane  
 Bestimmt, ob `pWnd` ist derzeit ein untergeordneten Bereich dieses Fensters Splitter.  
  
```  
BOOL IsChildPane(
    CWnd* pWnd,  
    int* pRow,  
    int* pCol);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) zu testende Objekt.  
  
 `pRow`  
 Ein Zeiger auf ein `int` in der Nummer der Zeile gespeichert.  
  
 `pCol`  
 Ein Zeiger auf eine `int` in dem Sie die Nummer einer Spalte zu speichern.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert ungleich NULL `pWnd` ist derzeit ein untergeordneter Bereich dieses Fensters Splitter und `pRow` und `pCol` werden mit der Position des Bereichs im Splitterfenster gefüllt. Wenn `pWnd` ist es sich nicht um ein untergeordneten Bereich dieses Fensters Splitter wird 0 zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 In Visual C++-Versionen vor 6.0 wurde diese Funktion als definiert.  
  
 `BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`  
  
 Diese Version ist mittlerweile veraltet und sollte nicht verwendet werden.  
  
##  <a name="a-nameistrackinga--csplitterwndistracking"></a><a name="istracking"></a>CSplitterWnd::IsTracking  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Teilerleiste im Fenster gerade verschoben wird.  
  
```  
BOOL IsTracking();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Splitter-Vorgang ausgeführt wird; andernfalls 0.  
  
##  <a name="a-nameondrawsplittera--csplitterwndondrawsplitter"></a><a name="ondrawsplitter"></a>CSplitterWnd::OnDrawSplitter  
 Rendert ein Abbild von einem geteilten Fenster.  
  
```  
virtual void OnDrawSplitter(
    CDC* pDC,  
    ESplitType nType,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Gerätekontext, in dem gezeichnet werden soll. Wenn `pDC` ist **NULL**, dann [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) wird aufgerufen, durch das Framework und keine Aufteilung Fensters gezeichnet wird.  
  
 `nType`  
 Der Wert der **Enum ESplitType**, dies kann einer der folgenden sein:  
  
- **SplitBox** der Splitter ziehen Sie das Feld.  
  
- `splitBar`Die Leiste, die zwischen den zwei Teilfenstern angezeigt wird.  
  
- **SplitIntersection** die Schnittmenge der geteilten Fenster. Dieses Element wird nicht aufgerufen werden, wenn auf Windows 95-und Windows 98 ausgeführt wird.  
  
- **SplitBorder** Fensterrahmen teilen.  
  
 `rect`  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Größe und Form der geteilten Fenster angibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird vom Framework zeichnen, und geben Sie die genauen Merkmale eines unterteilten Fensters aufgerufen. Überschreiben Sie `OnDrawSplitter` für die erweiterte Anpassung von der Bilder für die verschiedenen Grafikkomponenten eines unterteilten Fensters. Die Standard-Bilder ähnelt der Splitter in Microsoft Works für Windows oder Microsoft Windows 95/98, da die Schnittpunkte die Trennleisten gemischt werden.  
  
 Weitere Informationen über dynamische Splitterfenster, finden Sie unter "Splitterfenster" im Artikel [mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md), [Technische Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` Übersicht über die Klasse.  
  
##  <a name="a-nameoninverttrackera--csplitterwndoninverttracker"></a><a name="oninverttracker"></a>CSplitterWnd::OnInvertTracker  
 Rendert ein Teilfenster in der gleichen Größe und Form wie das Rahmenfenster werden.  
  
```  
virtual void OnInvertTracker(const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Ein Verweis auf ein `CRect` -Objekt, das Überwachungsprofil Rechteck angibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird vom Framework aufgerufen, beim Ändern der Größe von Bereichen. Überschreiben Sie `OnInvertTracker` für die erweiterte Anpassung von der Bilder des Splitterfensters. Die Standard-Bilder ähnelt der Splitter in Microsoft Works für Windows oder Microsoft Windows 95/98, da die Schnittpunkte die Trennleisten gemischt werden.  
  
 Weitere Informationen über dynamische Splitterfenster, finden Sie unter "Splitterfenster" im Artikel [mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md), [Technische Hinweis 29](../../mfc/tn029-splitter-windows.md), und die `CSplitterWnd` Übersicht über die Klasse.  
  
##  <a name="a-namerecalclayouta--csplitterwndrecalclayout"></a><a name="recalclayout"></a>CSplitterWnd::RecalcLayout  
 Rufen Sie auf, um das Splitterfenster erneut anzuzeigen, nach der Zeile oder Spalte Größe anpassen.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion auf, um ordnungsgemäß der unterteiltes Fenster erneut anzuzeigen, nachdem Sie die Zeile und Spalte Größe eingestellt haben die [SetRowInfo](#setrowinfo) und [SetColumnInfo](#setcolumninfo) Memberfunktionen. Wenn Sie als Teil des Erstellungsprozesses Zeilen- und Größen ändern, bevor das Splitterfenster angezeigt wird, ist es nicht notwendig, diese Memberfunktion aufrufen.  
  
 Das Framework ruft diese Memberfunktion auf, wenn der Benutzer die Fenstergröße Splitter oder eine Teilung verschiebt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CSplitterWnd::SetColumnInfo](#setcolumninfo).  
  
##  <a name="a-namesetactivepanea--csplitterwndsetactivepane"></a><a name="setactivepane"></a>CSplitterWnd::SetActivePane  
 Legt einen Bereich im Rahmen der aktiven vorhanden sein.  
  
```  
virtual void SetActivePane(
    int row,  
    int col,  
    CWnd* pWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `row`  
 Wenn `pWnd` ist **NULL**, gibt die Zeile im Bereich, der aktiv ist.  
  
 `col`  
 Wenn `pWnd` ist **NULL**, gibt die Spalte in den Bereich, der aktiv ist.  
  
 `pWnd`  
 Ein Zeiger auf ein `CWnd` Objekt. Wenn **NULL**, im angegebenen Bereich `row` und `col` aktiv festgelegt ist. Wenn dies nicht **NULL**, gibt der Bereich, der aktiv festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird aufgerufen, durch das Framework einen Bereich als aktiv festlegen, wenn der Benutzer den Fokus auf einen Bereich innerhalb des Rahmenfensters ändert. Sie können explizit aufrufen, `SetActivePane` in der angegebenen Ansicht wechseln.  
  
 Geben Sie im Bereich mithilfe Zeile und Spalte **oder** durch die Bereitstellung `pWnd`.  
  
##  <a name="a-namesetcolumninfoa--csplitterwndsetcolumninfo"></a><a name="setcolumninfo"></a>CSplitterWnd::SetColumnInfo  
 Rufen Sie die Informationen für die angegebene Spalte festgelegt.  
  
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
 Gibt eine ideale Breite der Spalte der Splitter Fenster in Pixel an.  
  
 `cxMin`  
 Gibt eine minimale Breite für die Spalte der Splitter-Fensters in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion zum neuen minimale Breite und die ideale Breite für eine Spalte festgelegt. Der Mindestwert für die Spalte wird bestimmt, wenn die Spalte zu klein, um vollständig angezeigt werden.  
  
 Wenn das Framework die unterteiltes Fenster angezeigt wird, ordnet er die Bereiche in Spalten und Zeilen gemäß ihrer idealen Dimensionen, die von der linken oberen Ecke auf der unteren rechten Ecke des Clientbereichs des Fensters Splitter arbeiten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&6;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]  
  
##  <a name="a-namesetrowinfoa--csplitterwndsetrowinfo"></a><a name="setrowinfo"></a>CSplitterWnd::SetRowInfo  
 Rufen Sie die Informationen für die angegebene Zeile festgelegt.  
  
```  
void SetRowInfo(
    int row,  
    int cyIdeal,  
    int cyMin);
```  
  
### <a name="parameters"></a>Parameter  
 `row`  
 Gibt eine Zeile der Splitter-Fenster.  
  
 *cyIdeal*  
 Gibt eine ideale Höhe für die Zeile der Splitter-Fensters in Pixel.  
  
 `cyMin`  
 Gibt eine Mindesthöhe für die Zeile der Splitter-Fensters in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um eine neue minimale Höhe und die optimale Höhe für eine Zeile festgelegt. Der Mindestwert für die Zeile bestimmt, wenn die Zeile zu klein, um vollständig angezeigt werden.  
  
 Wenn das Framework die unterteiltes Fenster angezeigt wird, ordnet er die Bereiche in Spalten und Zeilen gemäß ihrer idealen Dimensionen, die von der linken oberen Ecke auf der unteren rechten Ecke des Clientbereichs des Fensters Splitter arbeiten.  
  
##  <a name="a-namesetscrollstylea--csplitterwndsetscrollstyle"></a><a name="setscrollstyle"></a>CSplitterWnd::SetScrollStyle  
 Gibt der neuen Scroll-Stil für die unterteiltes Fenster Bildlaufleisten-Support freigegeben.  
  
```  
void SetScrollStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Die neue Scroll-Formatvorlage für des Splitter-Fensters freigegebene Bildlaufleisten-Unterstützung, die folgenden Werte sind möglich:  
  
- **WS_HSCROLL** erstellen ein-und horizontalen Bildlaufleisten freigegeben.  
  
- **WS_VSCROLL** erstellen ein-und vertikale Bildlaufleisten freigegeben.  
  
### <a name="remarks"></a>Hinweise  
 Nach der Erstellung einer Bildlaufleiste es nicht zerstört, wenn `SetScrollStyle` aufgerufen wird, ohne diesen Stil; stattdessen die Bildlaufleisten ausgeblendet sind. Dies ermöglicht die Anzeige der Bildlaufleisten Zustand beibehalten, auch wenn sie ausgeblendet sind. Nach dem Aufruf von `SetScrollStyle` es ist notwendig, rufen Sie [RecalcLayout](#recalclayout) , damit die Änderung wirksam wird.  
  
##  <a name="a-namesplitcolumna--csplitterwndsplitcolumn"></a><a name="splitcolumn"></a>CSplitterWnd::SplitColumn  
 Gibt an, ob ein Rahmenfenster vertikal aufgeteilt wird.  
  
```  
virtual BOOL SplitColumn(int cxBefore);
```  
  
### <a name="parameters"></a>Parameter  
 *cxBefore*  
 Die Position in Pixel, vor denen die Teilung auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird aufgerufen, wenn ein vertikaler Splitter-Fenster erstellt wird. `SplitColumn`Gibt den Standardspeicherort, wo die Teilung auftritt.  
  
 `SplitColumn`wird vom Framework aufgerufen wird zum Implementieren der Logik des Fensters dynamischer Splitter (d. h., wenn das Splitterfenster verfügt über die **SPLS_DYNAMIC_SPLIT** Stil). Sie können angepasst werden, zusammen mit der virtuellen Funktion [CreateView](#createview), um erweiterte dynamische Splitter zu implementieren.  
  
##  <a name="a-namesplitrowa--csplitterwndsplitrow"></a><a name="splitrow"></a>CSplitterWnd::SplitRow  
 Gibt an, ob ein Rahmenfenster horizontal aufgeteilt wird.  
  
```  
virtual BOOL SplitRow(int cyBefore);
```  
  
### <a name="parameters"></a>Parameter  
 *cyBefore*  
 Die Position in Pixel, vor denen die Teilung auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird aufgerufen, wenn ein horizontaler Splitter-Fenster erstellt wird. `SplitRow`Gibt den Standardspeicherort, wo die Teilung auftritt.  
  
 `SplitRow`wird vom Framework aufgerufen wird zum Implementieren der Logik des Fensters dynamischer Splitter (d. h., wenn das Splitterfenster verfügt über die **SPLS_DYNAMIC_SPLIT** Stil). Sie können angepasst werden, zusammen mit der virtuellen Funktion [CreateView](#createview), um erweiterte dynamische Splitter zu implementieren.  
  
##  <a name="a-nameondrawa--csplitterwndondraw"></a><a name="ondraw"></a>CSplitterWnd::OnDraw  
 Vom Framework zum Zeichnen der unterteiltes Fenster aufgerufen.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel Wahl](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)

