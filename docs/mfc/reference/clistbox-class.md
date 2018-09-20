---
title: CListBox-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CListBox
- AFXWIN/CListBox
- AFXWIN/CListBox::CListBox
- AFXWIN/CListBox::AddString
- AFXWIN/CListBox::CharToItem
- AFXWIN/CListBox::CompareItem
- AFXWIN/CListBox::Create
- AFXWIN/CListBox::DeleteItem
- AFXWIN/CListBox::DeleteString
- AFXWIN/CListBox::Dir
- AFXWIN/CListBox::DrawItem
- AFXWIN/CListBox::FindString
- AFXWIN/CListBox::FindStringExact
- AFXWIN/CListBox::GetAnchorIndex
- AFXWIN/CListBox::GetCaretIndex
- AFXWIN/CListBox::GetCount
- AFXWIN/CListBox::GetCurSel
- AFXWIN/CListBox::GetHorizontalExtent
- AFXWIN/CListBox::GetItemData
- AFXWIN/CListBox::GetItemDataPtr
- AFXWIN/CListBox::GetItemHeight
- AFXWIN/CListBox::GetItemRect
- AFXWIN/CListBox::GetListBoxInfo
- AFXWIN/CListBox::GetLocale
- AFXWIN/CListBox::GetSel
- AFXWIN/CListBox::GetSelCount
- AFXWIN/CListBox::GetSelItems
- AFXWIN/CListBox::GetText
- AFXWIN/CListBox::GetTextLen
- AFXWIN/CListBox::GetTopIndex
- AFXWIN/CListBox::InitStorage
- AFXWIN/CListBox::InsertString
- AFXWIN/CListBox::ItemFromPoint
- AFXWIN/CListBox::MeasureItem
- AFXWIN/CListBox::ResetContent
- AFXWIN/CListBox::SelectString
- AFXWIN/CListBox::SelItemRange
- AFXWIN/CListBox::SetAnchorIndex
- AFXWIN/CListBox::SetCaretIndex
- AFXWIN/CListBox::SetColumnWidth
- AFXWIN/CListBox::SetCurSel
- AFXWIN/CListBox::SetHorizontalExtent
- AFXWIN/CListBox::SetItemData
- AFXWIN/CListBox::SetItemDataPtr
- AFXWIN/CListBox::SetItemHeight
- AFXWIN/CListBox::SetLocale
- AFXWIN/CListBox::SetSel
- AFXWIN/CListBox::SetTabStops
- AFXWIN/CListBox::SetTopIndex
- AFXWIN/CListBox::VKeyToItem
dev_langs:
- C++
helpviewer_keywords:
- CListBox [MFC], CListBox
- CListBox [MFC], AddString
- CListBox [MFC], CharToItem
- CListBox [MFC], CompareItem
- CListBox [MFC], Create
- CListBox [MFC], DeleteItem
- CListBox [MFC], DeleteString
- CListBox [MFC], Dir
- CListBox [MFC], DrawItem
- CListBox [MFC], FindString
- CListBox [MFC], FindStringExact
- CListBox [MFC], GetAnchorIndex
- CListBox [MFC], GetCaretIndex
- CListBox [MFC], GetCount
- CListBox [MFC], GetCurSel
- CListBox [MFC], GetHorizontalExtent
- CListBox [MFC], GetItemData
- CListBox [MFC], GetItemDataPtr
- CListBox [MFC], GetItemHeight
- CListBox [MFC], GetItemRect
- CListBox [MFC], GetListBoxInfo
- CListBox [MFC], GetLocale
- CListBox [MFC], GetSel
- CListBox [MFC], GetSelCount
- CListBox [MFC], GetSelItems
- CListBox [MFC], GetText
- CListBox [MFC], GetTextLen
- CListBox [MFC], GetTopIndex
- CListBox [MFC], InitStorage
- CListBox [MFC], InsertString
- CListBox [MFC], ItemFromPoint
- CListBox [MFC], MeasureItem
- CListBox [MFC], ResetContent
- CListBox [MFC], SelectString
- CListBox [MFC], SelItemRange
- CListBox [MFC], SetAnchorIndex
- CListBox [MFC], SetCaretIndex
- CListBox [MFC], SetColumnWidth
- CListBox [MFC], SetCurSel
- CListBox [MFC], SetHorizontalExtent
- CListBox [MFC], SetItemData
- CListBox [MFC], SetItemDataPtr
- CListBox [MFC], SetItemHeight
- CListBox [MFC], SetLocale
- CListBox [MFC], SetSel
- CListBox [MFC], SetTabStops
- CListBox [MFC], SetTopIndex
- CListBox [MFC], VKeyToItem
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ceef559e83b111a9ca8bcb96541fe8fbda19cf0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387173"
---
# <a name="clistbox-class"></a>CListBox-Klasse

Stellt die Funktionalität eines Windows-Listenfelds bereit.

## <a name="syntax"></a>Syntax

