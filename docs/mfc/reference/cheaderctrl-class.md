---
title: CHeaderCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
helpviewer_keywords:
- CHeaderCtrl [MFC], CHeaderCtrl
- CHeaderCtrl [MFC], ClearAllFilters
- CHeaderCtrl [MFC], ClearFilter
- CHeaderCtrl [MFC], Create
- CHeaderCtrl [MFC], CreateDragImage
- CHeaderCtrl [MFC], CreateEx
- CHeaderCtrl [MFC], DeleteItem
- CHeaderCtrl [MFC], DrawItem
- CHeaderCtrl [MFC], EditFilter
- CHeaderCtrl [MFC], GetBitmapMargin
- CHeaderCtrl [MFC], GetFocusedItem
- CHeaderCtrl [MFC], GetImageList
- CHeaderCtrl [MFC], GetItem
- CHeaderCtrl [MFC], GetItemCount
- CHeaderCtrl [MFC], GetItemDropDownRect
- CHeaderCtrl [MFC], GetItemRect
- CHeaderCtrl [MFC], GetOrderArray
- CHeaderCtrl [MFC], GetOverflowRect
- CHeaderCtrl [MFC], HitTest
- CHeaderCtrl [MFC], InsertItem
- CHeaderCtrl [MFC], Layout
- CHeaderCtrl [MFC], OrderToIndex
- CHeaderCtrl [MFC], SetBitmapMargin
- CHeaderCtrl [MFC], SetFilterChangeTimeout
- CHeaderCtrl [MFC], SetFocusedItem
- CHeaderCtrl [MFC], SetHotDivider
- CHeaderCtrl [MFC], SetImageList
- CHeaderCtrl [MFC], SetItem
- CHeaderCtrl [MFC], SetOrderArray
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
ms.openlocfilehash: a683c877b67f4eae1a7411f5916987c9789b6817
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261348"
---
# <a name="cheaderctrl-class"></a>CHeaderCtrl-Klasse

