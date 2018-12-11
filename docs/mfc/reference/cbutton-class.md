---
title: CButton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CButton
- AFXWIN/CButton
- AFXWIN/CButton::CButton
- AFXWIN/CButton::Create
- AFXWIN/CButton::DrawItem
- AFXWIN/CButton::GetBitmap
- AFXWIN/CButton::GetButtonStyle
- AFXWIN/CButton::GetCheck
- AFXWIN/CButton::GetCursor
- AFXWIN/CButton::GetIcon
- AFXWIN/CButton::GetIdealSize
- AFXWIN/CButton::GetImageList
- AFXWIN/CButton::GetNote
- AFXWIN/CButton::GetNoteLength
- AFXWIN/CButton::GetSplitGlyph
- AFXWIN/CButton::GetSplitImageList
- AFXWIN/CButton::GetSplitInfo
- AFXWIN/CButton::GetSplitSize
- AFXWIN/CButton::GetSplitStyle
- AFXWIN/CButton::GetState
- AFXWIN/CButton::GetTextMargin
- AFXWIN/CButton::SetBitmap
- AFXWIN/CButton::SetButtonStyle
- AFXWIN/CButton::SetCheck
- AFXWIN/CButton::SetCursor
- AFXWIN/CButton::SetDropDownState
- AFXWIN/CButton::SetIcon
- AFXWIN/CButton::SetImageList
- AFXWIN/CButton::SetNote
- AFXWIN/CButton::SetSplitGlyph
- AFXWIN/CButton::SetSplitImageList
- AFXWIN/CButton::SetSplitInfo
- AFXWIN/CButton::SetSplitSize
- AFXWIN/CButton::SetSplitStyle
- AFXWIN/CButton::SetState
- AFXWIN/CButton::SetTextMargin
helpviewer_keywords:
- CButton [MFC], CButton
- CButton [MFC], Create
- CButton [MFC], DrawItem
- CButton [MFC], GetBitmap
- CButton [MFC], GetButtonStyle
- CButton [MFC], GetCheck
- CButton [MFC], GetCursor
- CButton [MFC], GetIcon
- CButton [MFC], GetIdealSize
- CButton [MFC], GetImageList
- CButton [MFC], GetNote
- CButton [MFC], GetNoteLength
- CButton [MFC], GetSplitGlyph
- CButton [MFC], GetSplitImageList
- CButton [MFC], GetSplitInfo
- CButton [MFC], GetSplitSize
- CButton [MFC], GetSplitStyle
- CButton [MFC], GetState
- CButton [MFC], GetTextMargin
- CButton [MFC], SetBitmap
- CButton [MFC], SetButtonStyle
- CButton [MFC], SetCheck
- CButton [MFC], SetCursor
- CButton [MFC], SetDropDownState
- CButton [MFC], SetIcon
- CButton [MFC], SetImageList
- CButton [MFC], SetNote
- CButton [MFC], SetSplitGlyph
- CButton [MFC], SetSplitImageList
- CButton [MFC], SetSplitInfo
- CButton [MFC], SetSplitSize
- CButton [MFC], SetSplitStyle
- CButton [MFC], SetState
- CButton [MFC], SetTextMargin
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
ms.openlocfilehash: 26dcf50cc3dc48fec5d6e4957ffd1ef340ad1dbf
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178642"
---
# <a name="cbutton-class"></a>CButton-Klasse

Stellt die Funktionalität von Windows-Schaltflächensteuerelementen bereit.

## <a name="syntax"></a>Syntax