```
class CListBox : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CListBox::CListBox](#clistbox)|Erstellt ein `CListBox`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CListBox::AddString](#addstring)|Ein Listenfeld, das hinzugefügt eine Zeichenfolge.|
|[CListBox::CharToItem](#chartoitem)|Außer Kraft setzen Sie, um benutzerdefinierte WM_CHAR Klassenbehandlung für das Ownerdrawn-Listenfeldern die Zeichenfolgen haben keine bereitzustellen.|
|[CListBox::CompareItem](#compareitem)|Wird aufgerufen, durch das Framework, um die Position eines neuen Elements in einem sortierten Ownerdrawn-Listenfeld zu ermitteln.|
|[CListBox::Create](#create)|Erstellt im Windows-Listenfeld aus, und fügt es der `CListBox` Objekt.|
|[CListBox::DeleteItem](#deleteitem)|Wird vom Framework aufgerufen, wenn der Benutzer ein Element aus einem Ownerdrawn-Listenfeld löscht.|
|[CListBox::DeleteString](#deletestring)|Löscht eine Zeichenfolge aus einem Listenfeld.|
|[CListBox::Dir](#dir)|Fügt Dateinamen, Laufwerke oder beides aus dem aktuellen Verzeichnis in ein Listenfeld an.|
|[CListBox::DrawItem](#drawitem)|Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Liste im Feld ändert.|
|[CListBox:: FindString](#findstring)|Sucht nach einer Zeichenfolge in einem Listenfeld.|
|[CListBox::FindStringExact](#findstringexact)|Sucht die erste Listenfeld-Zeichenfolge, die einer angegebenen Zeichenfolge übereinstimmt.|
|[CListBox::GetAnchorIndex](#getanchorindex)|Ruft ab, der nullbasierte Index des aktuellen Elements in einem Listenfeld Anker.|
|[CListBox::GetCaretIndex](#getcaretindex)|Bestimmt den Index des Elements, das das Fokusrechteck in einem Mehrfachauswahl-Listenfeld hat.|
|[CListBox::GetCount](#getcount)|Gibt die Anzahl der Zeichenfolgen in einem Listenfeld zurück.|
|[CListBox::GetCurSel](#getcursel)|Gibt den nullbasierten Index des aktuell ausgewählten Zeichenfolge in einem Listenfeld zurück.|
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|Gibt die Breite in Pixel, ein Listenfeld, das ein horizontaler Bildlauf durchgeführt werden kann.|
|[CListBox::GetItemData](#getitemdata)|Gibt den 32-Bit-Wert, der dem Listenfeld-Element zugeordnet.|
|[CListBox::GetItemDataPtr](#getitemdataptr)|Gibt einen Zeiger auf ein Element im Listenfeld an.|
|[CListBox::GetItemHeight](#getitemheight)|Bestimmt die Höhe der Elemente in einem Listenfeld.|
|[CListBox::GetItemRect](#getitemrect)|Gibt das umschließende Rechteck des Elements im Listenfeld an, wie er derzeit angezeigt wird.|
|[CListBox::GetListBoxInfo](#getlistboxinfo)|Ruft die Anzahl von Elementen pro Spalte.|
|[CListBox::GetLocale](#getlocale)|Ruft den Gebietsschemabezeichner für ein Listenfeld ab.|
|[CListBox::GetSel](#getsel)|Gibt den Auswahlzustand eines Elements im Listenfeld an.|
|[CListBox::GetSelCount](#getselcount)|Gibt die Anzahl von Zeichenfolgen, die derzeit in einem Mehrfachauswahl-Listenfeld ausgewählt.|
|[CListBox::GetSelItems](#getselitems)|Gibt zurück, die Indizes der Zeichenfolgen, die derzeit in einem Listenfeld ausgewählt.|
|[CListBox::GetText](#gettext)|Kopiert ein Listenfeld-Element in einen Puffer.|
|[CListBox::GetTextLen](#gettextlen)|Gibt die Länge in Bytes ein Listenfeld-Element zurück.|
|[CListBox::GetTopIndex](#gettopindex)|Gibt den Index des ersten sichtbaren Zeichenfolge in einem Listenfeld zurück.|
|[CListBox::InitStorage](#initstorage)|Belegt Speicherblöcke Listenfeldelemente und Zeichenfolgen.|
|[CListBox::InsertString](#insertstring)|Fügt eine Zeichenfolge an einer bestimmten Stelle in einem Listenfeld.|
|[CListBox::ItemFromPoint](#itemfrompoint)|Gibt den Index des Elements im Listenfeld nächste einen Punkt.|
|[CListBox::MeasureItem](#measureitem)|Vom Framework aufgerufen, wenn ein Ownerdrawn-Listenfeld erstellt wird, um zu bestimmen, Listenfeld Dimensionen.|
|[CListBox::ResetContent](#resetcontent)|Löscht alle Einträge aus einem Listenfeld.|
|[CListBox::SelectString](#selectstring)|Sucht und wählt aus einer Zeichenfolge in einem Mehrfachauswahl-Listenfeld.|
|[CListBox::SelItemRange](#selitemrange)|Aktiviert bzw. deaktiviert einen Bereich von Zeichenfolgen in einem Mehrfachauswahl-Listenfeld.|
|[CListBox::SetAnchorIndex](#setanchorindex)|Legt den Anker in einem Mehrfachauswahl-Listenfeld um eine erweiterte Auswahl zu beginnen.|
|[CListBox::SetCaretIndex](#setcaretindex)|Legt das Fokusrechteck auf das Element am angegebenen Index in einem Mehrfachauswahl-Listenfeld fest.|
|[CListBox::SetColumnWidth](#setcolumnwidth)|Wird die Breite der ein mehrspaltiges Listenfeld an.|
|[CListBox::SetCurSel](#setcursel)|Wählt eine Zeichenfolge im Listenfeld aus.|
|[CListBox:: SetHorizontalExtent](#sethorizontalextent)|Legt die Breite in Pixel, ein Listenfeld, das ein horizontaler Bildlauf durchgeführt werden kann.|
|[CListBox::SetItemData](#setitemdata)|Legt den 32-Bit-Wert, der dem Listenfeld-Element zugeordnet.|
|[CListBox::SetItemDataPtr](#setitemdataptr)|Legt einen Zeiger auf das Listenfeld-Element fest.|
|[CListBox::SetItemHeight](#setitemheight)|Legt die Höhe der Elemente in einem Listenfeld fest.|
|[CListBox::SetLocale](#setlocale)|Legt den Gebietsschemabezeichner für ein Listenfeld, das fest.|
|[CListBox::SetSel](#setsel)|Wählt oder hebt die Auswahl eines Elements im Listenfeld in einem Mehrfachauswahl-Listenfeld.|
|[CListBox::SetTabStops](#settabstops)|Legt fest, die Tabstopp Positionen in einem Listenfeld.|
|[CListBox::SetTopIndex](#settopindex)|Legt den nullbasierten Index des ersten sichtbaren Zeichenfolge in einem Listenfeld fest.|
|[CListBox::VKeyToItem](#vkeytoitem)|Außer Kraft setzen Sie, um benutzerdefinierte Behandlung für Listenfelder mit festgelegtem Format LBS_WANTKEYBOARDINPUT WM_KEYDOWN bereitzustellen.|

## <a name="remarks"></a>Hinweise

Ein Listenfeld zeigt eine Liste der Elemente, z. B. Dateinamen, die der Benutzer anzeigen und auswählen kann.

In einem Mehrfachauswahl-Listenfeld kann der Benutzer nur ein Element auswählen. In einem Mehrfachauswahl-Listenfeld kann ein Bereich von Elementen ausgewählt werden. Wenn der Benutzer ein Element auswählt, wird dieses hervorgehoben, und das Listenfeld sendet eine Benachrichtigung an das übergeordnete Fenster.

Sie können ein Listenfeld, das entweder aus einer Dialogfeldvorlage oder direkt in Ihrem Code erstellen. Um direkt zu erstellen, erstellen die `CListBox` Objekt aus, und rufen Sie dann die [erstellen](#create) Memberfunktion versucht, erstellen Sie das Windows-Listenfeld-Steuerelement, und fügen Sie ihn auf die `CListBox` Objekt. Um ein Listenfeld, das in einer Dialogfeldvorlage verwenden zu können, deklarieren Sie in Ihre Dialogfeldklasse Listenfeld Variable, und verwenden Sie `DDX_Control` in Ihre Dialogfeldklasse `DoDataExchange` Funktion, um die Membervariable auf das Steuerelement eine Verbindung herstellen. (Dies ist für Sie automatisch konfiguriert, wenn Sie Ihre Dialogfeldklasse eine Steuerelementvariable hinzufügen.)

Erstellung kann ein langwieriger Vorgang in einer Klasse abgeleitet sein `CListBox`. Schreiben Sie einen Konstruktor für die abgeleitete Klasse und rufen `Create` von innerhalb des Konstruktors.

Wenn Sie Windows gesendete benachrichtigungsmeldungen von ein Listenfeld, das an der übergeordnete behandeln möchten (in der Regel eine abgeleitete Klasse [CDialog](../../mfc/reference/cdialog-class.md)), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag "und"-Nachrichtenhandler-Memberfunktion hinzugefügt.

Jede Nachricht-Zuordnungseintrag weist folgende Form:

`ON_Notification( id, memberFxn )`

wo `id` gibt die untergeordneten Fenster-ID des Listenfeld-Steuerelements, das Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten Member-Funktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.

Funktionsprototyp des übergeordneten Elements lautet wie folgt aus:

`afx_msg void memberFxn( );`

Es folgt eine Liste der möglichen Meldungszuordnungseinträge und eine Beschreibung der Fälle in denen sie das dem übergeordneten gesendet werden sollen:

- ON_LBN_DBLCLK der Benutzer doppelklickt eine Zeichenfolge in einem Listenfeld. Nur ein Listenfeld, die die [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Stil wird diese Benachrichtigung gesendet.

- ON_LBN_ERRSPACE im Listenfeld Speicherplatz nicht genügend zum Erfüllen der Anforderungs.

- ON_LBN_KILLFOCUS im Listenfeld verliert den Eingabefokus.

- ON_LBN_SELCANCEL die aktuelle Auswahl im Listenfeld wird abgebrochen. Diese Meldung wird nur gesendet, wenn ein Listenfeld, das das LBS_NOTIFY-Format aufweist.

- ON_LBN_SELCHANGE die Auswahl im Listenfeld hat sich geändert. Diese Benachrichtigung wird nicht gesendet werden, wenn die Auswahl, durch geändert wird die [CListBox::SetCurSel](#setcursel) Member-Funktion. Diese Benachrichtigung gilt nur für ein Listenfeld, das den Stil LBS_NOTIFY verfügt. Die benachrichtigungsmeldung LBN_SELCHANGE wird für eine Mehrfachauswahl-Listenfeld gesendet, wenn der Benutzer eine Taste drückt, auch wenn die Auswahl nicht geändert wird.

- ON_LBN_SETFOCUS im Listenfeld empfängt den Eingabefokus.

- ON_WM_CHARTOITEM ein Ownerdrawn-Listenfeld aus, die keine Zeichenfolgen empfängt eine Meldung WM_CHAR.

- ON_WM_VKEYTOITEM ein Listenfeld mit dem Stil LBS_WANTKEYBOARDINPUT empfängt eine WM_KEYDOWN-Meldung.

Bei der Erstellung einer `CListBox` Objekt in einem Dialogfeld (mithilfe einer Ressource), die `CListBox` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.

Bei der Erstellung einer `CListBox` Objekt innerhalb eines Zeitfensters, müssen Sie möglicherweise zerstört die `CListBox` Objekt. Bei der Erstellung der `CListBox` Objekt im Stapel automatisch zerstört wird. Bei der Erstellung der `CListBox` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das es zerstört, wenn der Benutzer das übergeordnete Fenster geschlossen wird.

Wenn Sie im Arbeitsspeicher zuordnen der `CListBox` Objekt außer Kraft, indem die `CListBox` Destruktor, der die Zuordnung zu verwerfen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="addstring"></a>  CListBox::AddString

Ein Listenfeld, das hinzugefügt eine Zeichenfolge.

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>Parameter

*lpszItem*<br/>
Verweist auf die Null-terminierte Zeichenfolge, die hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index in die Zeichenfolge in das Listenfeld. Der Rückgabewert ist LB_ERR auf, wenn ein Fehler auftritt; der Rückgabewert ist LB_ERRSPACE auf, wenn nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge verfügbar ist.

### <a name="remarks"></a>Hinweise

Wenn das Listenfeld nicht erstellt wurde, mit der [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Stil, die Zeichenfolge am Ende der Liste hinzugefügt wird. Andernfalls wird die Zeichenfolge in die Liste eingefügt, und die Liste sortiert wird. Wenn das Listenfeld mit den LBS_SORT-Stil erstellt wurde, nicht jedoch die [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Format, das Framework sortiert die Liste durch einen oder mehrere Aufrufe der `CompareItem` Member-Funktion.

Verwendung [InsertString](#insertstring) um eine Zeichenfolge an einer bestimmten Position innerhalb des Listenfelds einzufügen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

##  <a name="chartoitem"></a>  CListBox::CharToItem

Vom Framework aufgerufen, wenn das Listenfeld übergeordnetes Fenster eine WM_CHARTOITEM-Nachricht aus dem Listenfeld empfängt.

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Parameter

*nKey*<br/>
Der ANSI-Code, der das Zeichen, die der Benutzer eingegeben werden soll.

*nIndex*<br/>
Die aktuelle Position der Einfügemarke im Listenfeld.

### <a name="return-value"></a>Rückgabewert

Gibt - 1 "oder"-2 für die keine weitere Aktion oder eine nicht negative Zahl an einen Index eines Elements im Listenfeld für die die Standardaktion für die Tastatureingabe ausgeführt. Die Standardimplementierung gibt - 1.

### <a name="remarks"></a>Hinweise

Vom Listenfeld wird die WM_CHARTOITEM-Nachricht gesendet, wenn sie eine WM_CHAR-Meldung empfängt, aber nur verwendet werden, wenn das Listenfeld alle folgenden Kriterien erfüllt:

- Ist ein Ownerdrawn-Listenfeld.

- Verfügt nicht über die [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Satz formatieren.

- Verfügt über mindestens ein Element aus.

Sie sollten diese Funktion nicht selbst aufrufen. Überschreiben Sie diese Funktion, um eigene benutzerdefinierte Behandlung von tastaturmeldungen bereitzustellen.

In der Überschreibung müssen Sie einen Wert, um dem Framework angeben, welche Aktion Sie ausführen, zurückgeben. Ein Rückgabewert von - 1 "oder"-2, gibt Sie an, dass Sie alle Aspekte der Auswahl des Elements behandelt und erfordert keine weitere Aktion vom Listenfeld. Vor der Rückgabe - 1 - 2, Sie konnten legen Sie die Auswahl oder Verschieben der Einfügemarke oder beides. Verwenden Sie zum Festlegen der Auswahl [SetCurSel](#setcursel) oder [Memberfunktion SetSel](#setsel). Verwenden Sie zum Verschieben der Einfügemarke [SetCaretIndex](#setcaretindex).

Ein Wert zurückgegeben, der größer oder gleich 0 gibt den Index eines Elements in das Listenfeld und gibt an, dass das Listenfeld die Standardaktion für die Tastatureingabe auf das angegebene Element ausführen soll.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

##  <a name="clistbox"></a>  CListBox::CListBox

Erstellt ein `CListBox`-Objekt.

```
CListBox();
```

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CListBox` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor `ClistBox` und rufen dann `Create`, die das Windows-Listenfeld initialisiert und fügt es der `CListBox`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

