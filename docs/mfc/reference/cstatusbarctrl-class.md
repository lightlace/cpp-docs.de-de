---
title: CStatusBarCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
- AFXCMN/CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::Create
- AFXCMN/CStatusBarCtrl::CreateEx
- AFXCMN/CStatusBarCtrl::DrawItem
- AFXCMN/CStatusBarCtrl::GetBorders
- AFXCMN/CStatusBarCtrl::GetIcon
- AFXCMN/CStatusBarCtrl::GetParts
- AFXCMN/CStatusBarCtrl::GetRect
- AFXCMN/CStatusBarCtrl::GetText
- AFXCMN/CStatusBarCtrl::GetTextLength
- AFXCMN/CStatusBarCtrl::GetTipText
- AFXCMN/CStatusBarCtrl::IsSimple
- AFXCMN/CStatusBarCtrl::SetBkColor
- AFXCMN/CStatusBarCtrl::SetIcon
- AFXCMN/CStatusBarCtrl::SetMinHeight
- AFXCMN/CStatusBarCtrl::SetParts
- AFXCMN/CStatusBarCtrl::SetSimple
- AFXCMN/CStatusBarCtrl::SetText
- AFXCMN/CStatusBarCtrl::SetTipText
helpviewer_keywords:
- CStatusBarCtrl [MFC], CStatusBarCtrl
- CStatusBarCtrl [MFC], Create
- CStatusBarCtrl [MFC], CreateEx
- CStatusBarCtrl [MFC], DrawItem
- CStatusBarCtrl [MFC], GetBorders
- CStatusBarCtrl [MFC], GetIcon
- CStatusBarCtrl [MFC], GetParts
- CStatusBarCtrl [MFC], GetRect
- CStatusBarCtrl [MFC], GetText
- CStatusBarCtrl [MFC], GetTextLength
- CStatusBarCtrl [MFC], GetTipText
- CStatusBarCtrl [MFC], IsSimple
- CStatusBarCtrl [MFC], SetBkColor
- CStatusBarCtrl [MFC], SetIcon
- CStatusBarCtrl [MFC], SetMinHeight
- CStatusBarCtrl [MFC], SetParts
- CStatusBarCtrl [MFC], SetSimple
- CStatusBarCtrl [MFC], SetText
- CStatusBarCtrl [MFC], SetTipText
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
ms.openlocfilehash: 71ae39cb62da7938880973dc48b65ed69b9c8b92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569730"
---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl-Klasse

Stellt die Funktionalität des allgemeinen Windows-Statusleisten-Steuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CStatusBarCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|Erstellt ein `CStatusBarCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CStatusBarCtrl::Create](#create)|Erstellt ein Statusleisten-Steuerelement, und fügt sie an einer `CStatusBarCtrl` Objekt.|
|[CStatusBarCtrl::CreateEx](#createex)|Erstellt ein Statusleisten-Steuerelement mit dem angegebenen erweiterten Stile für Windows und fügt sie an einer `CStatusBarCtrl` Objekt.|
|[CStatusBarCtrl::DrawItem](#drawitem)|Wird aufgerufen, wenn ein visueller Aspekt der ein ownerdrawn-Statusleisten-Steuerelements ändert.|
|[CStatusBarCtrl::GetBorders](#getborders)|Ruft die aktuelle Breite der horizontalen und vertikalen Rahmen ein Statusleisten-Steuerelement ab.|
|[CStatusBarCtrl::GetIcon](#geticon)|Ruft das Symbol für einen Teil (auch bekannt als ein Bereich) in das aktuelle StatusBar-Steuerelement ab.|
|[CStatusBarCtrl::GetParts](#getparts)|Ruft die Anzahl der Teile in ein Statusleisten-Steuerelement ab.|
|[CStatusBarCtrl::GetRect](#getrect)|Ruft das umschließende Rechteck eines Parts im ein Statusleisten-Steuerelement ab.|
|[CStatusBarCtrl:: GetText](#gettext)|Ruft den Text aus den angegebenen Teil ein Statusleisten-Steuerelement ab.|
|[CStatusBarCtrl:: getTextLength](#gettextlength)|Rufen Sie die Länge in Zeichen des Texts aus dem angegebenen Teil des ein Statusleisten-Steuerelement.|
|[CStatusBarCtrl::GetTipText](#gettiptext)|Ruft den QuickInfo-Text für einen Bereich in einer Statusleiste ab.|
|[CStatusBarCtrl::IsSimple](#issimple)|Überprüft, um festzustellen, ob es sich im einfachen Modus ist ein Fenster-Steuerelement.|
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|Legt die Hintergrundfarbe in einer Statusleiste fest.|
|[CStatusBarCtrl::SetIcon](#seticon)|Legt das Symbol für einen Bereich in einer Statusleiste fest.|
|[CStatusBarCtrl::SetMinHeight](#setminheight)|Legt die minimale Höhe des Status steuerleistenbereichs Zeichnen des Steuerelements fest.|
|[CStatusBarCtrl::SetParts](#setparts)|Legt die Anzahl der Teile in einer Statusleisten-Steuerelement und die Koordinate des rechten Rands der einzelnen Teile fest.|
|[CStatusBarCtrl::SetSimple](#setsimple)|Gibt an, ob ein Statusleisten-Steuerelement einfachen Text zeigt oder alle Steuerelementteile, die von einem vorherigen Aufruf von festgelegt `SetParts`.|
|[CStatusBarCtrl::SetText](#settext)|Legt den Text im bestimmten Teil eines Statusleisten-Steuerelements fest.|
|[CStatusBarCtrl:: setTipText](#settiptext)|Legt die QuickInfo-Text für einen Bereich in einer Statusleiste fest.|

## <a name="remarks"></a>Hinweise

Ein "Statusleisten-Steuerelement" ist ein horizontales Fenster, in der Regel angezeigt wird, am Ende ein übergeordnetes Fenster, in denen eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann. Das StatusBar-Steuerelement kann in Webparts zum Anzeigen von mehr als eine Art von Informationen unterteilt werden.

Dieses Steuerelement (und somit die `CStatusBarCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.

