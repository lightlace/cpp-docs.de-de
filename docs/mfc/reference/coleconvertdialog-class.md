---
title: COleConvertDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
ms.openlocfilehash: e1e13f96eb90c81127723afcacf463478b75a894
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569753"
---
# <a name="coleconvertdialog-class"></a>COleConvertDialog-Klasse

Weitere Informationen finden Sie unter den [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) Struktur im Windows SDK.

## <a name="syntax"></a>Syntax

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|Erstellt ein `COleConvertDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleConvertDialog::DoConvert](#doconvert)|Führt die Konvertierung in das Dialogfeld angegeben.|
|[COleConvertDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Change-Element.|
|[COleConvertDialog::GetClassID](#getclassid)|Ruft die CLSID, die dem ausgewählten Element zugeordnet.|
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Gibt an, ob das Element als ein Symbol zu zeichnen.|
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle der Metadatei zugeordnete Symbol Form dieses Elements ab.|
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Ruft den Typ der getroffenen Auswahl ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleConvertDialog::m_cv](#m_cv)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|

## <a name="remarks"></a>Hinweise

> [!NOTE]
>  Vom Assistenten generierten Container-Anwendungscode verwendet diese Klasse.

Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs.h

##  <a name="coleconvertdialog"></a>  COleConvertDialog::COleConvertDialog

Erstellt nur eine `COleConvertDialog` Objekt.

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Verweist auf das Element konvertiert oder aktiviert werden.

*dwFlags*<br/>
Flag der Erstellung, die eine beliebige Anzahl von die folgenden Werte enthält, kombiniert mit dem bitweisen- or -Operator:

- CF_SELECTCONVERTTO gibt an, die das Konvertieren in Optionsfeld ausgewählt anfänglich Wenn das Dialogfeld aufgerufen wird. Dies ist die Standardeinstellung.

- CF_SELECTACTIVATEAS gibt an, die das Optionsfeld aktivieren als Anfang ausgewählt Wenn das Dialogfeld aufgerufen wird.

- CF_SETCONVERTDEFAULT gibt an, dass die Klasse, deren CLSID, indem angegeben wird, die `clsidConvertDefault` Mitglied der `m_cv` Struktur wird als Standardauswahl im Listenfeld der Klasse verwendet werden, wenn das Konvertieren in Optionsfeld ausgewählt ist.

- CF_SETACTIVATEDEFAULT gibt an, dass die Klasse, deren CLSID, indem angegeben wird, die `clsidActivateDefault` Mitglied der `m_cv` Struktur wird als Standardauswahl im Listenfeld der Klasse verwendet werden, wenn das Aktivieren als Optionsfeld ausgewählt ist.

- CF_SHOWHELPBUTTON gibt an, dass die Schaltfläche "Hilfe" angezeigt wird, wenn das Dialogfeld aufgerufen wird.

*pClassID*<br/>
Zeigt auf die CLSID des Elements, das konvertiert oder aktiviert werden. Wenn der Wert NULL ist, die CLSID zugeordnete *pItem* verwendet werden.

*pParentWnd*<br/>
Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs `CWnd`) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.

Weitere Informationen finden Sie unter [Schlüssel CLSID](/windows/desktop/com/clsid-key-hklm) und [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) Struktur.

##  <a name="doconvert"></a>  COleConvertDialog::DoConvert

Mit dieser Funktion wird, nach der Rückgabe erfolgreich vom [DoModal](#domodal), entweder um konvertieren oder um ein Objekt des Typs aktivieren [COleClientItem](../../mfc/reference/coleclientitem-class.md).

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Verweist auf das Element konvertiert oder aktiviert werden. Darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Das Element konvertiert oder entsprechend den Informationen, die vom Benutzer im Dialogfeld "konvertieren" ausgewählt wurde aktiviert.

##  <a name="domodal"></a>  COleConvertDialog::DoModal

Rufen Sie diese Funktion, um das Konvertieren OLE-Dialogfeld angezeigt.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- IDABORT, wenn ein Fehler aufgetreten. Wenn IDABORT zurückgegeben wird, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Liste der möglichen Fehler, finden Sie unter den [OleUIConvert](/windows/desktop/api/oledlg/nf-oledlg-oleuiconverta) -Funktion in das Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_cv](#m_cv) Struktur, sollten Sie dies tun, vor dem Aufruf `DoModal`, allerdings nachdem das Dialogfeldobjekt erstellt wird.

Wenn `DoModal` gibt IDOK, Sie können andere Memberfunktionen aufrufen zum Abrufen der Einstellungen oder die Informationen, die in das Dialogfeld vom Benutzer eingegeben wurde.

##  <a name="getclassid"></a>  COleConvertDialog::GetClassID

Aufruf, dass diese Funktion zum Abrufen der CLSID des Elements vom Benutzer ausgewählten im Dialogfeld "konvertieren" zugeordnet.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Rückgabewert

Die CLSID zugeordnete das Element, das das Dialogfeld "konvertieren" ausgewählt wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion nur nach dem Aufruf [DoModal](#domodal) IDOK zurückgibt.

Weitere Informationen finden Sie unter [Schlüssel CLSID](/windows/desktop/com/clsid-key-hklm) im Windows SDK.

##  <a name="getdrawaspect"></a>  COleConvertDialog::GetDrawAspect

Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer hat das ausgewählte Element als Symbol anzuzeigen.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Rückgabewert

Die Methode, die zum Rendern des Objekts erforderlich sind.

- DVASPECT_CONTENT zurückgegeben, wenn das als Symbol Kontrollkästchen nicht aktiviert wurde.

- DVASPECT_ICON zurückgegeben, wenn das als Symbol Kontrollkästchen aktiviert wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion nur nach dem Aufruf [DoModal](#domodal) IDOK zurückgibt.

Weitere Informationen zum Zeichnen der Aspekt, finden Sie unter den [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur der Daten in das Windows SDK.

##  <a name="geticonicmetafile"></a>  COleConvertDialog::GetIconicMetafile

Rufen Sie diese Funktion, um ein Handle der Metadatei zu erhalten, den Symbol Aspekt des ausgewählten Elements enthält.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Rückgabewert

Das Handle der Metadatei, die den iconic Aspekt, der das ausgewählte Element enthält, wenn das als Symbol Kontrollkästchen wurde überprüft, wenn das Dialogfeld geschlossen wurde, wählen Sie OK. andernfalls NULL.

##  <a name="getselectiontype"></a>  COleConvertDialog::GetSelectionType

Rufen Sie diese Funktion aus, um zu bestimmen, die Art der Konvertierung in das Dialogfeld "konvertieren" ausgewählt.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Rückgabewert

Typ der Auswahl getroffen wurde.

### <a name="remarks"></a>Hinweise

Der Rückgabetyp Werte angegeben sind die `Selection` Enumerationstyp deklariert wird, der `COleConvertDialog` Klasse.

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

Führen Sie die kurze Beschreibungen der folgenden Werte:

- `COleConvertDialog::noConversion` Wenn das Dialogfeld abgebrochen wurde oder vom Benutzer keine Konvertierung ausgewählte zurückgegeben. Wenn `COleConvertDialog::DoModal` IDOK wird zurückgegeben, es ist möglich, dass der Benutzer ein anderes Symbol als die zuvor ausgewählte ausgewählt.

- `COleConvertDialog::convertItem` Zurückgegeben wird, wenn das Optionsfeld konvertieren in aktiviert wurde, wird der Benutzer ein anderes Element konvertiert, ausgewählt und `DoModal` IDOK zurückgegeben.

- `COleConvertDialog::activateAs` Zurückgegeben wird, wenn das Optionsfeld aktivieren als aktiviert wurde, wird der Benutzer ein anderes Element zu aktivieren, ausgewählt und `DoModal` IDOK zurückgegeben.

##  <a name="m_cv"></a>  COleConvertDialog::m_cv

Struktur des Typs OLEUICONVERT verwendet zur Steuerung des Verhaltens im Dialogfeld "konvertieren".

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>Hinweise

Mitglieder dieser Struktur können entweder direkt oder über Memberfunktionen geändert werden.

Weitere Informationen finden Sie unter den [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) Struktur im Windows SDK.

## <a name="see-also"></a>Siehe auch

[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
