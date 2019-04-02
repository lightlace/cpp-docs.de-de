---
title: CScrollView-Klasse
ms.date: 11/04/2016
f1_keywords:
- CScrollView
- AFXWIN/CScrollView
- AFXWIN/CScrollView::CScrollView
- AFXWIN/CScrollView::CheckScrollBars
- AFXWIN/CScrollView::FillOutsideRect
- AFXWIN/CScrollView::GetDeviceScrollPosition
- AFXWIN/CScrollView::GetDeviceScrollSizes
- AFXWIN/CScrollView::GetScrollPosition
- AFXWIN/CScrollView::GetTotalSize
- AFXWIN/CScrollView::ResizeParentToFit
- AFXWIN/CScrollView::ScrollToPosition
- AFXWIN/CScrollView::SetScaleToFitSize
- AFXWIN/CScrollView::SetScrollSizes
helpviewer_keywords:
- CScrollView [MFC], CScrollView
- CScrollView [MFC], CheckScrollBars
- CScrollView [MFC], FillOutsideRect
- CScrollView [MFC], GetDeviceScrollPosition
- CScrollView [MFC], GetDeviceScrollSizes
- CScrollView [MFC], GetScrollPosition
- CScrollView [MFC], GetTotalSize
- CScrollView [MFC], ResizeParentToFit
- CScrollView [MFC], ScrollToPosition
- CScrollView [MFC], SetScaleToFitSize
- CScrollView [MFC], SetScrollSizes
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
ms.openlocfilehash: d60082092bd42fbe220eee08953ad5fda0ff0a85
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774152"
---
# <a name="cscrollview-class"></a>CScrollView-Klasse

Ein [CView](../../mfc/reference/cview-class.md) mit Bildlauffunktionen.

## <a name="syntax"></a>Syntax