```
class CButton : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CButton::CButton](#cbutton)|Erstellt ein `CButton`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CButton::Create](#create)|Erstellt das Schaltflächen-Steuerelement von Windows und fügt es der `CButton` Objekt.|
|[CButton::DrawItem](#drawitem)|Außer Kraft setzen, um ein Ownerdrawn-zeichnen `CButton` Objekt.|
|[CButton::GetBitmap](#getbitmap)|Ruft das Handle der Bitmap für die zuvor festgelegten mit [SetBitmap](#setbitmap).|
|[CButton::GetButtonStyle](#getbuttonstyle)|Ruft Informationen zu den Schaltflächenstil für das Steuerelement ab.|
|[CButton::GetCheck](#getcheck)|Ruft den Aktivierungszustand eines Schaltflächen-Steuerelements ab.|
|[CButton::GetCursor](#getcursor)|Ruft das Handle des Cursors Image zuvor festgelegt wird, mit [SetCursor](#setcursor).|
|[CButton::GetIcon](#geticon)|Ruft das Handle des Symbols, das zuvor mit festgelegten [SetIcon](#seticon).|
|[CButton::GetIdealSize](#getidealsize)|Ruft die ideale Größe der Schaltflächen-Steuerelement ab.|
|[CButton::GetImageList](#getimagelist)|Ruft die Bildliste des Button-Steuerelements ab.|
|[CButton::GetNote](#getnote)|Ruft die Hinweis-Komponente des aktuellen Befehls Link-Steuerelements ab.|
|[CButton::GetNoteLength](#getnotelength)|Ruft die Länge des Texts Hinweis für den aktuellen Befehl Link-Steuerelement ab.|
|[CButton::GetSplitGlyph](#getsplitglyph)|Ruft ab, das das aktuelle SplitButton-Steuerelement zugeordnete Symbol.|
|[CButton::GetSplitImageList](#getsplitimagelist)|Ruft die Bildliste für das aktuelle SplitButton-Steuerelement ab.|
|[CButton::GetSplitInfo](#getsplitinfo)|Ruft die Informationen, die das aktuelle SplitButton-Steuerelement zu definieren.|
|[CButton::GetSplitSize](#getsplitsize)|Ruft das umschließende Rechteck der Dropdown-Komponente des die aktuelle SplitButton-Steuerelement ab.|
|[CButton::GetSplitStyle](#getsplitstyle)|Ruft ab, der Split-Button-Stile, die das aktuelle SplitButton-Steuerelement zu definieren.|
|[CButton::GetState](#getstate)|Ruft ab, der Aktivierungszustand Hervorhebung Zustand und Fokuszustands eines Schaltflächen-Steuerelements.|
|[CButton::GetTextMargin](#gettextmargin)|Ruft den Textrand des Button-Steuerelements ab.|
|[CButton:: SetBitmap](#setbitmap)|Gibt an, eine Bitmap, die auf die Schaltfläche angezeigt werden.|
|[CButton::SetButtonStyle](#setbuttonstyle)|Ändert den Stil einer Schaltfläche an.|
|[CButton::SetCheck](#setcheck)|Legt den Aktivierungszustand eines Schaltflächen-Steuerelements fest.|
|[CButton::SetCursor](#setcursor)|Gibt ein Cursorbild auf die Schaltfläche angezeigt werden.|
|[CButton::SetDropDownState](#setdropdownstate)|Legt den Dropdown-Zustand der aktuellen SplitButton-Steuerelement fest.|
|[CButton::SetIcon](#seticon)|Gibt ein Symbol auf die Schaltfläche angezeigt werden.|
|[CButton::SetImageList](#setimagelist)|Legt die Liste der Bilder des Button-Steuerelements fest.|
|[CButton::SetNote](#setnote)|Legt den Hinweis für den aktuellen Befehl Link-Steuerelement fest.|
|[CButton::SetSplitGlyph](#setsplitglyph)|Ordnet einer angegebenen Symbols das aktuelle SplitButton-Steuerelement.|
|[CButton::SetSplitImageList](#setsplitimagelist)|Ordnet eine Bildliste an das aktuelle SplitButton-Steuerelement.|
|[CButton::SetSplitInfo](#setsplitinfo)|Gibt die Informationen, die das aktuelle SplitButton-Steuerelement zu definieren.|
|[CButton::SetSplitSize](#setsplitsize)|Legt das umschließende Rechteck der Dropdown-Komponente des die aktuelle SplitButton-Steuerelement fest.|
|[CButton::SetSplitStyle](#setsplitstyle)|Legt fest, der die Darstellung der aktuellen SplitButton-Steuerelement.|
|[CButton::SetState](#setstate)|Legt die Treffermarkierung Zustand ein Schaltflächen-Steuerelement fest.|
|[CButton::SetTextMargin](#settextmargin)|Legt den Textrand des Button-Steuerelements fest.|

## <a name="remarks"></a>Hinweise

Ein Schaltflächen-Steuerelement ist ein kleines, rechteckiges untergeordnete Fenster, das ein- und ausschalten geklickt werden kann. Schaltflächen können allein oder in Gruppen verwendet werden, können entweder mit der Bezeichnung und ohne Text angezeigt werden. Eine Schaltfläche ändert sich normalerweise aussehen, wenn der Benutzer darauf klickt.

Typische Schaltflächen sind die Kontrollkästchen, Optionsfeld und Pushbutton. Ein `CButton` Objekt kann eines dieser, werden gemäß der [Schaltfläche Stil](../../mfc/reference/styles-used-by-mfc.md#button-styles) angegebenen seiner Initialisierung durch die [erstellen](#create) Member-Funktion.

Darüber hinaus die [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) abgeleitete Klasse `CButton` unterstützt die Erstellung von Schaltflächen-Steuerelemente, die mit Bitmapbildern statt Text beschriftet. Ein `CBitmapButton` haben können separate Bitmaps, eine Schaltfläche des einrichten, konzentriert und deaktivierten Zustand.

Sie können ein Schaltflächen-Steuerelement aus einer Dialogfeldvorlage oder direkt in Ihrem Code erstellen. In beiden Fällen rufen Sie zunächst den Konstruktor `CButton` zum Erstellen der `CButton` Objekt, rufen Sie dann die `Create` Member-Funktion zum Erstellen der Windows Schaltflächen-Steuerelement, und fügen Sie ihn auf die `CButton` Objekt.

Erstellung kann ein langwieriger Vorgang in einer Klasse abgeleitet sein `CButton`. Schreiben Sie einen Konstruktor für die abgeleitete Klasse und rufen `Create` von innerhalb des Konstruktors.

Wenn Sie Windows gesendete benachrichtigungsmeldungen von einem Schaltflächen-Steuerelement an sein übergeordnetes Element behandeln möchten (in der Regel eine abgeleitete Klasse [CDialog](../../mfc/reference/cdialog-class.md)), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag "und"-Nachrichtenhandler-Memberfunktion hinzugefügt.

Jede Nachricht-Zuordnungseintrag weist folgende Form:

**ON\_**_Benachrichtigung_ **(** _Id_, _MemberFxn_ **)**

wo *Id* gibt die untergeordneten Fenster-ID des Steuerelements, das Senden der Benachrichtigung und *MemberFxn* ist der Name der übergeordneten Member-Funktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.

Funktionsprototyp des übergeordneten Elements lautet wie folgt aus:

`afx_msg void memberFxn();`

Potenzielle Meldungszuordnungseinträge lauten wie folgt aus:

|Zuordnungseintrag|Wenn übergeordnete gesendet...|
|---------------|----------------------------|
|ON_BN_CLICKED|Der Benutzer auf eine Schaltfläche klickt.|
|ON_BN_DOUBLECLICKED|Der Benutzer doppelklickt eine Schaltfläche.|

Bei der Erstellung einer `CButton` Objekt aus einer Ressource, die `CButton` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.

Bei der Erstellung einer `CButton` Objekt innerhalb eines Zeitfensters, müssen Sie möglicherweise zerstören. Bei der Erstellung der `CButton` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** Schaltflächen-Steuerelement auf das Objekt, das es zerstört, wenn der Benutzer die Windows schließt. Bei der Erstellung der `CButton` -Objekt im Stapel oder im übergeordneten Dialogfeldobjekt eingebettet ist, wird es automatisch zerstört.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CButton`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cbutton"></a>  CButton::CButton

