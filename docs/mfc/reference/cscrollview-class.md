---
title: CScrollView Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82ffdb26c5766a0ff7cbada511c9bc9c82ebfd93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375541"
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
|[CScrollView::CheckScrollBars](#checkscrollbars)|Gibt an, ob die Sicht Scroll horizontale und vertikale Bildlaufleisten verfügt.|  
|[CScrollView::FillOutsideRect](#filloutsiderect)|Füllt den Bereich einer Sicht außerhalb des Bereichs Durchführen eines Bildlaufs.|  
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Ruft die aktuelle Bildlaufposition in Geräteeinheiten ab.|  
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Ruft den aktuellen Zuordnungsmodus, die Gesamtgröße und die Zeilen- und Größen der bildlauffähige Ansicht ab. Größen sind im Geräteeinheiten.|  
|[CScrollView::GetScrollPosition](#getscrollposition)|Ruft die aktuelle Bildlaufposition in logischen Einheiten ab.|  
|[CScrollView::GetTotalSize](#gettotalsize)|Ruft die Gesamtgröße der Bildlaufansicht einen in logischen Einheiten ab.|  
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|Bewirkt, dass die Größe der Ansicht zum Festlegen, der Größe des Rahmens.|  
|[CScrollView::ScrollToPosition](#scrolltoposition)|Führt einen Bildlauf die Ansicht zu einem bestimmten Zeitpunkt, in logischen Einheiten angegeben.|  
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|Versetzt das Scroll-Ansicht in Skalierung auf Anpassen Modus.|  
|[CScrollView::SetScrollSizes](#setscrollsizes)|Legt fest, das Scroll-Ansicht Zuordnungsmodus Gesamtgröße und horizontalen und vertikalen Bildlauf Mengen.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die Standard Bildlauf selbst in einer Klasse abgeleitet behandeln `CView` durch Überschreiben der Nachricht zugeordnete [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) Memberfunktionen. Aber `CScrollView` bietet die folgenden Features, dessen `CView` Funktionen:  
  
-   Er verwaltet die Zuordnungsmodi "und" Fenster-und Viewport.  
  
-   Es wird automatisch als Antwort auf Bildlaufleisten-Nachrichten.  
  
-   Es wird automatisch als Antwort auf Nachrichten von der Tastatur oder Maus nicht durchführen eines Bildlaufs Rad der IntelliMouse.  
  
 Um automatisch als Antwort auf Nachrichten über die Tastatur zu blättern, Hinzufügen einer Meldung WM_KEYDOWN und Testen für VK_DOWN, VK_PREV und Aufruf [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597).  
  
 Sie können selbst durch Überschreiben der Nachricht zugeordnete Bildlauf Mausrad behandeln [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) und [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) Memberfunktionen. Wie für `CScrollView`, diese Memberfunktionen unterstützen das empfohlene Verhalten für [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617), die Wheel Drehung-Nachricht.  
  
 Der automatische Bildlauf nutzen möchten, leiten Sie eine Ansichtsklasse von `CScrollView` anstelle von `CView`. Wenn die Sicht wird zuerst erstellt, wenn Sie die Größe der bildlauffähige Ansicht basierend auf der Größe des Dokuments Aufruf berechnet werden soll die `SetScrollSizes` Memberfunktion der Ihre Überschreibung entweder [CView:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) oder [ CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate). (Sie müssen Ihre eigenen Code aus, um die Größe des Dokuments Abfragen schreiben. Ein Beispiel finden Sie die [Scribble-Beispiel](../../visual-cpp-samples.md).)  
  
 Der Aufruf der `SetScrollSizes` Memberfunktion legt Zuordnungsmodus die Sicht, die insgesamt Dimensionen das Scroll-Ansicht und die Beträge, horizontaler und vertikaler Richtung zu scrollen. Alle Größen sind in logischen Einheiten. Die logische Größe der Sicht wird in der Regel aus Daten in das Dokument berechnet, jedoch in einigen Fällen möchten Sie möglicherweise eine feste Größe angeben. Beispiele für beide Vorgehensweisen, finden Sie unter [CScrollView::SetScrollSizes](#setscrollsizes).  
  
 Sie geben die Beträge, horizontal und vertikal in logischen Einheiten zu scrollen. Klickt der Benutzer Scroll Bar Welle außerhalb des scrollfelds standardmäßig `CScrollView` verschiebt "Seite". Wenn der Benutzer ein Bildlaufpfeils an beiden Enden einer Bildlaufleiste klickt `CScrollView` scrollt eine "Linie". Standardmäßig wird eine Seite 1/10 der Gesamtgröße der Sicht; eine Zeile ist 1/10 der Seitengröße. Überschreiben Sie diese Standardwerte durch Übergabe von benutzerdefinierten Größen in der `SetScrollSizes` Memberfunktion. Beispielsweise können Sie die horizontale Größe auf ein Anteil von der Breite der Gesamtgröße und die vertikale Größe, der die Höhe einer Zeile in der aktuellen Schriftart festgelegt.  
  
 Anstelle von scrolling `CScrollView` können automatisch die Ansicht, um die Größe des aktuellen Fensters zu skalieren. In diesem Modus kann die Sicht hat keine Bildlaufleisten und die logische Sicht gestreckt oder verkleinert werden, genau Clientbereich des Fensters angepasst wird. Rufen Sie zum Verwenden dieser Funktion für die Skalierung auf Anpassen [CScrollView::SetScaleToFitSize](#setscaletofitsize). (Rufen Sie entweder `SetScaleToFitSize` oder `SetScrollSizes`, aber nicht beides.)  
  
 Vor der `OnDraw` Memberfunktion der Klasse abgeleitete Sicht aufgerufen wird, `CScrollView` automatisch anpasst und den Ursprung des Ausschnitts für die `CPaintDC` übergibt an gerätkontextobjekt `OnDraw`.  
  
 Der Ursprung des Ausschnitts für das Durchführen eines Bildlaufs Fenster anpassen `CScrollView` überschreibt [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc). Diese Anpassung wird automatisch für die `CPaintDC` Gerätekontext, `CScrollView` übergibt an `OnDraw`, allerdings müssen Aufrufen **CScrollView::OnPrepareDC** selbst für alle anderen Gerätekontexte Sie verwenden, z. B. eine `CClientDC`. Sie können außer Kraft setzen **CScrollView::OnPrepareDC** der Stift, Hintergrundfarbe und andere Zeichnungsattribute festlegen, aber der Basisklasse hierzu Skalierung aufrufen.  
  
 Bildlaufleisten können an drei Orten relativ zu einer Ansicht angezeigt werden, wie in den folgenden Fällen angezeigt:  
  
-   Standard Fensterstil Bildlaufleisten können festgelegt werden, für die Sicht mithilfe der **WS_HSCROLL** und **WS_VSCROLL**[Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
-   Bildlaufleisten-Steuerelemente können auch hinzugefügt werden, auf den Frame mit der Ansicht, in dem Fall das Framework leitet `WM_HSCROLL` und `WM_VSCROLL` Nachrichten vom Rahmenfenster der momentan aktiven Ansicht.  
  
-   Das Framework auch leitet Scrollen von Nachrichten von einer `CSplitterWnd` Splitter-Steuerelement in den derzeit aktiven Splitter-Bereich (eine Sicht). In platziert eine [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) mit freigegebenen Bildlaufleisten, eine `CScrollView` Objekt verwenden freigegebene diejenigen, anstatt einen eigenen zu erstellen.  
  
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
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Scroll-Sicht horizontale und vertikale Balken enthält.  
  
```  
void CheckScrollBars(
    BOOL& bHasHorzBar,  
    BOOL& bHasVertBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *bHasHorzBar*  
 Gibt an, dass die Anwendung eine horizontale Bildlaufleiste angezeigt wurde.  
  
 *bHasVertBar*  
 Gibt an, dass die Anwendung eine vertikale Bildlaufleiste verfügt.  
  
##  <a name="cscrollview"></a>  CScrollView::CScrollView  
 Erstellt ein `CScrollView`-Objekt.  
  
```  
CScrollView();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen entweder Aufrufen `SetScrollSizes` oder `SetScaleToFitSize` vor den Bildlauf Sicht kann verwendet werden.  
  
##  <a name="filloutsiderect"></a>  CScrollView::FillOutsideRect  
 Rufen Sie `FillOutsideRect` um den Bereich der Ansicht zu füllen, die außerhalb des Bereichs Durchführen eines Bildlaufs angezeigt wird.  
  
```  
void FillOutsideRect(
    CDC* pDC,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Gerätekontext, in dem die füllen ist, durchgeführt werden.  
  
 `pBrush`  
 Der Pinsel, der Bereich ist gefüllt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `FillOutsideRect` in Ihrer Scroll Ansicht `OnEraseBkgnd` Handler-Funktion, um zu verhindern, dass eine übermäßige im Hintergrund aktualisiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]  
  
##  <a name="getdevicescrollposition"></a>  CScrollView::GetDeviceScrollPosition  
 Rufen Sie `GetDeviceScrollPosition` Wenn Sie die aktuelle horizontalen und vertikalen Position der Bildlaufleiste Felder in die Bildlaufleisten benötigen.  
  
```  
CPoint GetDeviceScrollPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die horizontalen und vertikalen Position (in Geräteeinheiten) der Bildlauffelder als eine `CPoint` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Koordinatenpaar entspricht der Speicherort des Dokuments, der die linke obere Ecke der Sicht Bildlauf ausgeführt wurde. Dies ist hilfreich für das Mausgerät Positionen, Scroll-View-Gerät Positionen versetzen.  
  
 `GetDeviceScrollPosition` Gibt Werte in Geräteeinheiten zurück. Wenn Sie logische Einheiten möchten, verwenden `GetScrollPosition` stattdessen.  
  
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
 `nMapMode`  
 Gibt den aktuellen Zuordnungsmodus für diese Sicht zurück. Eine Liste der möglichen Werte finden Sie unter `SetScrollSizes`.  
  
 `sizeTotal`  
 Gibt die aktuelle Gesamtgröße der Bildlaufansicht einen im Geräteeinheiten zurück.  
  
 `sizePage`  
 Gibt die aktuelle horizontale und vertikale Beträge für einen Bildlauf in jede Richtung als Antwort auf eine Maus eine Bildlaufleiste klicken Sie auf zurück. Die **Cx** Member enthält, die horizontale Größe. Die **cy** Member enthält, die vertikale Größe.  
  
 `sizeLine`  
 Gibt die aktuelle horizontale und vertikale Beträge für einen Bildlauf in jede Richtung als Antwort auf eine Maus in einen Bildlaufpfeil klicken Sie auf zurück. Die **Cx** Member enthält, die horizontale Größe. Die **cy** Member enthält, die vertikale Größe.  
  
### <a name="remarks"></a>Hinweise  
 Größen sind im Geräteeinheiten. Diese Memberfunktion wird selten aufgerufen.  
  
##  <a name="getscrollposition"></a>  CScrollView::GetScrollPosition  
 Rufen Sie `GetScrollPosition` Wenn Sie die aktuelle horizontalen und vertikalen Position der Bildlaufleiste Felder in die Bildlaufleisten benötigen.  
  
```  
CPoint GetScrollPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die horizontalen und vertikalen Position (in logischen Einheiten) der Bildlauffelder als eine `CPoint` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Koordinatenpaar entspricht der Speicherort des Dokuments, der die linke obere Ecke der Sicht Bildlauf ausgeführt wurde.  
  
 `GetScrollPosition` Gibt Werte in logischen Einheiten zurück. Verwenden Sie gegebenenfalls Geräteeinheiten `GetDeviceScrollPosition` stattdessen.  
  
##  <a name="gettotalsize"></a>  CScrollView::GetTotalSize  
 Rufen Sie `GetTotalSize` zum Abrufen der aktuellen horizontalen und vertikalen Größen der Bildlaufleiste angezeigt.  
  
```  
CSize GetTotalSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Gesamtgröße der Bildlaufansicht einen in logischen Einheiten. Die horizontale Größe wird in der **Cx** Mitglied der `CSize` Rückgabewert. Die vertikale Größe wird in der **cy** Member.  
  
##  <a name="resizeparenttofit"></a>  CScrollView::ResizeParentToFit  
 Rufen Sie `ResizeParentToFit` , lassen die Größe der Ansicht bestimmen die Größe des zugehörigen Rahmenfenster.  
  
```  
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bShrinkOnly*  
 Die Art der Größe ausführen. Der Standardwert **"true"**, verkleinert das Rahmenfenster, falls zutreffend. Bildlaufleisten werden weiterhin für große Sichten oder kleinen Rahmenfenster angezeigt. Der Wert **"false"** bewirkt, dass die Sicht, ändern Sie die Größe des Rahmenfensters genau. Dies kann etwas gefährlich sein, da das Rahmenfenster zu groß für die Frame-Fensters von multiple Document Interface (MDI) oder den Bildschirm einpassen abgerufen werden konnte.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist nur für Ansichten im Rahmen des untergeordneten MDI-Fenstern empfohlen. Verwendung `ResizeParentToFit` in der `OnInitialUpdate` Handlerfunktion von Ihr abgeleiteten `CScrollView` Klasse. Ein Beispiel für diese Memberfunktion auf, finden Sie unter [CScrollView::SetScrollSizes](#setscrollsizes).  
  
 `ResizeParentToFit` wird davon ausgegangen, dass die Größe des Ansichtsfensters festgelegt wurde. Wenn die Fenstergröße Ansicht nicht beim festgelegt wurde `ResizeParentToFit` wird aufgerufen, erhalten Sie eine Assertion. Um sicherzustellen, dass dies nicht geschieht, stellen Sie vor dem Aufruf den folgenden Aufruf `ResizeParentToFit`:  
  
 [!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="scrolltoposition"></a>  CScrollView::ScrollToPosition  
 Rufen Sie `ScrollToPosition` , führen Sie einen Bildlauf zu einem bestimmten Zeitpunkt in der Ansicht.  
  
```  
void ScrollToPosition(POINT pt);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Der Punkt, in logischen Einheiten befindet, zu scrollen. Die **x** angehören muss ein positiver Wert (größer als oder gleich 0 (null) bis zu der Gesamtgröße der Ansicht). Dasselbe gilt für die **y** Element wird vom Zuordnungsmodus `MM_TEXT`. Die **y** angehört, die bei der Zuordnung der Modi außer negative `MM_TEXT`.  
  
### <a name="remarks"></a>Hinweise  
 Die Ansicht wird Bildlauf durchgeführt werden, damit dieser Punkt auf der linken oberen Ecke des Fensters ist. Diese Memberfunktion darf nicht aufgerufen werden, wenn die Ansicht skaliert wird.  
  
##  <a name="setscaletofitsize"></a>  CScrollView::SetScaleToFitSize  
 Rufen Sie `SetScaleToFitSize` sollen die Viewportgröße auf die aktuelle Fenstergröße automatisch zu skalieren.  
  
```  
void SetScaleToFitSize(SIZE sizeTotal);
```  
  
### <a name="parameters"></a>Parameter  
 `sizeTotal`  
 Die horizontalen und vertikalen Größen für die Ansicht wird skaliert werden. Das Scroll-Ansicht Größe wird in logischen Einheiten gemessen. Die horizontale Größe ist Bestandteil der **Cx** Member. Die vertikale Größe ist Bestandteil der **cy** Member. Beide **Cx** und **cy** muss größer als oder gleich 0 sein.  
  
### <a name="remarks"></a>Hinweise  
 Mit Bildlaufleisten angezeigt werden kann nur ein Teil der logischen Ansicht jederzeit sichtbar. Aber mithilfe der Funktion für die Skalierung auf anpassen, die Sicht hat keine Bildlaufleisten und die logische Sicht gestreckt oder verkleinert werden, genau Clientbereich des Fensters angepasst wird. Beim Ändern der Größe des Fensters, zeichnet die Ansicht seine Daten an einen neuen Skalierung basierend auf der Größe des Fensters.  
  
 Sie müssen in der Regel setzen Sie den Aufruf von `SetScaleToFitSize` in Ihre Überschreibung der Ansicht `OnInitialUpdate` Memberfunktion. Wenn Sie nicht wünschen, automatische Skalierung, rufen Sie die `SetScrollSizes` Memberfunktion stattdessen.  
  
 `SetScaleToFitSize` kann verwendet werden, um einen Vorgang "Zoom anpassen" implementieren. Verwendung `SetScrollSizes` zum Durchführen eines Bildlaufs erneut zu initialisieren.  
  
 `SetScaleToFitSize` wird davon ausgegangen, dass die Größe des Ansichtsfensters festgelegt wurde. Wenn die Fenstergröße Ansicht nicht beim festgelegt wurde `SetScaleToFitSize` wird aufgerufen, erhalten Sie eine Assertion. Um sicherzustellen, dass dies nicht geschieht, stellen Sie vor dem Aufruf den folgenden Aufruf `SetScaleToFitSize`:  
  
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
 `nMapMode`  
 Der Zuordnungsmodus für diese Sicht festgelegt. Mögliche Werte:  
  
|Zuordnungsmodus|Logische Einheit|Positive y-Achse Extends...|  
|------------------|------------------|---------------------------------|  
|`MM_TEXT`|1 pixel|Nach unten|  
|`MM_HIMETRIC`|0,01 mm|Nach oben|  
|`MM_TWIPS`|1/1440 in|Nach oben|  
|`MM_HIENGLISH`|0,001 in|Nach oben|  
|`MM_LOMETRIC`|0,1 mm|Nach oben|  
|`MM_LOENGLISH`|0,01 in|Nach oben|  
  
 Diese Modi werden von Windows definiert. Zwei standardmäßige Zuordnungsmodi `MM_ISOTROPIC` und `MM_ANISOTROPIC`, werden nicht zum `CScrollView`. Die-Klassenbibliothek stellt die `SetScaleToFitSize` Memberfunktion für die Skalierung der Ansicht, um die Fenstergröße. Spalte 3 in der obigen Tabelle beschreibt die-Koordinate Ausrichtung.  
  
 `sizeTotal`  
 Die Gesamtgröße der Bildlaufleiste angezeigt. Die **Cx** Member enthält den horizontalen Umfang. Die **cy** Member enthält den vertikalen Wertebereich. Größen sind in logischen Einheiten. Beide **Cx** und **cy** muss größer als oder gleich 0 sein.  
  
 `sizePage`  
 Die Beträge der horizontalen und vertikalen Bildlauf in jede Richtung als Antwort auf eine Maus klicken Sie auf einer Bildlaufleiste. Die **Cx** Member enthält, die horizontale Größe. Die **cy** Member enthält, die vertikale Größe.  
  
 `sizeLine`  
 Die Beträge der horizontalen und vertikalen Bildlauf in jede Richtung als Antwort auf eine Maus klicken Sie in einen Bildlaufpfeil. Die **Cx** Member enthält, die horizontale Größe. Die **cy** Member enthält, die vertikale Größe.  
  
### <a name="remarks"></a>Hinweise  
 In der Außerkraftsetzung von Aufrufen der `OnUpdate` Memberfunktion, Durchführen eines Bildlaufs Merkmale anzupassen, oder wenn Sie z. B. das Dokument anfänglich angezeigt wird, wenn sich die Größe ändert.  
  
 Sie werden in der Regel Informationen zur Datenbankgröße aus der Ansicht zugeordnete Dokument abrufen, durch den Aufruf einer Memberfunktion Dokument, das möglicherweise aufgerufen `GetMyDocSize`, den Sie mit der abgeleiteten Dokumentklasse angeben. Der folgende Code zeigt diesen Ansatz:  
  
 [!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]  
  
 Alternativ müssen Sie möglicherweise gelegentlich eine feste Größe, wie im folgenden Code festlegen:  
  
 [!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]  
  
 Müssen Sie den Zuordnungsmodus auf keines der Windows-Zuordnungsmodi außer festlegen `MM_ISOTROPIC` oder `MM_ANISOTROPIC`. Wenn Sie eine nicht eingeschränkte Zuordnungsmodus verwenden möchten, rufen Sie die `SetScaleToFitSize` Memberfunktion anstelle der `SetScrollSizes`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DIBLOOK](../../visual-cpp-samples.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CSplitterWnd-Klasse](../../mfc/reference/csplitterwnd-class.md)
