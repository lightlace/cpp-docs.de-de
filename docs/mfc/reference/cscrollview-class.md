---
title: CScrollView-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CScrollView
dev_langs:
- C++
helpviewer_keywords:
- CScrollView class
- views, scrolling
- scrolling views
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
caps.latest.revision: 24
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
ms.openlocfilehash: 0dc937a9559306ff527779c45af9fdb62cf602df
ms.lasthandoff: 02/24/2017

---
# <a name="cscrollview-class"></a>CScrollView-Klasse
Ein [CView](../../mfc/reference/cview-class.md) mit Bildlauffunktionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CScrollView : public CView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CScrollView::CScrollView](#cscrollview)|Erstellt ein `CScrollView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CScrollView::CheckScrollBars](#checkscrollbars)|Gibt an, ob die Bildlaufansicht horizontale und vertikale Schiebeleisten besitzt.|  
|[CScrollView::FillOutsideRect](#filloutsiderect)|Füllt den Bereich einer Ansicht außerhalb der Bildlaufleiste.|  
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Ruft die aktuelle Bildlaufposition in Geräteeinheiten ab.|  
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Ruft den aktuellen Zuordnungsmodus, die Gesamtgröße und die Zeilen- und Größen der bildlauffähige Ansicht ab. In Geräteeinheiten sind.|  
|[CScrollView::GetScrollPosition](#getscrollposition)|Ruft die aktuelle Bildlaufposition in logischen Einheiten ab.|  
|[CScrollView::GetTotalSize](#gettotalsize)|Ruft die Gesamtgröße der Bildlaufansicht in logischen Einheiten ab.|  
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|Bewirkt, dass die Größe der Sicht festgelegt werden, die Größe des Rahmens.|  
|[CScrollView::ScrollToPosition](#scrolltoposition)|Führt einen Bildlauf die Ansicht zu einem bestimmten Zeitpunkt, die in logischen Einheiten angegeben.|  
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|Scale-Anpassung Modus Bildlaufansicht füllt.|  
|[CScrollView::SetScrollSizes](#setscrollsizes)|Der Bildlaufansicht Zuordnungsmodus, Gesamtgröße und horizontalen und vertikalen Bildlauf Mengen festgelegt.|  
  
## <a name="remarks"></a>Hinweise  
 Können Sie die Standard-Bildlauf selbst in jeder abgeleiteten Klasse behandeln `CView` durch Überschreiben der Nachricht zugeordnete [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) Memberfunktionen. Aber `CScrollView` fügt die folgenden Funktionen, um seine `CView` Funktionen:  
  
-   Er verwaltet Fenster-und Viewport und Mapping-Modi.  
  
-   Es wird automatisch als Antwort auf Bildlaufleisten-Nachrichten.  
  
-   Es wird automatisch als Antwort auf Nachrichten von der Tastatur oder Maus ohne Bildlauf das Rad der IntelliMouse.  
  
 Automatisch als Antwort auf Nachrichten über die Tastatur einen Bildlauf durchführen, fügen Sie eine WM_KEYDOWN-Meldung und Testen für VK_DOWN, VK_PREV und Aufruf [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597).  
  
 Sie können behandeln, Mausrad Bildlauf selbst durch Überschreiben der Nachricht zugeordnet [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) und [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) Memberfunktionen. Wie für `CScrollView`, diese Memberfunktionen unterstützen das empfohlene Verhalten für [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617), die Rad-Drehung-Nachricht.  
  
 Leiten Sie zur Nutzung des automatischen Bildlaufs aus die Ansichtsklasse `CScrollView` anstelle von `CView`. Erstellung der Ansicht wird zuerst, wenn Sie die Größe der bildlauffähige Ansicht basierend auf der Größe des Dokuments Aufruf berechnen möchten die `SetScrollSizes` der Überschreibung der Memberfunktion [CView:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) oder [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate). (Sie müssen Ihren eigenen Code zum Abfragen der Größe des Dokuments schreiben. Ein Beispiel finden Sie unter der [Scribble-Beispiel](../../visual-cpp-samples.md).)  
  
 Der Aufruf der `SetScrollSizes` Member-Funktion legt Zuordnungsmodus die Ansicht, die insgesamt Dimensionen der Bildlaufansicht und den Beträgen horizontal und vertikal scrollen. Alle Größen sind in logischen Einheiten. Die logische Größe der Ansicht wird in der Regel berechnet anhand der Daten, die im Dokument gespeichert, aber in einigen Fällen möchten Sie möglicherweise eine feste Größe angeben. Beispiele für beide Ansätze, finden Sie unter [CScrollView::SetScrollSizes](#setscrollsizes).  
  
 Sie geben die Beträge in logischen Einheiten horizontal und vertikal scrollen. Klickt der Benutzer Scroll-Leiste Welle außerhalb das Bildlauffeld standardmäßig `CScrollView` führt einen Bildlauf durch eine "Seite". Wenn der Benutzer auf einen Bildlaufpfeil an den Enden einer Bildlaufleiste klickt `CScrollView` führt einen Bildlauf durch eine "Linie". Standardmäßig ist eine Seite 1/10 der Gesamtgröße der Ansicht. eine Zeile ist 1/10 der Seitengröße. Überschreiben Sie diese Standardwerte durch Übergeben der benutzerdefinierte Größen in der `SetScrollSizes` Member-Funktion. Sie können z. B. die horizontale Größe auf einen Bruchteil der Breite des der Gesamtgröße und die vertikale Größe, der die Höhe einer Zeile in der aktuellen Schriftart festlegen.  
  
 Anstelle von Bildlauf `CScrollView` kann automatisch die Ansicht, um die aktuelle Fenstergröße skaliert werden. In diesem Modus kann die Ansicht besitzt keine Bildlaufleisten und die logische Ansicht gestreckt oder verkleinert, damit genau Clientbereich des Fensters entspricht. Rufen Sie zum Verwenden dieser Funktion Scale-Anpassung [CScrollView::SetScaleToFitSize](#setscaletofitsize). (Rufen Sie entweder `SetScaleToFitSize` oder `SetScrollSizes`, aber nicht beide.)  
  
 Vor der `OnDraw` der abgeleiteten Ansichtsklasse-Memberfunktion aufgerufen wird, `CScrollView` passt den Ursprung des Ausschnitts für die `CPaintDC` Gerätekontext Objekt, das an `OnDraw`.  
  
 Anpassen der Ursprung des Ausschnitts bei fortlaufenden `CScrollView` überschreibt [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc). Diese Anpassung wird automatisch für die `CPaintDC` Gerätekontext, `CScrollView` übergibt an `OnDraw`, allerdings müssen Aufrufen **CScrollView::OnPrepareDC** selbst für alle anderen Gerätekontexte Sie verwenden, z. B. eine `CClientDC`. Sie können außer Kraft setzen **CScrollView::OnPrepareDC** zum Festlegen der Stift, Hintergrundfarbe und andere Zeichnungsattribute rufen Sie die Basisklasse für Skalierung.  
  
 Bildlaufleisten können an drei Orten relativ zu einer Ansicht angezeigt werden, wie in den folgenden Fällen angezeigt:  
  
-   Standard Fensterstil Bildlaufleisten können festgelegt werden, für die Ansicht mit den **WS_HSCROLL** und **WS_VSCROLL**[Fensterstile](../../mfc/reference/window-styles.md).  
  
-   Bildlaufleisten-Steuerelemente können auch hinzugefügt werden, auf den Frame mit der Ansicht, in dem Fall das Framework leitet `WM_HSCROLL` und `WM_VSCROLL` Nachrichten vom Rahmenfenster auf die derzeit aktive Ansicht.  
  
-   Das Framework auch leitet Nachrichten von Blättern eine `CSplitterWnd` Splitter-Steuerelement in den derzeit aktiven Splitter-Bereich (eine Sicht). Wenn in platziert eine [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) mit freigegebenen Bildlaufleisten angezeigt werden, eine `CScrollView` -Objekt verwendet die freigegebenen Dateien, anstatt eine eigene zu erstellen.  
  
 Weitere Informationen zur Verwendung von `CScrollView`, finden Sie unter [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md) und [abgeleiteten Ansicht Klassen in MFC verfügbare](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CScrollView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecheckscrollbarsa--cscrollviewcheckscrollbars"></a><a name="checkscrollbars"></a>CScrollView::CheckScrollBars  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Bildlaufansicht horizontale und vertikale Balken enthält.  
  
```  
void CheckScrollBars(
    BOOL& bHasHorzBar,  
    BOOL& bHasVertBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *bHasHorzBar*  
 Gibt an, dass die Anwendung eine horizontale Bildlaufleiste hat.  
  
 *bHasVertBar*  
 Gibt an, dass die Anwendung eine vertikale Bildlaufleiste hat.  
  
##  <a name="a-namecscrollviewa--cscrollviewcscrollview"></a><a name="cscrollview"></a>CScrollView::CScrollView  
 Erstellt ein `CScrollView`-Objekt.  
  
```  
CScrollView();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen entweder Aufrufen `SetScrollSizes` oder `SetScaleToFitSize` vor der Bildlaufleiste Sicht kann verwendet werden.  
  
##  <a name="a-namefilloutsiderecta--cscrollviewfilloutsiderect"></a><a name="filloutsiderect"></a>CScrollView::FillOutsideRect  
 Rufen Sie `FillOutsideRect` um den Bereich der Ansicht zu füllen, die außerhalb des Bereichs der Bildlaufleiste angezeigt wird.  
  
```  
void FillOutsideRect(
    CDC* pDC,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Der Gerätekontext, ist das Füllen durchgeführt werden.  
  
 `pBrush`  
 Pinsel, mit dem der Bereich ausgefüllt werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `FillOutsideRect` in Ihrer Bildlaufansicht `OnEraseBkgnd` Handler-Funktion, um zu verhindern, dass eine übermäßige Hintergrund neu aufgebaut.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#164;](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]  
  
##  <a name="a-namegetdevicescrollpositiona--cscrollviewgetdevicescrollposition"></a><a name="getdevicescrollposition"></a>CScrollView::GetDeviceScrollPosition  
 Rufen Sie `GetDeviceScrollPosition` Wenn Sie die aktuelle horizontalen und vertikalen Position der Bildlaufleiste Felder in den Bildlaufleisten benötigen.  
  
```  
CPoint GetDeviceScrollPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die horizontalen und vertikalen Position (in Geräteeinheiten) der Bildlaufleiste Felder als ein `CPoint` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Koordinatenpaar entspricht der Speicherort des Dokuments, der die linke obere Ecke der Sicht Bildlauf ausgeführt wurde. Dies ist hilfreich für den Ausgleich der Mausgerät Positionen, Bildlaufansicht Gerät Positionen.  
  
 `GetDeviceScrollPosition`Gibt Werte in Geräteeinheiten zurück. Verwenden Sie ggf. eine logische Einheit `GetScrollPosition` stattdessen.  
  
##  <a name="a-namegetdevicescrollsizesa--cscrollviewgetdevicescrollsizes"></a><a name="getdevicescrollsizes"></a>CScrollView::GetDeviceScrollSizes  
 `GetDeviceScrollSizes`Ruft den aktuellen Zuordnungsmodus, die Gesamtgröße und die Zeilen- und Größen der bildlauffähige Ansicht ab.  
  
```  
void GetDeviceScrollSizes(
    int& nMapMode,  
    SIZE& sizeTotal,  
    SIZE& sizePage,  
    SIZE& sizeLine) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nMapMode`  
 Gibt den aktuellen Zuordnungsmodus für diese Ansicht zurück. Eine Liste der möglichen Werte finden Sie unter `SetScrollSizes`.  
  
 `sizeTotal`  
 Gibt die aktuelle Gesamtgröße der Bildlaufansicht Gerät Einheiten zurück.  
  
 `sizePage`  
 Gibt die aktuelle horizontale und vertikale Beträge für einen Bildlauf in jede Richtung als Antwort auf eine Maus in einer Bildlaufleiste klicken Sie auf zurück. Die **Cx** Member enthält die horizontale. Die **cy** Member enthält, die vertikale Größe.  
  
 `sizeLine`  
 Gibt die aktuelle horizontale und vertikale Beträge für einen Bildlauf in jede Richtung als Antwort auf eine Maus in einen Bildlaufpfeil klicken. Die **Cx** Member enthält die horizontale. Die **cy** Member enthält, die vertikale Größe.  
  
### <a name="remarks"></a>Hinweise  
 In Geräteeinheiten sind. Diese Member-Funktion wird nur selten aufgerufen.  
  
##  <a name="a-namegetscrollpositiona--cscrollviewgetscrollposition"></a><a name="getscrollposition"></a>CScrollView::GetScrollPosition  
 Rufen Sie `GetScrollPosition` Wenn Sie die aktuelle horizontalen und vertikalen Position der Bildlaufleiste Felder in den Bildlaufleisten benötigen.  
  
```  
CPoint GetScrollPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die horizontalen und vertikalen Position (in logischen Einheiten) der Bildlaufleiste Felder als ein `CPoint` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Koordinatenpaar entspricht der Speicherort des Dokuments, der die linke obere Ecke der Sicht Bildlauf ausgeführt wurde.  
  
 `GetScrollPosition`Gibt Werte in logischen Einheiten zurück. Verwenden Sie ggf. Geräteeinheiten `GetDeviceScrollPosition` stattdessen.  
  
##  <a name="a-namegettotalsizea--cscrollviewgettotalsize"></a><a name="gettotalsize"></a>CScrollView::GetTotalSize  
 Rufen Sie `GetTotalSize` zum Abrufen der aktuellen horizontalen und vertikalen Größen der Bildlaufansicht.  
  
```  
CSize GetTotalSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Gesamtgröße der Bildlaufansicht in logischen Einheiten. Die horizontale Größe wird in der **Cx** Mitglied der `CSize` Wert zurückgeben. Die vertikale Größe wird in der **cy** Member.  
  
##  <a name="a-nameresizeparenttofita--cscrollviewresizeparenttofit"></a><a name="resizeparenttofit"></a>CScrollView::ResizeParentToFit  
 Rufen Sie `ResizeParentToFit` auf die Größe der Ansicht der Größe ihres Rahmenfensters diktieren lassen.  
  
```  
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bShrinkOnly*  
 Die Art der Größe ausführen. Der Standardwert **TRUE**, das Rahmenfenster verkleinert, falls zutreffend. Bildlaufleisten werden weiterhin Ansicht für die großen oder kleinen Rahmenfenster angezeigt. Der Wert **FALSE** bewirkt, dass die Ansicht immer genau das Rahmenfenster Größe ändern. Dies kann etwas gefährlich sein, da das Rahmenfenster zu groß, um in der Frame-Fensters von multiple Document Interface (MDI) oder den Bildschirm passt abgerufen werden konnte.  
  
### <a name="remarks"></a>Hinweise  
 Dies empfiehlt sich nur für Ansichten im Rahmen des untergeordneten MDI-Fenster. Verwendung `ResizeParentToFit` in der `OnInitialUpdate` Handlerfunktion von Ihr abgeleiteten `CScrollView` Klasse. Ein Beispiel für diese Memberfunktion, finden Sie unter [CScrollView::SetScrollSizes](#setscrollsizes).  
  
 `ResizeParentToFit`wird davon ausgegangen, dass die Größe des Ansichtsfensters festgelegt wurde. Wenn die Fenstergröße Ansicht nicht beim festgelegt wurde `ResizeParentToFit` wird aufgerufen, erhalten Sie eine Assertion. Um sicherzustellen, dass dies nicht geschieht, führen Sie den folgenden Aufruf vor dem Aufruf von `ResizeParentToFit`:  
  
 [!code-cpp[NVC_MFCDocView&#165;](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="a-namescrolltopositiona--cscrollviewscrolltoposition"></a><a name="scrolltoposition"></a>CScrollView::ScrollToPosition  
 Rufen Sie `ScrollToPosition` Bildlauf zu einem bestimmten Zeitpunkt in der Ansicht.  
  
```  
void ScrollToPosition(POINT pt);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Der Punkt, in logischen Einheiten zu scrollen. Die **x** -Element muss ein positiver Wert (größer als oder gleich 0 ist, bis die Gesamtgröße der Ansicht) sein. Das gleiche gilt für die **y** Element, wenn der Zuordnungsmodus ist `MM_TEXT`. Die **y** Element ist in der mapping-Modi als negativ `MM_TEXT`.  
  
### <a name="remarks"></a>Hinweise  
 Die Ansicht wird ein Bildlauf durchgeführt werden, sodass dieser Punkt an der oberen linken Ecke des Fensters ist. Diese Memberfunktion muss nicht aufgerufen werden, wenn die Ansicht skaliert wird.  
  
##  <a name="a-namesetscaletofitsizea--cscrollviewsetscaletofitsize"></a><a name="setscaletofitsize"></a>CScrollView::SetScaleToFitSize  
 Rufen Sie `SetScaleToFitSize` der Viewport-Größe auf die aktuelle Fenstergröße automatisch skalieren möchten.  
  
```  
void SetScaleToFitSize(SIZE sizeTotal);
```  
  
### <a name="parameters"></a>Parameter  
 `sizeTotal`  
 Die horizontalen und vertikalen Größen für die Ansicht skaliert wird. Die Bildlaufansicht Größe wird in logischen Einheiten gemessen. Die horizontale Größe ist Bestandteil der **Cx** Member. Die vertikale Größe ist Bestandteil der **cy** Member. Beide **Cx** und **cy** muss größer als oder gleich 0 sein.  
  
### <a name="remarks"></a>Hinweise  
 Bei Bildlaufleisten angezeigt werden kann nur ein Teil der logischen Ansicht jederzeit sichtbar sein. Mit der Skala-Anpassung-Funktion, die Ansicht besitzt keine Bildlaufleisten und die logische Ansicht gestreckt oder verkleinert, damit genau Clientbereich des Fensters entspricht. Beim Ändern der Fenstergröße, zeichnet die Ansicht die Daten an einer neuen Skalierung basierend auf der Größe des Fensters.  
  
 Platzieren Sie in der Regel den Aufruf von `SetScaleToFitSize` in der Überschreibung der Sicht `OnInitialUpdate` Member-Funktion. Wenn Sie nicht wünschen, automatische Skalierung, rufen Sie die `SetScrollSizes` Memberfunktion stattdessen.  
  
 `SetScaleToFitSize`kann verwendet werden, um einen Vorgang "Zoom anpassen" implementieren. Verwendung `SetScrollSizes` Bildlauf erneut initialisieren.  
  
 `SetScaleToFitSize`wird davon ausgegangen, dass die Größe des Ansichtsfensters festgelegt wurde. Wenn die Fenstergröße Ansicht nicht beim festgelegt wurde `SetScaleToFitSize` wird aufgerufen, erhalten Sie eine Assertion. Um sicherzustellen, dass dies nicht geschieht, führen Sie den folgenden Aufruf vor dem Aufruf von `SetScaleToFitSize`:  
  
 [!code-cpp[NVC_MFCDocView&#165;](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="a-namesetscrollsizesa--cscrollviewsetscrollsizes"></a><a name="setscrollsizes"></a>CScrollView::SetScrollSizes  
 Rufen Sie `SetScrollSizes` Wenn die Ansicht ist, aktualisiert werden sollen.  
  
```  
void SetScrollSizes(
    int nMapMode,  
    SIZE sizeTotal,  
    const SIZE& sizePage = sizeDefault,  
    const SIZE& sizeLine = sizeDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `nMapMode`  
 Die eines Zuordnungsmodus für diese Ansicht. Mögliche Werte:  
  
|Zuordnungsmodus|Logische Einheit|Positiven y-Achse erweitert...|  
|------------------|------------------|---------------------------------|  
|`MM_TEXT`|1-pixel|Nach unten|  
|`MM_HIMETRIC`|0,01 mm|Nach oben|  
|`MM_TWIPS`|1/1440 in|Nach oben|  
|`MM_HIENGLISH`|0,001 in|Nach oben|  
|`MM_LOMETRIC`|0,1 mm|Nach oben|  
|`MM_LOENGLISH`|0,01 Zoll|Nach oben|  
  
 Diese Modi werden von Windows definiert. Zwei standard-Mapping-Modi, `MM_ISOTROPIC` und `MM_ANISOTROPIC`, werden nicht zum `CScrollView`. Stellt die Klassenbibliothek die `SetScaleToFitSize` Memberfunktion für die Skalierung der Ansicht, um die Größe des Fensters. Spalte&3; in der obigen Tabelle beschreibt die-Koordinate Ausrichtung.  
  
 `sizeTotal`  
 Die Gesamtgröße der Bildlaufansicht. Die **Cx** Element enthält den horizontalen Umfang. Die **cy** Element enthält den vertikalen Wertebereich. Größen sind in logischen Einheiten. Beide **Cx** und **cy** muss größer als oder gleich 0 sein.  
  
 `sizePage`  
 Die horizontalen und vertikalen Beträge in jede Richtung als Antwort auf eine Maus einen Bildlauf durchführen, klicken Sie in einer Bildlaufleiste. Die **Cx** Member enthält die horizontale. Die **cy** Member enthält, die vertikale Größe.  
  
 `sizeLine`  
 Die horizontalen und vertikalen Beträge in jede Richtung als Antwort auf eine Maus einen Bildlauf durchführen, klicken Sie in einen Bildlaufpfeil. Die **Cx** Member enthält die horizontale. Die **cy** Member enthält, die vertikale Größe.  
  
### <a name="remarks"></a>Hinweise  
 In der Überschreibung der Aufrufen der `OnUpdate` Memberfunktion Bildlauf Eigenschaften anpassen, wenn z. B. das Dokument anfänglich angezeigt wird oder wenn Größe ändert.  
  
 In der Regel erhalten Sie Informationen aus der Ansicht zugeordnete Dokument, ein Dokument Memberfunktion, vielleicht aufgerufen `GetMyDocSize`, den Sie mit der abgeleiteten Dokumentklasse angeben. Der folgende Code zeigt dies:  
  
 [!code-cpp[NVC_MFCDocView&#166;](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]  
  
 Alternativ müssen Sie manchmal eine feste Größe, wie im folgenden Code festlegen:  
  
 [!code-cpp[NVC_MFCDocView&#167;](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]  
  
 Legen Sie den Zuordnungsmodus auf keines der Windows-Zuordnungsmodi außer `MM_ISOTROPIC` oder `MM_ANISOTROPIC`. Wenn Sie eine uneingeschränkte Zuordnungsmodus verwenden möchten, rufen Sie die `SetScaleToFitSize` Memberfunktion anstelle der `SetScrollSizes`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#168;](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#169;](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DIBLOOK](../../visual-cpp-samples.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [CSplitterWnd-Klasse](../../mfc/reference/csplitterwnd-class.md)