Erstellt ein `CButton`-Objekt.

```
CButton();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]

##  <a name="create"></a>  CButton::Create

Erstellt das Schaltflächen-Steuerelement von Windows und fügt es der `CButton` Objekt.

```
virtual BOOL Create(
    LPCTSTR lpszCaption,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*lpszCaption*<br/>
Gibt Text an das Schaltflächen-Steuerelement.

*dwStyle*<br/>
Gibt das Schaltflächen-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Schaltfläche Stile](../../mfc/reference/styles-used-by-mfc.md#button-styles) auf die Schaltfläche.

*Rect*<br/>
Gibt an, des Schaltflächen-Steuerelements die Größe und Position. Es kann sein, entweder eine `CRect` Objekt oder ein `RECT` Struktur.

*pParentWnd*<br/>
Gibt an, das Schaltflächen-Steuerelement übergeordnete Fenster, in der Regel eine `CDialog`. Es darf nicht NULL sein.

*nID*<br/>
Gibt das Schaltflächen-Steuerelement-ID an.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CButton` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen dann `Create`, die das Schaltflächen-Steuerelement von Windows erstellt, und fügt es der `CButton` Objekt.

Wenn das WS_VISIBLE-Format angegeben ist, sendet Windows dem Schaltflächen-Steuerelement alle Nachrichten, die für die Aktivierung und die Schaltfläche "anzeigen".

Übernehmen Sie das folgende [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) auf einem Schaltflächen-Steuerelement:

- WS_CHILD immer

- WS_VISIBLE in der Regel

- WS_DISABLED selten

- WS_GROUP zum Gruppieren von Steuerelementen

- WS_TABSTOP, schließen die Schaltfläche mit den in die Tab-Reihenfolge

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]

##  <a name="drawitem"></a>  CButton::DrawItem

Wird von Framework aufgerufen, wenn sich ein Darstellungsaspekt eine Ownerdrawn Schaltfläche geändert hat.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein long-Zeiger auf eine [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) Struktur. Die Struktur enthält Informationen über das Element, das gezeichnet werden und den Typ der Zeichnung, die erforderlich sind.

### <a name="remarks"></a>Hinweise

Eine Ownerdrawn Schaltfläche verfügt über die festgelegten BS_OWNERDRAW-Format. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CButton` Objekt. Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext in angegeben wiederherstellen *LpDrawItemStruct* vor dem Element Funktion beendet wird.

Siehe auch die [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) Werte formatieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]

##  <a name="getbitmap"></a>  CButton::GetBitmap