##  <a name="compareitem"></a>  CListBox::CompareItem

Wird aufgerufen, durch das Framework, um die relative Position eines neuen Elements in einem sortierten Ownerdrawn-Listenfeld zu ermitteln.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Parameter

*lpCompareItemStruct*<br/>
Ein long-Zeiger auf eine `COMPAREITEMSTRUCT` Struktur.

### <a name="return-value"></a>Rückgabewert

Die relative Position der beiden Elemente beschrieben, die der [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) Struktur. Es kann eine der folgenden Werte sein:

|Wert|Bedeutung|
|-----------|-------------|
|-1|Element 1 wird vor Element 2 sortiert.|
|0|Element 1 und Element 2 sortiert identisch.|
|1|Element 1 wird nach Element 2 sortiert.|

Finden Sie unter [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) eine Beschreibung der `COMPAREITEMSTRUCT` Struktur.

### <a name="remarks"></a>Hinweise

Standardmäßig ist diese Member-Funktion mit "nothing". Wenn Sie ein Ownerdrawn-Listenfeld mit dem LBS_SORT-Stil erstellen, müssen Sie diese Memberfunktion, um das Framework bei der Sortierung der neue Elemente im Listenfeld überschreiben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

##  <a name="create"></a>  CListBox::Create

Erstellt im Windows-Listenfeld aus, und fügt es der `CListBox` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt die Art des Listenfelds. Wenden Sie eine beliebige Kombination von [listenfeldstile](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) in das Feld.

*Rect*<br/>
Gibt an, die im Listenfeld Größe und Position. Kann es sich um eine `CRect` Objekt oder ein `RECT` Struktur.

