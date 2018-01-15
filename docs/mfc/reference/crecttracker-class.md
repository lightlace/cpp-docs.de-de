---
title: CRectTracker-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1f870ef92296636c8d27fc166d41cdefc54d1585
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crecttracker-class"></a>CRectTracker-Klasse
Ermöglicht es einem Element angezeigt, verschoben und in unterschiedlichen Größen dargestellt werden.  
  
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
|[CRectTracker::AdjustRect](#adjustrect)|Wird aufgerufen, wenn die Größe des Rechtecks geändert wird.|  
|[CRectTracker::Draw](#draw)|Rendert das Rechteck.|  
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|Wird aufgerufen, wenn am Rand Zeichnen einer `CRectTracker` Objekt.|  
|[CRectTracker::GetHandleMask](#gethandlemask)|Wird aufgerufen, um das Abrufen der Maske einer `CRectTracker` des Elements Handles zur Größenänderung.|  
|[CRectTracker::GetTrueRect](#gettruerect)|Breite und Höhe des Rechtecks, einschließlich der Ziehpunkte zurückgibt.|  
|[CRectTracker::HitTest](#hittest)|Gibt die aktuelle Position des Cursors im Zusammenhang mit der `CRectTracker` Objekt.|  
|[CRectTracker::NormalizeHit](#normalizehit)|Normalisiert einen Treffertest-Code.|  
|[CRectTracker::OnChangedRect](#onchangedrect)|Wird aufgerufen, wenn das Rechteck geändert oder verschoben wurde.|  
|[CRectTracker:: SetCursor](#setcursor)|Legt fest, den Cursor je nach seiner Position über dem Rechteck.|  
|[CRectTracker::Track](#track)|Ermöglicht dem Benutzer das Rechteck zu bearbeiten.|  
|[CRectTracker::TrackRubberBand](#trackrubberband)|Ermöglicht es dem Benutzer "Kunststoff-Band" die Auswahl.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|Bestimmt die Größe der Ziehpunkte.|  
|[CRectTracker::m_nStyle](#m_nstyle)|Aktuelle Style(s) Tracker.|  
|[CRectTracker::m_rect](#m_rect)|Aktuelle Position des Rechtecks (in Pixel).|  
|[CRectTracker::m_sizeMin](#m_sizemin)|Bestimmt, minimale Rechteck Breite und Höhe.|  
  
## <a name="remarks"></a>Hinweise  
 `CRectTracker`eine Basisklasse verfügt nicht über.  
  
 Obwohl die `CRectTracker` -Klasse kann der Benutzer über eine grafische Benutzeroberfläche mit OLE-Elementen interagieren kann, dessen Verwendung ist nicht auf OLE-fähigen Anwendungen beschränkt. Hiermit können an einer beliebigen Stelle solche eine Benutzeroberfläche erforderlich ist.  
  
 `CRectTracker`Rahmen können einfarbig sein oder gepunkteten Linien. Das Element kann schraffiert angegeben oder mit einer Schraffur an die verschiedenen Zustände des Elements Überlagerung werden. Sie können entweder außerhalb oder innerhalb acht Ziehpunkte platzieren Rahmen des Elements. (Eine Erläuterung der Ziehpunkte, finden Sie unter [GetHandleMask](#gethandlemask).) Schließlich eine `CRectTracker` können Sie die Ausrichtung eines Elements beim Ändern der Größe ändern.  
  
 Verwenden `CRectTracker`, erstellen Sie eine `CRectTracker` Objekt, und geben Sie an, welche Anzeigestatus initialisiert werden. Sie können dann mithilfe dieser Schnittstelle die Benutzer auf den aktuellen Status des zugeordneten OLE-Elements ein visuelles Feedback der `CRectTracker` Objekt.  
  
 Weitere Informationen zur Verwendung von `CRectTracker`, finden Sie im Artikel [Rahmenstile](../../mfc/trackers.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CRectTracker`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="adjustrect"></a>CRectTracker::AdjustRect  
 Vom Framework aufgerufen, wenn das Überwachungsprofil Rechteck unter Verwendung eines Handles zum Ändern der Größe angepasst wird.  
  
```  
virtual void AdjustRect(
    int nHandle,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `nHandle`  
 Der Index des Handles verwendet.  
  
 `lpRect`  
 Ein Zeiger auf die aktuelle Größe des Rechtecks. (Die Größe eines Rechtecks wird durch die Höhe und Breite angegeben.)  
  
### <a name="remarks"></a>Hinweise  
 Das Standardverhalten dieser Funktion ermöglicht das Rechteck Ausrichtung so ändern Sie nur, wenn `Track` und `TrackRubberBand` heißen mit invertieren zulässig.  
  
 Überschreiben Sie diese Funktion, um die Anpassung des Rechtecks Überwachung während eines Drag-Vorgangs steuern. Eine Methode besteht darin, passen Sie die angegebenen Koordinaten `lpRect` vor der Rückgabe.  
  
 Spezielle Funktionen, die von nicht direkt unterstützt werden `CRectTracker`, z. B. ausrichtungsgitter- oder-Seitenverhältnis beibehalten, kann durch Außerkraftsetzen von dieser Funktion implementiert werden.  
  
##  <a name="crecttracker"></a>CRectTracker::CRectTracker  
 Erstellt und initialisiert ein `CRectTracker` Objekt.  
  
```  
CRectTracker();

 
CRectTracker(
    LPCRECT lpSrcRect,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `lpSrcRect`  
 Die Koordinaten des Rechteckobjekts.  
  
 `nStyle`  
 Gibt das Format der `CRectTracker` Objekt. Die folgenden Stile werden unterstützt:  
  
- **CRectTracker::solidLine** verwenden eine durchgehende Linie für den Rechteckrahmen.  
  
- **CRectTracker::dottedLine** verwenden eine gepunktete Linie für den Rechteckrahmen.  
  
- **CRectTracker::hatchedBorder** eine Schraffur für das Rechteckrahmen verwenden.  
  
- **CRectTracker::resizeInside** Steuerpunkte befindet sich innerhalb des Rechtecks.  
  
- **CRectTracker::resizeOutside** Steuerpunkte befindet sich außerhalb des Rechtecks.  
  
- **CRectTracker::hatchInside** Hatched Muster behandelt das gesamte Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkonstruktor initialisiert die `CRectTracker` Objekt mit den Werten aus `lpSrcRect` und anderen Größen um Systemstandardwerte initialisiert. Wenn das Objekt, ohne Parameter erstellt wurde die `m_rect` und `m_nStyle` Datenmember nicht initialisiert werden.  
  
##  <a name="draw"></a>CRectTracker::Draw  
 Mit dieser Funktion wird zum Zeichnen des Rechtecks äußeren Zeilen und inneren Region.  
  
```  
void Draw(CDC* pDC) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Gerätekontext, auf dem gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Art des Tracker bestimmt, wie die Zeichnung erfolgt. Finden Sie im Konstruktor für `CRectTracker` für Weitere Informationen zu den Formaten zur Verfügung.  
  
##  <a name="drawtrackerrect"></a>CRectTracker::DrawTrackerRect  
 Vom Framework aufgerufen, wenn die Position des Tracker geändert hat zwar innerhalb der `Track` oder `TrackRubberBand` Memberfunktion.  
  
```  
virtual void DrawTrackerRect(
    LPCRECT lpRect,  
    CWnd* pWndClipTo,  
    CDC* pDC,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Zeiger auf die `RECT` , die zu zeichnenden Rechtecks enthält.  
  
 `pWndClipTo`  
 Ein Zeiger auf das Fenster, in das Rechteck verwendet.  
  
 `pDC`  
 Ein Zeiger auf den Gerätekontext, auf dem gezeichnet werden soll.  
  
 `pWnd`  
 Ein Zeiger auf das Fenster auf dem die Zeichnung ausgeführt wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft `CDC::DrawFocusRect`, die ein gepunktetes Rechteck gezeichnet.  
  
 Überschreiben Sie diese Funktion für verschiedene Feedback während des nachverfolgungsvorgangs.  
  
##  <a name="gethandlemask"></a>CRectTracker::GetHandleMask  
 Das Framework ruft diese Memberfunktion, um die Maske abzurufen, für die Ziehpunkte des Rechtecks.  
  
```  
virtual UINT GetHandleMask() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Maske einer `CRectTracker` des Elements Handles zur Größenänderung.  
  
### <a name="remarks"></a>Hinweise  
 Die Ziehpunkte auf den Seiten und die Ecken des Rechtecks angezeigt und ermöglicht dem Benutzer zum Steuern der Form und Größe des Rechtecks.  
  
 Ein Rechteck hat 8 Ziehpunkte, die 0-7 nummeriert. Jede Ziehpunkt wird durch ein bit in der Maske dargestellt; der Wert dieses Bit ist 2 ^  *n* , wobei  *n*  ist die Anzahl der Resize-Handle. Bits 0 bis 3 entsprechen die Ecke Ziehpunkte, die im oberen linken Bereich verschieben gegen den Uhrzeigersinn ab. Bits 4 bis 7 auf der Seite entsprechen Steuerpunkte, die beginnend am Anfang Uhrzeigersinn. Die folgende Abbildung zeigt die Größe des Rechtecks behandelt und die entsprechenden Größe, Nummern und Werte:  
  
 ![Ändern der Größe Nummern](../../mfc/reference/media/vc35dp1.gif "vc35dp1")  
  
 Die standardmäßige Implementierung des **GetHandleMask** gibt die Maske Bits zurück, sodass die Ziehpunkte angezeigt werden. Wenn es sich bei den einzelne Bit aktiviert ist, wird der entsprechende Ziehpunkt gezeichnet.  
  
 Überschreiben Sie diese Memberfunktion, um das angezeigte Ziehpunkte anzuzeigen oder auszublenden.  
  
##  <a name="gettruerect"></a>CRectTracker::GetTrueRect  
 Mit dieser Funktion wird zum Abrufen der Koordinaten des Rechtecks.  
  
```  
void GetTrueRect(LPRECT lpTrueRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpTrueRect`  
 Zeiger auf die `RECT` Struktur, die das Gerät enthalten Koordinaten, der die `CRectTracker` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Dimensionen des Rechtecks umfassen die Höhe und Breite des Ziehpunkte, die sich auf den äußeren Rahmen befindet. Beim Zurückgeben der `lpTrueRect` ist immer einem normalisierten Rechteck in logische Koordinaten.  
  
##  <a name="hittest"></a>CRectTracker::HitTest  
 Rufen Sie diese Funktion, um herauszufinden, ob der Benutzer einen Ziehpunkt Element erfasst wurde.  
  
```  
int HitTest(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Die Stelle im Gerätekoordinaten, um zu testen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der zurückgegebene Wert basiert auf den enumerierten Typ **CRectTracker::TrackerHit** und kann einen der folgenden Werte aufweisen:  
  
- **CRectTracker::hitNothing** -1  
  
- **CRectTracker::hitTopLeft** 0  
  
- **CRectTracker::hitTopRight** 1  
  
- **CRectTracker::hitBottomRight** 2  
  
- **CRectTracker::hitBottomLeft** 3  
  
- **CRectTracker::hitTop** 4  
  
- **CRectTracker::hitRight** 5  
  
- **CRectTracker::hitBottom** 6  
  
- **CRectTracker::hitLeft** 7  
  
- **CRectTracker::hitMiddle** 8  
  
##  <a name="m_nhandlesize"></a>CRectTracker::m_nHandleSize  
 Die Größe in Pixel, der die `CRectTracker` Handles zur Größenänderung.  
  
```  
int m_nHandleSize;  
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert mit dem Standardwert für das System.  
  
##  <a name="m_rect"></a>CRectTracker::m_rect  
 Die aktuelle Position des Rechtecks in Clientkoordinaten (in Pixel).  
  
```  
CRect m_rect;  
```  
  
##  <a name="m_sizemin"></a>CRectTracker::m_sizeMin  
 Die minimale Größe des Rechtecks.  
  
```  
CSize m_sizeMin;  
```  
  
### <a name="remarks"></a>Hinweise  
 Beide Standardwerte **Cx** und **cy**, aus der System-Standardwert für die Breite des Rahmens berechnet werden. Dieses Datenelement wird nur von verwendet die `AdjustRect` Memberfunktion.  
  
##  <a name="m_nstyle"></a>CRectTracker::m_nStyle  
 Aktuelle Stil des Rechtecks.  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CRectTracker::CRectTracker](#crecttracker) eine Liste der möglichen Formate.  
  
##  <a name="normalizehit"></a>CRectTracker::NormalizeHit  
 Mit dieser Funktion wird zum Konvertieren einer potenziell invertierten Handle.  
  
```  
int NormalizeHit(int nHandle) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nHandle`  
 Der Handle vom Benutzer ausgewählt wurden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des normalisierte Handles.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `CRectTracker::Track` oder `CRectTracker::TrackRubberBand` heißt mit invertieren zulässig, es ist möglich, für das Rechteck auf der x-Achse, die y-Achse oder beides umgekehrt werden. In diesem Fall `HitTest` Handles, die auch in Bezug auf das Rechteck invertiert werden zurück. Dies ist für zeichnen Cursors nicht geeignet, da das Feedback von Bildschirmposition des Rechtecks, nicht den Teil der Datenstruktur Rechteck abhängt, die geändert werden soll.  
  
##  <a name="onchangedrect"></a>CRectTracker::OnChangedRect  
 Vom Framework aufgerufen, wenn das Rechteck Tracker während eines Aufrufs geändert hat `Track`.  
  
```  
virtual void OnChangedRect(const CRect& rectOld);
```  
  
### <a name="parameters"></a>Parameter  
 *rectOld*  
 Mit den Gerätekoordinaten der alten von der `CRectTracker` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Zum Zeitpunkt dieser Funktion aufgerufen wird, Ihr Feedback mit gezeichneten `DrawTrackerRect` entfernt wurde. Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt.  
  
 Überschreiben Sie diese Funktion, wenn Sie möchten, dass erforderliche Aktionen auszuführen, nachdem die Größe des Rechtecks geändert wurde.  
  
##  <a name="setcursor"></a>CRectTracker:: SetCursor  
 Mit dieser Funktion können Sie die Form "Cursor" zu ändern, während er über ist die `CRectTracker` Region des Objekts.  
  
```  
BOOL SetCursor(
    CWnd* pWnd,  
    UINT nHitTest) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster, das derzeit den Cursor enthält.  
  
 `nHitTest`  
 Ergebnisse des vorherigen Treffertests, aus der `WM_SETCURSOR` Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, falls der vorherige Treffer über das Rechteck Tracker erfolgte; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion aus wird innerhalb der Funktion des Fensters, die behandelt die `WM_SETCURSOR` Nachricht (in der Regel `OnSetCursor`).  
  
##  <a name="track"></a>CRectTracker::Track  
 Mit dieser Funktion wird zum Anzeigen der Benutzeroberfläche zum Ändern der Größe des Rechtecks.  
  
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
 Gerätekoordinaten von der aktuellen Position des Mauszeigers relativ zum Clientbereich.  
  
 `bAllowInvert`  
 Wenn **"true"**, das Rechteck werden kann, andernfalls auf der x-Achse oder y-Achse invertierte **"false"**.  
  
 `pWndClipTo`  
 Das Fenster, dem Zeichenvorgänge auf zugeschnitten wird. Wenn **NULL**, `pWnd` dient als das Clippingrechteck an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die ESC-Taste gedrückt wird, der Tracking-Prozess wird angehalten, das Rechteck in der nachverfolgung gespeichert wird nicht geändert und wird 0 zurückgegeben. Wenn die Änderung übernommen wird, verschieben die Maus und die linke Maustaste loslassen, die neue Position und/oder die Größe in der nachverfolgung Rechteck aufgezeichnet wird und ungleich NULL wird zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird normalerweise aus aufgerufen, innerhalb der Funktion der Anwendung, die behandelt die `WM_LBUTTONDOWN` Nachricht (in der Regel `OnLButtonDown`).  
  
 Diese Funktion wird die Maus erfassen, bis der Benutzer die linke Maustaste loslässt, die ESC-Taste drückt oder die rechte Maustaste drückt. Wenn der Benutzer den Mauszeiger bewegt wird, wird das Feedback durch Aufrufen aktualisiert `DrawTrackerRect` und `OnChangedRect`.  
  
 Wenn `bAllowInvert` ist **"true"**, das Überwachungsprofil Rechteck auf der x-Achse oder y-Achse umgekehrt werden kann.  
  
##  <a name="trackrubberband"></a>CRectTracker::TrackRubberBand  
 Mit dieser Funktion können Kunststoff-Band-Auswahl nicht.  
  
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
 Gerätekoordinaten von der aktuellen Position des Mauszeigers relativ zum Clientbereich.  
  
 `bAllowInvert`  
 Wenn **"true"** Rechtecks werden kann, andernfalls auf der x-Achse oder y-Achse invertierte **"false"**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Maus bewegt hat und das Rechteck nicht leer ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Es ist in der Regel von aufgerufen, innerhalb der Funktion der Anwendung, die behandelt die `WM_LBUTTONDOWN` Nachricht (in der Regel `OnLButtonDown`).  
  
 Diese Funktion wird die Maus erfassen, bis der Benutzer die linke Maustaste loslässt, die ESC-Taste drückt oder die rechte Maustaste drückt. Wenn der Benutzer den Mauszeiger bewegt wird, wird das Feedback durch Aufrufen aktualisiert `DrawTrackerRect` und `OnChangedRect`.  
  
 Überwachung erfolgt mit einer Kunststoff-Band-Type-Auswahl aus der unteren rechten Handle. Wenn invertieren zulässig ist, kann das Rechteck angepasst werden, entweder oben und nach links oder nach unten und rechts ziehen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel TRACKER](../../visual-cpp-samples.md)   
 [MFC-Beispiel DRAWCLI](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleResizeBar-Klasse](../../mfc/reference/coleresizebar-class.md)   
 [CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)
