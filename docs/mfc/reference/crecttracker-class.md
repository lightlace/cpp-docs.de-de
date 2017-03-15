---
title: CRectTracker-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRectTracker
dev_langs:
- C++
helpviewer_keywords:
- displaying items
- CRectTracker class
- resizing items
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
caps.latest.revision: 23
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
ms.openlocfilehash: 444eab5969339cf2a3d5797807eae3dcad32a694
ms.lasthandoff: 02/24/2017

---
# <a name="crecttracker-class"></a>CRectTracker-Klasse
Ermöglicht es einem Element angezeigt, verschoben, und in verschiedenen Größen dargestellt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRectTracker  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRectTracker::CRectTracker](#crecttracker)|Erstellt ein `CRectTracker`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRectTracker::AdjustRect](#adjustrect)|Wird aufgerufen, wenn die Größe des Rechtecks geändert wird.|  
|[CRectTracker::Draw](#draw)|Rendert das Rechteck.|  
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|Wird aufgerufen, wenn der Rahmen zeichnen ein `CRectTracker` Objekt.|  
|[CRectTracker::GetHandleMask](#gethandlemask)|Aufgerufen, um die Maske erhalten eine `CRectTracker`Vergrößern des Elements.|  
|[CRectTracker::GetTrueRect](#gettruerect)|Breite und Höhe des Rechtecks, einschließlich der Ziehpunkte zurückgibt.|  
|[CRectTracker::HitTest](#hittest)|Gibt die aktuelle Position des Cursors im Zusammenhang mit der `CRectTracker` Objekt.|  
|[CRectTracker::NormalizeHit](#normalizehit)|Normalisiert einen Treffertest-Code.|  
|[CRectTracker::OnChangedRect](#onchangedrect)|Wird aufgerufen, wenn das Rechteck geändert oder verschoben wurde.|  
|[CRectTracker:: SetCursor](#setcursor)|Legt den Cursor je nach seiner Position über dem Rechteck.|  
|[CRectTracker::Track](#track)|Ermöglicht dem Benutzer das Rechteck zu ändern.|  
|[CRectTracker::TrackRubberBand](#trackrubberband)|Ermöglicht dem Benutzer "Gummiband" die Auswahl.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|Bestimmt die Größe der Ziehpunkte.|  
|[CRectTracker::m_nStyle](#m_nstyle)|Aktuelle Style(s) Tracker.|  
|[CRectTracker::m_rect](#m_rect)|Aktuelle Position des Rechtecks (in Pixel).|  
|[CRectTracker::m_sizeMin](#m_sizemin)|Bestimmt, minimale Rechteck Breite und Höhe.|  
  
## <a name="remarks"></a>Hinweise  
 `CRectTracker`eine Basisklasse keinen.  
  
 Obwohl die `CRectTracker` Klasse zur Interaktion mit OLE-Elemente mithilfe einer Benutzeroberfläche dem Benutzer ermöglichen, ihre Verwendung ist nicht auf OLE-fähige Anwendung beschränkt. Hiermit können an einer beliebigen Stelle dieser Benutzeroberfläche erforderlich ist.  
  
 `CRectTracker`Rahmen können sein oder gepunktete Linien. Das Element erhält einen schraffierten Rahmen oder überlagerten mit einer Schraffur Zustände des Elements an. Sie können acht Ziehpunkte auf außen oder innen platzieren Rahmen des Elements. (Eine Erläuterung der Ziehpunkte, finden Sie unter [GetHandleMask](#gethandlemask).) Schließlich eine `CRectTracker` können Sie die Ausrichtung eines Elements während der Größenänderung ändern.  
  
 Verwenden `CRectTracker`, erstellen Sie ein `CRectTracker` -Objekt und angeben, welche Zustände Anzeige initialisiert werden. Dann können Sie diese Schnittstelle, die Benutzer über den aktuellen Status des OLE-Elements zugeordnete ein visuelles Feedback der `CRectTracker` Objekt.  
  
 Weitere Informationen zur Verwendung von `CRectTracker`, finden Sie im Artikel [Rahmenstile](../../mfc/trackers.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CRectTracker`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="a-nameadjustrecta--crecttrackeradjustrect"></a><a name="adjustrect"></a>CRectTracker::AdjustRect  
 Vom Framework aufgerufen, das Rechteck Überwachung mithilfe eines Handles zum Ändern der Größe geändert wird.  
  
```  
virtual void AdjustRect(
    int nHandle,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `nHandle`  
 Der Index des Handles verwendet.  
  
 `lpRect`  
 Ein Zeiger auf die aktuelle Größe des Rechtecks. (Die Größe eines Rechtecks wird durch seine Höhe und Breite angegeben.)  
  
### <a name="remarks"></a>Hinweise  
 Das Standardverhalten dieser Funktion ermöglicht das Rechteck Ausrichtung so ändern Sie nur, wenn `Track` und `TrackRubberBand` mit invertieren zulässige aufgerufen werden.  
  
 Überschreiben Sie diese Funktion, um die Anpassung des Rechtecks Überwachung während eines Drag & Drop-Vorgangs zu steuern. Eine Methode besteht darin, passen Sie die angegebenen Koordinaten `lpRect` vor der Rückgabe.  
  
 Spezielle Funktionen, die von nicht direkt unterstützt werden `CRectTracker`, wie z. B.-Rasters oder-Seitenverhältnis beibehalten, kann durch das Überschreiben dieser Funktion implementiert werden.  
  
##  <a name="a-namecrecttrackera--crecttrackercrecttracker"></a><a name="crecttracker"></a>CRectTracker::CRectTracker  
 Erstellt und initialisiert ein `CRectTracker` Objekt.  
  
```  
CRectTracker();

 
CRectTracker(
    LPCRECT lpSrcRect,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `lpSrcRect`  
 Die Koordinaten des Rectangle-Objekts.  
  
 `nStyle`  
 Gibt das Format der `CRectTracker` Objekt. Die folgenden Formate werden unterstützt:  
  
- **CRectTracker::solidLine** verwenden eine durchgezogene Linie für den Rechteckrahmen.  
  
- **CRectTracker::dottedLine** verwenden eine gepunktete Linie für den Rechteckrahmen.  
  
- **CRectTracker::hatchedBorder** eine Schraffur für das Rechteckrahmen verwenden.  
  
- **CRectTracker::resizeInside** Steuerpunkte befinden sich innerhalb des Rechtecks.  
  
- **CRectTracker::resizeOutside** Steuerpunkte außerhalb des Rechtecks.  
  
- **CRectTracker::hatchInside** Hatched Muster deckt das gesamte Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkonstruktor initialisiert die `CRectTracker` Objekt mit den Werten aus `lpSrcRect` und andere Größen zur Systemstandards initialisiert. Wenn das Objekt, ohne Parameter erstellt wurde die `m_rect` und `m_nStyle` Datenmember sind nicht initialisiert.  
  
##  <a name="a-namedrawa--crecttrackerdraw"></a><a name="draw"></a>CRectTracker::Draw  
 Rufen Sie diese Funktion, um des Rechtecks äußeren Zeilen und inneren Bereich zu zeichnen.  
  
```  
void Draw(CDC* pDC) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Gerätekontext, auf dem gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Das Format der Tracker bestimmt, wie gezeichnet wird. Finden Sie im Konstruktor für `CRectTracker` für Weitere Informationen über die verfügbaren Formate.  
  
##  <a name="a-namedrawtrackerrecta--crecttrackerdrawtrackerrect"></a><a name="drawtrackerrect"></a>CRectTracker::DrawTrackerRect  
 Vom Framework aufgerufen, wenn die Position des Tracker geändert wurde zwar innerhalb der `Track` oder `TrackRubberBand` -Memberfunktion.  
  
```  
virtual void DrawTrackerRect(
    LPCRECT lpRect,  
    CWnd* pWndClipTo,  
    CDC* pDC,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Zeiger auf die `RECT` , die das zu zeichnende Rechteck enthält.  
  
 `pWndClipTo`  
 Ein Zeiger auf das Fenster, in das Rechteck verwendet.  
  
 `pDC`  
 Ein Zeiger auf den Gerätekontext, auf dem gezeichnet werden soll.  
  
 `pWnd`  
 Ein Zeiger auf das Fenster auf dem die Zeichnung ausgeführt wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung führt einen Aufruf von `CDC::DrawFocusRect`, die ein gepunktetes Rechteck gezeichnet.  
  
 Überschreiben Sie diese Funktion Informationen zu anderen Feedback während des nachverfolgungsvorgangs.  
  
##  <a name="a-namegethandlemaska--crecttrackergethandlemask"></a><a name="gethandlemask"></a>CRectTracker::GetHandleMask  
 Das Framework ruft diese Member-Funktion, um die Maske abzurufen, für die Ziehpunkte des Rechtecks.  
  
```  
virtual UINT GetHandleMask() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Maske eine `CRectTracker` Vergrößern des Elements.  
  
### <a name="remarks"></a>Hinweise  
 Die Ziehpunkte an den Seiten und Ecken des Rechtecks angezeigt und ermöglichen den Benutzer, die Form und Größe des Rechtecks zu steuern.  
  
 Ein Rechteck hat 8 Ziehpunkte nummeriert von 0 bis 7. Jede Ziehpunkt ist ein wenig in der Maske durch dargestellt. der Wert dieses Bits ist 2 ^ *n*, wobei *n* ist die Anzahl der Resize-Handle. Bits 0 bis 3 entsprechen die Ziehpunkte des Ecke verschieben links oben im Uhrzeigersinn ab. Bits 4 bis 7 auf der Seite entsprechen Steuerpunkte, die oben im Uhrzeigersinn verschieben. Die folgende Abbildung zeigt die Größe des Rechtecks behandelt und die entsprechenden Größe von Nummern und Werte:  
  
 ![Ändern der Größe Nummern](../../mfc/reference/media/vc35dp1.gif "vc35dp1")  
  
 Die standardmäßige Implementierung des **GetHandleMask** gibt die Maske der Bits zurück, sodass die Steuerpunkte werden angezeigt. Wenn es sich bei den einzelne Bit aktiviert ist, wird der entsprechende Ziehpunkt gezeichnet.  
  
 Überschreiben Sie diese Memberfunktion, um den angegebenen Ziehpunkte anzuzeigen oder auszublenden.  
  
##  <a name="a-namegettruerecta--crecttrackergettruerect"></a><a name="gettruerect"></a>CRectTracker::GetTrueRect  
 Rufen Sie diese Funktion zum Abrufen der Koordinaten des Rechtecks.  
  
```  
void GetTrueRect(LPRECT lpTrueRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpTrueRect`  
 Zeiger auf die `RECT` -Struktur, die das Gerät enthält-Koordinaten der `CRectTracker` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Dimensionen des Rechtecks umfassen die Höhe und Breite des Ziehpunkte, die sich auf den äußeren Rahmen befindet. Bei der Rückkehr, `lpTrueRect` ist immer einem normalisierten Rechtecks in logische Koordinaten.  
  
##  <a name="a-namehittesta--crecttrackerhittest"></a><a name="hittest"></a>CRectTracker::HitTest  
 Rufen Sie diese Funktion, um herauszufinden, gibt an, ob der Benutzer einen Ziehpunkt erfassten hat.  
  
```  
int HitTest(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Der Punkt in Gerätekoordinaten, um zu testen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der zurückgegebene Wert basiert auf den Aufzählungstyp **CRectTracker::TrackerHit** und kann einen der folgenden Werte haben:  
  
- **CRectTracker::hitNothing** –&1;  
  
- **CRectTracker::hitTopLeft** 0  
  
- **CRectTracker::hitTopRight** 1  
  
- **CRectTracker::hitBottomRight** 2  
  
- **CRectTracker::hitBottomLeft** 3  
  
- **CRectTracker::hitTop** 4  
  
- **CRectTracker::hitRight** 5  
  
- **CRectTracker::hitBottom** 6  
  
- **CRectTracker::hitLeft** 7  
  
- **CRectTracker::hitMiddle** 8  
  
##  <a name="a-namemnhandlesizea--crecttrackermnhandlesize"></a><a name="m_nhandlesize"></a>CRectTracker::m_nHandleSize  
 Die Größe in Pixel, der den `CRectTracker` vergrößern.  
  
```  
int m_nHandleSize;  
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert mit dem Standardwert für das System.  
  
##  <a name="a-namemrecta--crecttrackermrect"></a><a name="m_rect"></a>CRectTracker::m_rect  
 Die aktuelle Position des Rechtecks in Clientkoordinaten (in Pixel).  
  
```  
CRect m_rect;  
```  
  
##  <a name="a-namemsizemina--crecttrackermsizemin"></a><a name="m_sizemin"></a>CRectTracker::m_sizeMin  
 Die minimale Größe des Rechtecks.  
  
```  
CSize m_sizeMin;  
```  
  
### <a name="remarks"></a>Hinweise  
 Beide Standardwerte **Cx** und **cy**, aus der System-Standardwert für die Breite des Rahmens berechnet werden. Dieses Datenelement wird nur verwendet, die `AdjustRect` -Memberfunktion.  
  
##  <a name="a-namemnstylea--crecttrackermnstyle"></a><a name="m_nstyle"></a>CRectTracker::m_nStyle  
 Aktuelle Stil des Rechtecks.  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CRectTracker::CRectTracker](#crecttracker) für eine Liste der möglichen Formate.  
  
##  <a name="a-namenormalizehita--crecttrackernormalizehit"></a><a name="normalizehit"></a>CRectTracker::NormalizeHit  
 Rufen Sie diese Funktion, um ein potenziell invertierten Handle zu konvertieren.  
  
```  
int NormalizeHit(int nHandle) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nHandle`  
 Der Handle vom Benutzer ausgewählt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Handles normalisierte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `CRectTracker::Track` oder `CRectTracker::TrackRubberBand` heißt mit invertieren zulässig, es ist möglich, das Rechteck auf der x-Achse, y-Achse oder beides umgekehrt werden. In diesem Fall `HitTest` Handles, die in Bezug auf das Rechteck auch umgekehrt werden zurück. Grund hierfür ist für das Zeichnen des Cursors das Feedback von Bildschirmposition des Rechtecks nicht den Teil der Datenstruktur Rechteck abhängt, die geändert werden soll.  
  
##  <a name="a-nameonchangedrecta--crecttrackeronchangedrect"></a><a name="onchangedrect"></a>CRectTracker::OnChangedRect  
 Vom Framework aufgerufen, wenn das Rechteck Tracker während des Aufrufs geändert wurde `Track`.  
  
```  
virtual void OnChangedRect(const CRect& rectOld);
```  
  
### <a name="parameters"></a>Parameter  
 *rectOld*  
 Enthält die alten Gerätekoordinaten der `CRectTracker` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Zum Zeitpunkt dieser Funktion aufgerufen wird, Ihr Feedback mit gezeichneten `DrawTrackerRect` wurde entfernt. Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt.  
  
 Überschreiben Sie diese Funktion, wenn Sie möchten, um Aktionen auszuführen, nachdem die Größe des Rechtecks geändert wurde.  
  
##  <a name="a-namesetcursora--crecttrackersetcursor"></a><a name="setcursor"></a>CRectTracker:: SetCursor  
 Mit dieser Funktion können Sie die Cursorform zu ändern, während er über ist die `CRectTracker` Region des Objekts.  
  
```  
BOOL SetCursor(
    CWnd* pWnd,  
    UINT nHitTest) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster, das den Cursor enthält.  
  
 `nHitTest`  
 Ergebnisse der vorherigen Treffertests aus der `WM_SETCURSOR` Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, war das vorherige ermittelte über dem Rechteck Tracker; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion von innerhalb der Funktion des Fensters, die behandelt die `WM_SETCURSOR` Nachricht (in der Regel `OnSetCursor`).  
  
##  <a name="a-nametracka--crecttrackertrack"></a><a name="track"></a>CRectTracker::Track  
 Rufen Sie diese Funktion, um die Benutzeroberfläche zum Ändern der Größe des Rechtecks anzuzeigen.  
  
```  
BOOL Track(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = FALSE,  
    CWnd* pWndClipTo = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Das Window-Objekt, das das Rechteck enthält.  
  
 `point`  
 Gerätekoordinaten von der aktuellen Position relativ zum Clientbereich.  
  
 `bAllowInvert`  
 Wenn **TRUE**, das Rechteck werden kann, andernfalls auf der x-Achse oder y-Achse invertierten **FALSE**.  
  
 `pWndClipTo`  
 Das Fenster, dem Zeichenvorgänge, abgeschnitten wird. Wenn **NULL**, `pWnd` als das Clippingrechteck verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die ESC-Taste gedrückt wird, den Überwachungsvorgang wird angehalten, in Tracker gespeicherten Rechtecks nicht geändert wird und 0 zurückgegeben. Wenn die Änderung übernommen wird, durch Bewegen der Maus, und halten Sie die linke Maustaste gedrückt, die neue Position und/oder die Größe in den Tracker Rechteck aufgezeichnet wird und ungleich NULL wird zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird normalerweise aus aufgerufen, in der Funktion der Anwendung, die behandelt die `WM_LBUTTONDOWN` Nachricht (in der Regel `OnLButtonDown`).  
  
 Diese Funktion wird die Maus erfassen, bis der Benutzer die linke Maustaste loslässt, die ESC-Taste drückt oder rechte Maustaste drückt. Wenn der Benutzer den Mauszeiger bewegt, wird das Feedback durch Aufrufen von aktualisiert `DrawTrackerRect` und `OnChangedRect`.  
  
 Wenn `bAllowInvert` ist **TRUE**, das Überwachungsprofil Rechteck auf der x-Achse oder y-Achse umgekehrt werden kann.  
  
##  <a name="a-nametrackrubberbanda--crecttrackertrackrubberband"></a><a name="trackrubberband"></a>CRectTracker::TrackRubberBand  
 Mit dieser Funktion können Gummiband-Auswahl nicht.  
  
```  
BOOL TrackRubberBand(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Das Window-Objekt, das das Rechteck enthält.  
  
 `point`  
 Gerätekoordinaten von der aktuellen Position relativ zum Clientbereich.  
  
 `bAllowInvert`  
 Wenn **"TRUE"** das Rechteck werden kann, andernfalls auf der x-Achse oder y-Achse invertierten **FALSE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Maus hat und das Rechteck nicht leer ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Es wird normalerweise aus aufgerufen, in der Funktion der Anwendung, die behandelt die `WM_LBUTTONDOWN` Nachricht (in der Regel `OnLButtonDown`).  
  
 Diese Funktion wird die Maus erfassen, bis der Benutzer die linke Maustaste loslässt, die ESC-Taste drückt oder rechte Maustaste drückt. Wenn der Benutzer den Mauszeiger bewegt, wird das Feedback durch Aufrufen von aktualisiert `DrawTrackerRect` und `OnChangedRect`.  
  
 Überwachung erfolgt eine weiche Ränder Bereichstyp Auswahl aus dem Handle unten rechts. Wenn invertieren zulässig ist, vergrößert das Rechteck kann entweder oben und nach links oder nach unten und rechts ziehen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiels TRACKER](../../visual-cpp-samples.md)   
 [MFC-Beispiel DRAWCLI](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleResizeBar-Klasse](../../mfc/reference/coleresizebar-class.md)   
 [CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)

