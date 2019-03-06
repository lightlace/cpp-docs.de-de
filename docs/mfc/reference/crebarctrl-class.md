---
title: CReBarCtrl-Klasse
ms.date: 11/19/2018
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
ms.openlocfilehash: db72dbab14db69f14d7c3d813562ec661df4b424
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417657"
---
# <a name="crebarctrl-class"></a>CReBarCtrl-Klasse

Kapselt die Funktionalität eines Grundleisten-Steuerelements. Dabei handelt es sich um einen Container für ein untergeordnetes Fenster.

## <a name="syntax"></a>Syntax

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|Erstellt ein `CReBarCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CReBarCtrl::BeginDrag](#begindrag)|Platziert die Grundleisten-Steuerelement in den Drag & Drop-Modus.|
|[CReBarCtrl::Create](#create)|Erstellt das Grundleistensteuerelement, und fügt es der `CReBarCtrl` Objekt.|
|[CReBarCtrl::CreateEx](#createex)|Erstellt von einem Grundleisten-Steuerelement mit der angegebenen Erweiterte Stile für Windows und fügt sie an einer `CReBarCtrl` Objekt.|
|[CReBarCtrl::DeleteBand](#deleteband)|Löscht ein Band von einem Infoleisten-Steuerelement.|
|[CReBarCtrl::DragMove](#dragmove)|Aktualisiert die Position ziehen Sie in der Grundleisten-Steuerelement nach einem Aufruf von `BeginDrag`.|
|[CReBarCtrl::EndDrag](#enddrag)|Beendet das Grundleistensteuerelement Drag & Drop-Vorgang.|
|[CReBarCtrl::GetBandBorders](#getbandborders)|Ruft die Rahmen eines Bandes ab.|
|[CReBarCtrl::GetBandCount](#getbandcount)|Ruft die Anzahl der Bänder, die derzeit in der Infoleisten-Steuerelements ab.|
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Ruft Informationen über ein angegebenes Band in einem Grundleisten-Steuerelement ab.|
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Ruft die Ränder eines Bandes ab.|
|[CReBarCtrl::GetBarHeight](#getbarheight)|Ruft die Höhe des Infoleiste-Steuerelements ab.|
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Ruft Informationen über Infoleisten-Steuerelements und der verwendeten Bildliste ab.|
|[CReBarCtrl::GetBkColor](#getbkcolor)|Ruft die Standardhintergrundfarbe eines Grundleisten-Steuerelements ab.|
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Ruft die [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) Struktur Infoleisten-Steuerelements zugeordnet ist.|
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Ruft ein Grundleistensteuerelement `IDropTarget` Schnittstellenzeiger auf.|
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Ruft den erweiterten Stil des aktuellen Infoleisten-Steuerelements ab.|
|[CReBarCtrl::GetImageList](#getimagelist)|Ruft die einem Grundleistensteuerelement zugeordnete Bildliste ab.|
|[CReBarCtrl::GetPalette](#getpalette)|Ruft die aktuelle Palette des Infoleistensteuerelements ab.|
|[CReBarCtrl::GetRect](#getrect)|Ruft das umschließende Rechteck für ein bestimmtes Band in einem Grundleisten-Steuerelement ab.|
|[CReBarCtrl::GetRowCount](#getrowcount)|Ruft die Anzahl der-Band-Zeilen in einem Grundleisten-Steuerelement ab.|
|[CReBarCtrl::GetRowHeight](#getrowheight)|Ruft die Höhe einer angegebenen Zeile in einem Grundleisten-Steuerelement ab.|
|[CReBarCtrl::GetTextColor](#gettextcolor)|Ruft die Standardtextfarbe eines Grundleisten-Steuerelements ab.|
|[CReBarCtrl::GetToolTips](#gettooltips)|Ruft das Handle für alle Grundleisten-Steuerelement zugeordneten QuickInfo-Steuerelement ab.|
|[CReBarCtrl::HitTest](#hittest)|Bestimmt, welcher Teil ein Infoleistenband wird zu einem bestimmten Zeitpunkt auf dem Bildschirm, wenn ein Infoleistenband an diesem Punkt vorhanden ist.|
|[CReBarCtrl::IDToIndex](#idtoindex)|Konvertiert einen-Band-Bezeichner (ID) in einen Index-Band-in einem Grundleisten-Steuerelement.|
|[CReBarCtrl::InsertBand](#insertband)|Fügt ein neues Band in einem Grundleisten-Steuerelement ein.|
|[CReBarCtrl::MaximizeBand](#maximizeband)|Wird ein Band in einem Grundleisten-Steuerelement, auf die maximale Größe an.|
|[CReBarCtrl::MinimizeBand](#minimizeband)|Wird ein Band in einem Grundleisten-Steuerelement, auf die kleinste Größe angepasst.|
|[CReBarCtrl::MoveBand](#moveband)|Verschiebt ein Band aus einem Index.|
|[CReBarCtrl::PushChevron](#pushchevron)|Programmgesteuertes überträgt ein Steuerzeichen ein.|
|[CReBarCtrl::RestoreBand](#restoreband)|Wird ein Band in einem Grundleisten-Steuerelement, um die ideale Größe angepasst.|
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Legt die Eigenschaften einer vorhandenen Band in einem Grundleisten-Steuerelement fest.|
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Legt die Breite des angegebenen angedockten Band in der aktuellen Grundleisten-Steuerelement fest.|
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Legt die Eigenschaften eines Grundleisten-Steuerelements fest.|
|[CReBarCtrl::SetBkColor](#setbkcolor)|Legt die Standardhintergrundfarbe eines Grundleisten-Steuerelements fest.|
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Legt das Farbschema für die Schaltflächen auf einem Grundleisten-Steuerelement fest.|
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Legt fest, die erweiterten Stile für das aktuelle Grundleistensteuerelement.|
|[CReBarCtrl::SetImageList](#setimagelist)|Legt die Bildliste einem Grundleisten-Steuerelement fest.|
|[CReBarCtrl::SetOwner](#setowner)|Legt die besitzende Fenster einem Grundleisten-Steuerelement fest.|
|[CReBarCtrl::SetPalette](#setpalette)|Legt die aktuelle Palette des Infoleistensteuerelements fest.|
|[CReBarCtrl::SetTextColor](#settextcolor)|Legt die Standardtextfarbe eines Grundleisten-Steuerelements fest.|
|[CReBarCtrl::SetToolTips](#settooltips)|Ordnet das Grundleistensteuerelement ein QuickInfo-Steuerelement hinzu.|
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Legt den visuellen Stil des Infoleisten-Steuerelements fest.|
|[CReBarCtrl::ShowBand](#showband)|Anzeigen oder Ausblenden von einem bestimmten Sperrband in einem Grundleisten-Steuerelement.|
|[CReBarCtrl::SizeToRect](#sizetorect)|Entspricht einem Grundleisten-Steuerelement zu einem bestimmten Rechteck.|

## <a name="remarks"></a>Hinweise

Die Anwendung, die in der Infoleisten-Steuerelements befindet weist das untergeordnete Fenster Infoleisten-Steuerelements, das Infoleistenband enthalten sind. Das untergeordnete Fenster ist normalerweise eine andere Standardsteuerelements.

Grundleisten-Steuerelemente enthalten eine oder mehrere Bänder. Jedes Band kann es sich um eine Kombination aus eine Ziehpunktleiste, eine Bitmap, einer textbezeichnung und einem untergeordneten Fenster enthalten. Das Band kann nur jeweils eine der folgenden Elemente enthalten.

Infoleisten-Steuerelements kann das untergeordnete Fenster über eine angegebene Hintergrundbitmap angezeigt. Alle Bänder von Grundleisten-Steuerelement können geändert werden, mit Ausnahme derjenigen, die den Stil RBBS_FIXEDSIZE verwenden. Wie Sie neu positionieren, oder ändern ein Infoleistenband-Steuerelement, verwaltet das Grundleistensteuerelement die Größe und Position des untergeordneten Fensters, das Band zugewiesen. Klicken Sie zum Ändern der Größe oder die Reihenfolge der Bänder innerhalb des Steuerelements ändern, klicken Sie auf, und ziehen Sie die Ziehpunktleiste des Bands.

Die folgende Abbildung zeigt ein Grundleistensteuerelement, das drei Bändern:

- Band 0 enthält eine Flatfile, transparente Symbolleisten-Steuerelement.

- Band 1 enthält beide transparent Standard- und transparent Dropdown-Schaltfläche.

- Band 2 enthält ein Kombinationsfeld und vier Standardschaltflächen.

   ![Beispiel eines grundleistenmenüs](../../mfc/reference/media/vc4scc1.gif "Beispiel eines grundleistenmenüs")

## <a name="rebar-control"></a>Grundleisten-Steuerelement

Grundleisten Sie-Steuerelemente unterstützen:

- Bilderlisten.

- Nachrichtenverarbeitung.

- Benutzerdefiniertes Zeichnen-Funktionalität.

- Eine Vielzahl von Steuerelementtypen für die zusätzlich zum standard-Window-Stile. Eine Liste dieser Stile, finden Sie unter [Stile für Grundleisten-Steuerelemente](/windows/desktop/Controls/rebar-control-styles) im Windows SDK.

Weitere Informationen finden Sie unter [Verwenden von CReBarCtrl](../../mfc/using-crebarctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="begindrag"></a>  CReBarCtrl::BeginDrag

Implementiert das Verhalten der Win32-Nachricht [RB_BEGINDRAG](/windows/desktop/Controls/rb-begindrag), wie im Windows SDK beschrieben.

```
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index des Bands, die der Drag & Drop-Vorgang auswirkt.