```
class CScrollView : public CView
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CScrollView::CScrollView](#cscrollview)|Erstellt ein `CScrollView`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CScrollView::CheckScrollBars](#checkscrollbars)|Gibt an, ob die scrollansicht horizontale und vertikale Schiebeleisten besitzt.|
|[CScrollView::FillOutsideRect](#filloutsiderect)|Füllt den Bereich einer Sicht außerhalb des Bereichs scrollen.|
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Ruft die aktuelle Bildlaufposition in Geräteeinheiten ab.|
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Ruft den aktuellen Zuordnungsmodus, die Gesamtgröße und die Zeilen- und Größen der bildlauffähige Ansicht ab. Größen sind in Geräteeinheiten.|
|[CScrollView::GetScrollPosition](#getscrollposition)|Ruft die aktuelle Bildlaufposition in logischen Einheiten ab.|
|[CScrollView::GetTotalSize](#gettotalsize)|Ruft die Gesamtgröße der Bildlaufansicht in logischen Einheiten ab.|
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|Bewirkt, dass die Größe der Ansicht festgelegt werden, die Größe des zugehörigen Rahmen.|
|[CScrollView::ScrollToPosition](#scrolltoposition)|Führt einen Bildlauf zu einem bestimmten Zeitpunkt an, in logischen Einheiten angegeben.|
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|Legt die scrollansicht in den Modus der Skalierung auf anpassen.|
|[CScrollView::SetScrollSizes](#setscrollsizes)|Der scrollansicht Zuordnungsmodus, Gesamtgröße und horizontalen und vertikalen Bildlauf Mengen festgelegt.|

## <a name="remarks"></a>Hinweise

Sie können Standard selbst in einer Klasse abgeleitet zu scrollen behandeln `CView` durch Überschreiben der Nachricht zugeordnete [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) Memberfunktionen. Aber `CScrollView` bietet die folgenden Features, die `CView` Funktionen:

- Er verwaltet Fenster-und Viewport und Zuordnungsmodi.

- Es wird automatisch als Reaktion auf Bildlaufleisten-Nachrichten angezeigt.

- Es wird automatisch als Reaktion auf Nachrichten von der Tastatur, Maus ohne Bildlauf oder das Rad IntelliMouse angezeigt.

Automatisch als Reaktion auf Nachrichten über die Tastatur einen Bildlauf durchführen, fügen Sie eine WM_KEYDOWN-Meldung hinzu und Testen für VK_DOWN, VK_PREV und Aufruf [SetScrollPos](/windows/desktop/api/winuser/nf-winuser-setscrollpos).

Sie können die Mausrad Scrollen selbst durch Überschreiben der Nachricht zugeordnete behandeln [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) und [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) Memberfunktionen. Wie für `CScrollView`, diese Memberfunktionen unterstützen das empfohlene Verhalten für [WM_MOUSEWHEEL](/windows/desktop/inputdev/wm-mousewheel), die Rad-Rotation-Nachricht.

Leiten Sie zur Nutzung des automatischen Bildlaufs Ihrer Ansichtsklasse aus `CScrollView` anstelle von `CView`. Wenn die Ansicht zuerst erstellt wird, sollten Sie die Größe der bildlauffähige Ansicht basierend auf der Größe des Dokuments Aufruf berechnet die `SetScrollSizes` Memberfunktion der Ihre Überschreibung der [CView:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) oder [ CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate). (Sie müssen Ihren eigenen Code zum Abfragen der Größe des Dokuments schreiben. Ein Beispiel finden Sie unter den [Scribble-Beispiels](../../overview/visual-cpp-samples.md).)

Der Aufruf der `SetScrollSizes` Memberfunktion legt Zuordnungsmodus der Ansicht, die gesamten Dimensionen Bildlaufansicht, und die Beträge horizontal und vertikal scrollen. Alle Größen sind in logischen Einheiten. Die logische Größe der Ansicht wird aus Daten in das Dokument in der Regel berechnet, aber in einigen Fällen kann eine feste Größe angeben möchten. Beispiele für beide Ansätze, finden Sie unter [CScrollView::SetScrollSizes](#setscrollsizes).

Angabe wird die Beträge in logischen Einheiten horizontal und vertikal scrollen. Standardmäßig wird das Scroll-Leiste Welle außerhalb das Bildlauffeld, klickt der Benutzer auf `CScrollView` führt einen Bildlauf um eine "Seite". Klickt der Benutzer einen Bildlaufpfeil an beiden Enden einer Bildlaufleiste `CScrollView` führt einen Bildlauf um eine "Linie". Standardmäßig ist eine Seite 1/10 der Gesamtgröße der Ansicht. eine Zeile ist 1/10 der Seitengröße. Diese Standardwerte zu überschreiben, indem Sie die Übergabe von benutzerdefinierter Größen in der `SetScrollSizes` Member-Funktion. Beispielsweise können Sie die horizontale Größe auf ein Anteil von der Breite der Größe und die vertikale Größe auf die Höhe einer Zeile in der aktuellen Schriftart festlegen.

Anstelle von Scrollen `CScrollView` können die Ansicht in der aktuellen Fenstergröße automatisch skalieren. In diesem Modus wird die Sicht hat keine Bildlaufleisten und die logische Ansicht wird gestreckt oder verkleinert, damit genau Clientbereich des Fensters entspricht. Rufen Sie zum Verwenden dieser Funktion für die Skalierung auf Anpassen [CScrollView::SetScaleToFitSize](#setscaletofitsize). (Rufen Sie entweder `SetScaleToFitSize` oder `SetScrollSizes`, aber nicht beide.)

Vor der `OnDraw` Ihrer abgeleiteten Ansichtsklasse Memberfunktion aufgerufen wird, `CScrollView` automatisch angepasst wird, den Viewport-Ursprung für die `CPaintDC` gerätkontextobjekt, die an übergeben `OnDraw`.

Anpassen den Viewport-Ursprung für die scrollbaren Fensters `CScrollView` überschreibt [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc). Diese Anpassung ist automatisch für die `CPaintDC` Gerätekontext, `CScrollView` übergibt an `OnDraw`, allerdings müssen Aufrufen `CScrollView::OnPrepareDC` selbst für alle anderen Gerätekontexte Sie verwenden, z. B. eine `CClientDC`. Sie können außer Kraft setzen `CScrollView::OnPrepareDC` der Stift, Hintergrundfarbe und andere Zeichnungsattribute festlegen, aber der Basisklasse dazu Skalierung aufrufen.

Bildlaufleisten können an drei Stellen relativ zu einer Ansicht angezeigt werden, wie in den folgenden Fällen angezeigt:

- Standard-Stil für Fenster-Bildlaufleisten können festgelegt werden, für die Ansicht mit dem WS_HSCROLL und WS_VSCROLL[Windows Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).

- Bildlaufleisten-Steuerelemente können auch auf den Frame mit der Ansicht hinzugefügt werden, die in diesem Fall leitet das Framework WM_HSCROLL- und WM_VSCROLL-Meldungen vom Rahmenfenster, die derzeit aktive Ansicht.

- Das Framework leitet auch weiter Scrollen Sie Nachrichten von einem `CSplitterWnd` Splitter-Steuerelement in den derzeit aktiven Splitter-Bereich (eine Ansicht). Wenn in einem [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) mit freigegebenen Bildlaufleisten angezeigt werden, eine `CScrollView` -Objekt verwendet freigegebene diejenigen, anstatt eine eigene zu erstellen.

Weitere Informationen zur Verwendung von `CScrollView`, finden Sie unter [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md) und [abgeleitete Sicht Klassen in MFC verfügbare](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="checkscrollbars"></a>  CScrollView::CheckScrollBars

Rufen Sie diese Memberfunktion, um zu bestimmen, ob die scrollansicht horizontale und vertikale Balken an.

```
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>Parameter

