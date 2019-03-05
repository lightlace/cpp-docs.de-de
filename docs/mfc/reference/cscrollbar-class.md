---
title: CScrollBar-Klasse
ms.date: 11/04/2016
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
helpviewer_keywords:
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
ms.openlocfilehash: d677d72b7e758fcdaa7df0e2918e9bbec3e18ee9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263111"
---
# <a name="cscrollbar-class"></a>CScrollBar-Klasse

Stellt die Funktionalität eines Windows-Bildlaufleisten-Steuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CScrollBar : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CScrollBar::CScrollBar](#cscrollbar)|Erstellt ein `CScrollBar`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CScrollBar::Create](#create)|Erstellt die Bildlaufleiste von Windows und fügt es der `CScrollBar` Objekt.|
|[CScrollBar::EnableScrollBar](#enablescrollbar)|Aktiviert oder deaktiviert einen oder beide Pfeile auf einer Scrollleiste.|
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|Ruft Informationen über die Bildlaufleiste mit einer `SCROLLBARINFO` Struktur.|
|[CScrollBar::GetScrollInfo](#getscrollinfo)|Ruft Informationen über die Bildlaufleiste ab.|
|[CScrollBar::GetScrollLimit](#getscrolllimit)|Ruft den Grenzwert der scrollleiste|
|[CScrollBar::GetScrollPos](#getscrollpos)|Ruft die aktuelle Position eines Scrollfelds ab.|
|[CScrollBar::GetScrollRange](#getscrollrange)|Ruft die aktuellen minimalen und maximalen Bildlaufleisten-Positionen für die angegebene Bildlaufleiste ab.|
|[CScrollBar::SetScrollInfo](#setscrollinfo)|Legt die Informationen über die Bildlaufleiste fest.|
|[CScrollBar::SetScrollPos](#setscrollpos)|Legt die aktuelle Position des Bildlauffelds fest.|
|[CScrollBar::SetScrollRange](#setscrollrange)|Legt die minimalen und maximalen Positionswerte für die angegebene Scrollleiste fest.|
|[CScrollBar::ShowScrollBar](#showscrollbar)|Anzeigen oder ausblenden eine Bildlaufleiste.|

## <a name="remarks"></a>Hinweise

Sie erstellen ein Schiebeleisten-Steuerelement in zwei Schritten. Rufen Sie zunächst den Konstruktor `CScrollBar` zum Erstellen der `CScrollBar` Objekt aus, und rufen Sie dann die [erstellen](#create) Member-Funktion zum Erstellen von der Windows-Bildlaufleisten-Steuerelements, und fügen Sie ihn auf die `CScrollBar` Objekt.

Bei der Erstellung einer `CScrollBar` Objekt in einem Dialogfeld (mithilfe einer Ressource), die `CScrollBar` automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.

Bei der Erstellung einer `CScrollBar` Objekt innerhalb eines Zeitfensters, Sie müssen möglicherweise auch zerstören.

Bei der Erstellung der `CScrollBar` Objekt im Stapel automatisch zerstört wird. Bei der Erstellung der `CScrollBar` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das es zerstört, wenn der Benutzer die Bildlaufleiste von Windows beendet.

Wenn Sie im Arbeitsspeicher zuordnen der `CScrollBar` Objekt außer Kraft, indem die `CScrollBar` Destruktor, der Zuordnungen zu verwerfen.

Weitere Informationen zur Verwendung von `CScrollBar`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="create"></a>  CScrollBar::Create

Erstellt die Bildlaufleiste von Windows und fügt es der `CScrollBar` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt den Bildlauf Standardstil der Statusleiste des. Wenden Sie eine beliebige Kombination von [Stile des Schiebeleisten Steuerelements](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) auf die Bildlaufleiste.

*rect*<br/>
Gibt an, die Bildlaufleiste Größe und Position. Kann es sich um eine `RECT` Struktur oder ein `CRect` Objekt.

*pParentWnd*<br/>
Gibt den Bildlauf des Balkens übergeordnete Fenster, in der Regel eine `CDialog` Objekt. Es darf nicht NULL sein.

*nID*<br/>
Das Scroll Bar-Steuerelement-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CScrollBar` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor, der erstellt die `CScrollBar` Objekt, rufen Sie anschließend `Create`, die erstellt und initialisiert die zugeordnete Windows-Bildlaufleiste und fügt es der `CScrollBar` Objekt.

Übernehmen Sie das folgende [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) um eine Bildlaufleiste angezeigt:

- WS_CHILD immer

- WS_VISIBLE in der Regel

- WS_DISABLED selten

- WS_GROUP zum Gruppieren von Steuerelementen

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

##  <a name="cscrollbar"></a>  CScrollBar::CScrollBar

Erstellt ein `CScrollBar`-Objekt.

```
CScrollBar();
```

### <a name="remarks"></a>Hinweise

Rufen Sie nach dem Erstellen des Objekts, das `Create` Member-Funktion erstellen und initialisieren die Bildlaufleiste von Windows.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

##  <a name="enablescrollbar"></a>  CScrollBar::EnableScrollBar

Aktiviert oder deaktiviert einen oder beide Pfeile auf einer Scrollleiste.

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>Parameter

*nArrowFlags*<br/>
Gibt an, ob die Bildlauf-Pfeile aktiviert oder deaktiviert sind und welche Pfeile aktiviert oder deaktiviert sind. Dieser Parameter kann einen der folgenden Werte sein:

- ESB_ENABLE_BOTH können beide Bildlaufpfeile einer Bildlaufleiste.

- ESB_DISABLE_LTUP deaktiviert den Pfeil nach links, der eine horizontale Bildlaufleiste oder den Pfeil nach oben, der eine vertikale Bildlaufleiste angezeigt.

- ESB_DISABLE_RTDN deaktiviert den Pfeil nach rechts, der eine horizontale Bildlaufleiste oder den Pfeil nach unten, der eine vertikale Bildlaufleiste angezeigt.

- ESB_DISABLE_BOTH deaktiviert sowohl Bildlaufpfeile einer Bildlaufleiste.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Pfeile aktiviert oder werden, wie angegeben deaktiviert werden; andernfalls 0 (null) gibt an, dass die Pfeile bereits im angeforderten Zustand befinden oder ein Fehler aufgetreten ist.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CScrollBar::SetScrollRange](#setscrollrange).

##  <a name="getscrollbarinfo"></a>  CScrollBar::GetScrollBarInfo

Ruft die Informationen ab, die von der `SCROLLBARINFO`-Struktur über eine Scrollleiste verwaltet werden.

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>Parameter

*pScrollInfo*<br/>
Ein Zeiger auf die [SCROLLBARINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollbarinfo) Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen des die [SBM_SCROLLBARINFO](/windows/desktop/Controls/sbm-getscrollbarinfo) Nachricht, wie im Windows SDK beschrieben.

##  <a name="getscrollinfo"></a>  CScrollBar::GetScrollInfo

Ruft die Informationen ab, die von der `SCROLLINFO`-Struktur über eine Scrollleiste verwaltet werden.

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>Parameter

*lpScrollInfo*<br/>
Ein Zeiger auf eine [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) Struktur. Finden Sie im Windows-SDK Weitere Informationen zu dieser Struktur aus.

*nMask*<br/>
Gibt die Scroll-Leiste Parameter abrufen. Typische Verwendung, SIF_ALL, gibt eine Kombination von SIF_PAGE, SIF_POS, SIF_TRACKPOS und SIF_RANGE an. Finden Sie unter `SCROLLINFO` für Weitere Informationen zu den nMask-Werten.

### <a name="return-value"></a>Rückgabewert

Wenn die Nachricht keine Werte abgerufen werden, ist die Rückgabe "true". Andernfalls ist es "false".

### <a name="remarks"></a>Hinweise

`GetScrollInfo` ermöglicht Anwendungen die 32-Bit-Bildlaufpositionen zu verwenden.

Die [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) Struktur enthält Informationen über eine scrollleiste an, einschließlich des minimalen und maximalen Bildlauf Positionen, die Seitengröße und die Position des Bildlauffelds (Ziehpunkt). Finden Sie unter den `SCROLLINFO` Struktur Thema im Windows SDK für Weitere Informationen zum Ändern der Standardeinstellungen für die Struktur.

Die MFC-Windows message-Handler, die kennzeichnen der Position, [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), geben Sie nur 16 Bits des Position-Daten. `GetScrollInfo` und `SetScrollInfo` 32 Bits der scrollleiste an Position-Daten bereitstellen. Daher kann eine Anwendung aufrufen `GetScrollInfo` während der Verarbeitung entweder `CWnd::OnHScroll` oder `CWnd::OnVScroll` zum Abrufen von Daten für 32-Bit-Scroll-Leiste Position.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="getscrolllimit"></a>  CScrollBar::GetScrollLimit

Ruft die maximale Bildlauf der Position der Schiebeleiste ab.

```
int GetScrollLimit();
```

### <a name="return-value"></a>Rückgabewert

Gibt die maximale Position einer Bildlaufleiste, wenn erfolgreich; andernfalls 0.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="getscrollpos"></a>  CScrollBar::GetScrollPos

Ruft die aktuelle Position eines Scrollfelds ab.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt an, die aktuelle Position des Bildlauffelds bei erfolgreicher Ausführung; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die aktuelle Position ist ein relativer Wert, der von der aktuellen fortlaufenden Bereich abhängt. Wenn der Bildlauf Bereich liegt zwischen 100 und 200, und das Bildlauffeld, die in der Leiste befindet, wird die aktuelle Position 150.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="getscrollrange"></a>  CScrollBar::GetScrollRange

Kopiert die aktuellen minimalen und maximalen Bildlaufleisten-Positionen für die angegebene scrollleiste auf den von angegebenen Speicherorten *LpMinPos* und *LpMaxPos*.

```
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>Parameter

*lpMinPos*<br/>
Verweist auf die ganzzahlige Variable, die die minimale Position zu erhalten.

*lpMaxPos*<br/>
Verweist auf die ganzzahlige Variable, die die maximale Position zu erhalten.

### <a name="remarks"></a>Hinweise

Der Standardbereich für ein Schiebeleisten-Steuerelement ist leer (beide Werte sind 0).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="setscrollinfo"></a>  CScrollBar::SetScrollInfo

Legt der Informationen, die die `SCROLLINFO` Struktur über eine scrollleiste verwaltet.

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parameter

*lpScrollInfo*<br/>
Ein Zeiger auf eine [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) Struktur.

*bRedraw*<br/>
Gibt an, ob die Bildlaufleiste neu gezeichnet werden muss, um die neuen Informationen widerzuspiegeln. Wenn *bRedraw* ist "true", die Bildlaufleiste neu gezeichnet wird. Wenn sie auf "FALSE" ist, wird er nicht neu gezeichnet. Standardmäßig aktualisiert der Bildlaufleiste angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, ist die Rückgabe "true". Andernfalls ist es "false".

### <a name="remarks"></a>Hinweise

Sie müssen die erforderlichen Werte angeben der `SCROLLINFO` Struktur Parametern – einschließlich der Flagwerte.

Die `SCROLLINFO` Struktur enthält Informationen über eine scrollleiste an, einschließlich des minimalen und maximalen Bildlauf Positionen, die Seitengröße und die Position des Bildlauffelds (Ziehpunkt). Finden Sie unter den [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) Struktur Thema im Windows SDK für Weitere Informationen zum Ändern der Standardeinstellungen für die Struktur.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

##  <a name="setscrollpos"></a>  CScrollBar::SetScrollPos

Wird von der aktuellen Position des Bildlauffelds auf, die angegeben *nPos* und, falls angegeben, zeichnet die Bildlaufleiste, um die neue Position zu berücksichtigen.

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Gibt die neue Position für das Bildlauffeld. Es muss den fortlaufenden Bereich liegen.

*bRedraw*<br/>
Gibt an, ob die Bildlaufleiste neu gezeichnet werden muss, um die neue Position zu berücksichtigen. Wenn *bRedraw* ist "true", die Bildlaufleiste neu gezeichnet wird. Wenn sie auf "FALSE" ist, wird er nicht neu gezeichnet. Standardmäßig aktualisiert der Bildlaufleiste angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Gibt an, die vorherige Position des Bildlauffelds bei erfolgreicher Ausführung; andernfalls 0.

### <a name="remarks"></a>Hinweise

Legen Sie *bRedraw* auf "false" jedes Mal, wenn die Bildlaufleiste wird neu gezeichnet werden durch einen nachfolgenden Aufruf an eine andere Funktion, damit die Bildlaufleiste zweimal innerhalb kurzer Zeit neu gezeichnet werden müssen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CScrollBar::SetScrollRange](#setscrollrange).

##  <a name="setscrollrange"></a>  CScrollBar::SetScrollRange

Legt die minimalen und maximalen Positionswerte für die angegebene Scrollleiste fest.

```
void SetScrollRange(
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parameter

*nMinPos*<br/>
Gibt die mindestens erforderlichen Bildlaufposition.

*nMaxPos*<br/>
Gibt die maximale Bildlaufposition.

*bRedraw*<br/>
Gibt an, ob die Bildlaufleiste neu gezeichnet werden muss, um die Änderung wiederzugeben. Wenn *bRedraw* ist "true", die Bildlaufleiste neu gezeichnet wird; bei FALSE wird es nicht neu gezeichnet wird. Es wird standardmäßig neu gezeichnet.

### <a name="remarks"></a>Hinweise

Legen Sie *nMinPos* und *nMaxPos* auf 0, um die standard-Schiebeleisten ausblenden.

Rufen Sie diese Funktion, um eine Bildlaufleiste ausblenden beim Verarbeiten einer Nachricht der Bildlaufleisten-Benachrichtigung nicht.

Wenn ein Aufruf von `SetScrollRange` unmittelbar folgt einen Aufruf der `SetScrollPos` Member-Funktion festlegen *bRedraw* in `SetScrollPos` auf 0, um zu verhindern, dass die Bildlaufleiste zweimal neu gezeichnet wird.

Der Unterschied zwischen die angegebenen Werte von *nMinPos* und *nMaxPos* darf nicht größer als 32.767 sein. Der Standardbereich für ein Schiebeleisten-Steuerelement ist leer (beide *nMinPos* und *nMaxPos* sind 0).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

##  <a name="showscrollbar"></a>  CScrollBar::ShowScrollBar

Anzeigen oder ausblenden eine Bildlaufleiste.

```
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
Gibt an, ob die Bildlaufleiste ein- oder ausgeblendet ist. Wenn dieser Parameter auf true festgelegt ist, ist die Bildlaufleiste wird angezeigt, Andernfalls ist er ausgeblendet.

### <a name="remarks"></a>Hinweise

Eine Anwendung sollten diese Funktion, um eine Bildlaufleiste ausblenden beim Verarbeiten einer Nachricht der Bildlaufleisten-Benachrichtigung nicht aufrufen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CScrollBar::Create](#create).

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CButton-Klasse](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit-Klasse](../../mfc/reference/cedit-class.md)<br/>
[CListBox-Klasse](../../mfc/reference/clistbox-class.md)<br/>
[CStatic-Klasse](../../mfc/reference/cstatic-class.md)<br/>
[CDialog-Klasse](../../mfc/reference/cdialog-class.md)