Rufen Sie diese Memberfunktion rufen Sie das Handle einer Bitmap, die zuvor festgelegten mit [SetBitmap](#setbitmap), d. h. mit einer Schaltfläche verknüpft ist.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für eine Bitmap. NULL, wenn zuvor keine Bitmap angegeben wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

##  <a name="getbuttonstyle"></a>  CButton::GetButtonStyle

Ruft Informationen zu den Schaltflächenstil für das Steuerelement ab.

```
UINT GetButtonStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt das Button-Stile für dieses `CButton` Objekt. Diese Funktion gibt nur die [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) Style-Werte, keine der anderen Fenster.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

##  <a name="getcheck"></a>  CButton::GetCheck

Ruft den Aktivierungszustand des ein Optionsfeld oder ein Kontrollkästchen ab.

```
int GetCheck() const;
```

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert ein Schaltflächen-Steuerelement erstellt, mit dem BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON oder BS_3STATE-Format ist eines der folgenden Werte:

|Wert|Bedeutung|
|-----------|-------------|
|BST_UNCHECKED|Status der Schaltfläche ist deaktiviert.|
|BST_CHECKED|Status wird überprüft.|
|BST_INDETERMINATE|Status unbestimmt ist (gilt nur, wenn die Schaltfläche den BS_3STATE oder BS_AUTO3STATE-Stil).|

Wenn die Schaltfläche mit der alle anderen Stil geschrieben ist, ist der Rückgabewert BST_UNCHECKED an.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

##  <a name="getcursor"></a>  CButton::GetCursor

Rufen Sie diese Memberfunktion rufen Sie das Handle eines Cursors, der zuvor festgelegten mit [SetCursor](#setcursor), d. h. mit einer Schaltfläche verknüpft ist.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für ein Cursor-Image. NULL, wenn zuvor kein Cursor angegeben wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

##  <a name="geticon"></a>  CButton::GetIcon

Rufen Sie diese Memberfunktion rufen Sie das Handle eines Symbols, die zuvor festgelegten mit [SetIcon](#seticon), d. h. mit einer Schaltfläche verknüpft ist.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für ein Symbol. NULL, wenn zuvor kein Symbol angegeben wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

##  <a name="getidealsize"></a>  CButton::GetIdealSize

Ruft die optimale Größe für das Schaltflächen-Steuerelement ab.

```
BOOL GetIdealSize(SIZE* psize);
```

### <a name="parameters"></a>Parameter

*psize*<br/>
Ein Zeiger auf die aktuelle Größe der Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen der Nachricht BCM_GETIDEALSIZE aus, unter dem [Schaltflächen](/windows/desktop/controls/buttons) Abschnitt des Windows SDK.

##  <a name="getimagelist"></a>  CButton::GetImageList

Rufen Sie diese Methode, um die Liste der Bilder aus dem Schaltflächen-Steuerelement zu erhalten.

```
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Parameter

*pbuttonImagelist*<br/>
Ein Zeiger auf die Bildliste des der `CButton` Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen der Nachricht BCM_GETIMAGELIST aus, unter dem [Schaltflächen](/windows/desktop/controls/buttons) Abschnitt des Windows SDK.

##  <a name="getnote"></a>  CButton::GetNote

Ruft den dem aktuellen Befehl Link-Steuerelement zugeordnete Notiztext ab.

```
CString GetNote() const;

BOOL GetNote(
    LPTSTR lpszNote,
    UINT* cchNote) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*lpszNote*|[out] Zeiger auf einen Puffer, die der Aufrufer für das zuordnen und Freigeben von zuständig ist. Wenn der zurückgegebene Wert TRUE ist, enthält der Puffer die Hinweis-Text, der den aktuellen Befehl Link-Steuerelement zugeordnet ist; Andernfalls ist der Puffer nicht geändert.|
|*cchNote*|[in, out] Ein Zeiger auf die Variable eine ganze Zahl ohne Vorzeichen.<br /><br /> Wenn diese Methode aufgerufen wird, wird die Variable enthält die Größe des Puffers gemäß der *LpszNote* Parameter.<br /><br /> Wenn diese Methode beendet wird, ist der zurückgegebene Wert "true" die Variable enthält die Größe des Hinweises mit den aktuellen Befehl Link-Steuerelement verknüpft ist. Wenn der Rückgabewert FALSE ist, enthält die Variable die Größe des Puffers erforderlich, um den Hinweis enthalten.|

### <a name="return-value"></a>Rückgabewert

In der ersten Überladung ist eine [CString](../../atl-mfc-shared/using-cstring.md) -Objekt, den dem aktuellen Befehl Link-Steuerelement zugeordneten Notiztext enthält.

- oder - 

In der zweiten Überladung ist "true", wenn diese Methode erfolgreich ist; andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_COMMANDLINK oder BS_DEFCOMMANDLINK ist.

Diese Methode sendet die [BCM_GETNOTE](/windows/desktop/Controls/bcm-getnote) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getnotelength"></a>  CButton::GetNoteLength

Ruft die Länge des Texts Hinweis für den aktuellen Befehl Link-Steuerelement ab.

```
UINT GetNoteLength() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge des Texts Hinweis in 16-Bit-Unicode-Zeichen, für das aktuelle Befehl Link-Steuerelement.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_COMMANDLINK oder BS_DEFCOMMANDLINK ist.

Diese Methode sendet die [BCM_GETNOTELENGTH](/windows/desktop/Controls/bcm-getnotelength) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getsplitglyph"></a>  CButton::GetSplitGlyph

Ruft ab, das das aktuelle SplitButton-Steuerelement zugeordnete Symbol.

```
TCHAR GetSplitGlyph() const;
```

### <a name="return-value"></a>Rückgabewert

Das Symbol-Zeichen, das das aktuelle SplitButton-Steuerelement zugeordnet ist.

### <a name="remarks"></a>Hinweise

Ein Symbol ist die physikalische Darstellung eines Zeichens in einer bestimmten Schriftart an. Z. B. ein Trennschaltflächen-Steuerelement mit das Symbol des Unicode-Zeichens Häkchen versehen werden kann (U + 2713).

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_SPLITBUTTON oder BS_DEFSPLITBUTTON ist.

Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur mit dem BCSIF_GLYPH-Flag, und klicken Sie dann gesendet, die in der Struktur der [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Nachricht, das beschrieben ist die Windows SDK. Wenn die Nachricht-Funktion zurückgibt, wird diese Methode ruft das Symbol aus der `himlGlyph` Member der Struktur.

##  <a name="getsplitimagelist"></a>  CButton::GetSplitImageList

Ruft die [Bildliste](../../mfc/reference/cimagelist-class.md) für das aktuelle SplitButton-Steuerelement.

```
CImageList* GetSplitImageList() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_SPLITBUTTON oder BS_DEFSPLITBUTTON ist.

Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur mit dem BCSIF_IMAGE-Flag, und klicken Sie dann gesendet, die in der Struktur der [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Nachricht, das beschrieben ist die Windows SDK. Wenn die Nachricht-Funktion zurückgibt, diese Methode ruft die Liste der Bilder aus ab der `himlGlyph` Member der Struktur.

##  <a name="getsplitinfo"></a>  CButton::GetSplitInfo

Ruft ab die Parameter, die bestimmen, wie das aktuelle SplitButton-Steuerelement von Windows zieht.

```
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*"pInfo"*|[out] Zeiger auf eine [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) -Struktur, die Informationen über das aktuelle SplitButton-Steuerelement empfängt. Der Aufrufer ist verantwortlich für die Zuordnung von der Struktur.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_SPLITBUTTON oder BS_DEFSPLITBUTTON ist.

Diese Methode sendet die [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getsplitsize"></a>  CButton::GetSplitSize

Ruft das umschließende Rechteck der Dropdown-Komponente des die aktuelle SplitButton-Steuerelement ab.

```
BOOL GetSplitSize(LPSIZE pSize) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pSize*|[out] Zeiger auf eine [Größe](/windows/desktop/api/windef/ns-windef-tagsize) -Struktur, die Beschreibung eines Rechtecks empfängt.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_SPLITBUTTON oder BS_DEFSPLITBUTTON ist.

Wenn das SplitButton-Steuerelement erweitert ist, können sie eine Dropdown-Komponente, z. B. ein Listensteuerelement oder Pager-Steuerelement anzeigen. Diese Methode ruft das umschließende Rechteck, das Dropdown-Komponente enthält.

Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur mit dem BCSIF_SIZE-Flag, und klicken Sie dann gesendet, die in der Struktur der [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Nachricht, das beschrieben ist die Windows SDK. Wenn die Nachricht-Funktion zurückgibt, ruft diese Methode das umschließende Rechteck von der `size` Member der Struktur.

##  <a name="getsplitstyle"></a>  CButton::GetSplitStyle

Ruft ab, der Split-Button-Stile, die das aktuelle SplitButton-Steuerelement zu definieren.

```
UINT GetSplitStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Eine bitweise Kombination der Split-Button-Stile. Weitere Informationen finden Sie unter den `uSplitStyle` Mitglied der [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_SPLITBUTTON oder BS_DEFSPLITBUTTON ist.

Der Split-Button-Stile Geben Sie die Ausrichtung, Seitenverhältnis und grafischen Format mit dem Windows ein Split-Schaltflächensymbol zeichnet.

Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur mit dem BCSIF_STYLE-Flag, und klicken Sie dann gesendet, die in der Struktur der [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Nachricht, das beschrieben ist die Windows SDK. Wenn die Nachricht-Funktion zurückgibt, wird diese Methode ruft die Split-Button-Stile in die `uSplitStyle` Member der Struktur.

##  <a name="getstate"></a>  CButton::GetState

Ruft den Zustand eines Schaltflächen-Steuerelements ab.

```
UINT GetState() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Bitfeld, die die Kombination der Werte enthält, die den aktuellen Status eines Schaltflächen-Steuerelements angeben. In der folgende Tabelle sind die möglichen Werte aufgeführt.

|Status|Wert|Beschreibung|
|------------------|-----------|-----------------|
|BST_UNCHECKED|0x0000|Der ursprüngliche Status.|
|BST_CHECKED|0x0001|Das Schaltflächen-Steuerelement aktiviert ist.|
|BST_INDETERMINATE|0x0002|Der Zustand ist unbestimmt (nur möglich, wenn das Schaltflächen-Steuerelement drei Zustände hat).|
|BST_PUSHED|0x0004|Das Schaltflächen-Steuerelement wird gedrückt.|
|BST_FOCUS|0x0008|Das Schaltflächen-Steuerelement besitzt den Fokus.|

### <a name="remarks"></a>Hinweise

Ein Schaltflächen-Steuerelement mit den Schaltflächenstil BS_3STATE oder BS_AUTO3STATE erstellt ein Kontrollkästchen mit dem dritten Zustand mit dem Namen unbestimmten Zustand. Unbestimmte Zustand gibt an, dass das Kontrollkästchen weder aktiviert noch deaktiviert ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

##  <a name="gettextmargin"></a>  CButton::GetTextMargin

Rufen Sie diese Methode zum Abrufen der Textrand der `CButton` Objekt.

```
BOOL GetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Parameter

*pmargin*<br/>
Ein Zeiger auf den Textrand die `CButton` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt den Rand des Texts zurück.

### <a name="remarks"></a>Hinweise

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen der Nachricht BCM_GETTEXTMARGIN aus, unter dem [Schaltflächen](/windows/desktop/controls/buttons) Abschnitt des Windows SDK.

##  <a name="setbitmap"></a>  CButton:: SetBitmap

Rufen Sie diese Memberfunktion, um eine neue Bitmap mit der Schaltfläche zu verknüpfen.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parameter

*hBitmap*<br/>
Das Handle einer Bitmap.

### <a name="return-value"></a>Rückgabewert

Das Handle einer Bitmap, die die Schaltfläche mit den zuvor zugeordnet waren.

### <a name="remarks"></a>Hinweise

Die Bitmap wird auf der Schaltfläche, die zentriert wird standardmäßig automatisch gespeichert. Wenn die Bitmap für die Schaltfläche zu groß ist, wird es auf einer Seite abgeschnitten. Sie können die anderen Optionen für textausrichtung, einschließlich der folgenden:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Im Gegensatz zu [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), die vier Bitmaps pro Schaltfläche verwendet `SetBitmap` wird nur ein Bitmap pro der Schaltfläche verwendet. Wenn die Schaltfläche gedrückt wird, wird die Bitmap angezeigt, nach unten und nach rechts verschoben.

Sie sind verantwortlich für das Freigeben der Bitmaps, wenn Sie damit fertig sind.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

##  <a name="setbuttonstyle"></a>  CButton::SetButtonStyle

Ändert den Stil einer Schaltfläche an.

```
void SetButtonStyle(
    UINT nStyle,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parameter

*nStyle*<br/>
Gibt an, die [Schaltfläche Stil](../../mfc/reference/styles-used-by-mfc.md#button-styles).

*bRedraw*<br/>
Gibt an, ob die Schaltfläche neu gezeichnet wird. Ein Wert ungleich NULL zeichnet die Schaltfläche. Dem Wert 0 wird nicht die Schaltfläche neu gezeichnet. Die Schaltfläche wird standardmäßig neu gezeichnet.

### <a name="remarks"></a>Hinweise

Verwenden der `GetButtonStyle` Member-Funktion, um den Schaltflächenstil abzurufen. Das niederwertige Wort für den Stil der Schaltfläche "abschließen" ist die Schaltfläche Format.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

##  <a name="setcheck"></a>  CButton::SetCheck

Legt fest oder setzt den Status überprüfen ein Kontrollkästchen oder ein Optionsfeld zurück.

```
void SetCheck(int nCheck);
```

### <a name="parameters"></a>Parameter

*nPrüfen*<br/>
Gibt den Aktivierungszustand an. Dieser Parameter kann einen der folgenden sein:

|Wert|Bedeutung|
|-----------|-------------|
|BST_UNCHECKED|Zustand der Schaltfläche auf deaktiviert festgelegt.|
|BST_CHECKED|Legen Sie den Zustand der Schaltfläche überprüft.|
|BST_INDETERMINATE|Legen Sie den Zustand der Schaltfläche, einem unbestimmten Zustand. Dieser Wert kann verwendet werden, nur, wenn die Schaltfläche den BS_3STATE oder BS_AUTO3STATE-Stil.|

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wirkt sich nicht auf eine Schaltfläche aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

##  <a name="setcursor"></a>  CButton::SetCursor

Rufen Sie diese Memberfunktion, um einen neuen Cursor mit der Schaltfläche zu verknüpfen.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Parameter

*hCursor*<br/>
Das Handle eines Cursors.

### <a name="return-value"></a>Rückgabewert

Das Handle eines Cursors, auf die Schaltfläche mit den zuvor zugeordnet waren.

### <a name="remarks"></a>Hinweise

Der Cursor wird automatisch auf der Schaltfläche, die standardmäßig zentriert platziert werden. Wenn der Cursor zu groß für die Schaltfläche befindet, wird es auf einer Seite abgeschnitten. Sie können die anderen Optionen für textausrichtung, einschließlich der folgenden:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Im Gegensatz zu [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), die vier Bitmaps pro Schaltfläche verwendet `SetCursor` wird nur ein Cursor pro der Schaltfläche verwendet. Wenn die Schaltfläche gedrückt wird, wird der Cursor nach unten und nach rechts verschoben angezeigt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

##  <a name="setdropdownstate"></a>  CButton::SetDropDownState

Legt den Dropdown-Zustand der aktuellen SplitButton-Steuerelement fest.

```
BOOL SetDropDownState(BOOL fDropDown);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*fDropDown*|[in] True, um BST_DROPDOWNPUSHED Status festgelegt. andernfalls "false".|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Ein Trennschaltflächen-Steuerelement verfügt über einen Stil BS_SPLITBUTTON oder BS_DEFSPLITBUTTON und besteht aus einer Schaltfläche und ein Dropdown-Pfeil rechts davon. Weitere Informationen finden Sie unter [Button-Stile](/windows/desktop/Controls/button-styles). In der Regel wird der Status für die Dropdown-festgelegt, wenn der Benutzer auf den Dropdown-Pfeil klickt. Verwenden Sie diese Methode zum programmgesteuerten Festlegen der Dropdown-Zustands des Steuerelements. Die Dropdown-Pfeil gezeichnet wird schattiert, um den Status anzugeben.

Diese Methode sendet die [BCM_SETDROPDOWNSTATE](/windows/desktop/Controls/bcm-setdropdownstate) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable *M_splitButton*, d. h. verwendet, um das SplitButton-Steuerelement programmgesteuert zugreifen. Diese Variable wird im folgenden Beispiel verwendet.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel legt fest, den Zustand des das SplitButton-Steuerelement, um anzugeben, dass der Dropdown-Pfeil mithilfe von Push übertragen wird.

[!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]

##  <a name="setelevationrequired"></a>  CButton::SetElevationRequired

Legt den Zustand des aktuellen Button-Steuerelements, `elevation required`, der für das Steuerelement zum Anzeigen eines Symbols für die erhöhte Sicherheit erforderlich ist.

```
BOOL SetElevationRequired(BOOL fElevationRequired);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*fElevationRequired*|[in] "True" Set `elevation required` Status; andernfalls "false".|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn eine Schaltfläche oder Link-Steuerelement mit erhöhter Sicherheitsberechtigung zum Ausführen einer Aktion erforderlich ist, legen Sie das Steuerelement auf `elevation required` Zustand. Anschließend zeigt Windows das Shield-Symbol (User Account Control, UAC) auf dem Steuerelement. Weitere Informationen finden Sie unter "User Account Control" [MSDN](http://go.microsoft.com/fwlink/p/?linkid=18507).

Diese Methode sendet die [BCM_SETSHIELD](/windows/desktop/Controls/bcm-setshield) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="seticon"></a>  CButton::SetIcon

Rufen Sie diese Memberfunktion, um ein neues Symbol mit der Schaltfläche zu verknüpfen.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Parameter

*hIcon*<br/>
Das Handle eines Symbols.

### <a name="return-value"></a>Rückgabewert

Das Handle eines Symbols, auf die Schaltfläche mit den zuvor zugeordnet waren.

### <a name="remarks"></a>Hinweise

Das Symbol wird automatisch auf der Schaltfläche, die standardmäßig zentriert platziert werden. Wenn das Symbol für die Schaltfläche zu groß ist, wird es auf einer Seite abgeschnitten. Sie können die anderen Optionen für textausrichtung, einschließlich der folgenden:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Im Gegensatz zu [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), die vier Bitmaps pro Schaltfläche verwendet `SetIcon` verwendet nur ein Symbol pro die Schaltfläche. Wenn die Schaltfläche gedrückt wird, erscheint ein Symbol nach unten und nach rechts verschoben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

##  <a name="setimagelist"></a>  CButton::SetImageList

Rufen Sie diese Methode zum Festlegen der Bildliste der der `CButton` Objekt.

```
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Parameter

*pbuttonImagelist*<br/>
Ein Zeiger auf die neue Bildliste.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen der Nachricht BCM_SETIMAGELIST aus, unter dem [Schaltflächen](/windows/desktop/controls/buttons) Abschnitt des Windows SDK.

##  <a name="setnote"></a>  CButton::SetNote

Legt den Text der Hinweis für den aktuellen Befehl Link-Steuerelement.

```
BOOL SetNote(LPCTSTR lpszNote);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*lpszNote*|[in] Zeiger auf eine Unicode-Zeichenfolge, die als Hinweis Text für die befehlslinksteuerelement festgelegt ist.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_COMMANDLINK oder BS_DEFCOMMANDLINK ist.

Diese Methode sendet die [BCM_SETNOTE](/windows/desktop/Controls/bcm-setnote) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable *M_cmdLink*, d. h. verwendet, um die befehlslinksteuerelement programmgesteuert zugreifen. Diese Variable wird im folgenden Beispiel verwendet.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel legt fest, die Hinweis-Text für das Befehl-Link-Steuerelement.

[!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]

##  <a name="setsplitglyph"></a>  CButton::SetSplitGlyph

Ordnet einer angegebenen Symbols das aktuelle SplitButton-Steuerelement.

```
BOOL SetSplitGlyph(TCHAR chGlyph);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*chGlyph*|[in] Ein Zeichen, die das Symbol für die Verwendung als Dropdownpfeil für das Split-Schaltfläche angibt.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, die die Schaltflächen-Formatvorlage BS_SPLITBUTTON oder BS_DEFSPLITBUTTON haben.

Ein Symbol ist die physikalische Darstellung eines Zeichens in einer bestimmten Schriftart an. Die *ChGlyph* Parameter wird nicht als die Glyphe verwendet, jedoch wird eine Reihe von systemdefinierte Symbolen ein Symbol aus. Das standardmäßige Dropdown-Pfeil-Symbol wird angegeben, durch das Zeichen '6' und das Unicode-Zeichen Schwarz nach unten ZEIGENDEN DREIECK (U + 25BC) ähnelt.

Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur mit dem Kennzeichen BCSIF_GLYPH und die `himlGlyph` Member mit der *ChGlyph* -Parameter und sendet dann diese Struktur, die der [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Nachricht, die im Windows SDK beschrieben wird.

##  <a name="setsplitimagelist"></a>  CButton::SetSplitImageList

Ordnet eine [Bildliste](../../mfc/reference/cimagelist-class.md) mit der aktuellen SplitButton-Steuerelement.

```
BOOL SetSplitImageList(CImageList* pSplitImageList);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pSplitImageList*|[in] Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt, das das aktuelle SplitButton-Steuerelement zugewiesen.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_SPLITBUTTON oder BS_DEFSPLITBUTTON ist.

Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur mit dem Kennzeichen BCSIF_IMAGE und `himlGlyph` Member mit der *pSplitImageList* -Parameter, und anschließendes senden Diese Struktur in der [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Nachricht, die im Windows SDK beschrieben wird.

##  <a name="setsplitinfo"></a>  CButton::SetSplitInfo

Gibt Parameter an, die bestimmen, wie das aktuelle SplitButton-Steuerelement von Windows zieht.

```
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*"pInfo"*|[in] Zeiger auf eine [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur, die das aktuelle SplitButton-Steuerelement definiert.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_SPLITBUTTON oder BS_DEFSPLITBUTTON ist.

Diese Methode sendet die [BCM_SETSPLITINFO](/windows/desktop/Controls/bcm-setsplitinfo) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um das SplitButton-Steuerelement programmgesteuert zugreifen.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel ändert sich das Symbol, das für den Split-Schaltfläche Dropdown-Pfeil verwendet wird. Im Beispiel ersetzt ein oben zeigenden Dreieck ein Symbol für das standardmäßige nach unten zeigenden Dreieck-Symbol. Das Symbol, das angezeigt wird, hängt das Zeichen, das Sie, in angeben der `himlGlyph` Mitglied der `BUTTON_SPLITINFO` Struktur. Das nach unten zeigenden Dreieck-Symbol wird angegeben, durch das Zeichen ' 6 'und das oben zeigenden Dreieck-Symbol wird angegeben, durch das Zeichen ' 5'. Vergleich finden Sie in der Hilfsmethode [CButton::SetSplitGlyph](#setsplitglyph).

[!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]

##  <a name="setsplitsize"></a>  CButton::SetSplitSize

Legt das umschließende Rechteck der Dropdown-Komponente des die aktuelle SplitButton-Steuerelement fest.

```
BOOL SetSplitSize(LPSIZE pSize);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pSize*|[in] Zeiger auf eine [Größe](/windows/desktop/api/windef/ns-windef-tagsize) Struktur, die ein umschließendes Rechteck beschreibt.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_SPLITBUTTON oder BS_DEFSPLITBUTTON ist.

Wenn das SplitButton-Steuerelement erweitert ist, können sie eine Dropdown-Komponente, z. B. ein Listensteuerelement oder Pager-Steuerelement anzeigen. Diese Methode gibt die Größe des umschließenden Rechtecks, das Dropdown-Komponente enthält.

Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur mit dem Kennzeichen BCSIF_SIZE und `size` Member mit der *pSize* -Parameter, und anschließendes senden, die Struktur in der [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um das SplitButton-Steuerelement programmgesteuert zugreifen. Diese Variable wird im folgenden Beispiel verwendet.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Größe der Dropdownpfeil für das Split-Schaltfläche verdoppelt.

[!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]

##  <a name="setsplitstyle"></a>  CButton::SetSplitStyle

Legt fest, der die Darstellung der aktuellen SplitButton-Steuerelement.

```
BOOL SetSplitStyle(UINT uSplitStyle);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*uSplitStyle*|[in] Eine bitweise Kombination der Split-Button-Stile. Weitere Informationen finden Sie unter den `uSplitStyle` Mitglied der [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur mit Steuerelementen, deren Schaltflächen-Formatvorlage BS_SPLITBUTTON oder BS_DEFSPLITBUTTON ist.

Der Split-Button-Stile Geben Sie die Ausrichtung, Seitenverhältnis und grafischen Format mit dem Windows ein Split-Schaltflächensymbol zeichnet. Weitere Informationen finden Sie unter den `uSplitStyle` Mitglied der [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur.

Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) Struktur mit dem Kennzeichen BCSIF_STYLE und die `uSplitStyle` Member mit der *uSplitStyle* -Parameter und sendet dann diese Struktur, die der [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um das SplitButton-Steuerelement programmgesteuert zugreifen.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel legt den Stil der Dropdownpfeil für das Split-Schaltfläche fest. Styl BCSS_ALIGNLEFT zeigt den Pfeil auf der linken Seite der Schaltfläche und der Stil BCSS_STRETCH behält der Dropdown-Pfeil Proportionen beim Ändern der Größe der Schaltfläche.

[!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]

##  <a name="setstate"></a>  CButton::SetState

Legt fest, ob ein Schaltflächen-Steuerelement oder nicht hervorgehoben ist.

```
void SetState(BOOL bHighlight);
```

### <a name="parameters"></a>Parameter

*bHighlight*<br/>
Gibt an, ob die Schaltfläche mit der hervorgehoben werden. Ein Wert ungleich Null werden hervorgehoben, die Schaltfläche "; ein Wert 0 entfernt alle markieren.

### <a name="remarks"></a>Hinweise

Markieren, betrifft des äußeren Rings ein Schaltflächen-Steuerelement. Wirkt sich nicht auf den Aktivierungszustand des ein Optionsfeld oder Kontrollkästchen.

Ein Schaltflächen-Steuerelement wird automatisch hervorgehoben, wenn der Benutzer klickt auf und die linke Maustaste gedrückt enthält wird. Die Hervorhebung wird entfernt, wenn der Benutzer die Maustaste loslässt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

##  <a name="settextmargin"></a>  CButton::SetTextMargin

Rufen Sie diese Methode zum Festlegen der Textrand der `CButton` Objekt.

```
BOOL SetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Parameter

*pmargin*<br/>
Ein Zeiger auf den neuen Textrand.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen der Nachricht BCM_SETTEXTMARGIN aus, unter dem [Schaltflächen](/windows/desktop/controls/buttons) Abschnitt des Windows SDK.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit-Klasse](../../mfc/reference/cedit-class.md)<br/>
[CListBox-Klasse](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar-Klasse](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic-Klasse](../../mfc/reference/cstatic-class.md)<br/>
[CBitmapButton-Klasse](../../mfc/reference/cbitmapbutton-class.md)<br/>
[CDialog-Klasse](../../mfc/reference/cdialog-class.md)