*pParentWnd*<br/>
Gibt an, das Listenfeld des übergeordneten Fensters (in der Regel eine `CDialog` Objekt). Es darf nicht NULL sein.

*nID*<br/>
Gibt an, das Listenfeld-Steuerelement-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CListBox` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie anschließend `Create`, die das Windows-Listenfeld initialisiert und fügt es der `CListBox` Objekt.

Wenn `Create` ausgeführt wird, handelt es sich bei Windows sendet die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) die Nachrichten an das Listenfeld-Steuerelement.

Diese Nachrichten werden standardmäßig behandelt der [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standardbehandlung für die Nachricht zu erweitern, leiten Sie eine Klasse von `CListBox`, hinzufügen eine meldungszuordnung an die neue Klasse und überschreiben Sie die vorherigen Meldungshandler-Memberfunktionen. Außer Kraft setzen `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.

Übernehmen Sie das folgende [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) an ein Listenfeld-Steuerelement.

- WS_CHILD immer

- WS_VISIBLE in der Regel

- WS_DISABLED selten

- WS_VSCROLL hinzufügen eine vertikale Bildlaufleiste

- WS_HSCROLL hinzufügen eine horizontalen Schiebeleiste

- WS_GROUP zum Gruppieren von Steuerelementen

- WS_TABSTOP können TAB-Taste auf dieses Steuerelement

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

##  <a name="deleteitem"></a>  CListBox::DeleteItem

Vom Framework aufgerufen, wenn der Benutzer ein Element aus einem Ownerdrawn-löscht `CListBox` Objekt oder zerstört das Listenfeld.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDeleteItemStruct*<br/>
Ein long-Zeiger auf ein Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) -Struktur, die Informationen über das gelöschte Element enthält.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um ein Ownerdrawn-Listenfeld nach Bedarf neu zu zeichnen.

Finden Sie unter [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) eine Beschreibung der `DELETEITEMSTRUCT` Struktur.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

##  <a name="deletestring"></a>  CListBox::DeleteString

Löscht das Element an Position *nIndex* aus dem Listenfeld aus.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index der Zeichenfolge, die gelöscht werden.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Zeichenfolgen in der Liste bleiben. Der Rückgabewert ist LB_ERR aus, wenn *nIndex* Index größer als die Anzahl der Elemente in der Liste angibt.

### <a name="remarks"></a>Hinweise

Alle Elemente, die nach *nIndex* jetzt eine Position nach unten zu verschieben. Z. B. wenn ein Listenfeld, das zwei Elemente enthält, bewirkt löschen das erste Element den verbleibenden Artikel jetzt in der ersten Position sein. *nIndex*= 0 für das Element in der ersten Position.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

##  <a name="dir"></a>  CListBox::Dir

Fügt eine Liste der Dateinamen, Laufwerke oder beides um ein Listenfeld an.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Parameter