Weitere Informationen zur Verwendung von `CStatusBarCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="create"></a>  CStatusBarCtrl::Create

Erstellt ein Statusleisten-Steuerelement, und fügt sie an einer `CStatusBarCtrl` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt das StatusBar-Steuerelement Stil. Wenden Sie eine beliebige Kombination der Stile von Listensteuerelementen aufgeführt, die der Statusleiste [allgemeinen Stile von Listensteuerelementen](/windows/desktop/Controls/common-control-styles) im Windows SDK. Dieser Parameter muss das Format WS_CHILD enthalten. Darüber sollte hinaus das WS_VISIBLE-Format enthalten.

*Rect*<br/>
Gibt des StatusBar-Steuerelements die Größe und Position. Es kann sein, entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.

*pParentWnd*<br/>
Gibt an, der Statusleiste übergeordnete Fenster des Steuerelements, in der Regel eine `CDialog`. Es darf nicht NULL sein.

*nID*<br/>
Gibt das StatusBar-Steuerelement ID an.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CStatusBarCtrl` in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen dann `Create`, die das StatusBar-Steuerelement erstellt, und fügt es der `CStatusBarCtrl` Objekt.

Die Standardposition des ein Statusfenster wird am unteren Rand des übergeordneten Fensters, aber Sie können angeben, den Stil CCS_TOP-Format so, dass sie am oberen Rand der Clientbereich des übergeordneten Fensters angezeigt werden. Sie können den Stil SBARS_SIZEGRIP einen Größenziehpunkt am rechten Ende das Statusfenster enthält angeben. Kombiniert die Stile CCS_TOP-Format und SBARS_SIZEGRIP wird nicht empfohlen, da der resultierende Größenziehpunkt nicht funktionsfähig ist, auch wenn das System im Statusfenster zeichnet.

