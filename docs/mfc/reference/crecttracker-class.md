---
title: CRectTracker-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
dev_langs:
- C++
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b39561c19754d35fc08755d7c8cf49b07ec95995
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851407"
---
# <a name="crecttracker-class"></a>CRectTracker-Klasse
Ermöglicht es einem Element angezeigt werden, verschoben und in unterschiedlichen Größen dargestellt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRectTracker  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRectTracker::CRectTracker](#crecttracker)|Erstellt ein `CRectTracker`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRectTracker::AdjustRect](#adjustrect)|Aufgerufen, wenn die Größe des Rechtecks geändert wird.|  
|[CRectTracker::Draw](#draw)|Rendert das Rechteck.|  
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|Wird aufgerufen, wenn es sich bei der Rahmen gezeichnet eine `CRectTracker` Objekt.|  
|[CRectTracker::GetHandleMask](#gethandlemask)|Wird aufgerufen, um das Abrufen der Maske einer `CRectTracker` Handles zur Größenänderung des Elements.|  
|[CRectTracker::GetTrueRect](#gettruerect)|Gibt zurück, Breite und Höhe des Rechtecks, einschließlich des Handles zur Größenänderung.|  
|[CRectTracker::HitTest](#hittest)|Gibt die aktuelle Position des Cursors im Zusammenhang mit der `CRectTracker` Objekt.|  
|[CRectTracker::NormalizeHit](#normalizehit)|Normalisiert einen Treffertest-Code.|  
|[CRectTracker::OnChangedRect](#onchangedrect)|Wird aufgerufen, wenn das Rechteck geändert oder verschoben wurde.|  
|[CRectTracker:: SetCursor](#setcursor)|Legt den Cursor je nach Position seine über das Rechteck fest.|  
|[CRectTracker::Track](#track)|Ermöglicht dem Benutzer das Rechteck zu bearbeiten.|  
|[CRectTracker::TrackRubberBand](#trackrubberband)|Ermöglicht dem Benutzer "Gummiband" die Auswahl.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|Bestimmt die Größe des Handles zur Größenänderung.|  
|[CRectTracker::m_nStyle](#m_nstyle)|Aktuelle Style(s) Tracker.|  
|[CRectTracker::m_rect](#m_rect)|Aktuelle Position (in Pixel) des Rechtecks.|  
|[CRectTracker::m_sizeMin](#m_sizemin)|Bestimmt, minimale Rechteck Breite und Höhe.|  
  
## <a name="remarks"></a>Hinweise  
 `CRectTracker` eine Basisklasse keinen.  
  
 Obwohl die `CRectTracker` Klasse soll es den Benutzer, die OLE-Elementen interagieren mit einer grafischen Oberfläche ermöglicht, ihre Verwendung ist nicht auf OLE-fähigen Anwendungen beschränkt. Es kann verwendet werden an einer beliebigen Stelle eine solche Benutzeroberfläche erforderlich ist.  
  
 `CRectTracker` Rahmen können solid sein oder die gepunkteten Linien. Das Element möglich angegebenen schraffiert oder zusammen mit einer Schraffur an die unterschiedlichen Zustände des Elements. Sie können acht Ziehpunkte platzieren, auf der Außenseite oder den inneren Rahmen des Elements. (Eine Erläuterung der die Handles zur Größenänderung, finden Sie unter [GetHandleMask](#gethandlemask).) Zum Schluss eine `CRectTracker` können Sie die Ausrichtung eines Elements während der Größenänderung ändern.  
  
 Mit `CRectTracker`, erstellen Sie eine `CRectTracker` Objekt, und geben Sie die Anzeige, welche Status initialisiert werden. Anschließend können Sie diese Schnittstelle die Benutzer auf den aktuellen Status des zugeordneten OLE-Elements ein visuelles Feedback die `CRectTracker` Objekt.  
  
 Weitere Informationen zur Verwendung von `CRectTracker`, finden Sie im Artikel [Nachverfolgungsmodule](../../mfc/trackers.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CRectTracker`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="adjustrect"></a>  CRectTracker::AdjustRect  
 Vom Framework aufgerufen, wenn das Rechteck für die Überwachung unter Verwendung eines Handles Ändern der Größe geändert wird.  
  
```  
virtual void AdjustRect(
    int nHandle,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 *nHandle*  
 Der Index des Handles verwendet.  
  
 *lpRect*  
 Zeiger auf die aktuelle Größe des Rechtecks. (Die Größe eines Rechtecks wird durch seine Höhe und Breite angegeben.)  
  
### <a name="remarks"></a>Hinweise  
 Das Standardverhalten dieser Funktion ermöglicht die Ausrichtung des Rechtecks, so ändern Sie nur, wenn `Track` und `TrackRubberBand` heißen mit invertieren zulässig.  
  
 Überschreiben Sie diese Funktion, um die Anpassung des Rechtecks nachverfolgen, während ein Ziehvorgang zu steuern. Eine Methode besteht darin, passen Sie den angegebenen Koordinaten *LpRect* vor der Rückgabe.  
  
 Spezielle Features, die von nicht direkt unterstützt werden `CRectTracker`, wie z.B. Snap-in-Raster oder-Seitenverhältnis beibehalten, können durch das überschreiben diese Funktion implementiert werden.  
  
##  <a name="crecttracker"></a>  CRectTracker::CRectTracker  
 Erstellt und initialisiert ein `CRectTracker` Objekt.  
  
```  
CRectTracker();

 
CRectTracker(
    LPCRECT lpSrcRect,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 *lpSrcRect*  
 Die Koordinaten des Rectangle-Objekts.  
  
 *nStyle*  
 Gibt an, der die Darstellung der `CRectTracker` Objekt. Die folgenden Formate werden unterstützt:  
  
- `CRectTracker::solidLine` Verwenden Sie eine durchgehende Linie für den Rand des Rechtecks.  
  
- `CRectTracker::dottedLine` Verwenden Sie eine gepunktete Linie für den Rand des Rechtecks.  
  
- `CRectTracker::hatchedBorder` Verwenden Sie eine Schraffurmuster für den Rand des Rechtecks.  
  
- `CRectTracker::resizeInside` Ziehpunkte, die innerhalb des Rechtecks.  
  
- `CRectTracker::resizeOutside` Befindet sich außerhalb des Rechtecks Handles zur Größenänderung.  
  
- `CRectTracker::hatchInside` Ausgebrütet Muster deckt das gesamte Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkonstruktor initialisiert die `CRectTracker` Objekt mit den Werten aus *LpSrcRect* und andere Größen Systemstandards initialisiert. Wenn das Objekt, ohne Parameter erstellt wird der `m_rect` und `m_nStyle` Datenmember sind nicht initialisiert.  
  
##  <a name="draw"></a>  CRectTracker::Draw  
 Rufen Sie diese Funktion, um die Zeilen der äußeren und inneren Region des Rechtecks gezeichnet werden soll.  
  
```  
void Draw(CDC* pDC) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Zeiger auf den Gerätekontext, in dem gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Den Stil für die nachverfolgung wird bestimmt, wie die Zeichnung erfolgt. Finden Sie im Konstruktor für `CRectTracker` für Weitere Informationen zu den Formaten zur Verfügung.  
  
##  <a name="drawtrackerrect"></a>  CRectTracker::DrawTrackerRect  
 Vom Framework aufgerufen, wenn die Position der nachverfolgung geändert hat zwar innerhalb der `Track` oder `TrackRubberBand` Member-Funktion.  
  
```  
virtual void DrawTrackerRect(
    LPCRECT lpRect,  
    CWnd* pWndClipTo,  
    CDC* pDC,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *lpRect*  
 Zeiger auf die `RECT` , die zu zeichnenden Rechtecks enthält.  
  
 *pWndClipTo*  
 Zeiger auf das Fenster, in das Rechteck verwendet.  
  
 *pDC*  
 Zeiger auf den Gerätekontext, in dem gezeichnet werden soll.  
  
 *Aufnehmen*  
 Zeiger auf das Fenster auf dem die Zeichnung ausgeführt wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft `CDC::DrawFocusRect`, die einen gepunkteten Rahmen zeichnet.  
  
 Überschreiben Sie diese Funktion Informationen zu anderen Feedback während des nachverfolgungsvorgangs.  
  
##  <a name="gethandlemask"></a>  CRectTracker::GetHandleMask  
 Das Framework ruft diese Memberfunktion zum Abrufen von der Maske für Handles Größe eines Rechtecks zu ändern.  
  
```  
virtual UINT GetHandleMask() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Maske einer `CRectTracker` Handles zur Größenänderung des Elements.  
  
### <a name="remarks"></a>Hinweise  
 Die Handles zur Größenänderung werden auf den Seiten und die Ecken des Rechtecks angezeigt und ermöglicht dem Benutzer, die die Form und Größe des Rechtecks zu steuern.  
  
 Ein Rechteck ist 8 Handles zur Größenänderung nummeriert von 0 bis 7. Jede Ziehpunkt wird durch ein wenig in der Maske dargestellt; der Wert dieses Bit ist 2 ^ *n*, wobei *n* ist die Anzahl der Größenänderung-Handle. Bits 0 bis 3 entsprechen die Ecke Ziehpunkte, die oben links, gleitenden im Uhrzeigersinn ab. Bits 4 bis 7 auf der Seite entsprechen Ziehpunkte, die oben im Uhrzeigersinn verschieben. Die folgende Abbildung zeigt das Ändern der Größe eines Rechtecks behandelt und die entsprechenden Nummern der Ziehpunkte und Werte Größe:  
  
 ![Ändern Sie die Nummern der Ziehpunkte Größe](../../mfc/reference/media/vc35dp1.gif "vc35dp1")  
  
 Die standardmäßige Implementierung des `GetHandleMask` gibt die Maske der Bits zurück, sodass die Handles zur Größenänderung angezeigt werden. Wenn es sich bei den einzelne Bit aktiviert ist, wird der entsprechenden Ziehpunkt gezeichnet.  
  
 Überschreiben Sie diese Memberfunktion zum aus- oder einblenden, dass das angezeigte Ziehpunkte an.  
  
##  <a name="gettruerect"></a>  CRectTracker::GetTrueRect  
 Rufen Sie diese Funktion zum Abrufen der Koordinaten des Rechtecks.  
  
```  
void GetTrueRect(LPRECT lpTrueRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpTrueRect*  
 Zeiger auf die `RECT` Struktur, die das Gerät enthalten Koordinaten, der die `CRectTracker` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Abmessungen des Rechtecks enthalten die Höhe und Breite der alle Handles zur Größenänderung befindet sich auf der äußere Rahmen. Nach dem Beenden, *LpTrueRect* ist immer ein normalisierter Rechteck in Gerätekoordinaten.  
  
##  <a name="hittest"></a>  CRectTracker::HitTest  
 Rufen Sie diese Funktion finden Sie heraus, ob der Benutzer einen Ziehpunkt repräsentierte, hat.  
  
```  
int HitTest(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *Zeigen Sie*  
 Der Punkt in Gerätekoordinaten, um zu testen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der zurückgegebene Wert basiert auf den enumerierten Typ `CRectTracker::TrackerHit` und kann einen der folgenden Werte aufweisen:  
  
- `CRectTracker::hitNothing` -1  
  
- `CRectTracker::hitTopLeft` 0  
  
- `CRectTracker::hitTopRight` 1  
  
- `CRectTracker::hitBottomRight` 2  
  
- `CRectTracker::hitBottomLeft` 3  
  
- `CRectTracker::hitTop` 4  
  
- `CRectTracker::hitRight` 5  
  
- `CRectTracker::hitBottom` 6  
  
- `CRectTracker::hitLeft` 7  
  
- `CRectTracker::hitMiddle` 8  
  
##  <a name="m_nhandlesize"></a>  CRectTracker::m_nHandleSize  
 Die Größe in Pixel an, der die `CRectTracker` Handles zur Größenänderung.  
  
```  
int m_nHandleSize;  
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert mit den standardmäßigen Systemwert.  
  
##  <a name="m_rect"></a>  CRectTracker::m_rect  
 Die aktuelle Position des Rechtecks in Clientkoordinaten (in Pixel).  
  
```  
CRect m_rect;  
```  
  
##  <a name="m_sizemin"></a>  CRectTracker::m_sizeMin  
 Die minimale Größe des Rechtecks.  
  
```  
CSize m_sizeMin;  
```  
  
### <a name="remarks"></a>Hinweise  
 Beide Standardwerte `cx` und `cy`, aus den standardmäßigen Systemwert für die Breite des Rahmens berechnet werden. Dieses Datenelement wird nur verwendet, die `AdjustRect` Member-Funktion.  
  
##  <a name="m_nstyle"></a>  CRectTracker::m_nStyle  
 Aktuelle Stil des Rechtecks.  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CRectTracker::CRectTracker](#crecttracker) eine Liste der möglichen Formate.  
  
##  <a name="normalizehit"></a>  CRectTracker::NormalizeHit  
 Rufen Sie diese Funktion zum Konvertieren von einem potenziell invertierten Handle.  
  
```  
int NormalizeHit(int nHandle) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nHandle*  
 Der Handle vom Benutzer ausgewählt wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Handles normalisierte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `CRectTracker::Track` oder `CRectTracker::TrackRubberBand` heißt mit invertieren zulässig, es ist möglich, für das Rechteck auf der x-Achse, y-Achse oder beides umgekehrt werden soll. In diesem Fall `HitTest` Handles, die in Bezug auf das Rechteck auch umgekehrt werden zurück. Dies ist für zeichnen Cursor Feedback nicht geeignet, da das Feedback von die Bildschirmposition des Rechtecks nicht den Teil der Datenstruktur Rechteck abhängig ist, die geändert wird.  
  
##  <a name="onchangedrect"></a>  CRectTracker::OnChangedRect  
 Vom Framework aufgerufen, wenn das Rechteck Tracker während des Aufrufs geändert hat `Track`.  
  
```  
virtual void OnChangedRect(const CRect& rectOld);
```  
  
### <a name="parameters"></a>Parameter  
 *rectOld*  
 Mit den Gerätekoordinaten der alten von der `CRectTracker` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Zum Zeitpunkt dieser Funktion aufgerufen wird, Ihr Feedback mit gezeichneten `DrawTrackerRect` wurde entfernt. Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt.  
  
 Überschreiben Sie diese Funktion, wenn Sie möchten, dass zur Ausführung von Aktionen nach der Größe des Rechtecks geändert wurde.  
  
##  <a name="setcursor"></a>  CRectTracker:: SetCursor  
 Mit dieser Funktion können Sie die Cursorform zu ändern, während er über ist die `CRectTracker` des Objekts Region.  
  
```  
BOOL SetCursor(
    CWnd* pWnd,  
    UINT nHitTest) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Verweist auf das Fenster, das derzeit den Cursor enthält.  
  
 *nHitTest*  
 Die Ergebnisse des vorherigen Treffertests, aus der WM_SETCURSOR-Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das vorherige ermittelte über das Rechteck zur objektnachverfolgung wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion aus wird innerhalb der Funktion des Fensters, das die WM_SETCURSOR-Nachricht verarbeitet (in der Regel `OnSetCursor`).  
  
##  <a name="track"></a>  CRectTracker::Track  
 Rufen Sie diese Funktion, um die Benutzeroberfläche zum Ändern der Größe des Rechtecks anzuzeigen.  
  
```  
BOOL Track(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = FALSE,  
    CWnd* pWndClipTo = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Das Window-Objekt, das das Rechteck enthält.  
  
 *Zeigen Sie*  
 Gerätekoordinaten von der aktuellen Mausposition relativ zum Clientbereich.  
  
 *bAllowInvert*  
 Bei "true", kann das Rechteck entlang der x-Achse oder y-Achse umgekehrt werden soll; andernfalls "false".  
  
 *pWndClipTo*  
 Das Fenster, dem Zeichenvorgänge auf abgeschnitten wird. Wenn der Wert NULL, *aufnehmen* dient als das Clippingrechteck an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die ESC-Taste gedrückt wird, wird der Prozess der nachverfolgung angehalten, das Rechteck in die nachverfolgung gespeichert wird nicht geändert und wird 0 zurückgegeben. Wenn die Änderung ein Commit ausgeführt wurde, durch Bewegen der Maus und die linke Maustaste loslassen, die neue Position und/oder die Größe in die nachverfolgung des Rechtecks aufgezeichnet wird und ungleich NULL zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird in der Regel von bezeichnet, in der Funktion Ihrer Anwendung, die behandelt die `WM_LBUTTONDOWN` Nachricht (in der Regel `OnLButtonDown`).  
  
 Diese Funktion wird die Maus erfassen, bis der Benutzer die linke Maustaste loslässt, die ESC-Taste drückt oder die rechte Maustaste drückt. Wenn der Benutzer den Mauszeiger bewegt, wird das Feedback durch den Aufruf aktualisiert `DrawTrackerRect` und `OnChangedRect`.  
  
 Wenn *bAllowInvert* ist "true", das Rechteck für die nachverfolgung auf der x-Achse oder y-Achse umgekehrt werden kann.  
  
##  <a name="trackrubberband"></a>  CRectTracker::TrackRubberBand  
 Rufen Sie diese Funktion dazu Gummibandauswahl.  
  
```  
BOOL TrackRubberBand(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Das Window-Objekt, das das Rechteck enthält.  
  
 *Zeigen Sie*  
 Gerätekoordinaten von der aktuellen Mausposition relativ zum Clientbereich.  
  
 *bAllowInvert*  
 Bei "true", kann das Rechteck entlang der x-Achse oder y-Achse umgekehrt werden soll; andernfalls "false".  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn der Mauszeiger bewegt hat und nicht das Rechteck leer ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie wird in der Regel aus aufgerufen, innerhalb der Funktion der Anwendung, die die Nachricht WM_LBUTTONDOWN verarbeitet (in der Regel `OnLButtonDown`).  
  
 Diese Funktion wird die Maus erfassen, bis der Benutzer die linke Maustaste loslässt, die ESC-Taste drückt oder die rechte Maustaste drückt. Wenn der Benutzer den Mauszeiger bewegt, wird das Feedback durch den Aufruf aktualisiert `DrawTrackerRect` und `OnChangedRect`.  
  
 Überwachung wird mit einer Kunststoff-Band-Type-Auswahl aus der unteren rechten Handle ausgeführt. Wenn invertieren zulässig ist, kann das Rechteck ziehen entweder oben und links oder nach unten und rechts Größe angepasst werden.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel zur OBJEKTNACHVERFOLGUNG](../../visual-cpp-samples.md)   
 [MFC-Beispiel DRAWCLI](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleResizeBar-Klasse](../../mfc/reference/coleresizebar-class.md)   
 [CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)