*dwPos*<br/>
Mit der Maus eines DWORD-Wert, der die Anfangsposition enthält Koordinaten. Die horizontale Koordinate in der LOWORD enthalten ist, und die vertikale Koordinate befindet sich in der HIWORD verschlüsselt ist. Wenn Sie auf "(DWORD)-1" übergeben, verwenden Infoleisten-Steuerelements die Position der Maus bei der letzten-Thread des Steuerelements aufgerufen `GetMessage` oder `PeekMessage`.

##  <a name="create"></a>  CReBarCtrl::Create

Erstellt das Grundleistensteuerelement, und fügt es der `CReBarCtrl` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt die Kombination der Grundleisten-Steuerelement-Formate, die auf das Steuerelement angewendet. Finden Sie unter [Stile für Grundleisten-Steuerelemente](/windows/desktop/Controls/rebar-control-styles) im Windows SDK für eine Liste der unterstützten Formate.

*rect*<br/>
Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Position und Größe des Infoleisten-Steuerelements ist.

*pParentWnd*<br/>
Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Infoleisten-Steuerelements ist. Es darf nicht NULL sein.

*nID*<br/>
Gibt an, das Grundleistensteuerelement-Steuerelement-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Objekt wurde erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Erstellen eines Grundleisten-Steuerelements in zwei Schritten:

1. Rufen Sie [CReBarCtrl](#crebarctrl) zum Erstellen einer `CReBarCtrl` Objekt.

1. Rufen Sie diese Memberfunktion, die Windows Infoleisten-Steuerelements erstellt und fügt es der `CReBarCtrl` Objekt.

Beim Aufruf `Create`, die allgemeinen Steuerelemente werden initialisiert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

##  <a name="createex"></a>  CReBarCtrl::CreateEx

Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet ihn dem `CReBarCtrl` Objekt.

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
Gibt die Kombination der Grundleisten-Steuerelement-Formate, die auf das Steuerelement angewendet. Eine Liste der unterstützten Formate, finden Sie unter [Stile für Grundleisten-Steuerelemente](/windows/desktop/Controls/rebar-control-styles) im Windows SDK.

*rect*<br/>
Ein Verweis auf eine [RECT](/previous-versions/dd162897\(v=vs.85\)) Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt *pParentWnd*.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.

*nID*<br/>
Der ID des Steuerelements untergeordneten Fensters mit.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende Erweiterte Windows-Stile, angegeben durch den Wert der Windows-erweiterten Stil **WS_EX_**.

##  <a name="crebarctrl"></a>  CReBarCtrl::CReBarCtrl

Erstellt ein `CReBarCtrl`-Objekt.

```
CReBarCtrl();
```

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CReBarCtrl::Create](#create).

##  <a name="deleteband"></a>  CReBarCtrl::DeleteBand

Implementiert das Verhalten der Win32-Nachricht [RB_DELETEBAND](/windows/desktop/Controls/rb-deleteband), wie im Windows SDK beschrieben.

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index des Bands gelöscht werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Band wurde erfolgreich gelöscht; andernfalls 0 (null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

##  <a name="dragmove"></a>  CReBarCtrl::DragMove

Implementiert das Verhalten der Win32-Nachricht [RB_DRAGMOVE](/windows/desktop/Controls/rb-dragmove), wie im Windows SDK beschrieben.

```
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parameter

*dwPos*<br/>
Eine DWORD-Wert, der die neuen Koordinaten enthält. Die horizontale Koordinate in der LOWORD enthalten ist, und die vertikale Koordinate befindet sich in der HIWORD verschlüsselt ist. Wenn Sie auf "(DWORD)-1" übergeben, verwenden Infoleisten-Steuerelements die Position der Maus bei der letzten-Thread des Steuerelements aufgerufen `GetMessage` oder `PeekMessage`.

##  <a name="enddrag"></a>  CReBarCtrl::EndDrag

Implementiert das Verhalten der Win32-Nachricht [RB_ENDDRAG](/windows/desktop/Controls/rb-enddrag), wie im Windows SDK beschrieben.

```
void EndDrag();
```

##  <a name="getbandborders"></a>  CReBarCtrl::GetBandBorders

Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDBORDERS](/windows/desktop/Controls/rb-getbandborders), wie im Windows SDK beschrieben.

```
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index des dem Band für das die Rahmen abgerufen werden sollen.

*prc*<br/>
Ein Zeiger auf eine [RECT](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Rahmen-Band-erhält. Wenn Infoleisten-Steuerelements styl RBS_BANDBORDERS verfügt, erhält jedes Mitglied dieser Struktur die Anzahl der Pixel, auf der entsprechenden Seite des Bands, die den Rahmen darstellen. Wenn Infoleisten-Steuerelements keinen styl RBS_BANDBORDERS, empfängt nur das linke Element dieser Struktur gültige Informationen. Eine Beschreibung der Stile für Grundleisten-Steuerelemente, finden Sie unter [Steuerelementtypen für die Grundleiste](/windows/desktop/Controls/rebar-control-styles) im Windows SDK.

##  <a name="getbandcount"></a>  CReBarCtrl::GetBandCount

Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDCOUNT](/windows/desktop/Controls/rb-getbandcount), wie im Windows SDK beschrieben.

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bänder, die dem Steuerelement zugewiesen werden soll.

##  <a name="getbandinfo"></a>  CReBarCtrl::GetBandInfo

Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDINFO](/windows/desktop/Controls/rb-getbandinfo) wie beschrieben in das Windows SDK.

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index des dem Band für das die Informationen abgerufen werden sollen.

*prbbi*<br/>
Ein Zeiger auf eine [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) Struktur, die-Band-Informationen zu erhalten. Müssen Sie festlegen, die `cbSize` Mitglied dieser Struktur zu `sizeof(REBARBANDINFO)` und legen Sie die `fMask` Mitglied zu den Elementen, die vor dem Senden dieser Nachricht abgerufen werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

##  <a name="getbandmargins"></a>  CReBarCtrl::GetBandMargins

Ruft die Ränder des Bands ab.

```
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>Parameter

*pMargins*<br/>
Ein Zeiger auf eine [RÄNDER](/windows/desktop/api/uxtheme/ns-uxtheme-_margins)-Struktur, die die Informationen zu erhalten.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen des die [RB_GETBANDMARGINS](/windows/desktop/Controls/rb-getbandmargins) Nachricht, wie im Windows SDK beschrieben.

##  <a name="getbarheight"></a>  CReBarCtrl::GetBarHeight

Ruft die Höhe des Balkens Infoleiste ab.

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>Rückgabewert

Der Wert, der die Höhe des Steuerelements in Pixel darstellt.

##  <a name="getbarinfo"></a>  CReBarCtrl::GetBarInfo

Implementiert das Verhalten der Win32-Nachricht [RB_GETBARINFO](/windows/desktop/Controls/rb-getbarinfo), wie im Windows SDK beschrieben.

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>Parameter

*prbi*<br/>
Ein Zeiger auf eine [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) -Struktur, die die Grundleisten-Steuerelement-Informationen erhält. Sie müssen festlegen, die *CbSize* Mitglied dieser Struktur zu `sizeof(REBARINFO)` vor dem Senden dieser Nachricht.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

##  <a name="getbkcolor"></a>  CReBarCtrl::GetBkColor

Implementiert das Verhalten der Win32-Nachricht [RB_GETBKCOLOR](/windows/desktop/Controls/rb-getbkcolor), wie im Windows SDK beschrieben.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Rückgabewert

Eine COLORREF-Wert, der die aktuelle Standardhintergrundfarbe darstellen.

##  <a name="getcolorscheme"></a>  CReBarCtrl::GetColorScheme

Ruft die [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) Struktur für das Grundleistensteuerelement.

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parameter

*lpcs*<br/>
Ein Zeiger auf eine [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) Struktur, wie im Windows SDK beschrieben.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Die `COLORSCHEME` Struktur umfasst die Hervorhebungsfarbe für Schaltfläche und die Schattenfarbe der Schaltfläche.

##  <a name="getdroptarget"></a>  CReBarCtrl::GetDropTarget

Implementiert das Verhalten der Win32-Nachricht [RB_GETDROPTARGET](/windows/desktop/Controls/rb-getdroptarget), wie im Windows SDK beschrieben.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) Schnittstelle.

##  <a name="getextendedstyle"></a>  CReBarCtrl::GetExtendedStyle

Ruft die erweiterten Stile des aktuellen Infoleisten-Steuerelements ab.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Eine bitweise Kombination (OR) von Flags, die die erweiterten Stile angeben. Die möglichen Flags sind RBS_EX_SPLITTER und RBS_EX_TRANSPARENT. Weitere Informationen finden Sie unter den *DwMask* Parameter, der die [CReBarCtrl::SetExtendedStyle](#setextendedstyle) Methode.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [RB_GETEXTENDEDSTYLE](/windows/desktop/Controls/rb-dragmove) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getimagelist"></a>  CReBarCtrl::GetImageList

Ruft die `CImageList` Objekt mit einem Grundleisten-Steuerelement verknüpft ist.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt. Gibt NULL zurück, wenn keine Bildliste für das Steuerelement festgelegt ist.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion verwendet Größe und der Maske in gespeicherten Informationen dem [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) Struktur, wie im Windows SDK beschrieben.

##  <a name="getpalette"></a>  CReBarCtrl::GetPalette

Ruft die aktuelle Palette des Infoleistensteuerelements ab.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md) Objekt, das aktuelle Palette des Infoleistensteuerelements angibt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion verwendet ein `CPalette` Objekt als ihren Rückgabewert, anstatt eine HPALETTE.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

##  <a name="getrect"></a>  CReBarCtrl::GetRect

Implementiert das Verhalten der Win32-Nachricht [RB_GETRECT](/windows/desktop/Controls/rb-getrect), wie im Windows SDK beschrieben.

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index, der ein Band in der Grundleisten-Steuerelement.

*prc*<br/>
Ein Zeiger auf eine [RECT](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Grenzen des das Infoleistenband erhält.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

##  <a name="getrowcount"></a>  CReBarCtrl::GetRowCount

Implementiert das Verhalten der Win32-Nachricht [RB_GETROWCOUNT](/windows/desktop/Controls/rb-getrowcount), wie im Windows SDK beschrieben.

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>Rückgabewert

Ein UINT-Wert, der die Anzahl der Band Zeilen im Steuerelement darstellt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

##  <a name="getrowheight"></a>  CReBarCtrl::GetRowHeight

Implementiert das Verhalten der Win32-Nachricht [RB_GETROWHEIGHT](/windows/desktop/Controls/rb-getrowheight), wie im Windows SDK beschrieben.

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>Parameter

*uRow*<br/>
Nullbasierte Index des Bands, die die Höhe abgerufen hat.

### <a name="return-value"></a>Rückgabewert

Ein UINT-Wert, der die Zeilenhöhe in Pixel darstellt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

##  <a name="gettextcolor"></a>  CReBarCtrl::GetTextColor

Implementiert das Verhalten der Win32-Nachricht [RB_GETTEXTCOLOR](/windows/desktop/Controls/rb-gettextcolor), wie im Windows SDK beschrieben.

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>Rückgabewert

Eine COLORREF-Wert, der die aktuelle Standardtextfarbe darstellen.

##  <a name="gettooltips"></a>  CReBarCtrl::GetToolTips

Implementiert das Verhalten der Win32-Nachricht [RB_GETTOOLTIPS](/windows/desktop/Controls/rb-gettooltips), wie im Windows SDK beschrieben.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass die MFC-Implementierung von `GetToolTips` gibt einen Zeiger auf eine `CToolTipCtrl`, anstatt ein HWND.

##  <a name="hittest"></a>  CReBarCtrl::HitTest

Implementiert das Verhalten der Win32-Nachricht [RB_HITTEST](/windows/desktop/Controls/rb-hittest), wie im Windows SDK beschrieben.

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>Parameter

*prbht*<br/>
Ein Zeiger auf eine [RBHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-_rb_hittestinfo) Struktur. Vor dem Senden der Nachricht, die `pt` Member der Struktur muss initialisiert werden, zu dem Punkt, die getestet werden, in Clientkoordinaten.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des Bands auf dem angegebenen Punkt oder -1, wenn keine Infoleistenband an dem Punkt war.

##  <a name="idtoindex"></a>  CReBarCtrl::IDToIndex

Implementiert das Verhalten der Win32-Nachricht [RB_IDTOINDEX](https://msdn.microsoft.com/library/windows/desktop/bb774496), wie im Windows SDK beschrieben.

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>Parameter

*uBandID*<br/>
Der anwendungsspezifische Bezeichner des angegebenen Bands, übergeben wird, der `wID` Mitglied der [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) Struktur, wenn das Band eingefügt wird.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte-Band-Index im Erfolgsfall oder andernfalls -1. Wenn doppelte-Band-Indizes vorhanden sind, wird das erste Abonnement zurückgegeben.

##  <a name="insertband"></a>  CReBarCtrl:: InsertBand

Implementiert das Verhalten der Win32-Nachricht [RB_INSERTBAND](/windows/desktop/Controls/rb-insertband), wie im Windows SDK beschrieben.

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parameter

*uIndex*<br/>
Nullbasierte Index des Speicherorts, in dem das Band eingefügt wird. Wenn Sie diesen Parameter auf-1 festlegen, wird das Steuerelement das neue Band an der letzten Position hinzufügen.

*prbbi*<br/>
Ein Zeiger auf eine [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) -Struktur, die definiert, das Band eingefügt werden soll. Sie müssen festlegen, die *CbSize* Mitglied dieser Struktur zu `sizeof(REBARBANDINFO)` vor dem Aufrufen dieser Funktion.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

##  <a name="maximizeband"></a>  CReBarCtrl::MaximizeBand

Wird ein Band in einem Grundleisten-Steuerelement, auf die maximale Größe an.

```
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index des Bands, maximiert werden.

### <a name="remarks"></a>Hinweise

Implementiert das Verhalten der Win32-Nachricht [RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband) mit `fIdeal` auf 0 festgelegt, wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

##  <a name="minimizeband"></a>  CReBarCtrl::MinimizeBand

Wird ein Band in einem Grundleisten-Steuerelement, auf die kleinste Größe angepasst.

```
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index des Bands, minimiert werden.

### <a name="remarks"></a>Hinweise

Implementiert das Verhalten der Win32-Nachricht [RB_MINIMIZEBAND](/windows/desktop/Controls/rb-minimizeband), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

##  <a name="moveband"></a>  CReBarCtrl::MoveBand

Implementiert das Verhalten der Win32-Nachricht [RB_MOVEBAND](/windows/desktop/Controls/rb-moveband), wie im Windows SDK beschrieben.

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>Parameter

*uFrom*<br/>
Nullbasierte Index des dem Band verschoben werden soll.

*uTo*<br/>
Nullbasierte Index, der Position des neuen Band. Wert dieses Parameters muss nie größer als die Anzahl der Bänder minus 1 sein. Rufen Sie zum Abrufen der Anzahl der Bänder [GetBandCount](#getbandcount).

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

##  <a name="pushchevron"></a>  CReBarCtrl::PushChevron

Implementiert das Verhalten der Win32-Nachricht [RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron), wie im Windows SDK beschrieben.

```
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index des Bands, deren Chevron wird mithilfe von Push übertragen werden.

*lAppValue*<br/>
Eine Anwendung definiert, 32-Bit-Wert. Finden Sie unter *lAppValue* in [RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron) im Windows SDK.

##  <a name="restoreband"></a>  CReBarCtrl::RestoreBand

Wird ein Band in einem Grundleisten-Steuerelement, um die ideale Größe angepasst.

```
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index des Bands, maximiert werden.

### <a name="remarks"></a>Hinweise

Implementiert das Verhalten der Win32-Nachricht [RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband) mit `fIdeal` auf 1 festgelegt, wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

##  <a name="setbandinfo"></a>  CReBarCtrl::SetBandInfo

Implementiert das Verhalten der Win32-Nachricht [RB_SETBANDINFO](/windows/desktop/Controls/rb-setbandinfo), wie im Windows SDK beschrieben.

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index des Bands auf der neuen Einstellungen zu erhalten.

*prbbi*<br/>
Zeiger auf eine [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) -Struktur, die definiert, das Band eingefügt werden soll. Sie müssen festlegen, die `cbSize` Mitglied dieser Struktur zu `sizeof(REBARBANDINFO)` vor dem Senden dieser Nachricht.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

##  <a name="setbandwidth"></a>  CReBarCtrl::SetBandWidth

Legt die Breite des angegebenen angedockten Band in der aktuellen Grundleisten-Steuerelement fest.

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*uBand*|[in] Nullbasierte Index des ein Infoleistenband.|
|*cxWidth*|[in] Neue Breite des der Infoleistenband in Pixel.|

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [RB_SETBANDWIDTH](/windows/desktop/Controls/rb-setbandwidth) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_rebar`, d. h. für den Zugriff auf das aktuelle Grundleistensteuerelement. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel legt jedes Infoleistenband auf dieselbe Breite fest.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

##  <a name="setbarinfo"></a>  CReBarCtrl::SetBarInfo

Implementiert das Verhalten der Win32-Nachricht [RB_SETBARINFO](/windows/desktop/Controls/rb-setbarinfo), wie im Windows SDK beschrieben.

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>Parameter

*prbi*<br/>
Ein Zeiger auf eine [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) Struktur, die Informationen festgelegt werden. Sie müssen festlegen, die `cbSize` Mitglied dieser Struktur zu `sizeof(REBARINFO)` vor dem Senden dieser Nachricht

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

##  <a name="setbkcolor"></a>  CReBarCtrl::SetBkColor

Implementiert das Verhalten der Win32-Nachricht [RB_SETBKCOLOR](/windows/desktop/Controls/rb-setbkcolor), wie im Windows SDK beschrieben.

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>Parameter

*clr*<br/>
Der COLORREF-Wert, der die neue Standard-Hintergrundfarbe darstellt.

### <a name="return-value"></a>Rückgabewert

Ein [COLORREF](/windows/desktop/gdi/colorref) Wert, der vorherigen Standard-Hintergrundfarbe darstellt.

### <a name="remarks"></a>Hinweise

Finden Sie weitere Informationen, wann die Hintergrundfarbe festgelegt, und wie der Standardwert festgelegt.

##  <a name="setcolorscheme"></a>  CReBarCtrl::SetColorScheme

Legt das Farbschema für die Schaltflächen auf einem Grundleisten-Steuerelement fest.

```
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parameter

*lpcs*<br/>
Ein Zeiger auf eine [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) Struktur, wie im Windows SDK beschrieben.

### <a name="remarks"></a>Hinweise

Die `COLORSCHEME` Struktur umfasst die Hervorhebungsfarbe für Schaltfläche und die Schattenfarbe der Schaltfläche.

##  <a name="setextendedstyle"></a>  CReBarCtrl::SetExtendedStyle

Legt fest, die erweiterten Stile für das aktuelle Grundleistensteuerelement.

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwMask*|[in] Eine bitweise Kombination (OR) von Flags, die angeben, welche Flags-Seite in der *DwStyleEx* Parameter angewendet. Verwenden Sie eine oder mehrere der folgenden Werte ein:<br /><br /> RBS_EX_SPLITTER: Standardmäßig an den Splitter im unteren Bereich im horizontalen Modus, und klicken Sie auf der rechten Seite im vertikalen-Modus.<br /><br /> RBS_EX_TRANSPARENT: Weiterleiten der [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd) Nachricht für das übergeordnete Fenster.|
|*dwStyleEx*|[in] Eine bitweise Kombination (OR) von Flags, die angeben, die Stile angewendet werden. Um einen Stil zu festzulegen, geben Sie das gleiche Flag, das verwendet wird die *DwMask* Parameter. Geben Sie zum Zurücksetzen eines Stils binäre 0 (null).|

### <a name="return-value"></a>Rückgabewert

Die vorherige erweiterten Stil.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [RB_SETEXTENDEDSTYLE](/windows/desktop/Controls/rb-setextendedstyle) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="setimagelist"></a>  CReBarCtrl::SetImageList

Weist eine Bildliste einem Grundleisten-Steuerelement.

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parameter

*pImageList*<br/>
Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, enthält die Liste der Bilder, Infoleisten-Steuerelements zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

##  <a name="setowner"></a>  CReBarCtrl::SetOwner

Implementiert das Verhalten der Win32-Nachricht [RB_SETPARENT](/windows/desktop/Controls/rb-setparent), wie im Windows SDK beschrieben.

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Ein Zeiger auf eine `CWnd` Objekt, das als Besitzer des Infoleisten-Steuerelements festgelegt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das der aktuelle Besitzer des Infoleisten-Steuerelements ist.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass diese Memberfunktion auf Zeigern auf `CWnd` Objekte für den aktuellen und den ausgewählten Besitzer des Infoleisten-Steuerelements, anstatt Windows behandelt.

> [!NOTE]
>  Diese Memberfunktion ändert sich nicht auf das tatsächliche übergeordnete Element aus, das festgelegt wurde, wenn das Steuerelement erstellt wurde; Stattdessen sendet sie Benachrichtigungen an das Fenster, die, das Sie angeben.

##  <a name="setpalette"></a>  CReBarCtrl::SetPalette

Implementiert das Verhalten der Win32-Nachricht [RB_SETPALETTE](/windows/desktop/Controls/rb-setpalette), wie im Windows SDK beschrieben.

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>Parameter

*hPal*<br/>
Ein HPALETTE, der die neue Palette angibt, die das Grundleistensteuerelement verwendet wird.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md) Objekt, das vorherige Palette des Infoleistensteuerelements angibt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion verwendet ein `CPalette` Objekt als ihren Rückgabewert, anstatt eine HPALETTE.

##  <a name="settextcolor"></a>  CReBarCtrl::SetTextColor

Implementiert das Verhalten der Win32-Nachricht [RB_SETTEXTCOLOR](/windows/desktop/Controls/rb-settextcolor), wie im Windows SDK beschrieben.

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>Parameter

*clr*<br/>
Farbe ein COLORREF-Wert, der den neuen Text darstellt, die der `CReBarCtrl` Objekt.

### <a name="return-value"></a>Rückgabewert

Die [COLORREF](/windows/desktop/gdi/colorref) zugeordnete Wert, der die Farbe des vorherigen darstellt der `CReBarCtrl` Objekt.

### <a name="remarks"></a>Hinweise

Er wird bereitgestellt, um Text Color Flexibilität in einem Grundleisten-Steuerelement zu unterstützen.

##  <a name="settooltips"></a>  CReBarCtrl::SetToolTips

Ordnet einem Grundleisten-Steuerelement ein QuickInfo-Steuerelement hinzu.

```
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>Parameter

*pToolTip*<br/>
Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt

### <a name="remarks"></a>Hinweise

Sie müssen Zerstören der `CToolTipCtrl` Objekt, wenn Sie damit fertig sind.

##  <a name="setwindowtheme"></a>  CReBarCtrl::SetWindowTheme

Legt den visuellen Stil des Infoleisten-Steuerelements fest.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parameter

*pszSubAppName*<br/>
Ein Zeiger auf eine Unicode-Zeichenfolge, die den visuellen Stil der Infoleiste festzulegende enthält.

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert wird nicht verwendet.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen des die [RB_SETWINDOWTHEME](/windows/desktop/Controls/rb-setwindowtheme) Nachricht, wie im Windows SDK beschrieben.

##  <a name="showband"></a>  CReBarCtrl::ShowBand

Implementiert das Verhalten der Win32-Nachricht [RB_SHOWBAND](/windows/desktop/Controls/rb-showband), wie im Windows SDK beschrieben.

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Nullbasierte Index, der ein Band in der Grundleisten-Steuerelement.

*fShow*<br/>
Gibt an, ob das Band ein- oder ausgeblendet werden soll. Wenn dieser Wert "true" ist, wird das Band angezeigt. Andernfalls wird das Band ausgeblendet.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

##  <a name="sizetorect"></a>  CReBarCtrl::SizeToRect

Implementiert das Verhalten der Win32-Nachricht [RB_SIZETORECT](/windows/desktop/Controls/rb-sizetorect), wie im Windows SDK beschrieben.

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das das Rechteck angibt, dessen Größe Infoleisten-Steuerelements geändert werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion verwendet ein `CRect` Objekt als Parameter anstelle eines `RECT` Struktur.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
