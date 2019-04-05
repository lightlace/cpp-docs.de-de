---
title: CComboBox-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
helpviewer_keywords:
- CComboBox [MFC], CComboBox
- CComboBox [MFC], AddString
- CComboBox [MFC], Clear
- CComboBox [MFC], CompareItem
- CComboBox [MFC], Copy
- CComboBox [MFC], Create
- CComboBox [MFC], Cut
- CComboBox [MFC], DeleteItem
- CComboBox [MFC], DeleteString
- CComboBox [MFC], Dir
- CComboBox [MFC], DrawItem
- CComboBox [MFC], FindString
- CComboBox [MFC], FindStringExact
- CComboBox [MFC], GetComboBoxInfo
- CComboBox [MFC], GetCount
- CComboBox [MFC], GetCueBanner
- CComboBox [MFC], GetCurSel
- CComboBox [MFC], GetDroppedControlRect
- CComboBox [MFC], GetDroppedState
- CComboBox [MFC], GetDroppedWidth
- CComboBox [MFC], GetEditSel
- CComboBox [MFC], GetExtendedUI
- CComboBox [MFC], GetHorizontalExtent
- CComboBox [MFC], GetItemData
- CComboBox [MFC], GetItemDataPtr
- CComboBox [MFC], GetItemHeight
- CComboBox [MFC], GetLBText
- CComboBox [MFC], GetLBTextLen
- CComboBox [MFC], GetLocale
- CComboBox [MFC], GetMinVisible
- CComboBox [MFC], GetTopIndex
- CComboBox [MFC], InitStorage
- CComboBox [MFC], InsertString
- CComboBox [MFC], LimitText
- CComboBox [MFC], MeasureItem
- CComboBox [MFC], Paste
- CComboBox [MFC], ResetContent
- CComboBox [MFC], SelectString
- CComboBox [MFC], SetCueBanner
- CComboBox [MFC], SetCurSel
- CComboBox [MFC], SetDroppedWidth
- CComboBox [MFC], SetEditSel
- CComboBox [MFC], SetExtendedUI
- CComboBox [MFC], SetHorizontalExtent
- CComboBox [MFC], SetItemData
- CComboBox [MFC], SetItemDataPtr
- CComboBox [MFC], SetItemHeight
- CComboBox [MFC], SetLocale
- CComboBox [MFC], SetMinVisibleItems
- CComboBox [MFC], SetTopIndex
- CComboBox [MFC], ShowDropDown
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
ms.openlocfilehash: a76be4be87471f26970a5b517d9993ae324b56c5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778519"
---
# <a name="ccombobox-class"></a>CComboBox-Klasse

Stellt die Funktionalität eines Windows-Kombinationsfelds bereit.

## <a name="syntax"></a>Syntax