*bHasHorzBar*<br/>
Gibt an, dass die Anwendung eine horizontale Schiebeleiste hat.

*bHasVertBar*<br/>
Gibt an, dass die Anwendung eine vertikale Bildlaufleiste hat.

##  <a name="cscrollview"></a>  CScrollView::CScrollView

Erstellt ein `CScrollView`-Objekt.

```
CScrollView();
```

### <a name="remarks"></a>Hinweise

Sie müssen entweder Aufrufen `SetScrollSizes` oder `SetScaleToFitSize` vor den Bildlauf Sicht kann verwendet werden.

##  <a name="filloutsiderect"></a>  CScrollView::FillOutsideRect

Rufen Sie `FillOutsideRect` um den Bereich der Ansicht zu füllen, die außerhalb des Bereichs Bildlauf angezeigt wird.

```
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Gerätekontext, in dem die aufgefüllt ist, ausgeführt werden.

*pBrush*<br/>
Der Pinsel, mit dem ist der Bereich gefüllt werden soll.

### <a name="remarks"></a>Hinweise

Verwendung `FillOutsideRect` in Ihre scrollansicht `OnEraseBkgnd` Handler-Funktion, um zu verhindern, dass eine übermäßige Hintergrund neu gezeichnet.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

##  <a name="getdevicescrollposition"></a>  CScrollView::GetDeviceScrollPosition

Rufen Sie `GetDeviceScrollPosition` Wenn Sie die aktuelle horizontalen und vertikalen Position der Bildlauffelder in die Bildlaufleisten benötigen.

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Die horizontalen und vertikalen Position (in Geräteeinheiten) führen Sie einen Bildlauf Felder als ein `CPoint` Objekt.

### <a name="remarks"></a>Hinweise

Diese Koordinatenpaar entspricht der Speicherort des Dokuments, der die linke obere Ecke der Ansicht Bildlauf ausgeführt wurde. Dies ist nützlich für den Ausgleich der Mausgerät Positionen, um die scrollansicht Gerät-Positionen.

`GetDeviceScrollPosition` Gibt die Werte in Geräteeinheiten zurück. Verwenden Sie logische Einheiten können `GetScrollPosition` stattdessen.

##  <a name="getdevicescrollsizes"></a>  CScrollView::GetDeviceScrollSizes

`GetDeviceScrollSizes` Ruft den aktuellen Zuordnungsmodus, die Gesamtgröße und die Zeilen- und Größen der bildlauffähige Ansicht ab.

```
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>Parameter

*nMapMode*<br/>
Gibt den aktuellen Zuordnungsmodus für diese Ansicht zurück. Eine Liste der möglichen Werte, finden Sie unter `SetScrollSizes`.

*sizeTotal*<br/>
Gibt die aktuelle Gesamtgröße der Bildlaufansicht in Geräteeinheiten zurück.

*sizePage*<br/>
Gibt zurück, der den aktuellen horizontalen und vertikalen Betrag in jeder Richtung als Reaktion auf eine Maus Scrollen in einer Bildlaufleiste klicken Sie auf. Die `cx` Member enthält, die horizontale Größe. Die `cy` Member enthält, die vertikale Größe.

*sizeLine*<br/>
Gibt zurück, der aktuellen horizontalen und vertikalen Betrag für einen Bildlauf in jede Richtung als Reaktion auf eine Maus in einen Bildlaufpfeil klicken Sie auf. Die `cx` Member enthält, die horizontale Größe. Die `cy` Member enthält, die vertikale Größe.

### <a name="remarks"></a>Hinweise

Größen sind in Geräteeinheiten. Diese Memberfunktion wird nur selten aufgerufen.

##  <a name="getscrollposition"></a>  CScrollView::GetScrollPosition

Rufen Sie `GetScrollPosition` Wenn Sie die aktuelle horizontalen und vertikalen Position der Bildlauffelder in die Bildlaufleisten benötigen.

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Die horizontalen und vertikalen Position (in logischen Einheiten) der Bildlauffelder als ein `CPoint` Objekt.