*attr*<br/>
Kann eine beliebige Kombination von werden die **Enum** Werte, die in beschriebenen `CFile::GetStatu` [s](../../mfc/reference/cfile-class.md#getstatus), oder eine beliebige Kombination der folgenden Werte:

|Wert|Bedeutung|
|-----------|-------------|
|0x0000|Datei kann aus gelesen oder geschrieben werden.|
|0x0001|Datei auslesen, jedoch nicht geschrieben werden kann.|
|0x0002|Datei wird ausgeblendet und nicht in einer Verzeichnisliste angezeigt.|
|0x0004|Datei ist eine Systemdatei.|
|0x0010|Den Namen trägt *LpszWildCard* gibt ein Verzeichnis an.|
|0x0020|Datei wurde archiviert.|
|0 x 4000|Einschließen aller Laufwerke, die mit den vom angegebenen Namen übereinstimmen *LpszWildCard*.|
|0 x 8000|Exklusive Flag. Wenn das exclusive-Flag festgelegt ist, werden nur Dateien vom angegebenen Typ aufgeführt. Andernfalls werden Dateien vom angegebenen Typ zusätzlich zu "normal" Dateien aufgeführt.|

*lpszWildCard*<br/>
Verweist auf eine Dateispezifikation Zeichenfolge. Die Zeichenfolge kann Platzhalter enthalten (z. B. *.\*).

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des letzten Dateinamens zur Liste hinzugefügt werden soll. Der Rückgabewert ist LB_ERR auf, wenn ein Fehler auftritt; der Rückgabewert ist LB_ERRSPACE ist nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolgen zur Verfügung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

##  <a name="drawitem"></a>  CListBox::DrawItem

Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Liste im Feld ändert.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein long-Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, Informationen über den Typ der Zeichnung, die erforderlich sind enthält.

### <a name="remarks"></a>Hinweise

Die `itemAction` und `itemState` Mitglied der `DRAWITEMSTRUCT` Struktur definieren, die Zeichnen-Aktion, die ausgeführt werden soll.

Standardmäßig ist diese Member-Funktion mit "nothing". Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CListBox` Objekt. Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext in angegeben wiederherstellen *LpDrawItemStruct* vor diesem Member Funktion beendet wird.

Finden Sie unter [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) eine Beschreibung der `DRAWITEMSTRUCT` Struktur.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

##  <a name="findstring"></a>  CListBox:: FindString

Sucht die erste Zeichenfolge in einem Listenfeld, das das angegebene Präfix enthält, ohne die Auswahl im Listenfeld zu ändern.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>Parameter

*nStartAfter*<br/>
Enthält den nullbasierten Index des Elements vor dem ersten Element zu durchsuchenden an. Wenn die Suche am Ende das Listenfeld erreicht, weiterhin von der obersten Position des Listenfelds zurück vom angegebenen Elements *nStartAfter*. Wenn *nStartAfter* -1 ist, durchsucht das ganze Listenfeld ab.

*lpszItem*<br/>
Verweist auf die Null-terminierte Zeichenfolge, die das Präfix, das für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des übereinstimmenden Elements oder LB_ERR, wenn die Suche nicht erfolgreich war.

### <a name="remarks"></a>Hinweise

Verwenden der [SelectString](#selectstring) Memberfunktion versucht, sowohl suchen, und wählen Sie eine Zeichenfolge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

##  <a name="findstringexact"></a>  CListBox::FindStringExact

Sucht die erste Listenfeld-Zeichenfolge, die der angegebenen Zeichenfolge entspricht *LpszFind*.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Parameter

*nIndexStart*<br/>
Gibt an, der nullbasierte Index des Elements, bevor das erste Element, gesucht werden soll. Wenn die Suche am Ende das Listenfeld erreicht, weiterhin von der obersten Position des Listenfelds zurück vom angegebenen Elements *nIndexStart*. Wenn *nIndexStart* -1 ist, durchsucht das ganze Listenfeld ab.

*lpszFind*<br/>
Verweist auf die Null-terminierte Zeichenfolge zu suchende. Diese Zeichenfolge kann es sich um einen vollständigen Dateinamen, einschließlich der Erweiterung enthalten. Die Suche ist nicht Groß-/ Kleinschreibung, damit die Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.

### <a name="return-value"></a>Rückgabewert

Der Index des übereinstimmenden Elements oder LB_ERR, wenn die Suche nicht erfolgreich war.

### <a name="remarks"></a>Hinweise

Wenn das Listenfeld in einem Ownerdrawn-Format, jedoch ohne erstellt wurde die [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Stil, der `FindStringExact` Memberfunktion versucht, mit dem Wert zeigt Doppelwort mit dem Wert von übereinstimmen *LpszFind*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

##  <a name="getanchorindex"></a>  CListBox::GetAnchorIndex

Ruft den nullbasierten Index des die aktuelle Anchor-Element im Listenfeld ab.

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>Rückgabewert

Der Index des aktuellen Anchor-Elements, wenn erfolgreich; andernfalls LB_ERR.

### <a name="remarks"></a>Hinweise

In einem Mehrfachauswahl-Listenfeld ist das Anchor-Element der ersten oder letzten Element in einem Block zusammenhängender ausgewählter Elemente.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CListBox::SetAnchorIndex](#setanchorindex).

##  <a name="getcaretindex"></a>  CListBox::GetCaretIndex

Bestimmt den Index des Elements, das das Fokusrechteck in einem Mehrfachauswahl-Listenfeld hat.

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des Elements, das das Fokusrechteck in einem Listenfeld wurde. Ist im Listenfeld ein Einzelauswahl-Listenfeld, ist der Rückgabewert der Index des Elements, das ausgewählt ist, sofern vorhanden.

### <a name="remarks"></a>Hinweise

Das Element kann oder nicht mehr ausgewählt werden.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CListBox::SetCaretIndex](#setcaretindex).

##  <a name="getcount"></a>  CListBox::GetCount

Ruft die Anzahl der Elemente in einem Listenfeld ab.

```
int GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im Listenfeld oder LB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Die zurückgegebene Anzahl ist größer als der Wert für das letzte Element (der Index ist nullbasiert).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

##  <a name="getcursel"></a>  CListBox::GetCurSel

Ruft der nullbasierte Index des derzeit ausgewählten Elements ab, sofern vorhanden, in einem Mehrfachauswahl-Listenfeld.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des derzeit ausgewählten Elements ist dies ein Einzelauswahl-Listenfeld. Es ist LB_ERR, wenn derzeit kein Element ausgewählt ist.

In einem Mehrfachauswahl-Listenfeld, den Index des Elements, das den Fokus besitzt.

### <a name="remarks"></a>Hinweise

Rufen Sie keine `GetCurSel` für eine Mehrfachauswahl-Listenfeld. Verwendung [CListBox::GetSelItems](#getselitems) stattdessen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

##  <a name="gethorizontalextent"></a>  CListBox::GetHorizontalExtent

Ruft die Breite in Pixel, die mit denen sie ein horizontaler Bildlauf durchgeführt werden kann, aus dem Listenfeld ab.

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>Rückgabewert

Die bildlauffähigen Breite im Listenfeld, in Pixel.

### <a name="remarks"></a>Hinweise

Dies gilt nur, wenn das Listenfeld eine horizontale Bildlaufleiste angezeigt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

##  <a name="getitemdata"></a>  CListBox::GetItemData

Ruft den Wert von der Anwendung bereitgestellten zeigt Doppelwort mit dem Element im angegebenen Listenfeld ab.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index des Elements im Listenfeld an.

### <a name="return-value"></a>Rückgabewert

Der 32-Bit-Wert, dem Element oder LB_ERR zugeordnet, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Der Wert zeigt Doppelwort war der *DwItemData* Parameter eine [SetItemData](#setitemdata) aufrufen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

##  <a name="getitemdataptr"></a>  CListBox::GetItemDataPtr

Ruft ab, der von der Anwendung bereitgestellten 32-Bit-Wert zugeordnet ist, mit dem angegebenen Listenfeld-Element als Zeiger (**"void"** <strong>\*</strong>).

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index des Elements im Listenfeld an.

### <a name="return-value"></a>Rückgabewert

Ruft ab einen Zeiger oder -1, wenn ein Fehler auftritt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

##  <a name="getitemheight"></a>  CListBox::GetItemHeight

Bestimmt die Höhe der Elemente in einem Listenfeld.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index des Elements im Listenfeld an. Dieser Parameter wird verwendet, nur, wenn das Listenfeld den LBS_OWNERDRAWVARIABLE-Stil. Es sollte, andernfalls auf 0 festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Die Höhe in Pixel der Elemente im Listenfeld. Wenn das Listenfeld die [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Stil, der Rückgabewert ist die Höhe des Elements gemäß *nIndex*. Wenn ein Fehler auftritt, ist der Rückgabewert LB_ERR an.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

##  <a name="getitemrect"></a>  CListBox::GetItemRect

Ruft die Abmessungen des Rechtecks, Grenzen ein Listenfeld-Element ab, wie er derzeit im Fenster im Listenfeld angezeigt wird.

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index des Elements an.

*lpRect*<br/>
Gibt einen long-Zeiger auf eine [RECT-Struktur](../../mfc/reference/rect-structure1.md) , empfängt die Listenfeld Clientkoordinaten des Elements.

### <a name="return-value"></a>Rückgabewert

LB_ERR, wenn ein Fehler auftritt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

##  <a name="getlistboxinfo"></a>  CListBox::GetListBoxInfo

Ruft die Anzahl von Elementen pro Spalte.

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>Rückgabewert

Anzahl von Elementen pro Spalte der `CListBox` Objekt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen des die [LB_GETLISTBOXINFO](/windows/desktop/Controls/lb-getlistboxinfo) Nachricht, wie im Windows SDK beschrieben.

##  <a name="getlocale"></a>  CListBox::GetLocale

Ruft das Gebietsschema ein, die im Listenfeld ab.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Rückgabewert

Wert des Gebietsschemabezeichners (LCID) für die Zeichenfolgen in das Listenfeld.

### <a name="remarks"></a>Hinweise

Das Gebietsschema ist z. B. verwendet, um die Sortierreihenfolge der Zeichenfolgen in einem sortierten Listenfeld zu ermitteln.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CListBox::SetLocale](#setlocale).

##  <a name="getsel"></a>  CListBox::GetSel

Ruft den Auswahlzustand eines Elements ab.

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index des Elements an.

### <a name="return-value"></a>Rückgabewert

Eine positive Zahl, wenn das angegebene Element ausgewählt ist; Andernfalls ist er 0. Der Rückgabewert ist LB_ERR auf, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion funktioniert mit beiden einzelnen - und Mehrfachauswahl-Listenfelder.

Verwenden Sie zum Abrufen des Indexes des derzeit ausgewählten Listenfeldelement [CListBox::GetCurSel](#getcursel).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

##  <a name="getselcount"></a>  CListBox::GetSelCount

Ruft die Gesamtzahl der ausgewählten Elemente in einem Mehrfachauswahl-Listenfeld ab.

```
int GetSelCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der ausgewählten Elemente in einem Listenfeld. Wenn das Listenfeld ein Einzelauswahl-Listenfeld, das ist, ist der Rückgabewert LB_ERR an.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CListBox::GetSelItems](#getselitems).

##  <a name="getselitems"></a>  CListBox::GetSelItems

Füllt einen Puffer mit einem Array von ganzen Zahlen, die die Element-Anzahl der ausgewählten Elemente in einem Mehrfachauswahl-Listenfeld angibt.

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>Parameter

*nMaxItems*<br/>
Gibt die maximale Anzahl der ausgewählten Elemente, deren Artikelnummern sind in den Puffer abgelegt werden.

*rgIndex*<br/>
Gibt einen Zeiger auf einen Puffer, der groß genug ist, für die Anzahl von ganzen Zahlen, die anhand des *nMaxItems*.

### <a name="return-value"></a>Rückgabewert

Die tatsächliche Anzahl der Elemente, die in den Puffer abgelegt werden. Das Listenfeld ein Einzelauswahl-Listenfeld, das der Rückgabewert ist, `LB_ERR`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

##  <a name="gettext"></a>  CListBox::GetText

Ruft eine Zeichenfolge aus einem Listenfeld ab.

```
int GetText(
    int nIndex,
    LPTSTR lpszBuffer) const;

void GetText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index der Zeichenfolge, die abgerufen werden.

*lpszBuffer*<br/>
Verweist auf den Puffer, der die Zeichenfolge empfängt. Der Puffer muss über genügend Speicherplatz für die Zeichenfolge und ein abschließendes Nullzeichen verfügen. Die Größe der Zeichenfolge kann voraus bestimmt werden, indem die `GetTextLen` Member-Funktion.

*rString*<br/>
Ein Verweis auf ein `CString`-Objekt.

### <a name="return-value"></a>Rückgabewert

Die Länge (in Byte) der Zeichenfolge, mit Ausnahme des abschließenden Zeichens Null. Wenn *nIndex* gibt kein gültigen Index, der Rückgabewert ist LB_ERR.

### <a name="remarks"></a>Hinweise

Die zweite Form dieses Members-Funktion füllt eine `CString` Objekt mit der Text der Zeichenfolge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

##  <a name="gettextlen"></a>  CListBox::GetTextLen

Ruft die Länge einer Zeichenfolge in einem Listenfeld-Element ab.

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index der Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Die Länge der Zeichenfolge in Zeichen, die ohne des abschließenden Nullzeichen. Wenn *nIndex* gibt kein gültigen Index, der Rückgabewert ist LB_ERR.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CListBox::GetText](#gettext).

##  <a name="gettopindex"></a>  CListBox::GetTopIndex

Ruft den nullbasierten Index des ersten sichtbaren Elements in einem Listenfeld ab.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des ersten sichtbaren Elements in einem Listenfeld, wenn erfolgreich, andernfalls LB_ERR.

### <a name="remarks"></a>Hinweise

Zunächst Element 0 befindet sich oben im Listenfeld, aber wenn das Listenfeld ein Bildlauf durchgeführt wird, kann ein anderes Element am Anfang sein.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

##  <a name="initstorage"></a>  CListBox::InitStorage

Belegt Speicher zum Speichern von Listenfeld-Elementen.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>Parameter

*nItems*<br/>
Gibt die Anzahl der hinzuzufügenden Elemente.

*nBytes*<br/>
Gibt die Menge an Arbeitsspeicher, in Bytes, die für die Element-Zeichenfolgen zugeordnet werden.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, die maximale Anzahl von Elementen, die im Listenfeld werden, bevor Sie eine neuzuordnung von Arbeitsspeicher gespeichert kann wird benötigt, andernfalls LB_ERRSPACE, d.h. nicht genügend Arbeitsspeicher verfügbar ist.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird vor dem Hinzufügen der einer großen Anzahl von Elementen, die eine `CListBox`.

Diese Funktion hilft, die Initialisierung von Listenfeldern zu beschleunigen, die eine große Anzahl von Elementen (mehr als 100). Es belegt, dass die angegebene Menge Arbeitsspeicher, sodass nachfolgende [AddString](#addstring), [InsertString](#insertstring), und [Dir](#dir) Funktionen nehmen kurz wie möglich. Sie können die Schätzungen für die Parameter verwenden. Wenn Sie überschätzen, ist einige zusätzlichen Arbeitsspeicher zugeteilt. Wenn Sie unterschätzen, wird die normale Zuordnung für Elemente verwendet, die der vorab festgelegten Betrag übersteigen.

Nur Windows 95/98: die *nItems* Parameter ist auf 16-Bit-Werten beschränkt. Dies bedeutet, dass es sich bei Listenfelder mehr als 32.767 Elemente enthalten können. Obwohl die Anzahl der Elemente beschränkt ist, wird die Gesamtgröße der Elemente in einem Listenfeld nur durch den verfügbaren Arbeitsspeicher beschränkt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

##  <a name="insertstring"></a>  CListBox::InsertString

Fügt eine Zeichenfolge in das Listenfeld an.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt an, der nullbasierte Index der Position, um die Zeichenfolge einzufügen. Wenn dieser Parameter-1 ist, wird die Zeichenfolge am Ende der Liste hinzugefügt.

*lpszItem*<br/>
Zeigt auf die einzufügende nullterminierte Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index der Position, an der die Zeichenfolge eingefügt wurde. Der Rückgabewert ist LB_ERR auf, wenn ein Fehler auftritt; der Rückgabewert ist LB_ERRSPACE auf, wenn nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge verfügbar ist.

### <a name="remarks"></a>Hinweise

Im Gegensatz zu den [AddString](#addstring) Member-Funktion `InsertString` bewirkt nicht, eine Liste mit den [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Stil sortiert werden soll.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

##  <a name="itemfrompoint"></a>  CListBox::ItemFromPoint

Bestimmt das Element im Listenfeld am nächsten liegt der Punkt im angegebenen *pt*.

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Zeigen Sie für die das nächste Element relativ zu der oberen linken Ecke des Clientbereichs des Listenfelds gesucht.

*bOutside*<br/>
Ein Verweis auf eine "bool"-Variable, die auf "true" festgelegt wird *pt* ist außerhalb des Clientbereichs, der das nächste Listenfeldelement, FALSE, wenn *pt* befindet sich in den Clientbereich des das nächste Listenelement Feld.

### <a name="return-value"></a>Rückgabewert

Der Index des nächstgelegenen Elements im festgelegten *pt*.

### <a name="remarks"></a>Hinweise

Sie können diese Funktion verwenden, um zu bestimmen, welches Element im Listenfeld den Mauszeiger bewegt wird, über.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CListBox::SetAnchorIndex](#setanchorindex).

##  <a name="measureitem"></a>  CListBox::MeasureItem

Vom Framework aufgerufen, wenn ein Listenfeld, das mit einem Ownerdrawn-Format erstellt wird.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parameter

*lpMeasureItemStruct*<br/>
Ein long-Zeiger auf eine [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) Struktur.

### <a name="remarks"></a>Hinweise

Standardmäßig ist diese Member-Funktion mit "nothing". Überschreiben Sie diese Memberfunktion auf, und geben Sie die `MEASUREITEMSTRUCT` Struktur, die Windows-Listenfeld Dimensionen zu informieren. Wenn das Listenfeld erstellt wird, mit der [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Format, das Framework ruft diese Member-Funktion für jedes Element im Listenfeld. Andernfalls wird dieser Member nur einmal aufgerufen.

Weitere Informationen zur Verwendung der [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Format in ein Ownerdrawn-Listenfeld, die mit erstellt die `SubclassDlgItem` Memberfunktion `CWnd`, finden Sie unter den Ausführungen im [technischen Hinweis 14](../../mfc/tn014-custom-controls.md).

Finden Sie unter [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) eine Beschreibung der `MEASUREITEMSTRUCT` Struktur.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

##  <a name="resetcontent"></a>  CListBox::ResetContent

Entfernt alle Elemente aus einem Listenfeld.

```
void ResetContent();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

##  <a name="selectstring"></a>  CListBox::SelectString

Suchvorgänge für ein Element im Listenfeld, das der angegebenen Zeichenfolge entspricht, und wenn ein übereinstimmendes Element gefunden wird, wird das Element ausgewählt.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>Parameter

*nStartAfter*<br/>
Enthält den nullbasierten Index des Elements vor dem ersten Element zu durchsuchenden an. Wenn die Suche am Ende das Listenfeld erreicht, weiterhin von der obersten Position des Listenfelds zurück vom angegebenen Elements *nStartAfter*. Wenn *nStartAfter* -1 ist, durchsucht das ganze Listenfeld ab.

*lpszItem*<br/>
Verweist auf die Null-terminierte Zeichenfolge, die das Präfix, das für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.

### <a name="return-value"></a>Rückgabewert

Der Index des ausgewählten Elements, wenn die Suche erfolgreich war. Wenn die Suche nicht erfolgreich war, LB_ERR zurückgegeben wird, und die aktuelle Auswahl wird nicht geändert.

### <a name="remarks"></a>Hinweise

Im Listenfeld aus, bei Bedarf, um das ausgewählte Element in der Ansicht erscheinen ein Bildlauf durchgeführt wird.

Diese Memberfunktion kann nicht verwendet werden, in einem Listenfeld, die die [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Stil.

Ein Element ausgewählt ist, nur dann, wenn die erste Zeichen (vom Ausgangspunkt) die Zeichen in der angegebenen Zeichenfolge übereinstimmen *LpszItem*.

Verwenden der `FindString` Memberfunktion versucht, einer Zeichenfolge zu suchen, ohne das Element auszuwählen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

##  <a name="selitemrange"></a>  CListBox::SelItemRange

Wählt mehrere aufeinander folgende Elemente in einem Mehrfachauswahl-Listenfeld aus.

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>Parameter

*bWählen*<br/>
Gibt an, wie die Auswahl festgelegt. Wenn *bWählen* ist "true", die Zeichenfolge ausgewählt und hervorgehoben ist; False gibt an, die Hervorhebung wird entfernt, und die Zeichenfolge nicht mehr ausgewählt ist.

*nFirstItem*<br/>
Gibt an, der nullbasierte Index des ersten Elements festlegen.

*nLastItem*<br/>
Gibt an, der nullbasierte Index des letzten Elements festlegen.

### <a name="return-value"></a>Rückgabewert

LB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Memberfunktion auf, nur mit Mehrfachauswahl-Listenfelder. Wenn Sie nur ein Element in einem Mehrfachauswahl-Listenfeld auswählen möchten – d. h. wenn *nFirstItem* ist gleich *nLastItem* – Aufrufen der [Memberfunktion SetSel](#setsel) Memberfunktion stattdessen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

##  <a name="setanchorindex"></a>  CListBox::SetAnchorIndex

Legt den Anker in einem Mehrfachauswahl-Listenfeld um eine erweiterte Auswahl zu beginnen.

```
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt an, der nullbasierte Index des Elements im Listenfeld, die den Anker.

### <a name="remarks"></a>Hinweise

In einem Mehrfachauswahl-Listenfeld ist das Anchor-Element der ersten oder letzten Element in einem Block zusammenhängender ausgewählter Elemente.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

##  <a name="setcaretindex"></a>  CListBox::SetCaretIndex

Legt das Fokusrechteck auf das Element am angegebenen Index in einem Mehrfachauswahl-Listenfeld fest.

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt an, der nullbasierte Index des Elements, das das Fokusrechteck in das Listenfeld zu erhalten.

*bScroll*<br/>
Wenn dieser Wert 0 ist, das Element ein Bildlauf durchgeführt wird, bis es vollständig sichtbar ist. Wenn dieser Wert nicht 0 (null) das Element ein Bildlauf durchgeführt wird, bis es zumindest teilweise sichtbar ist.

### <a name="return-value"></a>Rückgabewert

LB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Wenn das Element nicht sichtbar ist, wird es in die Ansicht gescrollt werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

##  <a name="setcolumnwidth"></a>  CListBox::SetColumnWidth

Legt die Breite in Pixel aller Spalten in der ein mehrspaltiges Listenfeld fest (erstellt mit der [LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Stil).

```
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>Parameter

*cxWidth*<br/>
Gibt die Breite in Pixel aller Spalten an.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

##  <a name="setcursel"></a>  CListBox::SetCurSel

Wählt eine Zeichenfolge aus, und verschiebt es in der Ansicht, bei Bedarf.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Parameter

*. nalles auswählen*<br/>
Gibt den nullbasierten Index der Zeichenfolge, die ausgewählt werden. Wenn *. nalles auswählen* ist-1 und keine Auswahl im Listenfeld festgelegt ist.

### <a name="return-value"></a>Rückgabewert

LB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Wenn die neue Zeichenfolge ausgewählt ist, entfernt im Listenfeld die Markierung aus der zuvor ausgewählten Zeichenfolge.

Verwenden Sie diese Memberfunktion auf, nur mit Mehrfachauswahl-Listenfelder.

Um festzulegen, oder eine Auswahl in einem Mehrfachauswahl-Listenfeld zu entfernen, verwenden Sie [CListBox::SetSel](#setsel).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

##  <a name="sethorizontalextent"></a>  CListBox:: SetHorizontalExtent

Legt die Breite in Pixel mit denen ein Listenfeld, das ein horizontaler Bildlauf durchgeführt werden kann.

```
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>Parameter

*cxExtent*<br/>
Gibt die Anzahl der Pixel, die mit denen im Listenfeld ein horizontaler Bildlauf durchgeführt werden kann.

### <a name="remarks"></a>Hinweise

Wenn die Größe des Listenfelds kleiner als dieser Wert ist, wird die horizontale Bildlaufleiste horizontal Elemente im Listenfeld scrollen. Wenn das Listenfeld genauso groß oder größer als dieser Wert ist, wird die horizontale Bildlaufleiste ausgeblendet.

Auf einen Aufruf reagiert `SetHorizontalExtent`, im Listenfeld muss definiert worden mit der [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles) Stil.

Diese Memberfunktion ist nicht für mehrspaltige Listenfelder nützlich. Rufen Sie für den mehrspaltigen Listenfelder, die `SetColumnWidth` Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

##  <a name="setitemdata"></a>  CListBox::SetItemData

Legt einen 32-Bit-Wert, der das angegebene Element in einem Listenfeld zugeordnete fest.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index des Elements an.

*dwItemData*<br/>
Gibt den Wert mit dem Element zugeordnet werden soll.

### <a name="return-value"></a>Rückgabewert

LB_ERR, wenn ein Fehler auftritt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

##  <a name="setitemdataptr"></a>  CListBox::SetItemDataPtr

Legt den 32-Bit-Wert, der das angegebene Element in einem Listenfeld angegebenen Zeiger zugeordnet ( **"void"** <strong>\*</strong>).

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index des Elements an.

*pData*<br/>
Gibt den Zeiger mit dem Element zugeordnet werden soll.

### <a name="return-value"></a>Rückgabewert

LB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

This-Zeiger bleibt gültig, für die Lebensdauer des im Listenfeld, obwohl des Elements die relative Position innerhalb des Listenfelds ändern kann, wenn Elemente hinzugefügt oder entfernt werden. Daher kann den Index des Elements innerhalb des Felds ändern, aber der Zeiger bleibt zuverlässige.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

##  <a name="setitemheight"></a>  CListBox::SetItemHeight

Legt die Höhe der Elemente in einem Listenfeld fest.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den nullbasierten Index des Elements im Listenfeld an. Dieser Parameter wird verwendet, nur, wenn das Listenfeld den LBS_OWNERDRAWVARIABLE-Stil. Es sollte, andernfalls auf 0 festgelegt werden.

*cyItemHeight*<br/>
Gibt die Höhe in Pixel des Elements an.

### <a name="return-value"></a>Rückgabewert

LB_ERR, wenn der Index oder der Höhe ungültig ist.

### <a name="remarks"></a>Hinweise

Wenn das Listenfeld die [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Stil, diese Funktion legt die Höhe des angegebenen Elements vom *nIndex*. Andernfalls wird diese Funktion die Höhe aller Elemente im Listenfeld an.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

##  <a name="setlocale"></a>  CListBox::SetLocale

Legt den Gebietsschemabezeichner für dieses Listenfelds können Sie fest.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Parameter

*nNewLocale*<br/>
Der neue Gebietsschema-ID (LCID) Wert für das Listenfeld festgelegt.

### <a name="return-value"></a>Rückgabewert

Der vorherige Gebietsschema-ID (LCID) Wert für dieses Listenfelds können Sie.

### <a name="remarks"></a>Hinweise

Wenn `SetLocale` nicht aufgerufen wird, der Standardwert Gebietsschema wird vom System abgerufen. Diese standardsystemgebietsschema kann geändert werden, mithilfe der Systemsteuerung regionalen (oder International)-Anwendung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

##  <a name="setsel"></a>  CListBox::SetSel

Wählt aus eine Zeichenfolge in einem Mehrfachauswahl-Listenfeld.

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den nullbasierten Index der Zeichenfolge, die festgelegt werden. Wenn-1 und die Auswahl hinzugefügt oder aus allen Zeichenfolgen, abhängig vom Wert entfernt *bWählen*.

*bWählen*<br/>
Gibt an, wie die Auswahl festgelegt. Wenn *bWählen* ist "true", die Zeichenfolge ausgewählt und hervorgehoben ist; False gibt an, die Hervorhebung wird entfernt, und die Zeichenfolge nicht mehr ausgewählt ist. Die angegebene Zeichenfolge ist aktiviert und standardmäßig markiert.

### <a name="return-value"></a>Rückgabewert

LB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Memberfunktion auf, nur mit Mehrfachauswahl-Listenfelder.

Verwenden Sie zum Auswählen eines Elements aus einem Mehrfachauswahl-Listenfeld [CListBox::SetCurSel](#setcursel).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

##  <a name="settabstops"></a>  CListBox::SetTabStops

Legt fest, die Tabstopp Positionen in einem Listenfeld.

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);


BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Parameter

*cxEachStop*<br/>
Tabstopps festgelegt werden alle *CxEachStop* Dialogeinheiten. Finden Sie unter *RgTabStops* eine Beschreibung der eine Dialogeinheit.

*nTabStops*<br/>
Gibt die Anzahl von Tabstopps, um in das Listenfeld zu erhalten.

*rgTabStops*<br/>
Zeigt auf das erste Element eines Arrays von Ganzzahlen, die Tabstopp Positionen in Dialogeinheiten. Eine Dialogeinheit ist einem horizontalen oder vertikalen Abstand. Eine horizontale Dialogfeld-Einheit ist ein Viertel des die aktuelle Basis Breite Dialogeinheit gleich und entspricht einem vertikalen Dialogeinheit ein Achtel der aktuellen Dialogfeld Basis Height-Komponente. Die Dialogfeld Basiseinheiten werden basierend auf die Höhe und Breite der aktuellen Systemschriftart berechnet. Die `GetDialogBaseUnits` Windows-Funktion gibt den aktuellen Dialogfeld Basiseinheiten in Pixel. Die Tabstopps müssen in aufsteigender Reihenfolge sortiert werden; Back-Registerkarten sind nicht zulässig.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn alle Registerkarten festgelegt wurden; andernfalls 0.

### <a name="remarks"></a>Hinweise

Um die Standardgröße des 2 Dialogeinheiten Tabstopps festzulegen, rufen Sie die parameterlose Version von dieser Memberfunktion. Um eine andere Größe als 2 Tabstopps festzulegen, rufen Sie die Version mit der *CxEachStop* Argument.

Um ein Array von Größen Tabstopps festzulegen, verwenden Sie die Version mit der *RgTabStops* und *nTabStops* Argumente. Für jeden Wert in ein Tabstopp festgelegt *RgTabStops*, bis die angegebene Anzahl *nTabStops*.

Reagieren auf einen Aufruf der `SetTabStops` Member-Funktion, die im Listenfeld muss mit erstellt wurden die [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Stil.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

##  <a name="settopindex"></a>  CListBox::SetTopIndex

Stellt sicher, dass eine bestimmte Listenfeldelements sichtbar ist.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt an, der nullbasierte Index des Elements im Listenfeld.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn erfolgreich, oder LB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Das System führt einen Bildlauf im Listenfeld, bis entweder anhand des Elements *nIndex* wird am oberen Rand der Liste im Feld oder den maximalen Bildlauf-Bereich wurde erreicht.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

##  <a name="vkeytoitem"></a>  CListBox::VKeyToItem

Vom Framework aufgerufen, wenn das Listenfeld übergeordnete Fenster eine WM_VKEYTOITEM-Nachricht aus dem Listenfeld empfängt.

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>Parameter

*nKey*<br/>
Den virtueller Tastencode der Taste gedrückt, der Benutzer. Eine Liste der standardmäßige virtuelle Tastencodes finden Sie in der Winuser.h

*nIndex*<br/>
Die aktuelle Position der Einfügemarke im Listenfeld.

### <a name="return-value"></a>Rückgabewert

Gibt - 2 für die keine weitere Aktion, - 1 für die Standardaktion oder eine nicht negative Zahl an einen Index der eines Listenfeldelements, führen Sie die Standardaktion für die Tastatureingabe.

### <a name="remarks"></a>Hinweise

Die WM_VKEYTOITEM-Nachricht wird vom Listenfeld gesendet, wenn sie eine WM_KEYDOWN-Meldung empfängt, aber nur, wenn das Listenfeld beide der folgenden entspricht:

- Hat die [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) Satz formatieren.

- Verfügt über mindestens ein Element aus.

Sie sollten diese Funktion nicht selbst aufrufen. Überschreiben Sie diese Funktion, um eigene benutzerdefinierte Behandlung von tastaturmeldungen bereitzustellen.

Sie müssen einen Wert angeben, welche Aktion dem Framework die Außerkraftsetzung durchgeführt zurückkehren. Ein Rückgabewert von – 2 Gibt an, behandelt alle Aspekte der Sie das Element auswählen und erfordert keine weitere Aktion vom Listenfeld. Vor dem Zurückgeben von – 2, können die Auswahl oder Einfügemarke oder beides zu verschieben. Verwenden Sie zum Festlegen der Auswahl [SetCurSel](#setcursel) oder [Memberfunktion SetSel](#setsel). Verwenden Sie zum Verschieben der Einfügemarke [SetCaretIndex](#setcaretindex).

Ein Rückgabewert von – 1 zeigt an, dass im Listenfeld die Default-Aktion als Reaktion auf die Tastatureingabe ausführen soll. Die Standardimplementierung gibt - 1.

Ein Wert zurückgegeben, der größer oder gleich 0 gibt den Index eines Elements in das Listenfeld und gibt an, dass das Listenfeld die Standardaktion für die Tastatureingabe auf das angegebene Element ausführen soll.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CTRLTEST](../../visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CButton-Klasse](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit-Klasse](../../mfc/reference/cedit-class.md)<br/>
[CScrollBar-Klasse](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic-Klasse](../../mfc/reference/cstatic-class.md)
