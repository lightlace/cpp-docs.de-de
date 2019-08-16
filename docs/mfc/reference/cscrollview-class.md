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
ms.openlocfilehash: b89daaae4bb578d328e1468cc29470825e19c670
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502594"
---
# <a name="cscrollview-class"></a>CScrollView-Klasse

Eine [CView](../../mfc/reference/cview-class.md) mit scrollfunktionen.

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
|[CScrollView::CheckScrollBars](#checkscrollbars)|Gibt an, ob die scrollansicht über horizontale und vertikale Schiebe leisten verfügt.|
|[CScrollView::FillOutsideRect](#filloutsiderect)|Füllt den Bereich einer Ansicht außerhalb des scrollbereichs.|
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Ruft die aktuelle Bild Lauf Position in den Geräte Einheiten ab.|
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Ruft den aktuellen Zuordnungsmodus, die Gesamtgröße und die Zeilen-und Seitengrößen der scrollbaren Ansicht ab. Die Größen befinden sich in den Geräte Einheiten.|
|[CScrollView::GetScrollPosition](#getscrollposition)|Ruft die aktuelle Bild Lauf Position in logischen Einheiten ab.|
|[CScrollView::GetTotalSize](#gettotalsize)|Ruft die Gesamtgröße der scrollansicht in logischen Einheiten ab.|
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|Bewirkt, dass die Größe der Ansicht die Größe des Frames bestimmt.|
|[CScrollView::ScrollToPosition](#scrolltoposition)|Führt einen Bildlauf in der Ansicht zu einem angegebenen Punkt in logischen Einheiten durch.|
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|Versetzt die scrollansicht in den Skalierungs Modus.|
|[CScrollView::SetScrollSizes](#setscrollsizes)|Legt den Zuordnungsmodus, die Gesamtgröße und den horizontalen und vertikalen scrollbetrag der scrollansicht fest.|

## <a name="remarks"></a>Hinweise

Sie können den Standard Bildlauf selbst in einer beliebigen Klasse `CView` verarbeiten, die von abgeleitet ist, indem Sie die Nachrichten zugeordneten Member von [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) überschreiben `CScrollView` Es`CView` werden jedoch die folgenden Funktionen zu den Funktionen hinzugefügt:

- Die Fenster-und viewportgrößen und die Karten Modi werden verwaltet.

- Sie führt einen automatischen Bildlauf in Reaktion auf Bild Lauf leisten Meldungen durch.

- Sie führt einen automatischen Bildlauf in Reaktion auf Meldungen von der Tastatur, eine Maus ohne Bildlauf oder das intellimausrad aus.

Fügen Sie eine WM_KEYDOWN-Nachricht hinzu, und testen Sie " [setscrollpos](/windows/win32/api/winuser/nf-winuser-setscrollpos)", um automatisch einen Bildlauf als Reaktion auf Nachrichten von der Tastatur durchführen zu können.

Sie können den Bildlauf mit dem Mausrad selbst durchsetzen, indem Sie die Nachrichten zugeordneten [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) -und [onregisteredmousewheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) -Element Funktionen überschreiben. Wie dies für `CScrollView`der Fall ist, unterstützen diese Member-Funktionen das empfohlene Verhalten für [WM_MOUSEWHEEL](/windows/win32/inputdev/wm-mousewheel), die radrotations Nachricht.

Um den automatischen Bildlauf zu nutzen, leiten Sie die Ansichts Klasse `CScrollView` von `CView`anstelle von ab. Wenn Sie beim ersten Erstellen der Sicht die Größe der Bild lauffähigen Ansicht basierend auf der Größe des Dokuments berechnen möchten, können Sie die `SetScrollSizes` Member-Funktion entweder von der außer Kraft Setzung von [CView:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) oder [CView:: OnUpdate](../../mfc/reference/cview-class.md#onupdate)abrufen. (Sie müssen eigenen Code schreiben, um die Größe des Dokuments abzufragen. Ein Beispiel finden Sie unter [Scribble Sample (Scribble](../../overview/visual-cpp-samples.md)-Beispiel).

Der-Rückruf `SetScrollSizes` der Member-Funktion legt den Zuordnungs Modus der Ansicht, die Gesamt Dimensionen der scrollansicht und die Beträge für einen horizontalen und vertikalen Bildlauf fest. Alle Größen befinden sich in logischen Einheiten. Die logische Größe der Sicht wird in der Regel aus den im Dokument gespeicherten Daten berechnet, aber in einigen Fällen möchten Sie möglicherweise eine festgelegte Größe angeben. Beispiele für beide Ansätze finden Sie unter [CScrollView:: setscrollsizes](#setscrollsizes).

Sie geben die Beträge für einen horizontalen und vertikalen Bildlauf in logischen Einheiten an. Standardmäßig führt der Benutzer einen Bildlauf durch, `CScrollView` wenn der Benutzer außerhalb des Bild Lauf Felds auf eine Schiebe leisten-Säule klickt. Wenn der Benutzer auf einen Bild Lauf Pfeil an einem Ende einer Schiebe Leiste klickt `CScrollView` , führt einen Bildlauf in einer Zeile aus. Standardmäßig ist eine Seite 1/10 der Gesamtgröße der Ansicht. eine Zeile ist 1/10 der Seitengröße. Überschreiben Sie diese Standardwerte, indem Sie Benutzer `SetScrollSizes` definierte Größen in der Member-Funktion übergeben. Beispielsweise können Sie die horizontale Größe auf einen Bruchteil der Breite der Gesamtgröße und die vertikale Größe auf die Höhe einer Zeile in der aktuellen Schriftart festlegen.

Anstatt einen Bildlauf `CScrollView` durchführen zu können, kann die Ansicht automatisch auf die aktuelle Fenstergröße skalieren. In diesem Modus weist die Ansicht keine Bild Lauf leisten auf, und die logische Ansicht wird gestreckt oder verkleinert, sodass Sie exakt an den Client Bereich des Fensters angepasst ist. Um diese Funktion für die Skalierung zu verwenden, müssen Sie [CScrollView:: setscaledefitsize](#setscaletofitsize)aufrufen. (Entweder `SetScaleToFitSize` oder `SetScrollSizes`, aber nicht beides.)

Bevor die `OnDraw` Member-Funktion der abgeleiteten Ansichts Klasse aufgerufen `CScrollView` wird, wird der Viewportursprung für `CPaintDC` das Gerätekontext Objekt, an das es `OnDraw`weitergeleitet wird, von automatisch angepasst.

Um den Viewportursprung für das Scrollfenster anzupassen, `CScrollView` überschreibt [CView:: OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc). Diese Anpassung erfolgt automatisch für den `CPaintDC` Geräte `CScrollView` Kontext, der an `OnDraw`weitergeleitet wird `CClientDC`. Sie `CScrollView::OnPrepareDC` müssen sich jedoch selbst für alle anderen verwendeten Geräte Kontexte, z. b.,, anrufen. Sie können über `CScrollView::OnPrepareDC` schreiben, um den Stift, die Hintergrundfarbe und andere Zeichnungs Attribute festzulegen, aber die Basisklasse für die Skalierung aufzurufen.

Bild Lauf leisten können in Bezug auf eine Ansicht an drei Stellen angezeigt werden, wie in den folgenden Fällen:

- Standard Scrollleisten im Fenster Stil können mithilfe der[Windows-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles)WS_HSCROLL und WS_VSCROLL für die Ansicht festgelegt werden.

- ScrollBar-Steuerelemente können auch dem Frame hinzugefügt werden, der die Ansicht enthält. in diesem Fall leitet das Framework WM_HSCROLL-und WM_VSCROLL-Nachrichten aus dem Rahmen Fenster an die derzeit aktive Ansicht weiter.

- Das Framework leitet auch scrollnachrichten von einem `CSplitterWnd` Splitter Steuerelement an den momentan aktiven Splitter Bereich (eine Ansicht) weiter. Wenn Sie in einem [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) mit freigegebenen Scrollleisten platziert `CScrollView` werden, verwendet ein-Objekt die freigegebenen, anstatt eine eigene zu erstellen.

Weitere Informationen zum Verwenden von `CScrollView`finden Sie unter [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md) und [abgeleitete Ansichts Klassen, die in MFC verfügbar sind](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="checkscrollbars"></a>CScrollView:: checkscrollbars

Mit dieser Member-Funktion können Sie feststellen, ob die scrollansicht über horizontale und vertikale Balken verfügt.

```
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>Parameter

*bHasHorzBar*<br/>
Gibt an, dass die Anwendung über eine horizontale Schiebe Leiste verfügt.

*bHasVertBar*<br/>
Gibt an, dass die Anwendung über eine vertikale Scrollleiste verfügt.

##  <a name="cscrollview"></a>CScrollView:: CScrollView

Erstellt ein `CScrollView`-Objekt.

```
CScrollView();
```

### <a name="remarks"></a>Hinweise

Sie müssen entweder `SetScrollSizes` oder `SetScaleToFitSize` ausführen, bevor die scrollansicht verwendet werden kann.

##  <a name="filloutsiderect"></a>CScrollView:: filloutsiderect

Ruft `FillOutsideRect` auf, um den Bereich der Ansicht auszufüllen, der außerhalb des scrollbereichs angezeigt wird.

```
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Der Gerätekontext, in dem der Füllvorgang durchgeführt werden soll.

*pbrush*<br/>
Pinsel, mit dem der Bereich aufgefüllt werden soll.

### <a name="remarks"></a>Hinweise

Verwenden `FillOutsideRect` Sie in der `OnEraseBkgnd` Handlerfunktion der scrollansicht, um eine übermäßige Hintergrund Umgestaltung zu verhindern.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

##  <a name="getdevicescrollposition"></a>CScrollView:: getdevicescrollposition

Wird `GetDeviceScrollPosition` aufgerufen, wenn Sie die aktuellen horizontalen und vertikalen Positionen der scrollfelder in den Schiebe leisten benötigen.

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Die horizontalen und vertikalen Positionen (in Geräte Einheiten) der scrollfelder als `CPoint` -Objekt.

### <a name="remarks"></a>Hinweise

Dieses Koordinaten paar entspricht der Position im Dokument, auf die die obere linke Ecke der Ansicht gescrollt wurde. Dies ist nützlich, wenn Sie die Mauszeiger Positionen an die Geräte Positionen auslagern möchten.

`GetDeviceScrollPosition`Gibt Werte in Geräte Einheiten zurück. Wenn Sie logische Einheiten verwenden möchten, `GetScrollPosition` verwenden Sie stattdessen.

##  <a name="getdevicescrollsizes"></a>CScrollView:: getdevicescrollsizes

`GetDeviceScrollSizes`Ruft den aktuellen Zuordnungsmodus, die Gesamtgröße und die Zeilen-und Seitengrößen der scrollbaren Ansicht ab.

```
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>Parameter

*nMapMode*<br/>
Gibt den aktuellen Kartenmodus für diese Ansicht zurück. Eine Liste möglicher Werte finden `SetScrollSizes`Sie unter.

*sizeTotal*<br/>
Gibt die aktuelle Gesamtgröße der scrollansicht in den Geräte Einheiten zurück.

*sizePage*<br/>
Gibt die aktuellen horizontalen und vertikalen Beträge zurück, die in den einzelnen Richtungen als Reaktion auf einen Mausklick in einer Schiebe leisten-Säule durchlaufen werden sollen. Der `cx` -Member enthält den horizontalen Betrag. Der `cy` -Member enthält den vertikalen Betrag.

*sizeLine*<br/>
Gibt die aktuellen horizontalen und vertikalen Beträge zurück, die in den einzelnen Richtungen als Reaktion auf einen Mausklick in einem Bild Lauf Pfeil angezeigt werden. Der `cx` -Member enthält den horizontalen Betrag. Der `cy` -Member enthält den vertikalen Betrag.

### <a name="remarks"></a>Hinweise

Die Größen befinden sich in den Geräte Einheiten. Diese Member-Funktion wird nur selten aufgerufen.

##  <a name="getscrollposition"></a>CScrollView:: getscrollposition

Wird `GetScrollPosition` aufgerufen, wenn Sie die aktuellen horizontalen und vertikalen Positionen der scrollfelder in den Schiebe leisten benötigen.

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Die horizontalen und vertikalen Positionen (in logischen Einheiten) der scrollfelder als `CPoint` -Objekt.

### <a name="remarks"></a>Hinweise

Dieses Koordinaten paar entspricht der Position im Dokument, auf die die obere linke Ecke der Ansicht gescrollt wurde.

`GetScrollPosition`Gibt Werte in logischen Einheiten zurück. Wenn Sie Geräte Einheiten verwenden möchten, `GetDeviceScrollPosition` verwenden Sie stattdessen.

##  <a name="gettotalsize"></a>CScrollView:: gettotalsize

Rufen `GetTotalSize` Sie auf, um die aktuellen horizontalen und vertikalen Größen der scrollansicht abzurufen.

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Gesamtgröße der scrollansicht in logischen Einheiten. Die horizontale Größe befindet sich im `cx` -Member `CSize` des Rückgabewerts. Die vertikale Größe ist im `cy` -Member.

##  <a name="resizeparenttofit"></a>CScrollView:: resizeanfit

`ResizeParentToFit` Mit dem Befehl wird die Größe des Frame Fensters durch die Größe der Ansicht vorgegeben.

```
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>Parameter

*bShrinkOnly*<br/>
Die Art der Größe, die durchgeführt werden soll. Der Standardwert true verkleinert das Rahmen Fenster, falls zutreffend. Bild Lauf leisten werden weiterhin für große Ansichten oder kleine Rahmen Fenster angezeigt. Der Wert false bewirkt, dass die Ansicht die Größe des Frame Fensters immer genau ändert. Dies kann etwas gefährlich sein, da das Rahmen Fenster zu groß für das Rahmen Fenster der Multiple Document Interface (MDI) oder auf dem Bildschirm sein könnte.

### <a name="remarks"></a>Hinweise

Dies wird nur für Ansichten in untergeordneten MDI-Rahmen Fenstern empfohlen. Verwenden `ResizeParentToFit` Sie in `OnInitialUpdate` der Handlerfunktion Ihrer `CScrollView` abgeleiteten Klasse. Ein Beispiel für diese Member-Funktion finden Sie unter [CScrollView:: setscrollsizes](#setscrollsizes).

`ResizeParentToFit`geht davon aus, dass die Größe des Ansichts Fensters festgelegt wurde. Wenn die Anzeige Fenstergröße nicht festgelegt wurde, `ResizeParentToFit` wenn aufgerufen wird, erhalten Sie eine-Bestätigung. Um sicherzustellen, dass dies nicht der Fall ist, führen Sie den `ResizeParentToFit`folgenden Aufruf aus, bevor Sie aufrufen:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="scrolltoposition"></a>CScrollView:: scrolltoposition

Wird `ScrollToPosition` aufgerufen, um einen Bildlauf zu einem bestimmten Punkt in der Ansicht durchführen

```
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Der Punkt, zu dem durch Scrollen werden soll, in logische Einheiten. Der `x` Member muss ein positiver Wert (größer oder gleich 0) sein, bis zur Gesamtgröße der Ansicht. Das gleiche gilt für den `y` Member, wenn der Kartenmodus MM_TEXT ist. Der `y` Member ist in anderen Karten Modi als MM_TEXT negativ.

### <a name="remarks"></a>Hinweise

Die Ansicht wird gescrollt, sodass sich dieser Punkt in der oberen linken Ecke des Fensters befindet. Diese Member-Funktion darf nicht aufgerufen werden, wenn die Ansicht skaliert wird.

##  <a name="setscaletofitsize"></a>CScrollView:: setscaledefitsize

Wird `SetScaleToFitSize` aufgerufen, wenn Sie die Viewportgröße automatisch auf die aktuelle Fenstergröße skalieren möchten.

```
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>Parameter

*sizeTotal*<br/>
Die horizontale und vertikale Größe, auf die die Ansicht skaliert werden soll. Die Größe der scrollansicht wird in logischen Einheiten gemessen. Die horizontale Größe ist im `cx` -Member enthalten. Die vertikale Größe ist im `cy` -Member enthalten. `cx` Und`cy` müssen größer oder gleich 0 sein.

### <a name="remarks"></a>Hinweise

Bei Bild Lauf leisten kann jeweils nur ein Teil der logischen Ansicht sichtbar sein. Mit der Funktion zum Anpassen von Skalierungen weist die Ansicht jedoch keine Schiebe leisten auf, und die logische Ansicht wird gestreckt oder verkleinert, sodass Sie exakt an den Client Bereich des Fensters angepasst ist. Wenn die Größe des Fensters geändert wird, werden die Daten in der Ansicht basierend auf der Größe des Fensters auf einer neuen Skala gezeichnet.

`SetScaleToFitSize` In der Regel platzieren Sie den-Befehl in ihrer außer Kraft setzung der `OnInitialUpdate` Member-Funktion der Sicht. Wenn Sie die automatische Skalierung nicht wünschen, sollten `SetScrollSizes` Sie stattdessen die Member-Funktion verwenden.

`SetScaleToFitSize`kann verwendet werden, um einen "Zoom to fit"-Vorgang zu implementieren. Verwenden `SetScrollSizes` Sie, um den Bildlauf erneut zu initialisieren.

`SetScaleToFitSize`geht davon aus, dass die Größe des Ansichts Fensters festgelegt wurde. Wenn die Anzeige Fenstergröße nicht festgelegt wurde, `SetScaleToFitSize` wenn aufgerufen wird, erhalten Sie eine-Bestätigung. Um sicherzustellen, dass dies nicht der Fall ist, führen Sie den `SetScaleToFitSize`folgenden Aufruf aus, bevor Sie aufrufen:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="setscrollsizes"></a>CScrollView:: setscrollsizes

Wird `SetScrollSizes` aufgerufen, wenn die Ansicht im Begriff ist, aktualisiert zu werden.

```
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>Parameter

*nMapMode*<br/>
Der Zuordnungsmodus, der für diese Ansicht festgelegt wird. Mögliche Werte:

|Mapping-Modus|Logische Einheit|Positive y-Achse erweitert...|
|------------------|------------------|---------------------------------|
|MM_TEXT|1 Pixel|Abstieg|
|MM_HIMETRIC|0,01 mm|Auswär|
|MM_TWIPS|1/1440 in|Auswär|
|MM_HIENGLISH|0,001 in|Auswär|
|MM_LOMETRIC|0,1 mm|Auswär|
|MM_LOENGLISH|0,01 in|Auswär|

Alle diese Modi werden von Windows definiert. Zwei standardmäßige Karten Modi, MM_ISOTROPIC und MM_ANISOTROPIC, werden nicht für `CScrollView`verwendet. Die-Klassenbibliothek stellt `SetScaleToFitSize` die Member-Funktion zum Skalieren der Ansicht auf die Fenstergröße bereit. In der obigen Spalte in der obigen Tabelle wird die Koordinaten Ausrichtung beschrieben.

*sizeTotal*<br/>
Die Gesamtgröße der scrollansicht. Der `cx` Member enthält den horizontalen Wertebereich. Der `cy` -Member enthält den vertikalen Wertebereich. Die Größen befinden sich in logischen Einheiten. `cx` Und`cy` müssen größer oder gleich 0 sein.

*sizePage*<br/>
Die horizontale und vertikale Menge, um in den einzelnen Richtungen einen Bildlauf durchführen zu können, wenn ein Mausklick in einer Schiebe leisten-Schwelle angezeigt wird. Der `cx` -Member enthält den horizontalen Betrag. Der `cy` -Member enthält den vertikalen Betrag.

*sizeLine*<br/>
Die horizontale und vertikale Menge, um in den einzelnen Richtungen einen Bildlauf durchführen zu können, wenn ein Mausklick in einem scrollpfeil angezeigt wird. Der `cx` -Member enthält den horizontalen Betrag. Der `cy` -Member enthält den vertikalen Betrag.

### <a name="remarks"></a>Hinweise

Sie können es in der Überschreibung `OnUpdate` der Member-Funktion aufzurufen, um scrollmerkmale anzupassen, wenn z. b. das Dokument anfänglich angezeigt wird oder die Größe geändert wird.

Sie erhalten normalerweise Größen Informationen aus dem zugeordneten Dokument der Ansicht, indem Sie eine dokumentmember-Funktion `GetMyDocSize`aufrufen, die möglicherweise als bezeichnet wird und die Sie mit der abgeleiteten Dokument Klasse angeben. Der folgende Code zeigt diese Vorgehensweise:

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

Alternativ dazu müssen Sie möglicherweise auch eine festgelegte Größe festlegen, wie im folgenden Code:

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

Der Zuordnungsmodus muss auf einen der Windows-zuordnungsmodi mit Ausnahme von MM_ISOTROPIC oder MM_ANISOTROPIC festgelegt werden. Wenn Sie einen nicht eingeschränkten Zuordnungs Modus verwenden möchten, müssen Sie `SetScaleToFitSize` die-Member- `SetScrollSizes`Funktion anstelle von aufruft.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[CSplitterWnd-Klasse](../../mfc/reference/csplitterwnd-class.md)