```
class CComboBox : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComboBox::CComboBox](#ccombobox)|Erstellt ein `CComboBox`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComboBox:: AddString](#addstring)|Fügt eine Zeichenfolge an das Ende der Liste in das Listenfeld eines Kombinationsfelds oder an der Position der Sortierreihenfolge für Listenfelder, mit dem CBS_SORT-Stil.|
|[CComboBox::Clear](#clear)|(Löscht) Löscht die aktuelle Auswahl, falls vorhanden, in das Bearbeitungssteuerelement.|
|[CComboBox::CompareItem](#compareitem)|Wird aufgerufen, durch das Framework, um die relative Position eines neuen Listenelements in einem sortierten Ownerdrawn-Kombinationsfeld zu bestimmen.|
|[CComboBox::Copy](#copy)|Die aktuelle Auswahl, kopiert, sofern vorhanden, in die Zwischenablage HIERSVR-Format.|
|[CComboBox::Create](#create)|Das Kombinationsfeld erstellt, und fügt es der `CComboBox` Objekt.|
|[CComboBox::Cut](#cut)|(Schnitte) Löscht die aktuelle Auswahl, sofern zutreffend, in das Bearbeitungsfeld steuern und den gelöschten Text in die Zwischenablage HIERSVR Format kopiert.|
|[CComboBox::DeleteItem](#deleteitem)|Vom Framework aufgerufen, wenn ein Listenelement aus einem Ownerdrawn-Kombinationsfeld gelöscht wird.|
|[CComboBox::DeleteString](#deletestring)|Löscht eine Zeichenfolge aus dem Listenfeld eines Kombinationsfelds an.|
|[CComboBox::Dir](#dir)|Fügt eine Liste von Dateinamen in das Listenfeld eines Kombinationsfelds an.|
|[CComboBox::DrawItem](#drawitem)|Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Kombinationsfeld Feld ändert.|
|[CComboBox::FindString](#findstring)|Sucht die erste Zeichenfolge mit dem angegebenen Präfix in das Listenfeld eines Kombinationsfelds an.|
|[CComboBox::FindStringExact](#findstringexact)|Sucht die erste Listenfeld Zeichenfolge (in einem Kombinationsfeld), die der angegebenen Zeichenfolge übereinstimmt.|
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Ruft Informationen ab, zu der `CComboBox` Objekt.|
|[CComboBox::GetCount](#getcount)|Ruft die Anzahl der Elemente im Listenfeld eines Kombinationsfelds ab.|
|[CComboBox::GetCueBanner](#getcuebanner)|Ruft den Hinweistext, der angezeigt wird, ist für ein Kombinationsfeld-Steuerelement ab.|
|[CComboBox::GetCurSel](#getcursel)|Ruft den Index des derzeit ausgewählten Elements ab, sofern vorhanden, in das Listenfeld eines Kombinationsfelds.|
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Ruft die Bildschirmkoordinaten des sichtbar (Gelöschte nach unten) Listenfeld der ein Dropdown-Kombinationsfeld ab.|
|[CComboBox::GetDroppedState](#getdroppedstate)|Bestimmt, ob das Listenfeld ein Dropdown-Kombinationsfeld angezeigt wird (hat).|
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Ruft die minimal zulässige Breite für den Bereich im Dropdown-Listenfeld eines Kombinationsfelds ab.|
|[CComboBox::GetEditSel](#geteditsel)|Ruft die Zeichenpositionen Start- und Enddatum, der die aktuelle Auswahl in das Steuerelement zum Bearbeiten eines Kombinationsfelds ab.|
|[CComboBox::GetExtendedUI](#getextendedui)|Bestimmt, ob ein Kombinationsfeld die Standardbenutzeroberfläche oder die erweiterten Benutzeroberfläche hat.|
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Gibt die Breite in Pixel an, dass der Teil der im Listenfeld des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann.|
|[CComboBox::GetItemData](#getitemdata)|Ruft ab, der von der Anwendung bereitgestellten 32-Bit-Wert zugeordnet ist, mit dem angegebenen Kombinationsfeld-Element.|
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Ruft ab, der von der Anwendung bereitgestellten 32-Bit-Zeiger, der dem angegebenen Kombinationsfeld-Element zugeordnet ist.|
|[CComboBox::GetItemHeight](#getitemheight)|Ruft die Höhe der Listenelemente in einem Kombinationsfeld ab.|
|[CComboBox::GetLBText](#getlbtext)|Ruft eine Zeichenfolge aus dem Listenfeld eines Kombinationsfelds ab.|
|[CComboBox::GetLBTextLen](#getlbtextlen)|Ruft die Länge einer Zeichenfolge in das Listenfeld eines Kombinationsfelds ab.|
|[CComboBox::GetLocale](#getlocale)|Ruft den Gebietsschemabezeichner für ein Kombinationsfeld ab.|
|[CComboBox::GetMinVisible](#getminvisible)|Ruft die minimale Anzahl der sichtbaren Elemente in der Dropdownliste des Kombinationsfelds aktuelle ab.|
|[CComboBox::GetTopIndex](#gettopindex)|Gibt den Index des ersten sichtbaren Elements im Listenfeld Teil im Kombinationsfeld zurück.|
|[CComboBox::InitStorage](#initstorage)|Belegt, Speicherblöcke für Elemente und Zeichenfolgen in den Bereich im Listenfeld des Kombinationsfelds.|
|[CComboBox::InsertString](#insertstring)|Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds ein.|
|[CComboBox::LimitText](#limittext)|Begrenzt die Länge des Texts, der der Benutzer das Steuerelement zum Bearbeiten eines Kombinationsfelds eingegeben werden kann.|
|[CComboBox::MeasureItem](#measureitem)|Wird aufgerufen, durch das Framework um Combo Box Dimensionen zu bestimmen, wenn ein Ownerdrawn-Kombinationsfeld erstellt wird.|
|[CComboBox::Paste](#paste)|Die Daten aus der Zwischenablage in das Bearbeitungssteuerelement an der aktuellen Cursorposition eingefügt. Daten werden eingefügt, nur, wenn die Zwischenablage Daten im HIERSVR Format enthält.|
|[CComboBox::ResetContent](#resetcontent)|Entfernt, die alle Elemente aus der Liste ein, und bearbeiten die Kontrolle über ein Kombinationsfeld.|
|[CComboBox::SelectString](#selectstring)|Sucht nach einer Zeichenfolge in das Listenfeld eines Kombinationsfelds und, wenn die Zeichenfolge gefunden wird, die Zeichenfolge im Listenfeld auswählt und kopiert Sie die Zeichenfolge in das Steuerelement zum Bearbeiten.|
|[CComboBox::SetCueBanner](#setcuebanner)|Legt fest, den Hinweistext, der für ein Kombinationsfeld-Steuerelement angezeigt wird.|
|[CComboBox::SetCurSel](#setcursel)|Wählt aus eine Zeichenfolge in das Listenfeld eines Kombinationsfelds.|
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Legt fest, die minimal zulässige Breite für den Bereich im Dropdown-Listenfeld eines Kombinationsfelds.|
|[CComboBox::SetEditSel](#seteditsel)|Das Steuerelement zum Bearbeiten eines Kombinationsfelds markiert Zeichen.|
|[CComboBox::SetExtendedUI](#setextendedui)|Wählt entweder die Standardbenutzeroberfläche oder die erweiterte Benutzeroberfläche für ein Kombinationsfeld, das den Stil CBS_DROPDOWN oder CBS_DROPDOWNLIST verfügt.|
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Legt die Breite in Pixel an, dass der Teil der im Listenfeld des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann.|
|[CComboBox::SetItemData](#setitemdata)|Legt den 32-Bit-Wert, der das angegebene Element in einem Kombinationsfeld zugeordnet.|
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Legt fest, den 32-Bit-Zeiger, der das angegebene Element in einem Kombinationsfeld zugeordnet.|
|[CComboBox::SetItemHeight](#setitemheight)|Legt die Höhe der Listenelemente in einem Kombinationsfeld oder die Höhe des bearbeiten-Steuerelement (oder statischem Text) Teils eines Kombinationsfelds fest.|
|[CComboBox::SetLocale](#setlocale)|Legt den Gebietsschemabezeichner für ein Kombinationsfeld fest.|
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Legt die minimale Anzahl der sichtbaren Elemente in der Dropdown-Liste des aktuellen Kombinationsfelds fest.|
|[CComboBox::SetTopIndex](#settopindex)|Teilt den Teil im Listenfeld des Kombinationsfelds zum Anzeigen von des Elements mit dem angegebenen Index am Anfang.|
|[CComboBox::ShowDropDown](#showdropdown)|Zeigt an, oder blendet Sie aus dem Listenfeld eines Kombinationsfelds an, der den Stil CBS_DROPDOWN oder CBS_DROPDOWNLIST verfügt.|

## <a name="remarks"></a>Hinweise

Ein Kombinationsfeld besteht aus einem Listenfeld, kombiniert mit einem statischen Steuerelement oder Edit-Steuerelements. Listenfeld Teil des Steuerelements kann jederzeit angezeigt werden, oder es kann nur nach unten löschen, wenn der Benutzer auf den Dropdown-Pfeil neben dem Steuerelement auswählt.

Das aktuell ausgewählte Element im Listenfeld (sofern vorhanden) wird angezeigt, in der statischen oder edit-Steuerelement. Darüber hinaus verfügt das Kombinationsfeld den Dropdown-Listenfeld-Stil, der Benutzer kann das erste Zeichen eines der Elemente in der Liste eingeben, und klicken Sie im Listenfeld Wenn es sichtbar ist, wird markieren das nächste Element mit diesem ersten Zeichen.

Die folgende Tabelle vergleicht die drei im Kombinationsfeld [Stile](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

|Stil|Wenn im Listenfeld angezeigt wird|Statische oder Edit-Steuerelement|
|-----------|-------------------------------|-----------------------------|
|Einfach|Always|Bearbeiten|
|Drop-down|Wenn Sie gelöscht|Bearbeiten|
|Dropdownliste|Wenn Sie gelöscht|Statisch|

Sie erstellen eine `CComboBox` Objekt aus entweder einer Dialogfeldvorlage oder direkt in Ihrem Code. In beiden Fällen rufen Sie zunächst den Konstruktor `CComboBox` zum Erstellen der `CComboBox` Objekt, rufen Sie dann die [erstellen](#create) Member-Funktion zum Erstellen des Steuerelements, und fügen Sie ihn auf die `CComboBox` Objekt.

Wenn Sie Windows gesendete benachrichtigungsmeldungen von eines Kombinationsfelds an sein übergeordnetes Element behandeln möchten (in der Regel eine abgeleitete Klasse `CDialog`), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag "und"-Nachrichtenhandler-Memberfunktion hinzugefügt.

Jede Nachricht-Zuordnungseintrag weist folgende Form:

**ON\_**_Benachrichtigung_ **(** _Id_, _MemberFxn_ **)**

wo `id` gibt die ID der untergeordneten Fensters mit der im Kombinationsfeld-Steuerelements, das Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten Member-Funktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.

Funktionsprototyp des übergeordneten Elements lautet wie folgt aus:

**afx_msg** `void` `memberFxn` **( );**

Die Reihenfolge, in der bestimmte Benachrichtigung gesendet werden, kann nicht vorhergesagt werden. Insbesondere kann eine Benachrichtigung CBN_SELCHANGE entweder vor oder nach einer Benachrichtigung CBN_CLOSEUP auftreten.

Potenzielle Meldungszuordnungseinträge lauten wie folgt:

- ON_CBN_CLOSEUP (Windows 3.1 und höher.) Das Listenfeld eines Kombinationsfelds wurde geschlossen. Diese Nachricht wird nicht gesendet werden, für ein Kombinationsfeld, die die [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.

- ON_CBN_DBLCLK der Benutzer doppelklickt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds. Diese Benachrichtigung wird nur für ein Kombinationsfeld, in dem CBS_SIMPLE-Format gesendet. Für ein Kombinationsfeld, mit der [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) -Stil verfügt, ein Doppelklick auftreten, kann keinem einzigen Mausklick im Listenfeld Blendet.

- ON_CBN_DROPDOWN das Listenfeld eines Kombinationsfelds zum Dropdown-Liste ist (sichtbar gemacht werden). Diese Benachrichtigung kann nur für ein Kombinationsfeld, mit der Formatvorlage CBS_DROPDOWN oder CBS_DROPDOWNLIST auftreten.

- ON_CBN_EDITCHANGE der Benutzer hat eine Aktion ausgeführt, die den Text im Bearbeitungssteuerelement Teil eines Kombinationsfelds geändert haben kann. Im Gegensatz zu der Nachricht CBN_EDITUPDATE wird diese Nachricht gesendet, nachdem Windows den Bildschirm aktualisiert. Es wird nicht gesendet, wenn das Kombinationsfeld das CBS_DROPDOWNLIST-Format verfügt.

- ON_CBN_EDITUPDATE geändert Anzeigetext der Edit-Steuerelement Teil eines Kombinationsfelds zu werden. Diese Benachrichtigung wird gesendet, nachdem das Steuerelement den Text formatiert hat, aber bevor der Text angezeigt. Es wird nicht gesendet, wenn das Kombinationsfeld das CBS_DROPDOWNLIST-Format verfügt.

- Nicht Speicherplatz genügend entsprechend eine bestimmte Anforderung ON_CBN_ERRSPACE im Kombinationsfeld.

- ON_CBN_SELENDCANCEL (Windows 3.1 und höher.) Gibt an, dass die Auswahl des Benutzers abgebrochen werden soll. Der Benutzer klickt auf ein Element, und klickt dann auf ein anderes Fenster oder Steuerelement, um das Listenfeld eines Kombinationsfelds auszublenden. Diese Benachrichtigung wird gesendet, bevor Sie die benachrichtigungsmeldung CBN_CLOSEUP, um anzugeben, dass die Auswahl des Benutzers ignoriert werden sollen. Die CBN_SELENDCANCEL oder CBN_SELENDOK-Nachricht wird gesendet, auch wenn die benachrichtigungsmeldung CBN_CLOSEUP nicht (wie im Falle eines Kombinationsfelds mit dem CBS_SIMPLE-Stil) gesendet wird.

- ON_CBN_SELENDOK der Benutzer wählt ein Element und klicken Sie dann die EINGABETASTE drückt oder klickt auf die unten-Taste, um das Listenfeld eines Kombinationsfelds auszublenden. Diese Benachrichtigung wird gesendet, vor der CBN_CLOSEUP-Meldung, um anzugeben, dass die Auswahl des Benutzers als gültig eingestuft werden soll. Die CBN_SELENDCANCEL oder CBN_SELENDOK-Nachricht wird gesendet, auch wenn die benachrichtigungsmeldung CBN_CLOSEUP nicht (wie im Falle eines Kombinationsfelds mit dem CBS_SIMPLE-Stil) gesendet wird.

- ON_CBN_KILLFOCUS im Kombinationsfeld verliert den Eingabefokus.

- ON_CBN_SELCHANGE die Auswahl im Listenfeld eines Kombinationsfelds ist aufgrund der Benutzer, die Sie in das Listenfeld klicken, oder Ändern der Auswahl mithilfe der Pfeiltasten geändert wird. Bei der Verarbeitung dieser Nachricht der Text im Bearbeitungssteuerelement des Kombinationsfelds nur abgerufen werden kann über `GetLBText` oder eine andere ähnliche Funktion. `GetWindowText` kann nicht verwendet werden.

- ON_CBN_SETFOCUS im Kombinationsfeld erhält den Eingabefokus.

Bei der Erstellung einer `CComboBox` Objekt in einem Dialogfeld (mithilfe einer Ressource), die `CComboBox` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.

Wenn Sie Einbetten einer `CComboBox` Objekt in ein anderes Fenster-Objekt, Sie müssen nicht zerstören. Bei der Erstellung der `CComboBox` Objekt im Stapel automatisch zerstört wird. Bei der Erstellung der `CComboBox` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das es zerstört, wenn das Windows-Kombinationsfeld zerstört wird.

**Beachten Sie** Wenn WM_KEYDOWN und WM_CHAR-Nachrichten verarbeitet werden sollen, müssen Sie Unterklasse des Kombinationsfelds bearbeiten und Auflisten von Steuerelementen, leiten eine Klasse von `CEdit` und `CListBox`, und fügen Sie Handler für diese Nachrichten in die abgeleiteten Klassen hinzu. Weitere Informationen finden Sie unter [CWnd:: SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="addstring"></a>  CComboBox:: AddString

Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds an.

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parameter

*lpszString*<br/>
Verweist auf die Null-terminierte Zeichenfolge, die hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn der Rückgabewert größer als oder gleich 0 ist, ist es den nullbasierten Index in die Zeichenfolge in das Listenfeld aus. Der Rückgabewert ist CB_ERR auf, wenn ein Fehler auftritt; der Rückgabewert ist CB_ERRSPACE auf, wenn nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge verfügbar ist.

### <a name="remarks"></a>Hinweise

Wenn das Listenfeld nicht erstellt wurde, mit der [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil, die Zeichenfolge am Ende der Liste hinzugefügt wird. Andernfalls wird die Zeichenfolge in die Liste eingefügt, und die Liste sortiert wird.

> [!NOTE]
>  Diese Funktion wird nicht von der Windows `ComboBoxEx` Steuerelement. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx-Steuerelemente](/windows/desktop/Controls/comboboxex-controls) im Windows SDK.

Verwenden Sie zum Einfügen einer Zeichenfolge in einer bestimmten Position in der Liste der [InsertString](#insertstring) Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

##  <a name="ccombobox"></a>  CComboBox::CComboBox

Erstellt ein `CComboBox`-Objekt.

```
CComboBox();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