Stellt die Funktionalität des allgemeinen Windows-Headersteuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Erstellt ein `CHeaderCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|Löscht alle Filter für ein Headersteuerelement.|
|[CHeaderCtrl::ClearFilter](#clearfilter)|Löscht den Filter für ein Headersteuerelement.|
|[CHeaderCtrl::Create](#create)|Erstellt ein Kopfzeilen-Steuerelement, und fügt sie an einer `CHeaderCtrl` Objekt.|
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Erstellt eine transparente Version eines Elements von Images in einem Kopfzeilen-Steuerelement.|
|[CHeaderCtrl::CreateEx](#createex)|Erstellt ein Headersteuerelement mit der angegebenen Erweiterte Stile für Windows und fügt sie an einer `CListCtrl` Objekt.|
|[CHeaderCtrl::DeleteItem](#deleteitem)|Löscht ein Element aus einem Kopfzeilen-Steuerelement.|
|[CHeaderCtrl::DrawItem](#drawitem)|Zeichnet das angegebene Element von einem Kopfzeilen-Steuerelement.|
|[CHeaderCtrl::EditFilter](#editfilter)|Startet den angegebenen Filter einem Kopfzeilen-Steuerelement zu bearbeiten.|
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Ruft die Breite des Rands einer Bitmap in einem Kopfzeilen-Steuerelement ab.|
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Ruft den Bezeichner des Elements im aktuellen Kopfzeilen-Steuerelement, das den den Fokus besitzt.|
|[CHeaderCtrl::GetImageList](#getimagelist)|Ruft das Handle einer Bildliste, die zum Zeichnen verwendeten Headerelemente in einem Kopfzeilen-Steuerelement ab.|
|[CHeaderCtrl::GetItem](#getitem)|Ruft Informationen zu einem Element in einem Kopfzeilen-Steuerelement ab.|
|[CHeaderCtrl::GetItemCount](#getitemcount)|Ruft die Anzahl der Elemente in einem Kopfzeilen-Steuerelement ab.|
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Ruft das umschließende Rechteck-Informationen für die angegebene Dropdown-Schaltfläche in einem Kopfzeilen-Steuerelement ab.|
|[CHeaderCtrl::GetItemRect](#getitemrect)|Ruft das umschließende Rechteck für ein bestimmtes Element in einem Kopfzeilen-Steuerelement ab.|
|[CHeaderCtrl::GetOrderArray](#getorderarray)|Ruft die links-nach-rechts-Reihenfolge der Elemente in einem Kopfzeilen-Steuerelement ab.|
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Ruft das umschließende Rechteck des der Überlaufschaltfläche für das aktuelle Kopfzeilen-Steuerelement ab.|
|[CHeaderCtrl::HitTest](#hittest)|Bestimmt, welche Headerelement, sofern vorhanden, an einem angegebenen Punkt befindet.|
|[CHeaderCtrl::InsertItem](#insertitem)|Fügt ein neues Element in einem Kopfzeilen-Steuerelement.|
|[CHeaderCtrl::Layout](#layout)|Ruft ab, die Größe und Position von einem Kopfzeilen-Steuerelement in einem bestimmten Rechteck.|
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Ruft den Indexwert für ein Element basierend auf der Reihenfolge, in dem Kopfzeilen-Steuerelement ab.|
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Legt die Breite des Rands einer Bitmap in einem Kopfzeilen-Steuerelement fest.|
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Legt das Timeout-Intervall zwischen dem Zeitpunkt, die eine Änderung in den Filterattributen erfolgt und der Bereitstellung einer `HDN_FILTERCHANGE` Benachrichtigung.|
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Legt den Fokus zu einem angegebenen Header-Element in der aktuellen Kopfzeilen-Steuerelement fest.|
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Ziehen der Unterteiler zwischen Header-Elemente an, dass eine manuelle Änderungen and -Drop ein Headerelement.|
|[CHeaderCtrl::SetImageList](#setimagelist)|Weist eine Bildliste einem Kopfzeilen-Steuerelement.|
|[CHeaderCtrl::SetItem](#setitem)|Legt die Attribute des angegebenen Elements in einem Kopfzeilen-Steuerelement fest.|
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Legt die links-nach-rechts-Reihenfolge der Elemente in einem Kopfzeilen-Steuerelement fest.|

## <a name="remarks"></a>Hinweise

Einem Kopfzeilen-Steuerelement ist ein Fenster, das in der Regel über einen Satz von Spalten von Text oder Zahlen positioniert ist. Sie enthält einen Titel für jede Spalte, und es kann in Teile unterteilt werden. Der Benutzer kann etwa einem Trennblatt ziehen, die Trennung der Teile, um die Breite der einzelnen Spalten festzulegen. Eine Abbildung einem Kopfzeilen-Steuerelement, finden Sie unter [Headersteuerelemente](/windows/desktop/Controls/header-controls).

Dieses Steuerelement (und somit die `CHeaderCtrl` Klasse) ist nur für Programme, die Ausführung unter Windows 95/98 und Windows NT, Version 3.51 und höher.

Funktionen für allgemeine Steuerelemente von Windows 95/Internet Explorer 4.0 umfasst Folgendes:

- Header Element benutzerdefinierte Sortierung.

- Headerelement- Drag & drop, für die neuanordnung der Headerelemente. Verwenden Sie die HDS_DRAGDROP-Stil, bei der Erstellung der `CHeaderCtrl` Objekt.

- Spalte Headertext ständig angezeigt werden kann, während die Spaltengröße. Verwenden Sie den HDS_FULLDRAG-Stil, bei der Erstellung einer `CHeaderCtrl` Objekt.

- Header hot Track, wodurch das Headerelement hervorgehoben wird, wenn der Mauszeiger darauf zeigt. Verwenden Sie das HDS_HOTTRACK-Format, bei der Erstellung der `CHeaderCtrl` Objekt.

- Unterstützung für Image-Liste. Header-Elemente können in gespeicherte Bildern enthalten eine `CImageList` Objekt oder Text.

Weitere Informationen zur Verwendung von `CHeaderCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CHeaderCtrl](../../mfc/using-cheaderctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="cheaderctrl"></a>  CHeaderCtrl::CHeaderCtrl

Erstellt ein `CHeaderCtrl`-Objekt.

```
CHeaderCtrl();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

##  <a name="clearallfilters"></a>  CHeaderCtrl::ClearAllFilters

Löscht alle Filter für ein Headersteuerelement.

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode implementiert, das Verhalten der Win32-Nachricht [HDM_CLEARFILTER](/windows/desktop/Controls/hdm-clearfilter) mit einem Spaltenwert-1 verwendet, wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

##  <a name="clearfilter"></a>  CHeaderCtrl::ClearFilter

Löscht den Filter für ein Headersteuerelement.

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>Parameter

*nColumn*<br/>
Der Spaltenwert, der angibt, welcher filter um zu löschen.

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode implementiert, das Verhalten der Win32-Nachricht [HDM_CLEARFILTER](/windows/desktop/Controls/hdm-clearfilter), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

##  <a name="create"></a>  CHeaderCtrl

Erstellt ein Kopfzeilen-Steuerelement, und fügt sie an einer `CHeaderCtrl` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt das Kopfzeilen-Steuerelement-Stil. Eine Beschreibung der Header der Stile von Listensteuerelementen, finden Sie unter [Steuerelementstile Kopfzeile](/windows/desktop/Controls/header-control-styles) im Windows SDK.

*rect*<br/>
Gibt an, des Kopfzeilen-Steuerelements die Größe und Position. Es kann sein, entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.

*pParentWnd*<br/>
Gibt an, das Kopfzeilen-Steuerelement übergeordnete Fenster, in der Regel eine `CDialog`. Es darf nicht NULL sein.

*nID*<br/>
Gibt das Kopfzeilen-Steuerelement-ID an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CHeaderCtrl` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie anschließend `Create`, die das Kopfzeilen-Steuerelement erstellt, und fügt es der `CHeaderCtrl` Objekt.

Zusätzlich zu den Header Stile von Listensteuerelementen, können Sie die folgenden allgemeinen Steuerelementstile um zu ermitteln, wie das Kopfzeilen-Steuerelement positioniert, und seine Größe selbst ändert (finden Sie unter [allgemeinen Stile von Listensteuerelementen](/windows/desktop/Controls/common-control-styles) Informationen):

- CCS_BOTTOM bewirkt, dass das Steuerelement selbst am unteren Rand des übergeordneten Fensters den Clientbereich zu positionieren und die Breite auf das übergeordnete Element identisch sein Breite des Fensters.

- CCS_NODIVIDER wird verhindert, dass ein zwei Pixel markieren Sie aus, die am oberen Rand des Steuerelements gezeichnet wird.

- CCS_NOMOVEY bewirkt, dass das Steuerelement die Größe und Position sich horizontal, aber nicht vertikal in Reaktion auf eine WM_SIZE-Meldung. Wenn der CCS_NORESIZE-Stil verwendet wird, gilt dieses Format nicht. Headersteuerelemente haben dieses Format wird standardmäßig an.

- CCS_NOPARENTALIGN wird verhindert, dass das Steuerelement automatisch verschieben in den oberen oder unteren Rand des übergeordneten Fensters. Stattdessen hält das Steuerelement seine Position innerhalb des übergeordneten Fensters trotz Änderungen auf die Größe des übergeordneten Fensters. Wenn auch der CCS_TOP-Format oder CCS_BOTTOM-Stil verwendet wird, wird die Höhe wird angepasst, auf den Standardwert, aber die Position und die Breite bleiben unverändert.

- CCS_NORESIZE wird verhindert, dass das Steuerelement die Standardbreite und-Höhe verwenden, wenn Sie die anfängliche Größe oder eine neue Größe festlegen. Stattdessen verwendet das Steuerelement an die Breite und Höhe, die in der Anforderung für die Erstellung oder größenanpassung angegeben.

- CCS_TOP-Format bewirkt, dass das Steuerelement selbst am oberen Rand des übergeordneten Fensters den Clientbereich zu positionieren und die Breite auf das übergeordnete Element identisch sein Breite des Fensters.

Sie können auch die folgenden Fensterstile anwenden, um einem Kopfzeilen-Steuerelement (finden Sie unter [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) Informationen):

- WS_CHILD erstellt ein untergeordnetes Fenster. Kann nicht mit dem WS_POPUP-Stil verwendet werden.

- WS_VISIBLE erstellt ein Fenster, das anfänglich sichtbar ist.

- WS_DISABLED erstellt ein Fenster, das anfänglich deaktiviert ist.

- WS_GROUP gibt das erste Steuerelement einer Gruppe von Steuerelementen, die in denen der Benutzer von einem Steuerelement zum nächsten mit den Pfeiltasten verschieben kann. Alle Steuerelemente, die mit dem WS_GROUP-Stil definiert wird, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit dem WS_GROUP-Stil der formatvorlagengruppe beendet und startet die nächste Gruppe (d. h. eine Gruppe endet, in dem die nächste beginnt).

- WS_TABSTOP gibt eine Reihe von Steuerelementen, die über denen der Benutzer mit der TAB-TASTE wechseln kann. Die TAB-Taste wechselt der Benutzer auf das nächste Steuerelement, das durch den Stil WS_TABSTOP angegeben.

Wenn Sie erweiterte Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von `Create`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

##  <a name="createex"></a>  CHeaderCtrl::CreateEx

Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnen Sie sie der `CHeaderCtrl` Objekt.

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
Format des Headersteuerelements. Eine Beschreibung der Header der Stile von Listensteuerelementen, finden Sie unter [Steuerelementstile Kopfzeile](/windows/desktop/Controls/header-control-styles) im Windows SDK. Finden Sie unter [erstellen](#create) eine Liste der zusätzlichen Formatvorlagen.

*rect*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt *pParentWnd*.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.

*nID*<br/>
Der ID des Steuerelements untergeordneten Fensters mit.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwendung `CreateEx` anstelle von `Create` anzuwendende Erweiterte Windows-Stile, angegeben durch den Wert der Windows-erweiterten Stil **WS_EX_**.

##  <a name="createdragimage"></a>  CHeaderCtrl::CreateDragImage

Erstellt eine transparente Version eines Elements von Images in einem Kopfzeilen-Steuerelement.

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der nullbasierte Index des Elements in dem Kopfzeilen-Steuerelement. Das Image mit diesem Element zugewiesen ist die Grundlage für die transparentes Bild.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, wenn erfolgreich; andernfalls NULL. Die zurückgegebene Liste enthält nur ein Bild.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_CREATEDRAGIMAGE](/windows/desktop/Controls/hdm-createdragimage), wie im Windows SDK beschrieben. Er wird bereitgestellt, um Header-Element ziehen und ablegen zu unterstützen.

Die `CImageList` Objekt, zu dem der zurückgegebene Zeiger weist, ist ein temporäres Objekt, und in der nächsten Verarbeitung der Leerlauf-Ablaufzeitpunkt gelöscht wird.

##  <a name="deleteitem"></a>  CHeaderCtrl::DeleteItem

Löscht ein Element aus einem Kopfzeilen-Steuerelement.

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Gibt an, der nullbasierte Index des zu löschenden Elements.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

##  <a name="drawitem"></a>  CHeaderCtrl::DrawItem

Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Header-Steuerelements ändert.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein Zeiger auf eine [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) Struktur, beschreibt das Element gezeichnet werden.

### <a name="remarks"></a>Hinweise

Die `itemAction` Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll.

Standardmäßig ist diese Member-Funktion mit "nothing". Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CHeaderCtrl` Objekt.

Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext in angegeben wiederherstellen *LpDrawItemStruct* vor diesem Member Funktion beendet wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

##  <a name="editfilter"></a>  CHeaderCtrl::EditFilter

Beginnt damit, den angegebenen Filter, der einem Kopfzeilen-Steuerelement zu bearbeiten.

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>Parameter

*nColumn*<br/>
Die Spalte zu bearbeiten.

*bDiscardChanges*<br/>
Ein Wert, der angibt, wie den Benutzer behandelt Änderungen der bearbeiten kann, wenn der Benutzer gerade den Filter bearbeiten bei der [HDM_EDITFILTER](/windows/desktop/Controls/hdm-editfilter) Nachricht gesendet wird.

Geben Sie "true", die vom Benutzer oder "false" an die vom Benutzer vorgenommenen Änderungen zu übernehmen vorgenommenen Änderungen zu verwerfen.

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode implementiert, das Verhalten der Win32-Nachricht [HDM_EDITFILTER](/windows/desktop/Controls/hdm-editfilter), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

##  <a name="getbitmapmargin"></a>  CHeaderCtrl::GetBitmapMargin

Ruft die Breite des Rands einer Bitmap in einem Kopfzeilen-Steuerelement ab.

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>Rückgabewert

Die Breite des Rands Bitmap in Pixel.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_GETBITMAPMARGIN](/windows/desktop/Controls/hdm-getbitmapmargin), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

##  <a name="getfocuseditem"></a>  CHeaderCtrl::GetFocusedItem

Ruft den Index des Elements, das in der aktuellen Kopfzeilen-Steuerelement den Fokus besitzt.

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des Headerelements, das den Fokus besitzt.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [HDM_GETFOCUSEDITEM](/windows/desktop/Controls/hdm-getfocuseditem) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. für den Zugriff auf das aktuelle Kopfzeilen-Steuerelement. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, die `SetFocusedItem` und `GetFocusedItem` Methoden. In einem vorherigen Abschnitt des Codes haben wir ein Kopfzeilen-Steuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht angezeigt wird. Im folgende Beispiel legt fest, und klicken Sie dann bestätigt die letzte Spaltenüberschrift wie das Element den Fokus.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="getimagelist"></a>  CHeaderCtrl::GetImageList

Ruft das Handle einer Bildliste, die zum Zeichnen verwendeten Headerelemente in einem Kopfzeilen-Steuerelement ab.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_GETIMAGELIST](/windows/desktop/Controls/hdm-getimagelist), wie im Windows SDK beschrieben. Die `CImageList` Objekt, zu dem der zurückgegebene Zeiger weist, ist ein temporäres Objekt, und in der nächsten Verarbeitung der Leerlauf-Ablaufzeitpunkt gelöscht wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

##  <a name="getitem"></a>  CHeaderCtrl::GetItem

Ruft Informationen über ein Headerelement-Steuerelement ab.

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Gibt an, der nullbasierte Index des abzurufenden Elements.

*pHeaderItem*<br/>
Zeiger auf ein [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) -Struktur, die das neue Element empfängt. Diese Struktur wird verwendet, mit der `InsertItem` und `SetItem` Memberfunktionen. Flags festgelegt wird, der `mask` Element stellen Sie sicher, dass die Werte in die entsprechenden Elemente bei der Rückgabe ordnungsgemäß ausgefüllt werden. Wenn die `mask` Element auf 0 (null) festgelegt ist, Werte in den anderen Strukturelementen sind bedeutungslos.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

##  <a name="getitemcount"></a>  CHeaderCtrl::GetItemCount

Ruft die Anzahl der Elemente in einem Kopfzeilen-Steuerelement ab.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Header-Steuerelemente, wenn erfolgreich; andernfalls - 1.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CHeaderCtrl::DeleteItem](#deleteitem).

##  <a name="getitemdropdownrect"></a>  CHeaderCtrl::GetItemDropDownRect

Ruft das umschließende Rechteck der Dropdown-Schaltfläche für ein Headerelement in der aktuellen Kopfzeilen-Steuerelement ab.

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iItem*|[in] Nullbasierte Index des ein Headerelement, dessen Stil HDF_SPLITBUTTON ist. Weitere Informationen finden Sie unter den `fmt` Mitglied der [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) Struktur.|
|*lpRect*|[out] Zeiger auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die umgebenden Rechteck Informationen zu erhalten.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Funktion erfolgreich ausgeführt wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [HDM_GETITEMDROPDOWNRECT](/windows/desktop/Controls/hdm-getitemdropdownrect) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. für den Zugriff auf das aktuelle Kopfzeilen-Steuerelement. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, die `GetItemDropDownRect` Methode. In einem vorherigen Abschnitt des Codes haben wir ein Kopfzeilen-Steuerelement mit fünf Spalten erstellt. Im folgenden Codebeispiel wird zeichnet ein 3D Rechteck um die Position in der ersten Spalte, die für das Dropdown-Schaltfläche "Spaltenüberschrift" reserviert ist.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

##  <a name="getitemrect"></a>  CHeaderCtrl::GetItemRect

Ruft das umschließende Rechteck für ein bestimmtes Element in einem Kopfzeilen-Steuerelement ab.

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der nullbasierte Index, der das Headerelement-Steuerelement.

*lpRect*<br/>
Ein Zeiger auf die Adresse einer [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die umschließende Rechteck Informationen empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Methode implementiert, das Verhalten der Win32-Nachricht [HDM_GETITEMRECT](/windows/desktop/Controls/hdm-getitemrect), wie im Windows SDK beschrieben.

##  <a name="getorderarray"></a>  CHeaderCtrl:: GetOrderArray

Ruft die links-nach-rechts-Reihenfolge der Elemente in einem Kopfzeilen-Steuerelement ab.

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>Parameter

*piArray*<br/>
Ein Zeiger auf die Adresse eines Puffers, der die Indexwerte der Elemente im Kopfzeilen-Steuerelement, in der Reihenfolge empfängt, in dem sie von links nach rechts angezeigt werden.

*iCount*<br/>
Die Anzahl der Header-Steuerelemente. Darf nicht negativ sein.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_GETORDERARRAY](/windows/desktop/Controls/hdm-getorderarray), wie im Windows SDK beschrieben. Er wird bereitgestellt, um Header Elementreihenfolge zu unterstützen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

##  <a name="getoverflowrect"></a>  CHeaderCtrl::GetOverflowRect

Ruft das umschließende Rechteck des dokumentüberlauf-Schaltfläche, der dem aktuellen Kopfzeilen-Steuerelement ab.

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*lpRect*|[out] Zeiger auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die umschließende Rechteck Informationen empfängt.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Funktion erfolgreich ausgeführt wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

Enthält das Kopfzeilen-Steuerelement mehr Elemente als gleichzeitig angezeigt werden kann, kann das Steuerelement eine Überlaufschaltfläche an, die gescrollt für Elemente anzeigen, die nicht sichtbar sind. Das Kopfzeilen-Steuerelement muss die HDS_OVERFLOW und HDF_SPLITBUTTON Stile zum Anzeigen der Schaltfläche "Überlauf" verfügen. Das umschließende Rechteck der Schaltfläche "Überlauf" umschließt und existiert nur, wenn die Schaltfläche "Überlauf" angezeigt wird. Weitere Informationen finden Sie unter [Steuerelementstile Kopfzeile](/windows/desktop/Controls/header-control-styles).

Diese Methode sendet die [HDM_GETOVERFLOWRECT](/windows/desktop/Controls/hdm-getoverflowrect) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. für den Zugriff auf das aktuelle Kopfzeilen-Steuerelement. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, die `GetOverflowRect` Methode. In einem vorherigen Abschnitt des Codes haben wir ein Kopfzeilen-Steuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht angezeigt wird. Wenn einige Spalten nicht angezeigt werden, zeichnet das Kopfzeilen-Steuerelement eine Überlaufschaltfläche an. Im folgenden Codebeispiel wird zeichnet ein 3D-Rechteck, um den Speicherort der der Schaltfläche "Überlauf".

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

##  <a name="hittest"></a>  CHeaderCtrl::HitTest

Bestimmt, welche Headerelement, sofern vorhanden, an einem angegebenen Punkt befindet.

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*phdhti*|[in, out] Zeiger auf eine [HDHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-_hd_hittestinfo) Struktur, die den zu überprüfenden Punkt gibt an, und erhält die Ergebnisse des Tests.|

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des Headerelements, sofern vorhanden, an der angegebenen Position; andernfalls -1.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [HDM_HITTEST](/windows/desktop/Controls/hdm-hittest) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. für den Zugriff auf das aktuelle Kopfzeilen-Steuerelement. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, die `HitTest` Methode. Im weiter oben in diesem Codebeispiel wird haben wir ein Kopfzeilen-Steuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht angezeigt wird. In diesem Beispiel gibt den Index der Spalte aus, wenn es sichtbar ist, und 1, wenn die Spalte nicht angezeigt wird.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

##  <a name="insertitem"></a>  InsertItem

Fügt ein neues Element in einem Kopfzeilen-Steuerelement am angegebenen Index.

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Der nullbasierte Index des einzufügenden Elements. Wenn der Wert 0 (null) ist, wird das Element am Anfang des Headersteuerelements eingefügt. Wenn der Wert größer als der maximale Wert ist, wird das Element am Ende des Headersteuerelements eingefügt.

*phdi*<br/>
Zeiger auf ein [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) -Struktur, enthält Informationen über das Element eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Der Index des neuen Elements, wenn erfolgreich; andernfalls - 1.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

##  <a name="layout"></a>  CHeaderCtrl:: Layout

Ruft ab, die Größe und Position von einem Kopfzeilen-Steuerelement in einem bestimmten Rechteck.

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>Parameter

*pHeaderLayout*<br/>
Zeiger auf ein [HDLAYOUT](/windows/desktop/api/commctrl/ns-commctrl-_hd_layout) -Struktur, die Informationen zum Festlegen der Größe und Position von einem Kopfzeilen-Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Funktion wird verwendet, um den entsprechenden Dimensionen für ein neues Headersteuerelement zu ermitteln, die im angegebene Rechteck einnehmen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

##  <a name="ordertoindex"></a>  CHeaderCtrl::OrderToIndex

Ruft den Indexwert für ein Element basierend auf der Reihenfolge, in dem Kopfzeilen-Steuerelement ab.

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>Parameter

*nOrder*<br/>
Die nullbasierte Reihenfolge, die das Element im Kopfzeilen-Steuerelement, von links nach rechts angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Der Index des Elements basierend auf der Reihenfolge, in dem Kopfzeilen-Steuerelement. Der Index wird von links nach rechts und beginnend mit 0 gezählt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten des Win32-Makros [HDM_ORDERTOINDEX](https://msdn.microsoft.com/library/windows/desktop/bb775355), wie im Windows SDK beschrieben. Er wird bereitgestellt, um Header Elementreihenfolge zu unterstützen.

##  <a name="setbitmapmargin"></a>  CHeaderCtrl::SetBitmapMargin

Legt die Breite des Rands einer Bitmap in einem Kopfzeilen-Steuerelement fest.

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>Parameter

*nWidth*<br/>
Breite in Pixel der Rand, der eine Bitmap in einem vorhandenen Headersteuerelement umgeben ist angegeben.

### <a name="return-value"></a>Rückgabewert

Die Breite des Rands Bitmap in Pixel.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETBITMAPMARGIN](/windows/desktop/Controls/hdm-setbitmapmargin), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

##  <a name="setfilterchangetimeout"></a>  CHeaderCtrl::SetFilterChangeTimeout

Legt das Timeout-Intervall zwischen dem Zeitpunkt, die eine Änderung in den Filterattributen erfolgt und der Bereitstellung einer [HDN_FILTERCHANGE](/windows/desktop/Controls/hdn-filterchange) Benachrichtigung.

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>Parameter

*dwTimeOut*<br/>
Timeoutwert in Millisekunden.

### <a name="return-value"></a>Rückgabewert

Der Index des Filter-Steuerelements geändert wird.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETFILTERCHANGETIMEOUT](/windows/desktop/Controls/hdm-setfilterchangetimeout), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

##  <a name="setfocuseditem"></a>  CHeaderCtrl::SetFocusedItem

Legt den Fokus zu einem angegebenen Header-Element in der aktuellen Kopfzeilen-Steuerelement fest.

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iItem*|[in] Nullbasierte Index des Headerelements.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [HDM_SETFOCUSEDITEM](/windows/desktop/Controls/hdm-setfocuseditem) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. für den Zugriff auf das aktuelle Kopfzeilen-Steuerelement. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, die `SetFocusedItem` und `GetFocusedItem` Methoden. In einem vorherigen Abschnitt des Codes haben wir ein Kopfzeilen-Steuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht angezeigt wird. Im folgende Beispiel legt fest, und klicken Sie dann bestätigt die letzte Spaltenüberschrift wie das Element den Fokus.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="sethotdivider"></a>  CHeaderCtrl::SetHotDivider

Ziehen der Unterteiler zwischen Header-Elemente an, dass eine manuelle Änderungen and -Drop ein Headerelement.

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Die Position des Zeigers. Das Kopfzeilen-Steuerelement werden die entsprechenden Trennlinie, die auf der Grundlage des Zeigers Position hervorgehoben.

*nIndex*<br/>
Der Index des Unterteilers hervorgehoben.

### <a name="return-value"></a>Rückgabewert

Der Index des Unterteilers hervorgehoben.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETHOTDIVIDER](/windows/desktop/Controls/hdm-sethotdivider), wie im Windows SDK beschrieben. Er wird bereitgestellt, um Header-Element ziehen und ablegen zu unterstützen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

##  <a name="setimagelist"></a>  :: SetImageList

Weist eine Bildliste einem Kopfzeilen-Steuerelement.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parameter

*pImageList*<br/>
Ein Zeiger auf eine `CImageList` -Objekt, enthält die Liste der Bilder, dem Kopfzeilen-Steuerelement zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die [CImageList](../../mfc/reference/cimagelist-class.md) Objekt zuvor, dem Kopfzeilen-Steuerelement zugewiesen ist.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETIMAGELIST](/windows/desktop/Controls/hdm-setimagelist), wie im Windows SDK beschrieben. Die `CImageList` Objekt, zu dem der zurückgegebene Zeiger weist, ist ein temporäres Objekt, und in der nächsten Verarbeitung der Leerlauf-Ablaufzeitpunkt gelöscht wird.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CHeaderCtrl::GetImageList](#getimagelist).

##  <a name="setitem"></a>  CHeaderCtrl::SetItem

Legt die Attribute des angegebenen Elements in einem Kopfzeilen-Steuerelement fest.

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Der nullbasierte Index des Elements, das bearbeitet werden.

*pHeaderItem*<br/>
Zeiger auf ein [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) -Struktur, die Informationen über das neue Element enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CHeaderCtrl:: GetItem](#getitem).

##  <a name="setorderarray"></a>  CHeaderCtrl::SetOrderArray

Legt die links-nach-rechts-Reihenfolge der Elemente in einem Kopfzeilen-Steuerelement fest.

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>Parameter

*iCount*<br/>
Die Anzahl der Header-Steuerelemente.

*piArray*<br/>
Ein Zeiger auf die Adresse eines Puffers, der die Indexwerte der Elemente im Kopfzeilen-Steuerelement, in der Reihenfolge empfängt, in dem sie von links nach rechts angezeigt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten des Win32-Makros [HDM_SETORDERARRAY](/windows/desktop/Controls/hdm-setorderarray), wie im Windows SDK beschrieben. Er wird bereitgestellt, um Header Elementreihenfolge zu unterstützen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CHeaderCtrl:: GetOrderArray](#getorderarray).

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CTabCtrl-Klasse](../../mfc/reference/ctabctrl-class.md)<br/>
[CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)<br/>
[CImageList-Klasse](../../mfc/reference/cimagelist-class.md)