Rufen Sie zum Erstellen einer Statusleiste mit erweiterten Fensterstile [CStatusBarCtrl::CreateEx](#createex) anstelle von `Create`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

##  <a name="createex"></a>  CStatusBarCtrl::CreateEx

Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet ihn dem `CStatusBarCtrl` Objekt.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwExStyle*<br/>
Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Windows-Stile, finden Sie unter den *DwExStyle* -Parameter für [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) im Windows SDK.

*dwStyle*<br/>
Gibt das StatusBar-Steuerelement Stil. Wenden Sie eine beliebige Kombination der Stile von Listensteuerelementen aufgeführt, die der Statusleiste [allgemeinen Stile von Listensteuerelementen](/windows/desktop/Controls/common-control-styles) im Windows SDK. Dieser Parameter muss das Format WS_CHILD enthalten. Darüber sollte hinaus das WS_VISIBLE-Format enthalten.

*Rect*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt *pParentWnd*.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.

*nID*<br/>
Der ID des Steuerelements untergeordneten Fensters mit.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende Erweiterte Windows-Stile, angegeben durch den Wert der Windows-erweiterten Stil **WS_EX_**.

##  <a name="cstatusbarctrl"></a>  CStatusBarCtrl::CStatusBarCtrl

Erstellt ein `CStatusBarCtrl`-Objekt.

```
CStatusBarCtrl();
```

##  <a name="drawitem"></a>  CStatusBarCtrl::DrawItem

Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt ein ownerdrawn-Statusleisten-Steuerelements ändert.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein long-Zeiger auf eine [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) -Struktur, Informationen über den Typ der Zeichnung, die erforderlich sind enthält.

### <a name="remarks"></a>Hinweise

Die `itemAction` Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll.

Standardmäßig ist diese Member-Funktion mit "nothing". Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CStatusBarCtrl` Objekt.

Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext in angegeben wiederherstellen *LpDrawItemStruct* vor diesem Member Funktion beendet wird.

##  <a name="getborders"></a>  CStatusBarCtrl::GetBorders

Ruft das StatusBar-Steuerelement die aktuelle Breite der horizontalen und vertikalen Rahmen und der Abstand zwischen den Rechtecken ab.

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>Parameter

*pBorders*<br/>
Die Adresse eines Arrays von Ganzzahlen durch drei Elemente. Das erste Element empfängt die Breite des horizontalen Rands, die zweite erhält die Breite des vertikalen Rands und das dritte erhält die Breite des Rahmens zwischen Rechtecken.

*nHorz*<br/>
Verweis auf eine ganze Zahl, die die Breite des horizontalen Rands empfängt.

*Umwandeln*<br/>
Verweis auf eine ganze Zahl, die die Breite des vertikalen Rands empfängt.

*nSpacing*<br/>
Verweis auf eine ganze Zahl, die die Breite des Rahmens zwischen Rechtecken empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Dieser Rahmen bestimmt den Abstand zwischen den äußeren Rand des Steuerelements und den Rechtecken innerhalb des Steuerelements, die Text enthalten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

##  <a name="geticon"></a>  CStatusBarCtrl::GetIcon

Ruft das Symbol für einen Teil (auch bekannt als ein Bereich) in das aktuelle StatusBar-Steuerelement ab.

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iPart*|[in] Der nullbasierte Index des Teils, der das Symbol abgerufen werden sollen. Wenn dieser Parameter-1 ist, wird angenommen, dass die Statusleiste einer einfachen Modus Statusleiste angezeigt werden.|

### <a name="return-value"></a>Rückgabewert

Das Handle für das Symbol "Wenn die Methode erfolgreich ist; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [SB_GETICON](/windows/desktop/Controls/sb-geticon) -Nachricht, die im Windows SDK beschrieben wird.

Ein Statusleisten-Steuerelement besteht aus einer Zeile von Textausgabebereichen, auch bekannt als Teile sind. Weitere Informationen zu der Statusleiste, finden Sie unter [Status Befehlsleisten-Standardimplementierung in MFC](../../mfc/status-bar-implementation-in-mfc.md) und [Festlegen des CStatusBarCtrl-Objektmodus](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert eine Variable, `m_statusBar`, d. h. für den Zugriff auf das aktuelle StatusBar-Steuerelement. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel kopiert ein Symbol in zwei Bereiche, der das aktuelle StatusBar-Steuerelement. In einem vorherigen Abschnitt des Codebeispiels müssen wir ein Statusleisten-Steuerelement mit drei Bereiche erstellt und dann ein Symbol im ersten Bereich hinzugefügt. In diesem Beispiel ruft das Symbol ab, aus dem ersten Bereich, und klicken Sie dann in den zweiten und dritten Bereich hinzugefügt.

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

##  <a name="getparts"></a>  CStatusBarCtrl::GetParts

Ruft die Anzahl der Teile in ein Statusleisten-Steuerelement ab.

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>Parameter

*nParts*<br/>
Anzahl der Teile der Koordinaten abgerufen werden soll. Wenn dieser Parameter größer als die Anzahl der Teile in das Steuerelement ist, ruft die Nachricht die Koordinaten für die vorhandenen Komponenten nur ab.

*pParts*<br/>
Die Adresse eines Arrays von Ganzzahlen müssen die gleiche Anzahl von Elementen als die Anzahl der Teile, die anhand des *nParts*. Jedes Element im Array empfängt der Clientkoordinate des rechten Rands des entsprechenden Teils. Wenn ein Element festgelegt ist – erweitert 1, die Position des rechten Rands für den jeweiligen Teil an den rechten Rand der Statusleiste an.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in das Steuerelement im Erfolgsfall oder andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ruft auch die Koordinate des rechten Rands der angegebenen Anzahl von Teilen ab.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

##  <a name="getrect"></a>  CStatusBarCtrl::GetRect

Ruft das umschließende Rechteck eines Parts im ein Statusleisten-Steuerelement ab.

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*nPane*<br/>
Nullbasierte Index des Teils ist, dessen umschließendes Rechteck abgerufen werden.

*lpRect*<br/>
Adresse von einem [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das umschließende Rechteck empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

##  <a name="gettext"></a>  CStatusBarCtrl:: GetText

Ruft den Text aus den angegebenen Teil ein Statusleisten-Steuerelement ab.

```
CString GetText(
    int nPane,
    int* pType = NULL) const;

int GetText(
    LPCTSTR lpszText,
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Die Adresse des Puffers, der den Text empfängt. Dieser Parameter ist ein Null-terminierte Zeichenfolge.

*nPane*<br/>
Nullbasierte Index des Teils in der Text abgerufen werden soll.

*PGeben*<br/>
Zeiger auf eine ganze Zahl, die die Typinformationen empfängt. Der Typ kann einen der folgenden Werte sein:

- **0** mit einem Rahmen niedriger als die Ebene der Statusleiste angezeigt werden. der Text gezeichnet wird.

- SBT_NOBORDERS, die der Text ohne Rahmen gezeichnet wird.

- SBT_POPOUT der Text gezeichnet wird mit einem Rahmen höher als die Ebene der Statusleiste angezeigt werden.

- SBT_OWNERDRAW, wenn der Text wurde der Typ, der Zeichnung SBT_OWNERDRAW *PGeben* empfängt diese Nachricht und gibt den 32-Bit-Wert mit dem Text anstelle der Länge und den Vorgang.

### <a name="return-value"></a>Rückgabewert

Die Länge in Zeichen des Texts oder [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die den aktuellen Text enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

##  <a name="gettextlength"></a>  CStatusBarCtrl:: getTextLength

Ruft die Länge in Zeichen des Texts aus dem angegebenen Teil des ein Statusleisten-Steuerelement ab.

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>Parameter

*nPane*<br/>
Nullbasierte Index des Teils in der Text abgerufen werden soll.

*PGeben*<br/>
Zeiger auf eine ganze Zahl, die die Typinformationen empfängt. Der Typ kann einen der folgenden Werte sein:

- **0** mit einem Rahmen niedriger als die Ebene der Statusleiste angezeigt werden. der Text gezeichnet wird.

- SBT_NOBORDERS, die der Text ohne Rahmen gezeichnet wird.

- SBT_OWNERDRAW der Text wird vom übergeordneten Fenster gezeichnet.

- SBT_POPOUT der Text gezeichnet wird mit einem Rahmen höher als die Ebene der Statusleiste angezeigt werden.

### <a name="return-value"></a>Rückgabewert

Die Länge in Zeichen des Texts.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

##  <a name="gettiptext"></a>  CStatusBarCtrl::GetTipText

Ruft den QuickInfo-Text für einen Bereich in einer Statusleiste ab.

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>Parameter

*nPane*<br/>
Der nullbasierte Index des Statusleistenbereich zum Empfangen von des QuickInfo-Texts.

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt mit dem Text in der QuickInfo verwendet werden.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_GETTIPTEXT](/windows/desktop/Controls/sb-gettiptext), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

##  <a name="issimple"></a>  CStatusBarCtrl::IsSimple

Überprüft, um festzustellen, ob es sich im einfachen Modus ist ein Fenster-Steuerelement.

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist das Window-Steuerelement von Status im einfachen Modus; andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_ISSIMPLE](/windows/desktop/Controls/sb-issimple), wie im Windows SDK beschrieben.

##  <a name="setbkcolor"></a>  CStatusBarCtrl::SetBkColor

Legt die Hintergrundfarbe in einer Statusleiste fest.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Parameter

*CR*<br/>
COLORREF-Wert, der die neue Hintergrundfarbe angibt. Geben Sie den Wert CLR_DEFAULT dazu führen, dass verwenden Sie die Standard-Hintergrundfarbe die Statusleiste an.

### <a name="return-value"></a>Rückgabewert

Ein [COLORREF](/windows/desktop/gdi/colorref) Wert, der vorherigen Standard-Hintergrundfarbe darstellt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_SETBKCOLOR](/windows/desktop/Controls/sb-setbkcolor), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

