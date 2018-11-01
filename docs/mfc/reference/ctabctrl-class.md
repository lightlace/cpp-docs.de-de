---
title: CTabCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
ms.openlocfilehash: ae3daff2582b9e58cc325304fac449423fb673a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621428"
---
# <a name="ctabctrl-class"></a>CTabCtrl-Klasse

Stellt die Funktionalität des allgemeinen Windows-Registerkarten-Steuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CTabCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CTabCtrl::CTabCtrl](#ctabctrl)|Erstellt ein `CTabCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTabCtrl::AdjustRect](#adjustrect)|Ein Registerkarten-Steuerelement Anzeigebereich erhält ein Rechteck Fenster berechnet oder berechnet das fensterrechtecke aus, das die einen bestimmten Anzeigebereich entsprechen würden.|
|[CTabCtrl::Create](#create)|Ein Registerkarten-Steuerelement erstellt, und fügt ihn an eine Instanz von einem `CTabCtrl` Objekt.|
|[CTabCtrl::CreateEx](#createex)|Ein Registerkarten-Steuerelement mit dem angegebenen erweiterten Stile für Windows erstellt, und fügt ihn an eine Instanz von einem `CTabCtrl` Objekt.|
|[CTabCtrl::DeleteAllItems](#deleteallitems)|Entfernt alle Elemente aus einem Registerkarten-Steuerelement.|
|[CTabCtrl::DeleteItem](#deleteitem)|Entfernt ein Element aus einem Registerkarten-Steuerelement.|
|[CTabCtrl::DeselectAll](#deselectall)|Setzt die Elemente in einem Registersteuerelement, deaktivieren, die gedrückt wurden.|
|[CTabCtrl::DrawItem](#drawitem)|Zeichnet ein angegebenes Element ein Registerkarten-Steuerelements.|
|[CTabCtrl::GetCurFocus](#getcurfocus)|Ruft die Registerkarte mit der aktuelle Fokus des ein Registerkarten-Steuerelement ab.|
|[CTabCtrl::GetCurSel](#getcursel)|Bestimmt, die derzeit ausgewählte Registerkarte in einem Registersteuerelement.|
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Ruft die erweiterten Stile, die derzeit für das Registerkarten-Steuerelement verwendet werden.|
|[CTabCtrl::GetImageList](#getimagelist)|Ruft das ein Registerkarten-Steuerelement zugeordnete Bildliste ab.|
|[CTabCtrl::GetItem](#getitem)|Ruft Informationen zu einer Registerkarte in einem Registerkarten-Steuerelement ab.|
|[CTabCtrl::GetItemCount](#getitemcount)|Ruft die Anzahl der Registerkarten im Registerkarten-Steuerelement ab.|
|[CTabCtrl::GetItemRect](#getitemrect)|Ruft das umschließende Rechteck für eine Registerkarte in einem Registersteuerelement an.|
|[CTabCtrl::GetItemState](#getitemstate)|Ruft den Zustand des Steuerelement ein Element der angegebenen Registerkarte ab.|
|[CTabCtrl::GetRowCount](#getrowcount)|Ruft die aktuelle Anzahl der Zeilen mit Registerkarten in einem Registersteuerelement an.|
|[CTabCtrl::GetToolTips](#gettooltips)|Ruft das Handle des ein Registerkarten-Steuerelement zugeordneten QuickInfo-Steuerelements ab.|
|[CTabCtrl::HighlightItem](#highlightitem)|Legt die Hervorhebung Zustand eines Registerkartenelements fest.|
|[CTabCtrl::HitTest](#hittest)|Bestimmt, welche Registerkarte ggf. an einer angegebenen Bildschirmposition.|
|[CTabCtrl:: InsertItem](#insertitem)|Fügt eine neue Registerkarte in einem Registersteuerelement an.|
|[CTabCtrl::RemoveImage](#removeimage)|Entfernt ein Bild aus einer Bildliste für ein Registerkarten-Steuerelement.|
|[CTabCtrl::SetCurFocus](#setcurfocus)|Setzt den Fokus auf eine angegebene Registerkarte in einem Registersteuerelement an.|
|[CTabCtrl::SetCurSel](#setcursel)|Wählt eine Registerkarte in einem Registersteuerelement an.|
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Legt fest, die erweiterten Stile für ein Registerkarten-Steuerelement.|
|[CTabCtrl::SetImageList](#setimagelist)|Weist eine Bildliste ein Registerkarten-Steuerelement.|
|[CTabCtrl::SetItem](#setitem)|Legt fest, einige oder alle der Registerkarte Attribute.|
|[CTabCtrl::SetItemExtra](#setitemextra)|Legt die Anzahl von Bytes pro Registerkarte für die Anwendung definierte Daten in einem Registersteuerelement reserviert.|
|[CTabCtrl::SetItemSize](#setitemsize)|Legt fest, die Breite und Höhe eines Elements.|
|[CTabCtrl::SetItemState](#setitemstate)|Legt den Zustand für das angegebene Steuerelement Registerelement fest.|
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|Legt die minimale Breite der Elemente in einem Registersteuerelement an.|
|[CTabCtrl::SetPadding](#setpadding)|Legt die Größe des Speicherplatzes (Auffüllung) aus, um Symbol und eine Bezeichnung in einem Registersteuerelement jede Registerkarte fest.|
|[CTabCtrl::SetToolTips](#settooltips)|Ein Registerkarten-Steuerelement wird ein QuickInfo-Steuerelement zugewiesen.|

## <a name="remarks"></a>Hinweise

Ein "Registerkarten-Steuerelement" entspricht etwa einem Trennblatt in einem Notizbuch oder die Bezeichnungen in eine CAB-Datei. Durch Verwenden eines Registerkarten-Steuerelements können in einer Anwendung mehrere Seiten für denselben Bereich in einem Fenster oder Dialogfeld definiert werden. Jede Seite besteht aus einem Satz von Informationen oder eine Gruppe von Steuerelementen, die die Anwendung wird angezeigt, wenn der Benutzer die entsprechende Registerkarte auswählt. Eine besondere Art von Registerkarten-Steuerelement zeigt die Registerkarten an, die wie Schaltflächen aussehen. Klicken auf eine Schaltfläche klicken, sollten einen Befehl aus, anstatt eine Seite sofort ausführen.

Dieses Steuerelement (und somit die `CTabCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.

Weitere Informationen zur Verwendung von `CTabCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CTabCtrl](../../mfc/using-ctabctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="adjustrect"></a>  CTabCtrl::AdjustRect

Ein Registerkarten-Steuerelement Anzeigebereich erhält ein Rechteck Fenster berechnet oder berechnet das fensterrechtecke aus, das die einen bestimmten Anzeigebereich entsprechen würden.

```
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>Parameter

*bLarger*<br/>
Gibt an, welcher Vorgang ausgeführt. Wenn dieser Parameter auf "true" ist *LpRect* gibt ein Anzeigerechteck und das entsprechende fensterrechtecke empfängt. Wenn dieser Parameter auf "FALSE" ist *LpRect* gibt ein Rechteck Fenster und das entsprechende Anzeigerechteck empfängt.

*lpRect*<br/>
Zeiger auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, gibt das angegebene Rechteck und das berechnete Rechteck empfängt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

##  <a name="create"></a>  CTabCtrl::Create

Ein Registerkarten-Steuerelement erstellt, und fügt ihn an eine Instanz von einem `CTabCtrl` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt das Registerkarten-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Registerkarte Stile von Listensteuerelementen](/windows/desktop/Controls/tab-control-styles), die im Windows SDK beschrieben. Finden Sie unter **"Hinweise"** eine Liste der Window-Stile, die Sie auch auf das Steuerelement anwenden können.

*Rect*<br/>
Gibt an, Größe und Position des Steuerelements. Es kann sein, entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.

*pParentWnd*<br/>
Gibt an, das Registerkarten-Steuerelement übergeordnete Fenster, in der Regel eine `CDialog`. Es darf nicht NULL sein.

*nID*<br/>
Gibt das Registerkarten-Steuerelement-ID an.

### <a name="return-value"></a>Rückgabewert

True, wenn die Initialisierung des Objekts erfolgreich war. andernfalls "false".

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CTabCtrl` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen dann `Create`, die das Registerkarten-Steuerelement erstellt, und fügt es der `CTabCtrl` Objekt.

Neben der Registerkarte Stile von Listensteuerelementen können Sie die folgenden Fensterstile auf ein Registerkarten-Steuerelement anwenden:

- WS_CHILD erstellt ein untergeordnetes Fenster, das das Registerkarten-Steuerelement darstellt. Kann nicht mit dem WS_POPUP-Stil verwendet werden.

- WS_VISIBLE erstellt ein Registerkarten-Steuerelement, das anfänglich sichtbar ist.

- WS_DISABLED erstellt ein Fenster, das anfänglich deaktiviert ist.

- WS_GROUP gibt das erste Steuerelement einer Gruppe von Steuerelementen, die in denen der Benutzer von einem Steuerelement zum nächsten mit den Pfeiltasten verschieben kann. Alle Steuerelemente, die mit dem WS_GROUP-Stil definiert wird, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit dem WS_GROUP-Stil der formatvorlagengruppe beendet und startet die nächste Gruppe (d. h. eine Gruppe endet, in dem die nächste beginnt).

- WS_TABSTOP gibt eine Reihe von Steuerelementen, die über denen der Benutzer mit der TAB-TASTE wechseln kann. Die TAB-Taste wechselt der Benutzer auf das nächste Steuerelement, das durch den Stil WS_TABSTOP angegeben.

Rufen Sie zum Erstellen eines Registerkarten-Steuerelements mit erweiterten Fensterstile [CTabCtrl::CreateEx](#createex) anstelle von `Create`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

##  <a name="createex"></a>  CTabCtrl::CreateEx

Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet ihn dem `CTabCtrl` Objekt.

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
Gibt das Registerkarten-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Registerkarte Stile von Listensteuerelementen](/windows/desktop/Controls/tab-control-styles), die im Windows SDK beschrieben. Finden Sie unter **"Hinweise"** in [erstellen](#create) eine Liste der Window-Stile, die Sie auch auf das Steuerelement anwenden können.

*Rect*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt *pParentWnd*.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.

*nID*<br/>
Der ID des Steuerelements untergeordneten Fensters mit.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende Erweiterte Windows-Stile, angegeben durch den Wert der Windows-erweiterten Stil **WS_EX_**.

`CreateEx` erstellt das Steuerelement mit den erweiterten Windows-Formatvorlagen, die anhand des *DwExStyle*. Erweiterte Stile, die spezifisch für ein Steuerelement mithilfe Satz [SetExtendedStyle](#setextendedstyle). Verwenden Sie z. B. `CreateEx` solche Stile als WS_EX_CONTEXTHELP festgelegt, aber verwenden Sie `SetExtendedStyle` solche Stile als TCS_EX_FLATSEPARATORS festgelegt. Weitere Informationen finden Sie die Stile, die in beschriebenen [Stile von Listensteuerelementen erweiterte Registerkarte](/windows/desktop/Controls/tab-control-extended-styles) im Windows SDK.

##  <a name="ctabctrl"></a>  CTabCtrl::CTabCtrl

Erstellt ein `CTabCtrl`-Objekt.

```
CTabCtrl();
```

##  <a name="deleteallitems"></a>  CTabCtrl::DeleteAllItems

Entfernt alle Elemente aus einem Registerkarten-Steuerelement.

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="deleteitem"></a>  CTabCtrl::DeleteItem

Entfernt das angegebene Element aus einem Registerkarten-Steuerelement.

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
Nullbasierter Wert, der zu löschenden Elements.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

##  <a name="deselectall"></a>  CTabCtrl::DeselectAll

Setzt die Elemente in einem Registersteuerelement, deaktivieren, die gedrückt wurden.

```
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>Parameter

*fExcludeFocus*<br/>
Flag, die den Rahmen der Deaktivierung des Elements angibt. Wenn dieser Parameter auf "false" festgelegt ist, werden alle Registerkarten-Schaltflächen zurückgesetzt. Wenn sie "true" festgelegt ist, und klicken Sie dann alle Elemente mit Ausnahme der aktuell ausgewählten Registerkarte wird zurückgesetzt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_DESELECTALL](/windows/desktop/Controls/tcm-deselectall), wie im Windows SDK beschrieben.

##  <a name="drawitem"></a>  CTabCtrl::DrawItem

Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Registerkarte-Steuerelements ändert.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein Zeiger auf eine [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) Struktur, beschreibt das Element gezeichnet werden.

### <a name="remarks"></a>Hinweise

Die `itemAction` Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll.

Standardmäßig ist diese Member-Funktion mit "nothing". Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CTabCtrl` Objekt.

Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext in angegeben wiederherstellen *LpDrawItemStruct* vor diesem Member Funktion beendet wird.

##  <a name="getcurfocus"></a>  CTabCtrl::GetCurFocus

Ruft den Index der Registerkarte mit den aktuellen Fokus ab.

```
int GetCurFocus() const;
```

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index der Registerkarte mit den aktuellen Fokus.

##  <a name="getcursel"></a>  CTabCtrl::GetCurSel

Ruft ab, der derzeit ausgewählten Registerkarte in einem Registersteuerelement.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Rückgabewert

Nullbasierte Index des ausgewählten Registerkarte im Erfolgsfall oder -1, wenn keine Registerkarte ausgewählt ist.

##  <a name="getextendedstyle"></a>  CTabCtrl::GetExtendedStyle

Ruft die erweiterten Stile, die derzeit für das Registerkarten-Steuerelement verwendet werden.

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>Rückgabewert

Stellt die erweiterten Stile aktuell in Verwendung für das Registerkarten-Steuerelement dar. Dieser Wert ist eine Kombination von [Registerkarten-Steuerelement, die erweiterte Stile](/windows/desktop/Controls/tab-control-extended-styles), wie im Windows SDK beschrieben.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_GETEXTENDEDSTYLE](/windows/desktop/Controls/tcm-getextendedstyle), wie im Windows SDK beschrieben.

##  <a name="getimagelist"></a>  CTabCtrl::GetImageList

Ruft die einem Tab-Steuerelement zugeordnete Bildliste ab.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Rückgabewert

Bei Erfolg ein Zeiger auf die Liste der Bilder von der Registerkarte "-Steuerelement andernfalls NULL.

##  <a name="getitem"></a>  CTabCtrl::GetItem

Ruft Informationen zu einer Registerkarte in einem Registerkarten-Steuerelement ab.

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
Nullbasierter Index der Registerkarte.

*pTabCtrlItem*<br/>
Zeiger auf eine [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Struktur verwendet, um die abzurufenden Informationen anzugeben. Auch verwendet zum Empfangen von Informationen über die Registerkarte. Diese Struktur wird verwendet, mit der `InsertItem`, `GetItem`, und `SetItem` Memberfunktionen.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn erfolgreich; "False" andernfalls.

### <a name="remarks"></a>Hinweise

Wenn die Nachricht gesendet wird, die `mask` -Member gibt an, welche Attribute zurück. Wenn die `mask` -Member gibt an, den TCIF_TEXT-Wert, der `pszText` Member darf die Adresse des Puffers, der den Elementtext empfängt und die `cchTextMax` Member muss die Größe des Puffers angeben.

- `mask`

   Wert, der angibt, welche `TCITEM` Strukturmember abgerufen oder festgelegt. Dieser Member kann NULL oder eine Kombination der folgenden Werte sein:

   - TCIF_TEXT der `pszText` Member ist gültig.

   - TCIF_IMAGE der `iImage` Member ist gültig.

   - TCIF_PARAM der `lParam` Member ist gültig.

   - TCIF_RTLREADING den Text der `pszText` mit rechts-nach-Links-Lesefolge auf Systemen mit Hebräisch oder Arabisch angezeigt wird.

   - TCIF_STATE der `dwState` Member ist gültig.

- `pszText`

   Zeiger auf eine Null-terminierte Zeichenfolge, die mit den Registerkartentext ein, wenn die Struktur Informationen über eine Registerkarte enthält. Wenn die Struktur Informationen empfängt, gibt dieses Element die Adresse des Puffers, der den Registerkartentext ein empfängt.

- `cchTextMax`

   Größe des Puffers verweist `pszText`. Dieses Element wird ignoriert, wenn die Struktur keine Informationen empfängt.

- `iImage` Indizieren Sie in des Registerkarten-Steuerelements Bildliste oder -1, wenn kein Standardimage für die Registerkarte vorhanden ist.

- `lParam`

   Die Registerkarte zugeordnete anwendungsdefinierte Daten. Wenn mehr als vier Bytes der Anwendung definierte Daten pro Registerkarte, eine Anwendung muss eine Struktur definieren und Sie anstelle der `TCITEM` Struktur. Das erste Element der Anwendung definierte Struktur muss eine [TCITEMHEADER](/windows/desktop/api/commctrl/ns-commctrl-tagtcitemheadera)Struktur. Die `TCITEMHEADER` Struktur ist identisch mit der `TCITEM` Struktur, jedoch ohne die `lParam` Member. Der Unterschied zwischen der Größe Ihrer Struktur und die Größe der `TCITEMHEADER` Struktur sollte die Anzahl der zusätzlichen Bytes pro Tabstopp entsprechen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

##  <a name="getitemcount"></a>  CTabCtrl::GetItemCount

Ruft die Anzahl der Registerkarten im Registerkarten-Steuerelement ab.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Rückgabewert

Anzahl der Elemente im Registerkarten-Steuerelement.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="getitemrect"></a>  CTabCtrl::GetItemRect

Ruft das umschließende Rechteck für die angegebene Registerkarte in einem Registersteuerelement an.

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
Nullbasierte Index des Registerelements.

*lpRect*<br/>
Zeiger auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das umschließende Rechteck der Registerkarte empfängt. Diese Koordinaten verwenden des Ansichtsfensters aktuelle Zuordnungsmodus.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

##  <a name="getitemstate"></a>  CTabCtrl::GetItemState

Ruft den Zustand des Steuerelements Registerelements identifizierte *nItem*.

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
Die nullbasierte Indexnummer des Elements für die Statusinformationen abzurufen.

*dwMask*<br/>
Maske, die angeben, welche von der Zustand des Elements flags zurück. Eine Liste von Werten, finden Sie unter der Mask-Member der [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Struktur, wie im Windows SDK beschrieben.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf einen DWORD-Wert, der die Statusinformationen zu erhalten. Kann einer der folgenden Werte sein:

|Wert|Beschreibung|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Das Registerkartenelement-Steuerelement ausgewählt ist.|
|TCIS_HIGHLIGHTED|Das Registerkartenelement-Steuerelement wird hervorgehoben, und die Registerkarte und Text werden mit der aktuellen Hervorhebungsfarbe gezeichnet. Wenn Hervorhebungsfarbe verwenden zu können, ist dies eine "true" Interpolation, keine Ditheringfarbe werden.|

### <a name="remarks"></a>Hinweise

Der Zustand eines Elements wird angegeben, indem die `dwState` Mitglied der `TCITEM` Struktur.

##  <a name="getrowcount"></a>  CTabCtrl::GetRowCount

Ruft die aktuelle Anzahl der Zeilen in einem Registersteuerelement an.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Zeilen mit Registerkarten im Registerkarten-Steuerelement.

### <a name="remarks"></a>Hinweise

Nur Registerkarten-Steuerelementen, die den Stil TCS_MULTILINE haben mehrere Zeilen mit Registerkarten.

##  <a name="gettooltips"></a>  CTabCtrl::GetToolTips

Ruft das Handle des ein Registerkarten-Steuerelement zugeordneten QuickInfo-Steuerelements ab.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Rückgabewert

Handle des QuickInfo-Steuerelements bei erfolgreicher Ausführung; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Ein Registerkarten-Steuerelement erstellt ein QuickInfo-Steuerelement, wenn sie den Stil TCS_TOOLTIPS verfügt. Sie können auch ein Registerkarten-Steuerelement ein QuickInfo-Steuerelement zuweisen, mit der `SetToolTips` Member-Funktion.

##  <a name="highlightitem"></a>  CTabCtrl::HighlightItem

Legt die Hervorhebung Zustand eines Registerkartenelements fest.

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>Parameter

*idItem*<br/>
Nullbasierte Index des ein Registerkartenelement-Steuerelement.

*fHighlight*<br/>
Wert, der den Status "Hervorhebung" festgelegt werden angibt. Wenn dieser Wert TRUE ist, ist die Registerkarte hervorgehoben. Wenn "FALSE" wird die Registerkarte auf den Standardzustand festgelegt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert die Win32-Meldung [TCM_HIGHLIGHTITEM](/windows/desktop/Controls/tcm-highlightitem), wie im Windows SDK beschrieben.

##  <a name="hittest"></a>  CTabCtrl::HitTest

Bestimmt, welcher Registerkarte, sofern vorhanden, an der angegebenen Bildschirmposition ist.

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>Parameter

*pHitTestInfo*<br/>
Zeiger auf eine [TCHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtchittestinfo) Struktur, siehe das Windows SDK, der zu testenden Bildschirmposition angibt.

### <a name="return-value"></a>Rückgabewert

Gibt den nullbasierten Index des von der Registerkarte "oder"-1 zurück, wenn keine Registerkarte an der angegebenen Position befindet.

##  <a name="insertitem"></a>  CTabCtrl:: InsertItem

Fügt eine neue Registerkarte in einem vorhandenen Registerkarten-Steuerelement ein.

```
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam,
    DWORD dwState,
    DWORD dwStateMask);
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
Nullbasierte Index der neuen Registerkarte.

*pTabCtrlItem*<br/>
Zeiger auf eine [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) -Struktur, die die Attribute der Registerkarte angibt.

*lpszItem*<br/>
Die Adresse einer Null-terminierte Zeichenfolge mit dem Text der Registerkarte.

*Nbild*<br/>
Der nullbasierte Index eines Bildes zum Einfügen von aus einer Bildliste.

*nMask*<br/>
Gibt an, welche `TCITEM` Struktur Attribute festlegen. 0 (null) oder eine Kombination der folgenden Werte sind möglich:

- TCIF_TEXT der `pszText` Member ist gültig.

- TCIF_IMAGE der `iImage` Member ist gültig.

- TCIF_PARAM der *lParam* Member ist gültig.

- TCIF_RTLREADING den Text der `pszText` mit rechts-nach-Links-Lesefolge auf Systemen mit Hebräisch oder Arabisch angezeigt wird.

- TCIF_STATE der *dwState-Datenmember* Member ist gültig.

*lParam*<br/>
Die Registerkarte zugeordnete anwendungsdefinierte Daten.

*dwState-Datenmember*<br/>
Gibt Werte für das Element-Zustände. Weitere Informationen finden Sie unter [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) im Windows SDK.

*den dwStateMask*<br/>
Gibt an, welche Zustände festgelegt werden. Weitere Informationen finden Sie unter [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Nullbasierte Index der neuen Registerkarte im Erfolgsfall, andernfalls andernfalls - 1.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

##  <a name="removeimage"></a>  CTabCtrl::RemoveImage

Entfernt das angegebene Bild aus einer Bildliste für ein Registerkarten-Steuerelement.

```
void RemoveImage(int nImage);
```

### <a name="parameters"></a>Parameter

*Nbild*<br/>
Nullbasierte Index des zu entfernenden Bildes.

### <a name="remarks"></a>Hinweise

Das Registerkarten-Steuerelement aktualisiert jede Registerkarte Abbildindex, sodass jede Registerkarte mit dem gleichen Image verbunden bleibt.

##  <a name="setcurfocus"></a>  CTabCtrl::SetCurFocus

Setzt den Fokus auf eine angegebene Registerkarte in einem Registersteuerelement an.

```
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
Gibt den Index der Registerkarte, die den Fokus erhält.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETCURFOCUS](/windows/desktop/Controls/tcm-setcurfocus), wie im Windows SDK beschrieben.

##  <a name="setcursel"></a>  CTabCtrl::SetCurSel

Wählt eine Registerkarte in einem Registersteuerelement an.

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
Der nullbasierte Index des Elements, das ausgewählt werden.

### <a name="return-value"></a>Rückgabewert

Nullbasierte Index, der zuvor ausgewählte Registerkarte im Erfolgsfall, andernfalls - 1.

### <a name="remarks"></a>Hinweise

Ein Registerkarten-Steuerelement sendet keine benachrichtigungsmeldung TCN_SELCHANGING oder TCN_SELCHANGE, wenn eine Registerkarte ausgewählt wird mit dieser Funktion. Diese Benachrichtigungen werden gesendet, mit der WM_NOTIFY, wenn der Benutzer klickt auf oder verwendet die Tastatur zum Ändern von Registerkarten.

##  <a name="setextendedstyle"></a>  CTabCtrl::SetExtendedStyle

Legt fest, die erweiterten Stile für ein Registerkarten-Steuerelement.

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>Parameter

*dwNewStyle*<br/>
Wert, der eine Kombination von Registerkarte steuern Erweiterte Stile.

*dwExMask*<br/>
Ein DWORD-Wert, der gibt an, welche Formate in *DwNewStyle* betroffen sind. Nur die erweiterten Stile in *DwExMask* wird geändert. Alle anderen Formate werden unverändert beibehalten. Wenn dieser Parameter 0 (null), und klicken Sie dann alle Formatvorlagen in *DwNewStyle* wirkt sich auf.

### <a name="return-value"></a>Rückgabewert

Eine DWORD-Wert, der die vorherige enthält [Registerkarten-Steuerelement, die erweiterte Stile](/windows/desktop/Controls/tab-control-extended-styles), wie im Windows SDK beschrieben.

### <a name="return-value"></a>Rückgabewert

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETEXTENDEDSTYLE](/windows/desktop/Controls/tcm-setextendedstyle), wie im Windows SDK beschrieben.

##  <a name="setimagelist"></a>  CTabCtrl::SetImageList

Weist eine Bildliste ein Registerkarten-Steuerelement.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parameter

*pImageList*<br/>
Zeiger auf die Bildliste des Registersteuerelements zugewiesen werden.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den vorherigen Bildliste oder NULL, wenn keine Liste der vorherigen Image vorhanden ist.

##  <a name="setitem"></a>  CTabCtrl::SetItem

Legt fest, einige oder alle der Registerkarte Attribute.

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
Nullbasierte Index des Elements.

*pTabCtrlItem*<br/>
Zeiger auf eine [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Struktur, die die neuen Elementattribute enthält. Die `mask` -Member gibt an, welche Attribute festlegen. Wenn die `mask` -Member gibt an, den TCIF_TEXT-Wert, der `pszText` Member ist die Adresse einer Null-terminierte Zeichenfolge und die `cchTextMax` Member wird ignoriert.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [GetItem](#getitem).

##  <a name="setitemextra"></a>  CTabCtrl::SetItemExtra

Legt die Anzahl von Bytes pro Registerkarte für die Anwendung definierte Daten in einem Registersteuerelement reserviert.

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>Parameter

*nBytes*<br/>
Die Anzahl der zusätzlichen Bytes festgelegt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETITEMEXTRA](/windows/desktop/Controls/tcm-setitemextra), wie im Windows SDK beschrieben.

##  <a name="setitemsize"></a>  CTabCtrl::SetItemSize

Legt die Breite und Höhe des Registerkarten-Steuerelements fest.

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Die neue Breite und Höhe des Registerkarten-Steuerelements in Pixeln.

### <a name="return-value"></a>Rückgabewert

Gibt die alte Breite und Höhe des Registerkarten-Steuerelements zurück.

##  <a name="setitemstate"></a>  CTabCtrl::SetItemState

Legt den Zustand des das Registerkartenelement-Steuerelement identifizierte *nItem*.

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
Die nullbasierte Indexnummer des Elements, für die Zustandsinformationen festgelegt.

*dwMask*<br/>
Maske, die angeben, welche von der Zustand des Elements flags festgelegt werden. Eine Liste von Werten, finden Sie unter der Mask-Member der [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Struktur, wie im Windows SDK beschrieben.

*dwState-Datenmember*<br/>
Ein Verweis auf einen DWORD-Wert, der die Informationen zum Ansichtszustand enthält. Kann einer der folgenden Werte sein:

|Wert|Beschreibung|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|Das Registerkartenelement-Steuerelement ausgewählt ist.|
|TCIS_HIGHLIGHTED|Das Registerkartenelement-Steuerelement wird hervorgehoben, und die Registerkarte und Text werden mit der aktuellen Hervorhebungsfarbe gezeichnet. Wenn Hervorhebungsfarbe verwenden zu können, ist dies eine "true" Interpolation, keine Ditheringfarbe werden.|

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="setmintabwidth"></a>  CTabCtrl::SetMinTabWidth

Legt die minimale Breite der Elemente in einem Registersteuerelement an.

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>Parameter

*CX*<br/>
Minimale Breite für ein Registerkartenelement-Steuerelement festgelegt werden. Wenn dieser Parameter auf-1 festgelegt ist, wird das Steuerelement die Standardbreite für Registerkarte verwenden.

### <a name="return-value"></a>Rückgabewert

Die vorherige Registerkarte "minimale" Breite.

### <a name="return-value"></a>Rückgabewert

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETMINTABWIDTH](/windows/desktop/Controls/tcm-setmintabwidth), wie im Windows SDK beschrieben.

##  <a name="setpadding"></a>  CTabCtrl::SetPadding

Legt die Größe des Speicherplatzes (Auffüllung) aus, um Symbol und eine Bezeichnung in einem Registersteuerelement jede Registerkarte fest.

```
void SetPadding(CSize size);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Legt die Größe des Speicherplatzes (Auffüllung) aus, um Symbol und eine Bezeichnung in einem Registersteuerelement jede Registerkarte fest.

##  <a name="settooltips"></a>  CTabCtrl::SetToolTips

Ein Registerkarten-Steuerelement wird ein QuickInfo-Steuerelement zugewiesen.

```
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Parameter

*pWndTip*<br/>
Handle des QuickInfo-Steuerelements.

### <a name="remarks"></a>Hinweise

Sie erhalten das QuickInfo-Steuerelement ein Registerkarten-Steuerelement zugeordnet sind, von einem Aufruf an `GetToolTips`.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CHeaderCtrl-Klasse](../../mfc/reference/cheaderctrl-class.md)<br/>
[CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)