##  <a name="clear"></a>  CComboBox::Clear

(Löscht) Löscht die aktuelle Auswahl, falls vorhanden, in das Bearbeitungssteuerelement des Kombinationsfelds.

```
void Clear();
```

### <a name="remarks"></a>Hinweise

Verwenden Sie zum Löschen der aktuellen Auswahl, und fügen Sie den gelöschten Inhalt in die Zwischenablage, die [Ausschneiden](#cut) Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

##  <a name="compareitem"></a>  CComboBox::CompareItem

Wird aufgerufen, durch das Framework, um die relative Position eines neuen Elements im Listenfeld Teil einer sortierten Ownerdrawn-Kombinationsfeld zu bestimmen.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>Parameter

*lpCompareItemStruct*<br/>
Ein long-Zeiger auf eine [COMPAREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcompareitemstruct) Struktur.

### <a name="return-value"></a>Rückgabewert

Die relative Position der beiden Elemente beschrieben, die der `COMPAREITEMSTRUCT` Struktur. Eines der folgenden Werte sind möglich:

|Wert|Bedeutung|
|-----------|-------------|
|- 1|Element 1 wird vor Element 2 sortiert.|
|0|Element 1 und Element 2 sortiert identisch.|
|1|Element 1 wird nach Element 2 sortiert.|

Finden Sie unter [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) eine Beschreibung der `COMPAREITEMSTRUCT`.

### <a name="remarks"></a>Hinweise

Standardmäßig ist diese Member-Funktion mit "nothing". Wenn Sie ein Ownerdrawn-Kombinationsfeld mit dem LBS_SORT-Stil erstellen, müssen Sie diese Memberfunktion, um das Framework bei der Sortierung der neue Elemente im Listenfeld überschreiben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

##  <a name="copy"></a>  CComboBox::Copy

Kopiert die aktuelle Auswahl, ggf. in das Bearbeitungssteuerelement des Kombinationsfelds in die Zwischenablage HIERSVR-Format.

```
void Copy();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

##  <a name="create"></a>  CComboBox::Create

Das Kombinationsfeld erstellt, und fügt es der `CComboBox` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt das Format des Kombinationsfelds. Wenden Sie eine beliebige Kombination von [kombinationsfeldstile](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) in das Feld.

*rect*<br/>
Verweist auf die Position und Größe des Kombinationsfelds. Kann eine [RECT-Struktur](/windows/desktop/api/windef/ns-windef-tagrect) oder `CRect` Objekt.

*pParentWnd*<br/>
Gibt an, das Kombinationsfeld des übergeordneten Fensters (in der Regel eine `CDialog`). Es darf nicht NULL sein.

*nID*<br/>
Gibt an, das Kombinationsfeld-Steuerelement-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CComboBox` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie anschließend `Create`, die das Windows-Kombinationsfeld erstellt, und fügt es der `CComboBox` Objekt.

Wenn `Create` ausgeführt wird, handelt es sich bei Windows sendet die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Nachrichten im Kombinationsfeld.

Diese Nachrichten werden standardmäßig behandelt der [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standardbehandlung für die Nachricht zu erweitern, leiten Sie eine Klasse von `CComboBox`, hinzufügen eine meldungszuordnung an die neue Klasse und überschreiben Sie die vorherigen Meldungshandler-Memberfunktionen. Außer Kraft setzen `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.

Übernehmen Sie das folgende [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) an ein Kombinationsfeld-Steuerelement. :

- WS_CHILD immer

- WS_VISIBLE in der Regel

- WS_DISABLED selten

- WS_VSCROLL hinzufügen vertikalem Bildlauf für das Listenfeld im Kombinationsfeld

- WS_HSCROLL hinzufügen horizontalen Bildlauf für das Listenfeld im Kombinationsfeld

- WS_GROUP zum Gruppieren von Steuerelementen

- WS_TABSTOP, schließen das Kombinationsfeld in die Tab-Reihenfolge

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

##  <a name="cut"></a>  CComboBox::Cut

Löscht (Schnitte) die aktuelle Auswahl, wenn vorhanden, in dem Kombinationsfeld Bearbeiten steuern und den gelöschten Text in die Zwischenablage HIERSVR Format kopiert.

```
void Cut();
```

### <a name="remarks"></a>Hinweise

Um die aktuelle Auswahl ohne den gelöschten Text in die Zwischenablage zu löschen, rufen die [löschen](#clear) Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

##  <a name="deleteitem"></a>  CComboBox::DeleteItem

Vom Framework aufgerufen, wenn der Benutzer ein Element aus einem Ownerdrawn-löscht `CComboBox` Objekt oder Kombinationsfeld zerstört.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDeleteItemStruct*<br/>
Ein long-Zeiger auf ein Windows [DELETEITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdeleteitemstruct) -Struktur, die Informationen über das gelöschte Element enthält. Finden Sie unter [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) eine Beschreibung dieser Struktur.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um das Kombinationsfeld je nach Bedarf neu zu zeichnen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

##  <a name="deletestring"></a>  CComboBox::DeleteString

Löscht das Element an Position *nIndex* aus dem Kombinationsfeld.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt den Index in die Zeichenfolge, die gelöscht werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn der Rückgabewert größer als oder gleich 0 ist, ist es die Anzahl der Zeichenfolgen in der Liste Verbleibende. Der Rückgabewert ist CB_ERR aus, wenn *nIndex* Index größer als die Anzahl der Elemente in der Liste angibt.

### <a name="remarks"></a>Hinweise

Alle Elemente, die nach *nIndex* jetzt eine Position nach unten zu verschieben. Z. B. wenn ein Kombinationsfeld zwei Elemente enthält, bewirkt löschen das erste Element den verbleibenden Artikel jetzt in der ersten Position sein. *nIndex*= 0 für das Element in der ersten Position.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

##  <a name="dir"></a>  CComboBox::Dir

Fügt eine Liste mit Dateinamen oder Laufwerken in das Listenfeld eines Kombinationsfelds an.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>Parameter

*attr*<br/>
Kann eine beliebige Kombination von werden die **Enum** Werte, die in beschriebenen [CFile:: GetStatus](../../mfc/reference/cfile-class.md#getstatus) oder eine beliebige Kombination der folgenden Werte:

- DDL_READWRITE-Datei kann aus gelesen oder geschrieben werden.

- DDL_READONLY Datei auslesen, jedoch nicht geschrieben werden kann.

- DDL_HIDDEN-Datei wird ausgeblendet und nicht in einer Verzeichnisliste angezeigt.

- DDL_SYSTEM-Datei ist eine Systemdatei.

- DDL_DIRECTORY den Namen trägt *LpszWildCard* gibt ein Verzeichnis an.

- DDL_ARCHIVE-Datei wurde archiviert.

- DDL_DRIVES enthalten alle Laufwerke, die mit den vom angegebenen Namen übereinstimmen *LpszWildCard*.

- Exklusive DDL_EXCLUSIVE Flag. Wenn das exclusive-Flag festgelegt ist, werden nur Dateien vom angegebenen Typ aufgeführt. Andernfalls werden Dateien vom angegebenen Typ zusätzlich zu "normal" Dateien aufgeführt.

*lpszWildCard*<br/>
Verweist auf eine Dateispezifikation Zeichenfolge. Die Zeichenfolge kann Platzhalter enthalten (z. B. *.\*).

### <a name="return-value"></a>Rückgabewert

Wenn der Rückgabewert größer als oder gleich 0 ist, ist es den nullbasierten Index des letzten Dateinamen zur Liste hinzugefügt. Der Rückgabewert ist CB_ERR auf, wenn ein Fehler auftritt; der Rückgabewert ist CB_ERRSPACE ist nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolgen zur Verfügung.

### <a name="remarks"></a>Hinweise

Diese Funktion wird nicht von der Windows `ComboBoxEx` Steuerelement. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx-Steuerelemente](/windows/desktop/Controls/comboboxex-controls) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

##  <a name="drawitem"></a>  CComboBox::DrawItem

Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Kombinationsfeld Feld ändert.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein Zeiger auf eine [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) -Struktur, Informationen über den Typ der Zeichnung, die erforderlich sind enthält.

### <a name="remarks"></a>Hinweise

Die `itemAction` Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll. Finden Sie unter [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) eine Beschreibung dieser Struktur.

Standardmäßig ist diese Member-Funktion mit "nothing". Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CComboBox` Objekt. Bevor Sie diese Memberfunktion beendet wird, sollte die Anwendung alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext in angegeben wiederherstellen *LpDrawItemStruct*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

##  <a name="findstring"></a>  CComboBox:: FindString

Ermittelt, aber nicht auswählen, die erste Zeichenfolge, die das angegebene Präfix in das Listenfeld eines Kombinationsfelds enthält.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>Parameter

*nStartAfter*<br/>
Enthält den nullbasierten Index des Elements vor dem ersten Element zu durchsuchenden an. Wenn die Suche am Ende das Listenfeld erreicht, weiterhin von der obersten Position des Listenfelds zurück vom angegebenen Elements *nStartAfter*. Wenn-1 ist, wird das ganze Listenfeld vom Anfang durchsucht.

*lpszString*<br/>
Verweist auf die Null-terminierte Zeichenfolge, die das Präfix, das für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.

### <a name="return-value"></a>Rückgabewert

Wenn der Rückgabewert größer als oder gleich 0 ist, ist es der nullbasierte Index des übereinstimmenden Elements. Es ist CB_ERR, wenn die Suche nicht erfolgreich war.

### <a name="remarks"></a>Hinweise

Diese Funktion wird nicht von der Windows `ComboBoxEx` Steuerelement. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx-Steuerelemente](/windows/desktop/Controls/comboboxex-controls) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

##  <a name="findstringexact"></a>  CComboBox::FindStringExact

Rufen Sie die `FindStringExact` Memberfunktion, um die erste Listenfeld-Zeichenfolge (in einem Kombinationsfeld) zu finden, der angegebenen Zeichenfolge entspricht *LpszFind*.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>Parameter

*nIndexStart*<br/>
Gibt an, der nullbasierte Index des Elements, bevor das erste Element, gesucht werden soll. Wenn die Suche am Ende das Listenfeld erreicht, weiterhin von der obersten Position des Listenfelds zurück vom angegebenen Elements *nIndexStart*. Wenn *nIndexStart* -1 ist, durchsucht das ganze Listenfeld ab.

*lpszFind*<br/>
Verweist auf die Null-terminierte Zeichenfolge zu suchende. Diese Zeichenfolge kann es sich um einen vollständigen Dateinamen, einschließlich der Erweiterung enthalten. Die Suche ist nicht Groß-/ Kleinschreibung, damit diese Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des übereinstimmenden Elements oder CB_ERR, wenn die Suche nicht erfolgreich war.

### <a name="remarks"></a>Hinweise

Wenn das Kombinationsfeld in einem Ownerdrawn-Format, jedoch ohne erstellt wurde die [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil `FindStringExact` versucht, mit dem Wert zeigt Doppelwort mit dem Wert von überein *LpszFind*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

##  <a name="getcomboboxinfo"></a>  CComboBox::GetComboBoxInfo

Ruft Informationen für die `CComboBox` Objekt.

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>Parameter

*pcbi*<br/>
Ein Zeiger auf die [COMBOBOXINFO](/windows/desktop/api/winuser/ns-winuser-tagcomboboxinfo) Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen des die [CB_GETCOMBOBOXINFO](/windows/desktop/Controls/cb-getcomboboxinfo) Nachricht, wie im Windows SDK beschrieben.

##  <a name="getcount"></a>  CComboBox::GetCount

Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Elemente in der Listenfeld eines Kombinationsfelds an.

```
int GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente. Die zurückgegebene Anzahl ist größer als der Wert für das letzte Element (der Index ist nullbasiert). Es ist CB_ERR, wenn ein Fehler auftritt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

##  <a name="getcuebanner"></a>  CComboBox::GetCueBanner

Ruft den Hinweistext, der angezeigt wird, ist für ein Kombinationsfeld-Steuerelement ab.

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*lpszText*|[out] Zeiger auf einen Puffer, der den hinweisbannertext empfängt.|
|*cchText*|[in] Größe des Puffers, der die *LpszText* -Parameter zeigt.|

### <a name="return-value"></a>Rückgabewert

In der ersten Überladung ist eine [CString](../../atl-mfc-shared/using-cstring.md) Objekt, das den hinweisbannertext enthält, sofern vorhanden, andernfalls eine `CString` -Objekt, das keine Länge verfügt.

- oder - 

In der zweiten Überladung ist "true", wenn diese Methode erfolgreich ist; andernfalls "false".

### <a name="remarks"></a>Hinweise

Hinweistext wird eine Eingabeaufforderung, die in das Eingabefeld des Kombinationsfeld-Steuerelement angezeigt wird. Der Hinweistext wird angezeigt, bis der Benutzer die Eingabe vornimmt.

Diese Methode sendet die [CB_GETCUEBANNER](/windows/desktop/Controls/cb-getcuebanner) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getcursel"></a>  CComboBox::GetCurSel

Rufen Sie diese Memberfunktion, um zu bestimmen, welches Element im Kombinationsfeld ausgewählt wird.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des derzeit ausgewählten Elements in das Listenfeld eines Kombinationsfelds oder CB_ERR, wenn kein Element ausgewählt ist.

### <a name="remarks"></a>Hinweise

`GetCurSel` Gibt einen Index in der Liste zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

##  <a name="getdroppedcontrolrect"></a>  CComboBox::GetDroppedControlRect

Rufen Sie die `GetDroppedControlRect` Memberfunktion versucht, das die Bildschirmkoordinaten des Felds angezeigt (gelöscht) Dropdownliste eines Dropdown-Kombinationsfelds abrufen.

```
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>Parameter

*lprect*<br/>
Verweist auf die [RECT-Struktur](/windows/desktop/api/windef/ns-windef-tagrect) , die die Koordinaten empfangen werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

##  <a name="getdroppedstate"></a>  CComboBox::GetDroppedState

Rufen Sie die `GetDroppedState` Memberfunktion, um zu bestimmen, ob das Listenfeld ein Dropdown-Kombinationsfeld angezeigt wird (hat).

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn im Listenfeld angezeigt wird; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

##  <a name="getdroppedwidth"></a>  CComboBox::GetDroppedWidth

Rufen Sie diese Funktion, um die minimale zulässige Breite in Pixel im Listenfeld eines Kombinationsfelds abrufen.

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung die minimale zulässige Breite in Pixel; andernfalls CB_ERR.

### <a name="remarks"></a>Hinweise

Diese Funktion gilt nur für Kombinationsfelder, die mit der [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.

Standardmäßig ist die minimale zulässige Breite des Dropdown-Listenfelds 0. Die minimale zulässige Breite kann festgelegt werden, durch den Aufruf [SetDroppedWidth](#setdroppedwidth). Wenn der Teil der im Listenfeld des Kombinationsfelds angezeigt wird, wird seine Breite je größer die minimale zulässige Breite oder die Breite des Kombinationsfelds Feld.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [SetDroppedWidth](#setdroppedwidth).

##  <a name="geteditsel"></a>  CComboBox::GetEditSel

Ruft die Zeichenpositionen Start- und Enddatum, der die aktuelle Auswahl in das Steuerelement zum Bearbeiten eines Kombinationsfelds ab.

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>Rückgabewert

Ein 32-Bit-Wert, der die Anfangsposition in das niederwertige Wort und die Position des ersten Zeichens nicht ausgewählten nach dem Ende der Auswahl in das höherwertige Wort enthält. Wenn diese Funktion in einem Kombinationsfeld ohne ein Edit-Steuerelement verwendet wird, wird die CB_ERR zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

##  <a name="getextendedui"></a>  CComboBox::GetExtendedUI

Rufen Sie die `GetExtendedUI` Memberfunktion, um zu bestimmen, ob ein Kombinationsfeld die Standardbenutzeroberfläche oder die erweiterten Benutzeroberfläche hat.

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Kombinationsfeld die erweiterten Benutzeroberfläche hat; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die erweiterten Benutzeroberfläche kann auf folgende Weise identifiziert werden:

- Klicken auf das statische Steuerelement zeigt im Listenfeld nur für Kombinationsfelder, die mit der [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.

- Drücken der nach-unten-Taste zeigt im Listenfeld (F4 ist deaktiviert).

Bildlauf im statischen Steuerelement ist deaktiviert, wenn die Liste nicht sichtbar (Pfeil) ist die Schlüssel deaktiviert sind.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

##  <a name="gethorizontalextent"></a>  CComboBox::GetHorizontalExtent

Ruft die Breite in Pixel, die mit denen Bereich im Listenfeld des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann, aus dem Kombinationsfeld ab.

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>Rückgabewert

Die bildlauffähigen Breite des Listenfeld Teils im Kombinationsfeld in Pixel.

### <a name="remarks"></a>Hinweise

Dies gilt nur, wenn der Teil der im Listenfeld des Kombinationsfelds eine horizontale Bildlaufleiste angezeigt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

##  <a name="getitemdata"></a>  CComboBox::GetItemData

Ruft ab, der von der Anwendung bereitgestellten 32-Bit-Wert zugeordnet ist, mit dem angegebenen Kombinationsfeld-Element.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den nullbasierten Index eines Elements im Listenfeld des Kombinationsfelds.

### <a name="return-value"></a>Rückgabewert

Der 32-Bit-Wert, dem Element oder CB_ERR zugeordnet, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Die 32-Bit-Wert kann festgelegt werden, mit der *DwItemData* Parameter eine [SetItemData](#setitemdata) Aufruf der Memberfunktion. Verwenden der `GetItemDataPtr` Member-Funktion, wenn der 32-Bit-Wert abgerufen werden soll, ein Zeiger ist (**"void"** <strong>\*</strong>).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

##  <a name="getitemdataptr"></a>  CComboBox::GetItemDataPtr

Ruft ab, der von der Anwendung bereitgestellten 32-Bit-Wert zugeordnet ist, mit dem angegebenen Kombinationsfeld-Element als Zeiger (**"void"** <strong>\*</strong>).

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den nullbasierten Index eines Elements im Listenfeld des Kombinationsfelds.

### <a name="return-value"></a>Rückgabewert

Ruft ab einen Zeiger oder -1, wenn ein Fehler auftritt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

##  <a name="getitemheight"></a>  CComboBox::GetItemHeight

Rufen Sie die `GetItemHeight` Member-Funktion, um die Höhe der Listenelemente in einem Kombinationsfeld abzurufen.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt die Komponente des Kombinationsfelds, deren Höhe ist, abgerufen werden sollen. Wenn die *nIndex* Parameter ist 1, der die Höhe des bearbeiten-Steuerelement (oder statischem Text) Teils der im Kombinationsfeld wird abgerufen. Wenn das Kombinationsfeld hat die [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil *nIndex* gibt den nullbasierten Index des Listenelements, deren Höhe ist, abgerufen werden sollen. Andernfalls *nIndex* muss auf 0 festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Die Höhe des angegebenen Elements in einem Kombinationsfeld in Pixel. Der Rückgabewert ist CB_ERR auf, wenn ein Fehler auftritt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

##  <a name="getlbtext"></a>  CComboBox::GetLBText

Ruft eine Zeichenfolge aus dem Listenfeld eines Kombinationsfelds ab.

```
int GetLBText(
    int nIndex,
    LPTSTR lpszText) const;

void GetLBText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den nullbasierten Index des dem Listenfeld zu kopierende Zeichenfolge.

*lpszText*<br/>
Verweist auf einen Puffer, der die Zeichenfolge empfangen. Der Puffer muss über genügend Speicherplatz für die Zeichenfolge und ein abschließendes Nullzeichen verfügen.

*rString*<br/>
Ein Verweis auf eine `CString`.

### <a name="return-value"></a>Rückgabewert

Die Länge (in Byte) der Zeichenfolge, mit Ausnahme des abschließenden Zeichens Null. Wenn *nIndex* gibt kein gültigen Index, der Rückgabewert ist CB_ERR.

### <a name="remarks"></a>Hinweise

Die zweite Form dieses Members-Funktion füllt eine `CString` Objekt mit den Text des Elements.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

##  <a name="getlbtextlen"></a>  CComboBox::GetLBTextLen

Ruft die Länge einer Zeichenfolge in das Listenfeld eines Kombinationsfelds ab.

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den nullbasierten Index des Listenfeld Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Die Länge der Zeichenfolge in Bytes, ausgenommen das abschließende Nullzeichen. Wenn *nIndex* gibt kein gültigen Index, der Rückgabewert ist CB_ERR.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CComboBox::GetLBText](#getlbtext).

##  <a name="getlocale"></a>  CComboBox::GetLocale

Ruft das Gebietsschema ein, die im Kombinationsfeld ab.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Rückgabewert

Wert des Gebietsschemabezeichners (LCID) für die Zeichenfolgen im Kombinationsfeld.

### <a name="remarks"></a>Hinweise

Das Gebietsschema ist z. B. verwendet, um die Sortierreihenfolge der Zeichenfolgen in einem sortierten Kombinationsfeld zu bestimmen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CComboBox::SetLocale](#setlocale).

##  <a name="getminvisible"></a>  CComboBox::GetMinVisible

Ruft die minimale Anzahl der sichtbaren Elemente in der Dropdown-Liste der aktuellen Kombinationsfeld-Steuerelements ab.

```
int GetMinVisible() const;
```

### <a name="return-value"></a>Rückgabewert

Die minimale Anzahl der sichtbaren Elemente in der aktuellen Dropdown-Liste.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [CB_GETMINVISIBLE](/windows/desktop/Controls/cb-setminvisible) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="gettopindex"></a>  CComboBox::GetTopIndex

Ruft ab, der nullbasierte Index des ersten sichtbaren Elements im Bereich Listenfeld des Kombinationsfelds.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des ersten sichtbaren Elements im Listenfeld Teil im Kombinationsfeld, wenn erfolgreich, andernfalls CB_ERR.

### <a name="remarks"></a>Hinweise

Zunächst Element 0 befindet sich oben im Listenfeld, aber wenn das Listenfeld ein Bildlauf durchgeführt wird, kann ein anderes Element am Anfang sein.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

##  <a name="initstorage"></a>  CComboBox::InitStorage

Belegt Speicher zum Speichern von Listenfeldelemente im Bereich Listenfeld des Kombinationsfelds.

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

Wenn erfolgreich, die maximale Anzahl von Elementen, die Bereich Listenfeld des Kombinationsfelds werden, bevor Sie eine neuzuordnung von Arbeitsspeicher gespeichert kann wird benötigt, andernfalls CB_ERRSPACE, d.h. nicht genügend Arbeitsspeicher verfügbar ist.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird vor dem Hinzufügen einer großen Anzahl von Elementen dem Listenfeld-Teil der `CComboBox`.

Windows 95/98 nur: Die *wParam* Parameter ist auf 16-Bit-Werten beschränkt. Dies bedeutet, dass es sich bei Listenfelder mehr als 32.767 Elemente enthalten können. Obwohl die Anzahl der Elemente beschränkt ist, wird die Gesamtgröße der Elemente in einem Listenfeld nur durch den verfügbaren Arbeitsspeicher beschränkt.

Diese Funktion hilft, die Initialisierung von Listenfeldern zu beschleunigen, die eine große Anzahl von Elementen (mehr als 100). Es belegt, dass die angegebene Menge Arbeitsspeicher, sodass nachfolgende [AddString](#addstring), [InsertString](#insertstring), und [Dir](#dir) Funktionen nehmen kurz wie möglich. Sie können die Schätzungen für die Parameter verwenden. Wenn Sie überschätzen, ist einige zusätzlichen Arbeitsspeicher zugeteilt. Wenn Sie unterschätzen, wird die normale Zuordnung für Elemente verwendet, die der vorab festgelegten Betrag übersteigen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

##  <a name="insertstring"></a>  CComboBox::InsertString

Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds ein.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den nullbasierten Index der Position im Listenfeld, die die Zeichenfolge aufnehmen soll. Wenn dieser Parameter-1 ist, wird die Zeichenfolge am Ende der Liste hinzugefügt.

*lpszString*<br/>
Zeigt auf die einzufügende nullterminierte Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index der Position, an der die Zeichenfolge eingefügt wurde. Der Rückgabewert ist CB_ERR auf, wenn ein Fehler auftritt. Der Rückgabewert ist CB_ERRSPACE auf, wenn nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge verfügbar ist.

### <a name="remarks"></a>Hinweise

Im Gegensatz zur Memberfunktion [AddString](#addstring) bewirkt die `InsertString` -Memberfunktion nicht die Sortierung einer Liste mit der Formatvorlage [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) .

> [!NOTE]
>  Diese Funktion wird nicht von der Windows `ComboBoxEx` Steuerelement. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx-Steuerelemente](/windows/desktop/Controls/comboboxex-controls) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

##  <a name="limittext"></a>  CComboBox::LimitText

Begrenzt die Länge in Bytes des Texts, der der Benutzer das Steuerelement zum Bearbeiten eines Kombinationsfelds eingegeben werden kann.

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>Parameter

*nMaxChars*<br/>
Gibt die Länge (in Byte) des Texts, der der Benutzer eingeben kann. Wenn dieser Parameter 0 ist, wird die Länge des Texts auf 65.535 Byte festgelegt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich. Wenn für ein Kombinationsfeld, in dem Format namens [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder für ein Kombinationsfeld, ohne ein Bearbeitungssteuerelement, ist der Rückgabewert CB_ERR.

### <a name="remarks"></a>Hinweise

Wenn das Kombinationsfeld keinen styl [CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles), festlegen, die größer als die Größe des Bearbeitungssteuerelements sein Text hat keine Auswirkungen.

`LimitText` den Text, den der Benutzer eingeben kann Größe beschränkt. Wirkt sich nicht auf einen beliebigen Text ein bereits in das Bearbeitungssteuerelement Wenn die Nachricht gesendet wird, noch wirkt sie sich die Länge des Texts in das Bearbeitungssteuerelement kopiert werden, wenn eine Zeichenfolge im Listenfeld ausgewählt ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

##  <a name="measureitem"></a>  CComboBox::MeasureItem

Vom Framework aufgerufen, wenn ein Kombinationsfeld in einem Ownerdrawn-Format erstellt wird.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parameter

*lpMeasureItemStruct*<br/>
Ein long-Zeiger auf eine [MEASUREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagmeasureitemstruct) Struktur.

### <a name="remarks"></a>Hinweise

Standardmäßig ist diese Member-Funktion mit "nothing". Überschreiben Sie diese Memberfunktion auf, und geben Sie die `MEASUREITEMSTRUCT` zu informieren, Windows, der die Dimensionen der Liste im Feld im Kombinationsfeld-Struktur. Wenn das Kombinationsfeld erstellt wird, mit der [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Format, das Framework ruft diese Member-Funktion für jedes Element im Listenfeld. Andernfalls wird dieser Member nur einmal aufgerufen.

Mit dem CBS_OWNERDRAWFIXED-Stil in einem Ownerdrawn-Kombinationsfeld erstellt, mit der [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) Memberfunktion `CWnd` umfasst weitere Programmiersprache Überlegungen. Finden Sie unter den Ausführungen im [technischen Hinweis 14](../../mfc/tn014-custom-controls.md).

Finden Sie unter [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) eine Beschreibung der `MEASUREITEMSTRUCT` Struktur.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

##  <a name="paste"></a>  CComboBox::Paste

Die Daten aus der Zwischenablage in das Bearbeitungssteuerelement des Kombinationsfelds an der aktuellen Cursorposition eingefügt.

```
void Paste();
```

### <a name="remarks"></a>Hinweise

Daten werden eingefügt, nur, wenn die Zwischenablage Daten im HIERSVR Format enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

##  <a name="resetcontent"></a>  CComboBox::ResetContent

Entfernt, die alle Elemente aus der Liste ein, und bearbeiten die Kontrolle über ein Kombinationsfeld.

```
void ResetContent();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

##  <a name="selectstring"></a>  CComboBox::SelectString

Sucht nach einer Zeichenfolge in das Listenfeld eines Kombinationsfelds, und wenn die Zeichenfolge gefunden wird, die Zeichenfolge im Listenfeld auswählt und kopiert ihn in das Steuerelement zum Bearbeiten.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parameter

*nStartAfter*<br/>
Enthält den nullbasierten Index des Elements vor dem ersten Element zu durchsuchenden an. Wenn die Suche am Ende das Listenfeld erreicht, weiterhin von der obersten Position des Listenfelds zurück vom angegebenen Elements *nStartAfter*. Wenn-1 ist, wird das ganze Listenfeld vom Anfang durchsucht.

*lpszString*<br/>
Verweist auf die Null-terminierte Zeichenfolge, die das Präfix, das für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des ausgewählten Elements, wenn die Zeichenfolge gefunden wurde. Wenn die Suche nicht erfolgreich war, CB_ERR zurückgegeben wird, und die aktuelle Auswahl wird nicht geändert.

### <a name="remarks"></a>Hinweise

Eine Zeichenfolge, die ausgewählt ist, nur dann, wenn die erste Zeichen (vom Ausgangspunkt) der Zeichen in der Präfixzeichenfolge entsprechen.

Beachten Sie, dass die `SelectString` und `FindString` Memberfunktionen beide finden Sie eine Zeichenfolge, aber die `SelectString` Memberfunktion wählt auch die Zeichenfolge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

##  <a name="setcuebanner"></a>  CComboBox::SetCueBanner

Legt fest, den Hinweistext, der für ein Kombinationsfeld-Steuerelement angezeigt wird.

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*lpszText*|[in] Zeiger auf eine auf Null endende Puffer, der den Hinweistext enthält.|

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Hinweistext wird eine Eingabeaufforderung, die in das Eingabefeld des Kombinationsfeld-Steuerelement angezeigt wird. Der Hinweistext wird angezeigt, bis der Benutzer die Eingabe vornimmt.

Diese Methode sendet die [CB_SETCUEBANNER](/windows/desktop/Controls/cb-setcuebanner) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable *M_combobox*, d. h. verwendet, um das Kombinationsfeld-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel legt fest, das hinweisbanner für das Kombinationsfeld-Steuerelement.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

##  <a name="setcursel"></a>  CComboBox::SetCurSel

Wählt aus eine Zeichenfolge in das Listenfeld eines Kombinationsfelds.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>Parameter

*. nalles auswählen*<br/>
Gibt den nullbasierten Index des wählen Sie die Zeichenfolge an. Wenn-1 und aktuelle Auswahl im Listenfeld entfernt wird, und der Edit-Steuerelement deaktiviert ist.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des Elements ausgewählt, wenn die Nachricht erfolgreich ist. Der Rückgabewert ist CB_ERR aus, wenn *. nalles auswählen* ist größer als die Anzahl der Elemente in der Liste oder, wenn *. nalles auswählen* wird auf-1 festgelegt, die die Auswahl löscht.

### <a name="remarks"></a>Hinweise

Bei Bedarf führt einen Bildlauf im Listenfeld die Zeichenfolge in der Ansicht (Wenn Sie im Listenfeld angezeigt wird). Der Text im Bearbeitungssteuerelement des Kombinationsfelds wird geändert, um die neue Auswahl angewendet. Die vorherige Auswahl im Listenfeld entfernt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

##  <a name="setdroppedwidth"></a>  CComboBox::SetDroppedWidth

Rufen Sie diese Funktion, um die minimale zulässige Breite in Pixel, der im Listenfeld eines Kombinationsfelds festgelegt.

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>Parameter

*nWidth*<br/>
Die minimale zulässige Breite des Listenfeld Teils im Kombinationsfeld in Pixel.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, die neue Breite des ListBox-Felds, andernfalls CB_ERR.

### <a name="remarks"></a>Hinweise

Diese Funktion gilt nur für Kombinationsfelder, die mit der [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.

Standardmäßig ist die minimale zulässige Breite des Dropdown-Listenfelds 0. Wenn der Teil der im Listenfeld des Kombinationsfelds angezeigt wird, wird seine Breite je größer die minimale zulässige Breite oder die Breite des Kombinationsfelds Feld.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

##  <a name="seteditsel"></a>  CComboBox::SetEditSel

Das Steuerelement zum Bearbeiten eines Kombinationsfelds markiert Zeichen.

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>Parameter

*nStartChar*<br/>
Gibt die Anfangsposition an. Wenn die Position des ersten auf-1 festgelegt ist, wird dann eine vorhandene Auswahl entfernt.

*nEndChar*<br/>
Gibt die Endposition. Wenn die Endposition-1, klicken Sie dann allen Text aus die Position des ersten, mit dem letzten festgelegt ist ist Zeichen in das Bearbeitungssteuerelement ausgewählt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Member-Funktion erfolgreich ist; andernfalls 0. Wenn CB_ERR ist `CComboBox` hat die [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) formatieren oder verfügt nicht über ein Listenfeld.

### <a name="remarks"></a>Hinweise

Die Positionen sind nullbasiert. Um das erste Zeichen des Bearbeitungssteuerelements auszuwählen, geben Sie die Position des ersten 0. Die Endposition ist für das Zeichen direkt nach dem letzten Zeichen auswählen. Um die ersten vier Zeichen des Bearbeitungssteuerelements auszuwählen, würden Sie z. B. eine Startposition 0 und einer Endposition von 4 verwenden.

> [!NOTE]
>  Diese Funktion wird nicht von der Windows `ComboBoxEx` Steuerelement. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx-Steuerelemente](/windows/desktop/Controls/comboboxex-controls) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CComboBox::GetEditSel](#geteditsel).

##  <a name="setextendedui"></a>  CComboBox::SetExtendedUI

Rufen Sie die `SetExtendedUI` Memberfunktion versucht, wählen Sie entweder die Standard-Benutzeroberfläche oder die erweiterte Benutzeroberfläche für ein Kombinationsfeld, die die [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>Parameter

*bDie*<br/>
Gibt an, ob das Kombinationsfeld die erweiterten Benutzeroberfläche oder die Standardbenutzeroberfläche verwenden möchten. Der Wert "true", werden die erweiterten Benutzeroberfläche markiert. der Wert "false" wählt die Standardbenutzeroberfläche.

### <a name="return-value"></a>Rückgabewert

CB_OKAY, wenn der Vorgang erfolgreich ist, oder CB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Die erweiterten Benutzeroberfläche kann auf folgende Weise identifiziert werden:

- Durch Klicken auf statischen Steuerelements wird im Listenfeld nur für Kombinationsfelder, die mit dem CBS_DROPDOWNLIST-Stil.

- Drücken der nach-unten-Taste zeigt im Listenfeld (F4 ist deaktiviert).

Durchführen eines Bildlaufs im statischen Steuerelement deaktiviert ist, wenn die Liste nicht angezeigt wird (die Pfeiltasten sind deaktiviert).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CComboBox::GetExtendedUI](#getextendedui).

##  <a name="sethorizontalextent"></a>  CComboBox::SetHorizontalExtent

Legt die Breite in Pixel mit denen Bereich im Listenfeld des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann.

```
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>Parameter

*nExtent*<br/>
Gibt die Anzahl der Pixel, die mit denen Bereich im Listenfeld des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann.

### <a name="remarks"></a>Hinweise

Wenn die Breite des ListBox-Felds kleiner als dieser Wert ist, wird die horizontale Bildlaufleiste horizontal Elemente im Listenfeld scrollen. Die horizontale Bildlaufleiste wird ausgeblendet, wenn die Breite des ListBox-Felds gleich oder größer als dieser Wert ist, oder, wenn das Kombinationsfeld hat die [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil deaktiviert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

##  <a name="setitemdata"></a>  CComboBox::SetItemData

Legt den 32-Bit-Wert, der das angegebene Element in einem Kombinationsfeld zugeordnet.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält einen nullbasierte Index des Elements festlegen.

*dwItemData*<br/>
Enthält den neuen Wert, der dem Element zugeordnet.

### <a name="return-value"></a>Rückgabewert

CB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Verwenden der `SetItemDataPtr` Memberfunktion, wenn das 32-Bit-Element ist ein Zeiger sein.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

##  <a name="setitemdataptr"></a>  CComboBox::SetItemDataPtr

Legt den 32-Bit-Wert, der das angegebene Element in einem Kombinationsfeld angegebenen Zeiger zugeordnet (**"void"** <strong>\*</strong>).

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält einen nullbasierten Index des Elements an.

*pData*<br/>
Enthält den Zeiger zu dem Element zugeordnet.

### <a name="return-value"></a>Rückgabewert

CB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

This-Zeiger bleibt gültig, für die Lebensdauer des Kombinationsfelds, obwohl der Position des Elements relative innerhalb des Kombinationsfelds ändern kann, wenn Elemente hinzugefügt oder entfernt werden. Daher kann den Index des Elements innerhalb des Felds ändern, aber der Zeiger bleibt zuverlässige.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

##  <a name="setitemheight"></a>  CComboBox::SetItemHeight

Rufen Sie die `SetItemHeight` Member-Funktion, um die Höhe der Listenelemente in einem Kombinationsfeld oder die Höhe des bearbeiten-Steuerelement (oder statischem Text) Teils eines Kombinationsfelds festzulegen.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt an, ob die Höhe der Listenelemente oder die Höhe des bearbeiten-Steuerelement (oder statischem Text) Teils des Kombinationsfelds festgelegt ist.

Wenn das Kombinationsfeld hat die [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil *nIndex* gibt den nullbasierten Index des Listenelements, deren Höhe ist, andernfalls *nIndex* muss 0 sein und die Höhe aller Elemente der Liste wird festgelegt.

Wenn *nIndex* ist-1 und die Höhe des Edit-Steuerelements oder statischem Text Teils des Kombinationsfelds wird festgelegt werden.

*cyItemHeight*<br/>
Gibt die Höhe in Pixel der identifizierte Komponente im Kombinationsfeld *nIndex*.

### <a name="return-value"></a>Rückgabewert

CB_ERR, wenn der Index oder der Höhe ungültig ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Höhe des bearbeiten-Steuerelement (oder statischem Text) Teils des Kombinationsfelds ist unabhängig von der die Höhe der Listenelemente festgelegt werden. Eine Anwendung muss sicherzustellen, dass die Höhe des den bearbeiten-Steuerelement (oder statischem Text) nicht kleiner als die Höhe eines bestimmten Listenfeld-Elements.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

##  <a name="setlocale"></a>  CComboBox::SetLocale

Legt den Gebietsschemabezeichner für dieses Kombinationsfelds fest.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>Parameter

*nNewLocale*<br/>
Der neue Gebietsschema-ID (LCID) Wert für das Kombinationsfeld festgelegt.

### <a name="return-value"></a>Rückgabewert

Der vorherige Gebietsschema-ID (LCID) Wert für dieses Kombinationsfelds.

### <a name="remarks"></a>Hinweise

Wenn `SetLocale` nicht aufgerufen wird, der Standardwert Gebietsschema wird vom System abgerufen. Diese standardsystemgebietsschema kann geändert werden, mithilfe der Systemsteuerung regionalen (oder International)-Anwendung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

##  <a name="setminvisibleitems"></a>  CComboBox::SetMinVisibleItems

Legt die minimale Anzahl der sichtbaren Elemente in der Dropdown-Liste des aktuellen Kombinationsfeld-Steuerelement fest.

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iMinVisible*|[in] Gibt die minimale Anzahl der sichtbaren Elemente.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [CB_SETMINVISIBLE](/windows/desktop/Controls/cb-setminvisible) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable *M_combobox*, d. h. verwendet, um das Kombinationsfeld-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel fügt 20 Elemente in der Dropdown-Werteliste ein Kombinationsfeld-Steuerelement. Dann gibt es, dass mindestens 10 Elemente angezeigt werden, wenn ein Benutzer auf den Dropdown-Pfeil drückt.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

##  <a name="settopindex"></a>  CComboBox::SetTopIndex

Stellt sicher, dass ein bestimmtes Element im Listenfeld Teil im Kombinationsfeld angezeigt wird.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt an, der nullbasierte Index des Elements im Listenfeld.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn erfolgreich, oder CB_ERR, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Das System führt einen Bildlauf im Listenfeld, bis entweder anhand des Elements *nIndex* wird am oberen Rand der Liste im Feld oder den maximalen Bildlauf-Bereich wurde erreicht.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

##  <a name="showdropdown"></a>  CComboBox::ShowDropDown

Blendet das Listenfeld eines Kombinationsfelds an, die die [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.

```
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>Parameter

*bShowIt*<br/>
Gibt an, ob der Dropdown-Listenfeld angezeigt oder ausgeblendet werden. Der Wert "true" wird im Listenfeld. Der Wert "false" wird im Listenfeld ausgeblendet.

### <a name="remarks"></a>Hinweise

Standardmäßig wird ein Kombinationsfeld dieses Stils im Listenfeld angezeigt.

Diese Memberfunktion hat keine Auswirkungen auf das Kombinationsfeld erstellt, mit der [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CComboBox::GetDroppedState](#getdroppedstate).

## <a name="see-also"></a>Siehe auch

[MFC-Muster CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CButton-Klasse](../../mfc/reference/cbutton-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CListBox-Klasse](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar-Klasse](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic-Klasse](../../mfc/reference/cstatic-class.md)<br/>
[CDialog-Klasse](../../mfc/reference/cdialog-class.md)