### <a name="remarks"></a>Hinweise

Diese Koordinatenpaar entspricht der Speicherort des Dokuments, der die linke obere Ecke der Ansicht Bildlauf ausgeführt wurde.

`GetScrollPosition` Gibt Werte zurück, in logischen Einheiten. Wenn Sie Geräteeinheiten möchten, verwenden Sie `GetDeviceScrollPosition` stattdessen.

##  <a name="gettotalsize"></a>  CScrollView::GetTotalSize

Rufen Sie `GetTotalSize` um die aktuellen horizontalen und vertikalen Größen der Bildlaufansicht abzurufen.

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Gesamtgröße der Bildlaufansicht in logischen Einheiten. Die horizontale Größe ist in der `cx` Mitglied der `CSize` Wert zurückgeben. Die vertikale Größe ist in der `cy` Member.

##  <a name="resizeparenttofit"></a>  CScrollView::ResizeParentToFit

Rufen Sie `ResizeParentToFit` können Sie die Größe der Ansicht bestimmt die Größe des zugehörigen Rahmenfenster.

```
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>Parameter

*bShrinkOnly*<br/>
Die Art der Größenänderung von führen. Der Standardwert "true", wird das Rahmenfenster verkleinert, bei Bedarf. Bildlaufleisten werden weiterhin für große Ansichten oder kleinen Rahmenfenster angezeigt. Der Wert "false" bewirkt, dass die Ansicht immer genau Ändern der Größe der Frame-Fensters. Dies kann etwas gefährlich sein, da das Rahmenfenster zu groß für die Frame-Fensters von multiple Document Interface (MDI) oder dem Bildschirm abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Dies ist nur für Ansichten im Rahmen des untergeordneten MDI-Fenstern empfohlen. Verwendung `ResizeParentToFit` in die `OnInitialUpdate` Handlerfunktion, der dem abgeleiteten `CScrollView` Klasse. Ein Beispiel für diese Memberfunktion auf, finden Sie unter [CScrollView::SetScrollSizes](#setscrollsizes).

`ResizeParentToFit` wird davon ausgegangen, dass die Größe des Ansichtsfensters festgelegt wurde. Wenn die Größe der Ansicht Fenster nicht beim festgelegt wurde `ResizeParentToFit` ist aufgerufen wird, erhalten Sie eine Assertion. Um sicherzustellen, dass dies nicht der Fall, stellen Sie den folgenden Aufruf vor dem Aufruf `ResizeParentToFit`:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="scrolltoposition"></a>  CScrollView::ScrollToPosition

Rufen Sie `ScrollToPosition` zu einem bestimmten Zeitpunkt in der Ansicht einen Bildlauf durchführen.

```
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Der Punkt, in logischen Einheiten zu scrollen. Die `x` Member muss ein positiver Wert (größer als oder gleich 0 (null) bis zu die Gesamtgröße der Ansicht) sein. Das gleiche gilt für die `y` Member auf, wenn der Zuordnungsmodus MM_TEXT ist. Die `y` Member in Zuordnungsmodi als MM_TEXT negativ ist.

### <a name="remarks"></a>Hinweise

Damit dieser Punkt auf der linken oberen Ecke des Fensters ist, wird die Ansicht gescrollt werden. Diese Memberfunktion darf nicht aufgerufen werden, wenn die Ansicht entsprechend skaliert wird.

##  <a name="setscaletofitsize"></a>  CScrollView::SetScaleToFitSize

Rufen Sie `SetScaleToFitSize` bei der Viewport-Größe auf die aktuelle Fenstergröße automatisch skaliert werden soll.