##  <a name="seticon"></a>  CStatusBarCtrl::SetIcon

Legt das Symbol für einen Bereich in einer Statusleiste fest.

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>Parameter

*nPane*<br/>
Der nullbasierte Index des Bereichs, der das Symbol "erhält. Wenn dieser Parameter-1 ist, wird angenommen, dass die Statusleiste eine einfache Statusleiste werden.

*hIcon*<br/>
Handle für das Symbol "festgelegt werden. Wenn dieser Wert NULL ist, wird das Symbol aus dem Element entfernt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_SETICON](/windows/desktop/Controls/sb-seticon), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CStatusBarCtrl::SetBkColor](#setbkcolor).

##  <a name="setminheight"></a>  CStatusBarCtrl::SetMinHeight

Legt die minimale Höhe des Status steuerleistenbereichs Zeichnen des Steuerelements fest.

```
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>Parameter

*nmin.*<br/>
Minimale Höhe des Steuerelements in Pixel.

### <a name="remarks"></a>Hinweise

Die minimale Höhe ist die Summe der *nmin* und zweimal die Breite des vertikalen Rands des das StatusBar-Steuerelement in Pixel.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

##  <a name="setparts"></a>  CStatusBarCtrl::SetParts

Legt die Anzahl der Teile in einer Statusleisten-Steuerelement und die Koordinate des rechten Rands der einzelnen Teile fest.

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>Parameter

*nParts*<br/>
Die Anzahl von Teilen zu legen. Die Anzahl der Teile darf nicht mehr als 255 Zeichen sein.

*pWidths*<br/>
Die Adresse eines Arrays von Ganzzahlen müssen die gleiche Anzahl von Elementen als Teile, die anhand des *nParts*. Jedes Element im Array gibt die Position des rechten Rands des entsprechenden Teils in Clientkoordinaten. Wenn ein Element - 1, erweitert sich die Position des rechten Rands für den jeweiligen Teil an den rechten Rand des Steuerelements.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

##  <a name="setsimple"></a>  CStatusBarCtrl::SetSimple

Gibt an, ob ein Statusleisten-Steuerelement einfachen Text zeigt oder alle Steuerelementteile, die von einem vorherigen Aufruf von festgelegt [Sie SetParts](#setparts).

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>Parameter

*bSimple*<br/>
[in] Anzeigetyp Flag. Wenn dieser Parameter TRUE ist, zeigt das Steuerelement einfachen Text an. Wenn sie auf "FALSE" ist, wird mehrere Teile angezeigt.

### <a name="return-value"></a>Rückgabewert

Gibt immer 0 zurück.

### <a name="remarks"></a>Hinweise

Wenn Ihre Anwendung das StatusBar-Steuerelement von nicht einfacher in einfache (oder umgekehrt) geändert wird, zeichnet das System sofort das Steuerelement neu.

##  <a name="settext"></a>  CStatusBarCtrl::SetText

Legt den Text im bestimmten Teil eines Statusleisten-Steuerelements fest.

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Adresse einer mit NULL endenden Zeichenfolge, die den festzulegenden Text angibt. Wenn *nType* ist SBT_OWNERDRAW, *LpszText* 32 Bits der Daten darstellt.

*nPane*<br/>
Der nullbasierte Index des festzulegenden Teils. Wenn dieser Wert 255 ist, wird angenommen, dass das Statusleisten-Steuerelement ein einfaches Steuerelement mit nur einem Teil ist.

*nType*<br/>
Der Typ des Zeichenvorgangs. Finden Sie unter [SB_SETTEXT Meldung](/windows/desktop/Controls/sb-settext) eine Liste von möglichen Werten.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Nachricht wird den Teil des Steuerelements, das geändert wurde, aufgrund dessen der neue Text angezeigt, wenn das Steuerelement als Nächstes die WM_PAINT-Meldung erhält, ungültig.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

##  <a name="settiptext"></a>  CStatusBarCtrl:: setTipText

Legt die QuickInfo-Text für einen Bereich in einer Statusleiste fest.

```
void SetTipText(
    int nPane,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Parameter

*nPane*<br/>
Der nullbasierte Index des Statusleistenbereich zum Empfangen von des QuickInfo-Texts.

*pszTipText*<br/>
Ein Zeiger auf eine Zeichenfolge, die den QuickInfo-Text enthält.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_SETTIPTEXT](/windows/desktop/Controls/sb-settiptext), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl-Klasse](../../mfc/reference/ctoolbarctrl-class.md)
