---
title: CComboBoxEx-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
ms.openlocfilehash: 7d46f175a62cda7f1ff08327830f1dffe2967727
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507181"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx-Klasse

Erweitert das Kombinationsfeld-Steuerelement durch die Unterstützung für Bildlisten.

## <a name="syntax"></a>Syntax

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|Erstellt ein `CComboBoxEx`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComboBoxEx::Create](#create)|Erstellt das Kombinations Feld und fügt es an das `CComboBoxEx` -Objekt an.|
|[CComboBoxEx::CreateEx](#createex)|Erstellt ein Kombinations Feld mit den angegebenen erweiterten Windows-Stilen und fügt es an `ComboBoxEx` ein-Objekt an.|
|[CComboBoxEx::DeleteItem](#deleteitem)|Entfernt ein Element aus einem `ComboBoxEx` -Steuerelement.|
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Ruft einen Zeiger auf das untergeordnete Kombinations Feld-Steuerelement ab.|
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Ruft das Handle für den Bearbeitungs Steuerelement Teil eines `ComboBoxEx` -Steuer Elements ab.|
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|Ruft die erweiterten Stile ab, die für ein `ComboBoxEx` -Steuerelement verwendet werden.|
|[CComboBoxEx::GetImageList](#getimagelist)|Ruft einen Zeiger auf die Bildliste ab, die einem `ComboBoxEx` -Steuerelement zugewiesen ist.|
|[CComboBoxEx::GetItem](#getitem)|Ruft Element Informationen für ein `ComboBoxEx` angegebenes Element ab.|
|[CComboBoxEx::HasEditChanged](#haseditchanged)|Bestimmt, ob der Benutzer den Inhalt des `ComboBoxEx` Bearbeitungs Steuer Elements durch Eingabe von geändert hat.|
|[CComboBoxEx::InsertItem](#insertitem)|Fügt ein neues Element in ein `ComboBoxEx` -Steuerelement ein.|
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|Legt erweiterte Stile innerhalb eines `ComboBoxEx` -Steuer Elements fest.|
|[CComboBoxEx::SetImageList](#setimagelist)|Legt eine Bildliste für ein `ComboBoxEx` Steuerelement fest.|
|[CComboBoxEx::SetItem](#setitem)|Legt die Attribute für ein Element in einem `ComboBoxEx` -Steuerelement fest.|
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Legt den visuellen Stil des erweiterten Kombinations Feld-Steuer Elements fest.|

## <a name="remarks"></a>Hinweise

Wenn Sie `CComboBoxEx` zum Erstellen von Kombinations Feld-Steuerelementen verwenden, ist es nicht mehr erforderlich, eigenen Bild Zeichnungs Code zu implementieren. Verwenden `CComboBoxEx` Sie stattdessen, um auf Bilder aus einer Bildliste zuzugreifen.

## <a name="image-list-support"></a>Unterstützung von Image Listen

In einem Standard Kombinations Feld ist der Besitzer des Kombinations Felds für das Zeichnen eines Bilds zuständig, indem das Kombinations Feld als Steuerelement für das Besitzer zeichnen erstellt wird. Wenn Sie verwenden `CComboBoxEx`, müssen Sie die Zeichnungs Stile CBS_OWNERDRAWFIXED und CBS_HASSTRINGS nicht festlegen, da Sie impliziert sind. Andernfalls müssen Sie Code schreiben, um Zeichnungsvorgänge auszuführen. Ein `CComboBoxEx` Steuerelement unterstützt bis zu drei Bilder pro Element: eine für einen ausgewählten Zustand, eine für einen nicht ausgewählten Zustand und eine für ein Überlagerungs Bild.

## <a name="styles"></a>Stile

`CComboBoxEx`unterstützt die Stile CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST und WS_CHILD. Alle anderen Stile, die beim Erstellen des Fensters übergebenen werden, werden vom-Steuerelement ignoriert. Nachdem das Fenster erstellt wurde, können Sie weitere Kombinations Feld Stile bereitstellen, indem `CComboBoxEx` Sie die Member-Funktion " [SetExtendedStyle](#setextendedstyle)" aufrufen. Mit diesen Stilen können Sie folgende Aktionen ausführen:

- Legen Sie Zeichen folgen suchen in der Liste auf Groß-/Kleinschreibung fest.

- Erstellen Sie ein Kombinations Feld-Steuerelement, das den Schrägstrich ("/"),\\den umgekehrten Schrägstrich ("") und den Zeitraum (".") als Wort Trennzeichen verwendet. Dadurch können Benutzer mit der Tastenkombination Strg + Pfeil von Word zu Word springen.

- Legen Sie das Kombinations Feld-Steuerelement so fest, dass ein Bild angezeigt oder nicht angezeigt wird. Wenn kein Bild angezeigt wird, kann das Kombinations Feld den Text Einzug entfernen, der ein Bild berücksichtigt.

- Erstellen Sie ein enges Kombinations Feld-Steuerelement, einschließlich der Größenanpassung, damit es das größere Kombinations Feld abschneidet, das es enthält.

Diese stilflags werden weiter unten in [mit CComboBoxEx](../../mfc/using-ccomboboxex.md)beschrieben.

## <a name="item-retention-and-callback-item-attributes"></a>Attribute für Element Beibehaltung und Rückruf Element

Element Informationen, wie z. b. Indizes für Elemente und Bilder, Einzugs Werte und Text Zeichenfolgen, werden in der Win32-Struktur [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)gespeichert, wie im Windows SDK beschrieben. Die Struktur enthält auch Member, die Rückruf Flags entsprechen.

Eine ausführliche, konzeptionelle Erörterung finden [Sie unter Verwenden von CComboBoxEx](../../mfc/using-ccomboboxex.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="ccomboboxex"></a>CComboBoxEx:: CComboBoxEx

Rufen Sie diese Element Funktion auf, `CComboBoxEx` um ein-Objekt zu erstellen.

```
CComboBoxEx();
```

##  <a name="create"></a>CComboBoxEx:: Create

Erstellt das Kombinations Feld und fügt es an das `CComboBoxEx` -Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt die Kombination der Kombinations Feld Stile an, die auf das Kombinations Feld angewendet werden. Weitere Informationen zu **Stilen finden Sie unten in** den hinweisen.

*Rect*<br/>
Ein Verweis auf ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt oder eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Position und die Größe des Kombinations Felds ist.

*pParentWnd*<br/>
Ein Zeiger auf ein [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Kombinations Felds (Normal `CDialog`erweise ein) ist. Er darf nicht NULL sein.

*nID*<br/>
Gibt die Steuerelement-ID des Kombinations Felds an.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Objekt erfolgreich erstellt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Erstellen Sie `CComboBoxEx` ein-Objekt in zwei Schritten:

1. Rufen Sie [CComboBoxEx](#ccomboboxex) auf, `CComboBoxEx` um ein-Objekt zu erstellen.

1. Diese Member-Funktion wird aufgerufen, wodurch das erweiterte Windows-Kombinations Feld erstellt und an `CComboBoxEx` das-Objekt angefügt wird.

Wenn Sie aufzurufen `Create`, initialisiert MFC die allgemeinen Steuerelemente.

Wenn Sie das Kombinations Feld erstellen, können Sie einen oder alle der folgenden Kombinations Feld Stile angeben:

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

Alle anderen Stile, die beim Erstellen des Fensters übergebenen werden, werden ignoriert. Das `ComboBoxEx` -Steuerelement unterstützt auch erweiterte Stile, die zusätzliche Funktionen bereitstellen. Diese Stile werden unter [ComboBoxEx-Steuerelement erweiterte Stile](/windows/win32/Controls/comboboxex-control-extended-styles)im Windows SDK beschrieben. Legen Sie diese Stile durch Aufrufen von [SetExtendedStyle](#setextendedstyle)fest.

Wenn Sie erweiterte Windows-Stile mit dem Steuerelement verwenden möchten, müssen Sie anstelle von `Create`den Befehl " [kreateex](#createex) " aufrufen.

##  <a name="createex"></a>CComboBoxEx:: kreateex

Rufen Sie diese Funktion auf, um ein erweitertes Kombinations Feld-Steuerelement (ein untergeordnetes Fenster) `CComboBoxEx` zu erstellen und es dem-Objekt zuzuordnen.

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
Der Stil des Kombinations Feld-Steuer Elements. Eine Liste der Stile finden Sie unter [Erstellen](#create) .

*Rect*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Größe und Position des zu erstellenden Fensters in Client Koordinaten von *pparser*beschreibt.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das das übergeordnete Element des Steuer Elements ist.

*nID*<br/>
Die ID des untergeordneten Fensters des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwenden `CreateEx` Sie anstelle `Create` von, um erweiterte Windows-Stile anzuwenden, die durch den erweiterten Windows-Stil **WS_EX_** angegeben werden.

`CreateEx`erstellt das Steuerelement mit den erweiterten Windows-Stilen, die von *dwExStyle*angegeben werden. Sie müssen erweiterte Stile für ein erweitertes Kombinations Feld-Steuerelement mithilfe von " [setextendecodstyle](#setextendedstyle)" festlegen. Verwenden `CreateEx` Sie z. b., um solche Stile als WS_EX_CONTEXTHELP fest `SetExtendedStyle` zulegen, aber verwenden Sie, um solche Stile auf CBES_EX_CASESENSITIVE festzulegen. Weitere Informationen finden Sie in den Stilen, die im Thema [ComboBoxEx-Steuerelement erweiterte Stile](/windows/win32/Controls/comboboxex-control-extended-styles) in der Windows SDK beschrieben werden.

##  <a name="deleteitem"></a>CComboBoxEx::D eleteitem

Entfernt ein Element aus einem `ComboBoxEx` -Steuerelement.

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
Der null basierte Index des zu entfernenden Elements.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente, die im Steuerelement verbleiben. Wenn *iIndex* ungültig ist, gibt die Funktion CB_ERR zurück.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert die Funktionalität der Message [CBEM_DELETEITEM](/windows/win32/Controls/cbem-deleteitem), wie im Windows SDK beschrieben. Wenn Sie DeleteItem aufrufen, wird eine [WM_NOTIFY](/windows/win32/controls/wm-notify) -Nachricht mit CBEN_DELETEITEM-Benachrichtigung an das übergeordnete Fenster gesendet.

##  <a name="getcomboboxctrl"></a>CComboBoxEx:: getcomboboxctrl

Mit dieser Member-Funktion können Sie einen Zeiger auf ein Kombinations Feld-Steuer `CComboBoxEx` Element innerhalb eines-Objekts abrufen.

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `CComboBox` -Objekt.

### <a name="remarks"></a>Hinweise

Das `CComboBoxEx` -Steuerelement besteht aus einem übergeordneten Fenster, das `CComboBox`eine kapselt.

Das `CComboBox` Objekt, auf das der Rückgabewert verweist, ist ein temporäres Objekt und wird während der nächsten Leerlauf Verarbeitungszeit zerstört.

##  <a name="geteditctrl"></a>CComboBoxEx:: geteditctrl

Mit dieser Member-Funktion können Sie einen Zeiger auf das Bearbeitungs Steuerelement für ein Kombinations Feld abrufen.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CEdit](../../mfc/reference/cedit-class.md) -Objekt.

### <a name="remarks"></a>Hinweise

Ein `CComboBoxEx` -Steuerelement verwendet ein Bearbeitungsfeld, wenn es mit dem CBS_DROPDOWN-Stil erstellt wird.

Das `CEdit` Objekt, auf das der Rückgabewert verweist, ist ein temporäres Objekt und wird während der nächsten Leerlauf Verarbeitungszeit zerstört.

##  <a name="getextendedstyle"></a>CComboBoxEx:: GetExtendedStyle

Mit dieser Member-Funktion können Sie die erweiterten Stile abrufen, `CComboBoxEx` die für ein Steuerelement verwendet werden.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Der DWORD-Wert, der die erweiterten Stile enthält, die für das Kombinations Feld-Steuerelement verwendet werden.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu diesen Stilen finden Sie unter [ComboBoxEx-Steuerelement erweiterte Stile](/windows/win32/Controls/comboboxex-control-extended-styles) in der Windows SDK.

##  <a name="getimagelist"></a>CComboBoxEx:: GetImageList

Mit dieser Member-Funktion können Sie einen Zeiger auf die Bildliste abrufen, `CComboBoxEx` die von einem-Steuerelement verwendet wird.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt. Wenn dies nicht möglich ist, gibt diese Member-Funktion NULL zurück.

### <a name="remarks"></a>Hinweise

Das `CImageList` Objekt, auf das der Rückgabewert verweist, ist ein temporäres Objekt und wird während der nächsten Leerlauf Verarbeitungszeit zerstört.

##  <a name="getitem"></a>CComboBoxEx:: GetItem

Ruft Element Informationen für ein `ComboBoxEx` angegebenes Element ab.

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parameter

*pCBItem*<br/>
Ein Zeiger auf eine [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) -Struktur, die die Element Informationen empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Vorgang erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert die Funktionalität der Message [CBEM_GETITEM](/windows/win32/Controls/cbem-getitem), wie im Windows SDK beschrieben.

##  <a name="haseditchanged"></a>CComboBoxEx:: haseditchanged

Bestimmt, ob der Benutzer den Inhalt des `ComboBoxEx` Bearbeitungs Steuer Elements durch Eingabe von geändert hat.

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn der Benutzer das Eingabefeld des Steuer Elements eingegeben hat. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert die Funktionalität der Message [CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged), wie im Windows SDK beschrieben.

##  <a name="insertitem"></a>CComboBoxEx:: InsertItem

Fügt ein neues Element in ein `ComboBoxEx` -Steuerelement ein.

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parameter

*pCBItem*<br/>
Ein Zeiger auf eine [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) -Struktur, die die Element Informationen empfängt. Diese Struktur enthält Rückruf Flagwerte für das Element.

### <a name="return-value"></a>Rückgabewert

Der Index, an dem das neue Element eingefügt wurde, wenn erfolgreich. andernfalls-1.

### <a name="remarks"></a>Hinweise

Wenn Sie anrufen `InsertItem`, wird eine [WM_NOTIFY](/windows/win32/controls/wm-notify) -Nachricht mit [CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem) -Benachrichtigung an das übergeordnete Fenster gesendet.

##  <a name="setextendedstyle"></a>CComboBoxEx:: abtextendedstyle

Mit dieser Member-Funktion können Sie die erweiterten Stile festlegen, die für ein erweitertes Kombinations Feld-Steuerelement verwendet werden.

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>Parameter

*dwExMask*<br/>
Ein DWORD-Wert, der angibt, welche Stile in *dwexstyles* betroffen sein sollen. Nur die erweiterten Stile in *dwexmask* werden geändert. Alle anderen Stile werden unverändert beibehalten. Wenn dieser Parameter 0 (null) ist, werden alle Stile in *dwexstyles* beeinträchtigt.

*dwExStyles*<br/>
Ein DWORD-Wert, der das für das Steuerelement festzulegende erweiterte Kombinations Feld-Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Ein DWORD-Wert, der die erweiterten Stile enthält, die zuvor für das-Steuerelement verwendet wurden.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu diesen Stilen finden Sie unter [ComboBoxEx-Steuerelement erweiterte Stile](/windows/win32/Controls/comboboxex-control-extended-styles) in der Windows SDK.

[Verwenden Sie](#createex)zum Erstellen eines erweiterten Steuer Elements für einen Kombinations Feld mit erweiterten Windows-Stilen die Zeichenfolge.

##  <a name="setimagelist"></a>CComboBoxEx:: SetImageList

Legt eine Bildliste für ein `ComboBoxEx` Steuerelement fest.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parameter

*pImageList*<br/>
Ein Zeiger auf ein `CImageList` -Objekt, das die mit dem `CComboBoxEx` -Steuerelement zu verwendenden Bilder enthält.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, das die Bilder enthält, `CComboBoxEx` die zuvor vom-Steuerelement verwendet wurden. NULL, wenn zuvor keine Bildliste festgelegt wurde.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert die Funktionalität der Message [CBEM_SETIMAGELIST](/windows/win32/Controls/cbem-setimagelist), wie im Windows SDK beschrieben. Wenn Sie die Höhe des Standard-Bearbeitungs Steuer Elements ändern, müssen Sie die Win32-Funktion [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) aufrufen, um die Größe `SetImageList`des Steuer Elements nach dem Aufrufen von zu ändern, oder es wird nicht ordnungsgemäß angezeigt.

Das `CImageList` Objekt, auf das der Rückgabewert verweist, ist ein temporäres Objekt und wird während der nächsten Leerlauf Verarbeitungszeit zerstört.

##  <a name="setitem"></a>CComboBoxEx:: System Item

Legt die Attribute für ein Element in einem `ComboBoxEx` -Steuerelement fest.

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parameter

*pCBItem*<br/>
Ein Zeiger auf eine [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) -Struktur, die die Element Informationen empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Vorgang erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert die Funktionalität der Message [CBEM_SETITEM](/windows/win32/Controls/cbem-setitem), wie im Windows SDK beschrieben.

##  <a name="setwindowtheme"></a>CComboBoxEx:: SetWindowTheme

Legt den visuellen Stil des erweiterten Kombinations Feld-Steuer Elements fest.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parameter

*pszSubAppName*<br/>
Ein Zeiger auf eine Unicode-Zeichenfolge, die den festzulegenden erweiterten visuellen Kombinations Feld-Stil enthält.

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert wird nicht verwendet.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion emuliert die Funktionalität der [CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme) -Nachricht, wie im Windows SDK beschrieben.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)