```
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>Parameter

*sizeTotal*<br/>
Die horizontalen und vertikalen Größen, die Ansicht ist, skaliert werden. Die scrollansicht Größe wird in logischen Einheiten gemessen. Die horizontale Größe ist Bestandteil der `cx` Member. Die vertikale Größe ist Bestandteil der `cy` Member. Beide `cx` und `cy` muss größer als oder gleich 0 sein.

### <a name="remarks"></a>Hinweise

Mit Bildlaufleisten angezeigt werden kann zu einem beliebigen Zeitpunkt nur ein Teil der logischen Ansicht sichtbar sein. Aber mit der Skalierung auf Anpassen-Funktion, die Sicht hat keine Bildlaufleisten und die logische Ansicht wird gestreckt oder verkleinert, damit genau Clientbereich des Fensters entspricht. Beim Ändern der Größe des Fensters, zeichnet die Ansicht die Daten an einen neuen Skalierung basierend auf der Größe des Fensters.

Platzieren Sie in der Regel den Aufruf von `SetScaleToFitSize` in Ihre Überschreibung der Ansicht `OnInitialUpdate` Member-Funktion. Wenn Sie nicht wünschen, automatischer Skalierung, rufen Sie die `SetScrollSizes` Memberfunktion stattdessen.

`SetScaleToFitSize` kann verwendet werden, um einen Vorgang "Zoom anpassen" zu implementieren. Verwendung `SetScrollSizes` zum erneuten Initialisieren der Bildlauf.

`SetScaleToFitSize` wird davon ausgegangen, dass die Größe des Ansichtsfensters festgelegt wurde. Wenn die Größe der Ansicht Fenster nicht beim festgelegt wurde `SetScaleToFitSize` ist aufgerufen wird, erhalten Sie eine Assertion. Um sicherzustellen, dass dies nicht der Fall, stellen Sie den folgenden Aufruf vor dem Aufruf `SetScaleToFitSize`:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="setscrollsizes"></a>  CScrollView::SetScrollSizes

Rufen Sie `SetScrollSizes` Wenn die Ansicht ist dabei, die aktualisiert werden.

```
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>Parameter

*nMapMode*<br/>
Die eines Zuordnungsmodus für diese Ansicht. Mögliche Werte:

|Zuordnungsmodus|Logische Einheit|Positiven y-Achse erweitert...|
|------------------|------------------|---------------------------------|
|MM_TEXT|1-pixel|Nach unten|
|MM_HIMETRIC|0.01 mm|Nach oben|
|MM_TWIPS|1/1440 in|Nach oben|
|MM_HIENGLISH|0,001 Zoll|Nach oben|
|MM_LOMETRIC|0.1 mm|Nach oben|
|MM_LOENGLISH|0,01 Zoll|Nach oben|

Diese Modi werden durch Windows definiert. Zwei standard-Mapping-Modi, MM_ISOTROPIC und MM_ANISOTROPIC, werden nicht zum `CScrollView`. Stellt die Klassenbibliothek die `SetScaleToFitSize` Memberfunktion für die Skalierung der Ansicht, um die Größe des Fensters. Spalte 3 in der obigen Tabelle beschreibt die Koordinate Ausrichtung.

*sizeTotal*<br/>
Die Gesamtgröße der Bildlaufansicht. Die `cx` Member enthält den horizontalen Umfang. Die `cy` Member enthält den vertikalen Wertebereichs. Größen sind in logischen Einheiten. Beide `cx` und `cy` muss größer als oder gleich 0 sein.

*sizePage*<br/>
Die horizontalen und vertikalen Betrag in jeder Richtung als Reaktion auf einen Mausklick einen Bildlauf durchführen, klicken Sie in einer Bildlaufleiste. Die `cx` Member enthält, die horizontale Größe. Die `cy` Member enthält, die vertikale Größe.

*sizeLine*<br/>
Die horizontalen und vertikalen Betrag in jeder Richtung als Reaktion auf einen Mausklick einen Bildlauf durchführen, klicken Sie in einen Bildlaufpfeil. Die `cx` Member enthält, die horizontale Größe. Die `cy` Member enthält, die vertikale Größe.

### <a name="remarks"></a>Hinweise

Rufen Sie diese in Ihre Überschreibung der `OnUpdate` Memberfunktion versucht, den Bildlauf Merkmale anzupassen, wenn Sie z. B. das Dokument zuerst angezeigt wird oder wenn sie die Größe ändert.

In der Regel erhalten Sie Informationen zur Größe aus der Ansicht zugeordnete Dokument, Aufrufen von einer Memberfunktion Dokument, das möglicherweise aufgerufen `GetMyDocSize`, die Sie mit Ihrer Dokumentklasse abgeleiteten angeben. Der folgende Code zeigt diesen Ansatz:

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

Alternativ müssen Sie möglicherweise gelegentlich eine feste Größe, wie im folgenden Code festlegen:

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

Sie müssen den Zuordnungsmodus auf die Zuordnungsmodi für Windows mit Ausnahme von MM_ISOTROPIC oder MM_ANISOTROPIC festlegen. Wenn Sie eine uneingeschränkte Zuordnungsmodus verwenden möchten, rufen Sie die `SetScaleToFitSize` Memberfunktion anstelle der `SetScrollSizes`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[CSplitterWnd-Klasse](../../mfc/reference/csplitterwnd-class.md)
