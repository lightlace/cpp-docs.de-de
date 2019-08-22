---
title: Krebarctrl-Klasse
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
ms.openlocfilehash: 9a8c989988801bc7af993fbc69717ac7cff07dcf
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502742"
---
# <a name="crebarctrl-class"></a>Krebarctrl-Klasse

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
|[CReBarCtrl::BeginDrag](#begindrag)|Versetzt das Grund leisten-Steuerelement in den Drag & Drop-Modus.|
|[CReBarCtrl::Create](#create)|Erstellt das Grund leisten-Steuerelement und fügt es `CReBarCtrl` an das-Objekt an.|
|[CReBarCtrl::CreateEx](#createex)|Erstellt ein Grund leisten-Steuerelement mit den angegebenen erweiterten Windows-Stilen und fügt `CReBarCtrl` es an ein-Objekt an.|
|[CReBarCtrl::DeleteBand](#deleteband)|Löscht ein Band aus einem Grund leisten-Steuerelement.|
|[CReBarCtrl::DragMove](#dragmove)|Aktualisiert die Zieh Position im Grund leisten-Steuerelement nach einem- `BeginDrag`Rückruf.|
|[CReBarCtrl::EndDrag](#enddrag)|Beendet den Drag & Drop-Vorgang des Grund leisten-Steuer Elements.|
|[CReBarCtrl::GetBandBorders](#getbandborders)|Ruft die Rahmen eines Bands ab.|
|[CReBarCtrl::GetBandCount](#getbandcount)|Ruft die Anzahl der Bänder ab, die sich derzeit im Grund leisten-Steuerelement befinden.|
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Ruft Informationen zu einem angegebenen Band in einem Grund leisten-Steuerelement ab.|
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Ruft die Ränder eines Bands ab.|
|[CReBarCtrl::GetBarHeight](#getbarheight)|Ruft die Höhe des Grund leisten-Steuer Elements ab.|
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Ruft Informationen zum Grund leisten-Steuerelement und der von ihm verwendeten Bildliste ab.|
|[CReBarCtrl::GetBkColor](#getbkcolor)|Ruft die Standard Hintergrundfarbe eines Grund leisten-Steuer Elements ab.|
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Ruft die [ColorScheme](/windows/win32/api/commctrl/ns-commctrl-colorscheme) -Struktur ab, die dem Grund leisten-Steuerelement zugeordnet ist.|
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Ruft den Schnittstellen Zeiger eines Grund leisten `IDropTarget` -Steuer Elements ab.|
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Ruft den erweiterten Stil des aktuellen Grund leisten-Steuer Elements ab.|
|[CReBarCtrl::GetImageList](#getimagelist)|Ruft die Bildliste ab, die einem Grund leisten-Steuerelement zugeordnet ist.|
|[CReBarCtrl::GetPalette](#getpalette)|Ruft die aktuelle Palette des Grund leisten-Steuer Elements ab.|
|[CReBarCtrl::GetRect](#getrect)|Ruft das umschließende Rechteck für ein bestimmtes Band in einem Grund leisten-Steuerelement ab.|
|[CReBarCtrl::GetRowCount](#getrowcount)|Ruft die Anzahl der Band Zeilen in einem Grund leisten-Steuerelement ab.|
|[CReBarCtrl::GetRowHeight](#getrowheight)|Ruft die Höhe einer angegebenen Zeile in einem Grund leisten-Steuerelement ab.|
|[CReBarCtrl::GetTextColor](#gettextcolor)|Ruft die Standard Textfarbe eines Grund leisten-Steuer Elements ab.|
|[CReBarCtrl::GetToolTips](#gettooltips)|Ruft das Handle für ein QuickInfo-Steuerelement ab, das dem Grund leisten-Steuerelement zugeordnet ist.|
|[CReBarCtrl::HitTest](#hittest)|Bestimmt, welcher Teil eines Grund leisten Bands an einem bestimmten Punkt auf dem Bildschirm angezeigt wird, wenn ein Info leisten-Band an diesem Punkt vorhanden ist.|
|[CReBarCtrl::IDToIndex](#idtoindex)|Konvertiert einen Band Bezeichner (ID) in einen Band Index in einem Grund leisten-Steuerelement.|
|[CReBarCtrl::InsertBand](#insertband)|Fügt ein neues Band in ein Grund leisten-Steuerelement ein.|
|[CReBarCtrl::MaximizeBand](#maximizeband)|Ändert die Größe eines Bands in einem Grund leisten-Steuerelement auf seine größte Größe.|
|[CReBarCtrl::MinimizeBand](#minimizeband)|Ändert die Größe eines Bands in einem Grund leisten-Steuerelement auf seine kleinste Größe.|
|[CReBarCtrl::MoveBand](#moveband)|Verschiebt ein Band von einem Index zu einem anderen.|
|[CReBarCtrl::PushChevron](#pushchevron)|Überträgt ein Chevron Programm gesteuert.|
|[CReBarCtrl::RestoreBand](#restoreband)|Ändert die Größe eines Bands in einem Grund leisten-Steuerelement auf seine ideale Größe.|
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Legt die Eigenschaften eines vorhandenen Bands in einem Grund leisten-Steuerelement fest.|
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Legt die Breite des angegebenen angedockten Bands im aktuellen Grund leisten-Steuerelement fest.|
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Legt die Eigenschaften eines Grund leisten-Steuer Elements fest.|
|[CReBarCtrl::SetBkColor](#setbkcolor)|Legt die Standard Hintergrundfarbe eines Grund leisten-Steuer Elements fest.|
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Legt das Farbschema für die Schaltflächen eines Grund leisten-Steuer Elements fest.|
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Legt die erweiterten Stile für das aktuelle Grund leisten-Steuerelement fest.|
|[CReBarCtrl::SetImageList](#setimagelist)|Legt die Bildliste eines Grund leisten-Steuer Elements fest.|
|[CReBarCtrl::SetOwner](#setowner)|Legt das Besitzer Fenster eines Grund leisten-Steuer Elements fest.|
|[CReBarCtrl::SetPalette](#setpalette)|Legt die aktuelle Palette des Grund leisten-Steuer Elements fest.|
|[CReBarCtrl::SetTextColor](#settextcolor)|Legt die Standard Textfarbe eines Grund leisten-Steuer Elements fest.|
|[CReBarCtrl::SetToolTips](#settooltips)|Ordnet ein QuickInfo-Steuerelement dem Grund leisten-Steuerelement zu.|
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Legt den visuellen Stil des Grund leisten-Steuer Elements fest.|
|[CReBarCtrl::ShowBand](#showband)|Zeigt ein bestimmtes Band in einem Grund leisten-Steuerelement an oder blendet es aus.|
|[CReBarCtrl::SizeToRect](#sizetorect)|Passt ein Grund leisten-Steuerelement an ein angegebenes Rechteck an.|

## <a name="remarks"></a>Hinweise

Die Anwendung, in der das Grund leisten-Steuerelement residiert, weist das untergeordnete Fenster, das im Info leisten-Steuerelement enthalten ist, dem Info leisten- Das untergeordnete Fenster ist in der Regel ein weiteres häufiges Steuerelement.

Die Grund leisten-Steuerelemente enthalten ein oder mehrere Bänder. Jedes Band kann eine Kombination aus einer Zieh Punkt Leiste, einer Bitmap, einer Text Bezeichnung und einem untergeordneten Fenster enthalten. Das Band kann nur eines dieser Elemente enthalten.

Das Grund leisten-Steuerelement kann das untergeordnete Fenster über einer angegebenen Hintergrund Bitmap anzeigen. Für alle Grund leisten-Steuerelemente kann die Größe geändert werden, mit Ausnahme derjenigen, die den RBBS_FIXEDSIZE-Stil verwenden. Beim Neupositionieren oder Ändern der Größe eines Grund leisten-Steuer Elements verwaltet das Grund leisten-Steuerelement die Größe und Position des untergeordneten Fensters, das diesem Band zugewiesen ist. Wenn Sie die Größe der Bänder im Steuerelement ändern oder ändern möchten, klicken und ziehen Sie die Zieh Punkt Leiste eines Bands.

Die folgende Abbildung zeigt ein Grund leisten-Steuerelement, das drei Bänder umfasst:

- Band 0 enthält ein flaches, transparentes Symbolleisten-Steuerelement.

- Band 1 enthält sowohl transparente Standard-als auch transparente Dropdown-Schaltflächen.

- Band 2 enthält ein Kombinations Feld und vier Standard Schaltflächen.

   ![Beispiel für ein Rebar-Menü](../../mfc/reference/media/vc4scc1.gif "Beispiel für ein Rebar-Menü")

## <a name="rebar-control"></a>Grund leisten-Steuerelement

Unterstützung für Grund leisten Steuerelemente:

- Bildlisten.

- Nachrichtenverarbeitung.

- Benutzerdefinierte Zeichnungsfunktionen.

- Eine Reihe von Steuerelement Stilen zusätzlich zu Standardfenster Stilen. Eine Liste dieser Stile finden Sie Untergrund leisten- [Steuerelement Stile](/windows/win32/Controls/rebar-control-styles) in der Windows SDK.

Weitere Informationen finden Sie unter [verwenden](../../mfc/using-crebarctrl.md)von "debugstrg".

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="begindrag"></a>"Krebarctrl:: BeginDrag"

Implementiert das Verhalten der Win32-Nachricht [RB_BEGINDRAG](/windows/win32/Controls/rb-begindrag), wie im Windows SDK beschrieben.

```
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Der null basierte Index des Bands, auf den sich der Drag & Drop-Vorgang auswirkt.

*dwPos*<br/>
Ein DWORD-Wert, der die Start Maus Koordinaten enthält. Die horizontale Koordinate ist im LoWord enthalten, und die vertikale Koordinate ist im HIWORD enthalten. Wenn Sie (DWORD)-1 übergeben, verwendet das Grund leisten-Steuerelement die Position des Mauszeigers, wenn der Thread das letzte `GetMessage` Mal `PeekMessage`den Thread oder aufgerufen hat.

##  <a name="create"></a>"Erstellen": "erstellen"

Erstellt das Grund leisten-Steuerelement und fügt es `CReBarCtrl` an das-Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt die Kombination der auf das Steuerelement angewendeten Grundsteuer Element Stile an. Eine Liste unterstützter Stile finden Sie Untergrund leisten- [Steuerelement Stile](/windows/win32/Controls/rebar-control-styles) in der Windows SDK.

*Rect*<br/>
Ein Verweis auf ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt oder eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Position und Größe des Grund leisten-Steuer Elements ist.

*pParentWnd*<br/>
Ein Zeiger auf ein [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Grund leisten-Steuer Elements ist. Er darf nicht NULL sein.

*nID*<br/>
Gibt die Steuerelement-ID des Grund leisten Steuer Elements an.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Objekt erfolgreich erstellt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Erstellen Sie ein Grund leisten-Steuerelement in zwei Schritten:

1. Aufrufen von " [krebarctrl](#crebarctrl) " `CReBarCtrl` zum Erstellen eines-Objekts.

1. Mit dieser Member-Funktion wird das Windows-Steuerelement für die Grund Leiste erstellt und `CReBarCtrl` an das-Objekt angefügt.

Wenn Sie aufzurufen `Create`, werden die allgemeinen Steuerelemente initialisiert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

##  <a name="createex"></a>"Krebarctrl:: up-Ex"

Erstellt ein-Steuerelement (ein untergeordnetes Fenster) und ordnet `CReBarCtrl` es dem-Objekt zu.

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
Gibt die erweiterte Art des zu erstellenden Steuer Elements an. Eine Liste erweiterter Windows-Stile finden Sie unter dem *dwExStyle* -Parameter für " [kreatewindowex](/windows/win32/api/winuser/nf-winuser-createwindowexw) " in der Windows SDK.

*dwStyle*<br/>
Gibt die Kombination der auf das Steuerelement angewendeten Grundsteuer Element Stile an. Eine Liste unterstützter Stile finden Sie Untergrund leisten- [Steuerelement Stile](/windows/win32/Controls/rebar-control-styles) in der Windows SDK.

*Rect*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Größe und Position des zu erstellenden Fensters in Client Koordinaten von *pparser*beschreibt.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das das übergeordnete Element des Steuer Elements ist.

*nID*<br/>
Die ID des untergeordneten Fensters des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwenden `CreateEx` Sie anstelle von [Create](#create) , um erweiterte Windows-Stile anzuwenden, die durch den erweiterten Windows-Stil **WS_EX_** angegeben werden.

##  <a name="crebarctrl"></a>"Krebarctrl:: krebarctrl"

Erstellt ein `CReBarCtrl`-Objekt.

```
CReBarCtrl();
```

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für " [krebarctrl:: Create](#create)".

##  <a name="deleteband"></a>:D eleteout:

Implementiert das Verhalten der Win32-Nachricht [RB_DELETEBAND](/windows/win32/Controls/rb-deleteband), wie im Windows SDK beschrieben.

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Der null basierte Index des zu löschenden Bands.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Band erfolgreich gelöscht wurde. andernfalls NULL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

##  <a name="dragmove"></a>"Krebarctrl::D ragmove"

Implementiert das Verhalten der Win32-Nachricht [RB_DRAGMOVE](/windows/win32/Controls/rb-dragmove), wie im Windows SDK beschrieben.

```
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parameter

*dwPos*<br/>
Ein DWORD-Wert, der die neuen Maus Koordinaten enthält. Die horizontale Koordinate ist im LoWord enthalten, und die vertikale Koordinate ist im HIWORD enthalten. Wenn Sie (DWORD)-1 übergeben, verwendet das Grund leisten-Steuerelement die Position des Mauszeigers, wenn der Thread das letzte `GetMessage` Mal `PeekMessage`den Thread oder aufgerufen hat.

##  <a name="enddrag"></a>"Krebarctrl:: EndDrag"

Implementiert das Verhalten der Win32-Nachricht [RB_ENDDRAG](/windows/win32/Controls/rb-enddrag), wie im Windows SDK beschrieben.

```
void EndDrag();
```

##  <a name="getbandborders"></a>"Krebarctrl:: getbandrahmens"

Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDBORDERS](/windows/win32/Controls/rb-getbandborders), wie im Windows SDK beschrieben.

```
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Der null basierte Index des Bands, für das die Rahmen abgerufen werden.

*prc*<br/>
Ein Zeiger auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Band Rahmen empfängt. Wenn das Grund leisten-Steuerelement den RBS_BANDBORDERS-Stil hat, erhält jeder Member dieser Struktur die Anzahl der Pixel auf der entsprechenden Seite des Bands, die den Rahmen bilden. Wenn das Grund leisten-Steuerelement nicht den RBS_BANDBORDERS-Stil hat, erhält nur das linke Element dieser Struktur gültige Informationen. Eine Beschreibung der Grund leisten-Steuerelement Stile finden Sie Untergrund leisten- [Steuerelement Stile](/windows/win32/Controls/rebar-control-styles) in der Windows SDK.

##  <a name="getbandcount"></a>"Krebarctrl:: GetBandCount"

Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDCOUNT](/windows/win32/Controls/rb-getbandcount), wie im Windows SDK beschrieben.

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bänder, die dem Steuerelement zugewiesen sind.

##  <a name="getbandinfo"></a>"Krebarctrl:: GetBandInfo"

Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDINFO](/windows/win32/Controls/rb-getbandinfo) wie im Windows SDK beschrieben.

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Der null basierte Index des Bands, für das die Informationen abgerufen werden.

*prbbi*<br/>
Ein Zeiger auf eine [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) -Struktur zum Empfangen der Bandinformationen. Sie müssen den `cbSize` Member dieser Struktur auf `sizeof(REBARBANDINFO)` festlegen und den `fMask` Member auf die Elemente festlegen, die Sie vor dem Senden dieser Nachricht abrufen möchten.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

##  <a name="getbandmargins"></a>"Krebarctrl:: getbandmargin"

Ruft die Ränder des Bands ab.

```
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>Parameter

*pmargin*<br/>
Ein Zeiger auf eine [Ränder](/windows/win32/api/uxtheme/ns-uxtheme-margins)-Struktur, die die Informationen empfängt.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion emuliert die Funktionalität der [RB_GETBANDMARGINS](/windows/win32/Controls/rb-getbandmargins) -Nachricht, wie im Windows SDK beschrieben.

##  <a name="getbarheight"></a>"Krebarctrl:: getbarheight"

Ruft die Höhe der Info Leiste ab.

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der die Höhe des Steuer Elements in Pixel darstellt.

##  <a name="getbarinfo"></a>"Krebarctrl:: getbarinfo"

Implementiert das Verhalten der Win32-Nachricht [RB_GETBARINFO](/windows/win32/Controls/rb-getbarinfo), wie im Windows SDK beschrieben.

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>Parameter

*prbi*<br/>
Ein Zeiger auf eine [rebarinfo](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) -Struktur, die die Informationen zum Info leisten-Steuerelement empfängt. Sie müssen den *CBSIZE* -Member dieser-Struktur auf `sizeof(REBARINFO)` festlegen, bevor Sie diese Nachricht senden.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

##  <a name="getbkcolor"></a>"Krebarctrl:: GetBkColor"

Implementiert das Verhalten der Win32-Nachricht [RB_GETBKCOLOR](/windows/win32/Controls/rb-getbkcolor), wie im Windows SDK beschrieben.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein COLORREF-Wert, der die aktuelle Standard Hintergrundfarbe darstellt.

##  <a name="getcolorscheme"></a>"Krebarctrl:: getcolorscheme"

Ruft die [ColorScheme](/windows/win32/api/commctrl/ns-commctrl-colorscheme) -Struktur für das Grund leisten-Steuerelement ab.

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parameter

*lpcs*<br/>
Ein Zeiger auf eine [ColorScheme](/windows/win32/api/commctrl/ns-commctrl-colorscheme) -Struktur, wie im Windows SDK beschrieben.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Die `COLORSCHEME` -Struktur enthält die Schaltflächen Hervorhebungs Farbe und die Schatten Farbe der Schaltfläche.

##  <a name="getdroptarget"></a>"Krebarctrl:: getdroptarget"

Implementiert das Verhalten der Win32-Nachricht [RB_GETDROPTARGET](/windows/win32/Controls/rb-getdroptarget), wie im Windows SDK beschrieben.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) -Schnittstelle.

##  <a name="getextendedstyle"></a>  CReBarCtrl::GetExtendedStyle

Ruft die erweiterten Stile des aktuellen Grund leisten-Steuer Elements ab.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Eine bitweise Kombination (or) von Flags, die die erweiterten Stile angeben. Mögliche Flags sind RBS_EX_SPLITTER und RBS_EX_TRANSPARENT. Weitere Informationen finden Sie unter dem *dwMask*-Parameter der [CReBarCtrl::SetExtendedStyle](#setextendedstyle)-Methode.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [RB_GETEXTENDEDSTYLE](/windows/win32/Controls/rb-dragmove) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getimagelist"></a>"Krebarctrl:: GetImageList"

Ruft das `CImageList` einem Grund leisten-Steuerelement zugeordnete-Objekt ab.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt. Gibt NULL zurück, wenn keine Bildliste für das Steuerelement festgelegt ist.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion verwendet in der [rebarinfo](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) -Struktur gespeicherte Größen-und Masken Informationen, wie im Windows SDK beschrieben.

##  <a name="getpalette"></a>"Krebarctrl:: getpalette"

Ruft die aktuelle Palette des Grund leisten-Steuer Elements ab.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CPalette](../../mfc/reference/cpalette-class.md) -Objekt, das die aktuelle Palette des Grund leisten-Steuer Elements angibt.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass diese Member- `CPalette` Funktion ein-Objekt als Rückgabewert anstelle einer hpalette verwendet.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

##  <a name="getrect"></a>"Krebarctrl:: GetRect"

Implementiert das Verhalten der Win32-Nachricht [RB_GETRECT](/windows/win32/Controls/rb-getrect), wie im Windows SDK beschrieben.

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
NULL basierter Index eines Bands im Grund leisten-Steuerelement.

*prc*<br/>
Ein Zeiger auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Begrenzungen des Bereichs der Info Leiste empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

##  <a name="getrowcount"></a>"Krebarctrl:: GetRowCount"

Implementiert das Verhalten der Win32-Nachricht [RB_GETROWCOUNT](/windows/win32/Controls/rb-getrowcount), wie im Windows SDK beschrieben.

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>Rückgabewert

Ein uint-Wert, der die Anzahl der Band Zeilen im-Steuerelement darstellt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

##  <a name="getrowheight"></a>"Krebarctrl:: getRowHeight"

Implementiert das Verhalten der Win32-Nachricht [RB_GETROWHEIGHT](/windows/win32/Controls/rb-getrowheight), wie im Windows SDK beschrieben.

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>Parameter

*uRow*<br/>
Der null basierte Index des Bands, dessen Höhe abgerufen wird.

### <a name="return-value"></a>Rückgabewert

Ein uint-Wert, der die Zeilenhöhe in Pixel darstellt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

##  <a name="gettextcolor"></a>"Krebarctrl:: gettextcolor"

Implementiert das Verhalten der Win32-Nachricht [RB_GETTEXTCOLOR](/windows/win32/Controls/rb-gettextcolor), wie im Windows SDK beschrieben.

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein COLORREF-Wert, der die aktuelle Standard Textfarbe darstellt.

##  <a name="gettooltips"></a>"Krebarctrl:: gettooltips"

Implementiert das Verhalten der Win32-Nachricht [RB_GETTOOLTIPS](/windows/win32/Controls/rb-gettooltips), wie im Windows SDK beschrieben.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) -Objekt.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass die MFC `GetToolTips` -Implementierung von einen Zeiger `CToolTipCtrl`auf einen und nicht auf ein HWND zurückgibt.

##  <a name="hittest"></a>"Krebarctrl:: HitTest"

Implementiert das Verhalten der Win32-Nachricht [RB_HITTEST](/windows/win32/Controls/rb-hittest), wie im Windows SDK beschrieben.

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>Parameter

*prbht*<br/>
Ein Zeiger auf eine [rbhittestinfo](/windows/win32/api/commctrl/ns-commctrl-_rb_hittestinfo) -Struktur. Bevor die Nachricht gesendet wird, `pt` muss der Member dieser Struktur in Client Koordinaten mit dem zu testenden Punkt initialisiert werden.

### <a name="return-value"></a>Rückgabewert

Der null basierte Index des Bands am angegebenen Punkt, oder-1, wenn sich kein umfügeband an der Stelle befand.

##  <a name="idtoindex"></a>"Krebarctrl:: idto Index"

Implementiert das Verhalten der Win32-Nachricht [RB_IDTOINDEX](/windows/win32/controls/rb-idtoindex), wie im Windows SDK beschrieben.

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>Parameter

*uBandID*<br/>
Der von der Anwendung definierte Bezeichner des angegebenen Bands, der beim `wID` Einfügen des Bands an den Member der [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) -Struktur weitergegeben wird.

### <a name="return-value"></a>Rückgabewert

Der null basierte Band Index, wenn erfolgreich, andernfalls-1. Wenn doppelte Band Indizes vorhanden sind, wird der erste zurückgegeben.

##  <a name="insertband"></a>"Krebarctrl:: InsertBand"

Implementiert das Verhalten der Win32-Nachricht [RB_INSERTBAND](/windows/win32/Controls/rb-insertband), wie im Windows SDK beschrieben.

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parameter

*uIndex*<br/>
Der null basierte Index der Position, an der das Band eingefügt wird. Wenn Sie diesen Parameter auf "-1" festlegen, fügt das Steuerelement das neue Band am letzten Speicherort hinzu.

*prbbi*<br/>
Ein Zeiger auf eine [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) -Struktur, die das einzufügende Band definiert. Sie müssen den *CBSIZE* -Member dieser Struktur auf festlegen `sizeof(REBARBANDINFO)` , bevor Sie diese Funktion aufrufen.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

##  <a name="maximizeband"></a>"Krebarctrl:: maximizeband"

Ändert die Größe eines Bands in einem Grund leisten-Steuerelement auf seine größte Größe.

```
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Der null basierte Index des zu maximier enden Bands.

### <a name="remarks"></a>Hinweise

Implementiert das Verhalten der Win32-Nachricht [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) , `fIdeal` wobei auf 0 (null) festgelegt ist, wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

##  <a name="minimizeband"></a>"Krebarctrl:: minimizeband"

Ändert die Größe eines Bands in einem Grund leisten-Steuerelement auf seine kleinste Größe.

```
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Der null basierte Index des zu minimier enden Bands.

### <a name="remarks"></a>Hinweise

Implementiert das Verhalten der Win32-Nachricht [RB_MINIMIZEBAND](/windows/win32/Controls/rb-minimizeband), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

##  <a name="moveband"></a>"Krebarctrl:: muveband"

Implementiert das Verhalten der Win32-Nachricht [RB_MOVEBAND](/windows/win32/Controls/rb-moveband), wie im Windows SDK beschrieben.

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>Parameter

*uFrom*<br/>
Der null basierte Index des zu bewegenden Bands.

*uTo*<br/>
NULL basierter Index der neuen Bandposition. Dieser Parameterwert darf nicht größer als die Anzahl der Bänder minus 1 sein. Rufen Sie zum Abrufen der Anzahl der Bänder [GetBandCount](#getbandcount)auf.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

##  <a name="pushchevron"></a>"Krebarctrl::P ushchevron"

Implementiert das Verhalten der Win32-Nachricht [RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron), wie im Windows SDK beschrieben.

```
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
NULL basierter Index des Bands, dessen Chevron per pushübertragung durchgesetzt werden soll.

*lAppValue*<br/>
Ein von der Anwendung definierter 32-Bit-Wert. Siehe *lappvalue* in [RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron) im Windows SDK.

##  <a name="restoreband"></a>"Krebarctrl:: restoreband"

Ändert die Größe eines Bands in einem Grund leisten-Steuerelement auf seine ideale Größe.

```
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
Der null basierte Index des zu maximier enden Bands.

### <a name="remarks"></a>Hinweise

Implementiert das Verhalten der Win32-Nachricht [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) , `fIdeal` wobei auf 1 festgelegt ist, wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

##  <a name="setbandinfo"></a>"Krebarctrl:: SetBandInfo"

Implementiert das Verhalten der Win32-Nachricht [RB_SETBANDINFO](/windows/win32/Controls/rb-setbandinfo), wie im Windows SDK beschrieben.

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
NULL basierter Index des Bands, um die neuen Einstellungen zu erhalten.

*prbbi*<br/>
Ein Zeiger auf eine [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) -Struktur, die das einzufügende Band definiert. Sie müssen den `cbSize` -Member dieser-Struktur auf `sizeof(REBARBANDINFO)` festlegen, bevor Sie diese Nachricht senden.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

##  <a name="setbandwidth"></a>"Krebarctrl:: setbandwidth"

Legt die Breite des angegebenen angedockten Bands im aktuellen Grund leisten-Steuerelement fest.

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*uBand*|in NULL basierter Index eines Info leisten Bands.|
|*cxWidth*|in Neue Breite des Bereichs der Info Leiste in Pixel.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [RB_SETBANDWIDTH](/windows/win32/Controls/rb-setbandwidth) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die-Variable `m_rebar`definiert, die für den Zugriff auf das aktuelle Grund leisten-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird jedes Grund leisten-Band auf die gleiche Breite festgelegt.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

##  <a name="setbarinfo"></a>"Krebarctrl:: setbarinfo"

Implementiert das Verhalten der Win32-Nachricht [RB_SETBARINFO](/windows/win32/Controls/rb-setbarinfo), wie im Windows SDK beschrieben.

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>Parameter

*prbi*<br/>
Ein Zeiger auf eine [rebarinfo](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) -Struktur, die die festzulegenden Informationen enthält. Sie müssen den `cbSize` Member dieser Struktur auf festlegen, `sizeof(REBARINFO)` bevor Sie diese Nachricht senden.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

##  <a name="setbkcolor"></a>"Krebarctrl:: SetBkColor"

Implementiert das Verhalten der Win32-Nachricht [RB_SETBKCOLOR](/windows/win32/Controls/rb-setbkcolor), wie im Windows SDK beschrieben.

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>Parameter

*clr*<br/>
Der COLORREF-Wert, der die neue Standard Hintergrundfarbe darstellt.

### <a name="return-value"></a>Rückgabewert

Ein [COLORREF](/windows/win32/gdi/colorref) -Wert, der die vorherige Standard Hintergrundfarbe darstellt.

### <a name="remarks"></a>Hinweise

Weitere Informationen zum Festlegen der Hintergrundfarbe und zum Festlegen der Standardeinstellung finden Sie in diesem Thema.

##  <a name="setcolorscheme"></a>"Krebarctrl:: SetColorScheme"

Legt das Farbschema für die Schaltflächen eines Grund leisten-Steuer Elements fest.

```
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parameter

*lpcs*<br/>
Ein Zeiger auf eine [ColorScheme](/windows/win32/api/commctrl/ns-commctrl-colorscheme) -Struktur, wie im Windows SDK beschrieben.

### <a name="remarks"></a>Hinweise

Die `COLORSCHEME` Struktur enthält sowohl die Hervorhebungs Farbe der Schaltfläche als auch die Schaltfläche Schatten Farbe.

##  <a name="setextendedstyle"></a>"Krebarctrl:: abtextendecodstyle"

Legt die erweiterten Stile für das aktuelle Grund leisten-Steuerelement fest.

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwMask*|in Eine bitweise Kombination (or) von Flags, die angeben, welche Flags im Parameter " *dwstyleex* " angewendet werden. Verwenden Sie einen oder mehrere der folgenden Werte:<br /><br /> RBS_EX_SPLITTER: Standardmäßig wird der Splitter im horizontalen Modus im horizontalen und rechts im vertikalen Modus angezeigt.<br /><br /> RBS_EX_TRANSPARENT: Leiten Sie die [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) -Nachricht an das übergeordnete Fenster weiter.|
|*dwStyleEx*|in Eine bitweise Kombination (or) von Flags, die die anzuwendenden Stile angeben. Um einen Stil festzulegen, geben Sie das gleiche Flag an, das im *dwMask* -Parameter verwendet wird. Geben Sie zum Zurücksetzen eines Stils Binary NULL an.|

### <a name="return-value"></a>Rückgabewert

Der vorherige erweiterte Stil.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [RB_SETEXTENDEDSTYLE](/windows/win32/Controls/rb-setextendedstyle) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="setimagelist"></a>"Krebarctrl:: SetImageList"

Weist einem Grund leisten-Steuerelement eine Bildliste zu.

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parameter

*pImageList*<br/>
Ein Zeiger auf ein [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, das die Bildliste enthält, die dem Grund leisten-Steuerelement zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

##  <a name="setowner"></a>"Krebarctrl:: seetowner"

Implementiert das Verhalten der Win32-Nachricht [RB_SETPARENT](/windows/win32/Controls/rb-setparent), wie im Windows SDK beschrieben.

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Ein Zeiger auf ein `CWnd` -Objekt, das als Besitzer des Grund leisten-Steuer Elements festgelegt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das der aktuelle Besitzer des Grund leisten-Steuer Elements ist.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass diese Member-Funktion `CWnd` Zeiger auf-Objekte sowohl für den aktuellen als auch für den ausgewählten Besitzer des Grund leisten-Steuer Elements anstelle von Handles für Windows verwendet.

> [!NOTE]
>  Diese Member-Funktion ändert nicht das tatsächliche übergeordnete Element, das beim Erstellen des Steuer Elements festgelegt wurde. Stattdessen sendet Sie Benachrichtigungs Meldungen an das von Ihnen angegebene Fenster.

##  <a name="setpalette"></a>"Krebarctrl:: SetPalette"

Implementiert das Verhalten der Win32-Nachricht [RB_SETPALETTE](/windows/win32/Controls/rb-setpalette), wie im Windows SDK beschrieben.

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>Parameter

*hPal*<br/>
Eine hpalette, die die neue Palette angibt, die vom Grund leisten-Steuerelement verwendet wird.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CPalette](../../mfc/reference/cpalette-class.md) -Objekt, das die vorherige Palette des Grund leisten-Steuer Elements angibt.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass diese Member- `CPalette` Funktion ein-Objekt als Rückgabewert anstelle einer hpalette verwendet.

##  <a name="settextcolor"></a>"Krebarctrl:: SetTextColor"

Implementiert das Verhalten der Win32-Nachricht [RB_SETTEXTCOLOR](/windows/win32/Controls/rb-settextcolor), wie im Windows SDK beschrieben.

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>Parameter

*clr*<br/>
Ein COLORREF-Wert, der die neue Textfarbe im `CReBarCtrl` -Objekt darstellt.

### <a name="return-value"></a>Rückgabewert

Der [COLORREF](/windows/win32/gdi/colorref) -Wert, der die vorherige Textfarbe darstellt `CReBarCtrl` , die dem-Objekt zugeordnet ist.

### <a name="remarks"></a>Hinweise

Er wird bereitgestellt, um die Text Farb Flexibilität in einem Grund leisten-Steuerelement zu unterstützen

##  <a name="settooltips"></a>"Krebarctrl:: SetToolTips"

Ordnet ein QuickInfo-Steuerelement einem Grund leisten-Steuerelement zu.

```
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>Parameter

*pToolTip*<br/>
Ein Zeiger auf ein [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) -Objekt.

### <a name="remarks"></a>Hinweise

Sie müssen das `CToolTipCtrl` -Objekt zerstören, wenn Sie damit abgeschlossen sind.

##  <a name="setwindowtheme"></a>"Krebarctrl:: SetWindowTheme"

Legt den visuellen Stil des Grund leisten-Steuer Elements fest.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parameter

*pszSubAppName*<br/>
Ein Zeiger auf eine Unicode-Zeichenfolge, die den festzulegenden visuellen Stil der Grund Leiste enthält.

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert wird nicht verwendet.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion emuliert die Funktionalität der [RB_SETWINDOWTHEME](/windows/win32/Controls/rb-setwindowtheme) -Nachricht, wie im Windows SDK beschrieben.

##  <a name="showband"></a>"Krebarctrl:: Showband"

Implementiert das Verhalten der Win32-Nachricht [RB_SHOWBAND](/windows/win32/Controls/rb-showband), wie im Windows SDK beschrieben.

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>Parameter

*uBand*<br/>
NULL basierter Index eines Bands im Grund leisten-Steuerelement.

*fShow*<br/>
Gibt an, ob das Band angezeigt oder ausgeblendet werden soll. Wenn dieser Wert true ist, wird das Band angezeigt. Andernfalls wird das Band ausgeblendet.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

##  <a name="sizetorect"></a>"Krebarctrl:: sizetorect"

Implementiert das Verhalten der Win32-Nachricht [RB_SIZETORECT](/windows/win32/Controls/rb-sizetorect), wie im Windows SDK beschrieben.

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Ein Verweis auf ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das das Rechteck angibt, zu dem das Steuerelement der Grund Leiste passen soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass diese Member- `CRect` Funktion ein-Objekt als Parameter anstelle einer `RECT` -Struktur verwendet.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
