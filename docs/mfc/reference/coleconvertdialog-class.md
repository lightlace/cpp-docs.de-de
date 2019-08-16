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
ms.openlocfilehash: ba57e756457fcffca806eeba7454ddf7bcf99d34
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504294"
---
# <a name="coleconvertdialog-class"></a>COleConvertDialog-Klasse

Weitere Informationen finden Sie in der [oleuiconvert](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) -Struktur im Windows SDK.

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
|[COleConvertDialog::DoConvert](#doconvert)|Führt die im Dialogfeld angegebene Konvertierung aus.|
|[COleConvertDialog::DoModal](#domodal)|Zeigt das OLE-Dialogfeld "Element ändern" an.|
|[COleConvertDialog::GetClassID](#getclassid)|Ruft die CLSID ab, die dem ausgewählten Element zugeordnet ist.|
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Gibt an, ob das Element als Symbol gezeichnet werden soll.|
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle für die Metadatei ab, die der ikonischen Form dieses Elements zugeordnet ist.|
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Ruft den ausgewählten Typ der Auswahl ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleConvertDialog::m_cv](#m_cv)|Eine-Struktur, die das Verhalten des Dialog Felds steuert.|

## <a name="remarks"></a>Hinweise

> [!NOTE]
>  Vom Anwendungs-Assistenten generierter Container Code verwendet diese Klasse.

Weitere Informationen zu OLE-spezifischen Dialogfeldern finden Sie in den Artikel [Dialogfeldern in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs. h

##  <a name="coleconvertdialog"></a>COleConvertDialog:: COleConvertDialog

Erstellt nur ein `COleConvertDialog` -Objekt.

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Verweist auf das Element, das konvertiert oder aktiviert werden soll.

*dwFlags*<br/>
Erstellungs Kennzeichen, das eine beliebige Anzahl der folgenden Werte enthält, kombiniert mit dem bitweisen OR-Operator:

- CF_SELECTCONVERTTO gibt an, dass das Optionsfeld konvertieren in zuerst ausgewählt wird, wenn das Dialogfeld aufgerufen wird. Dies ist die Standardeinstellung.

- CF_SELECTACTIVATEAS gibt an, dass das Optionsfeld aktivieren als anfänglich ausgewählt wird, wenn das Dialogfeld aufgerufen wird.

- CF_SETCONVERTDEFAULT gibt an, dass die Klasse, deren CLSID vom `clsidConvertDefault` -Member `m_cv` der-Struktur angegeben wird, als Standardauswahl im Listenfeld Klasse verwendet wird, wenn das Optionsfeld konvertieren in ausgewählt ist.

- CF_SETACTIVATEDEFAULT gibt an, dass die Klasse, deren CLSID vom `clsidActivateDefault` -Member `m_cv` der-Struktur angegeben wird, als Standardauswahl im Listenfeld Klasse verwendet wird, wenn das Optionsfeld aktivieren als aktiviert ist.

- CF_SHOWHELPBUTTON gibt an, dass die Schaltfläche Hilfe angezeigt wird, wenn das Dialogfeld aufgerufen wird.

*pClassID*<br/>
Verweist auf die CLSID des zu konvertierenden oder zu aktivierenden Elements. Wenn der Wert NULL ist, wird die mit *pitem* verknüpfte CLSID verwendet.

*pParentWnd*<br/>
Zeigt auf das übergeordnete oder Besitzer Fenster Objekt (vom `CWnd`Typ), zu dem das Dialog Objekt gehört. Wenn er NULL ist, wird das übergeordnete Fenster des Dialog Felds auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Um das Dialogfeld anzuzeigen, müssen Sie die Funktion [DoModal](#domodal) aufrufen.

Weitere Informationen finden Sie unter [CLSID-Schlüssel](/windows/win32/com/clsid-key-hklm) und [oleuiconvert](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) -Struktur.

##  <a name="doconvert"></a>COleConvertDialog::D oconvert

Ruft diese Funktion nach der erfolgreichen Rückgabe von [DoModal](#domodal)auf, um ein Objekt vom Typ [COleClientItem](../../mfc/reference/coleclientitem-class.md)zu konvertieren oder zu aktivieren.

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Verweist auf das Element, das konvertiert oder aktiviert werden soll. Lässt keine NULL-Werte zu.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Das Element wird entsprechend der vom Benutzer im Dialogfeld Konvertieren ausgewählten Informationen konvertiert oder aktiviert.

##  <a name="domodal"></a>COleConvertDialog::D omodal

Aufrufen Sie diese Funktion, um das Dialogfeld OLE Convert anzuzeigen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Abschluss Status für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- Idabort, wenn ein Fehler aufgetreten ist. Wenn idabort zurückgegeben wird, können Sie die Member-Funktion [COleDialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) aufrufen, um weitere Informationen zum aufgetretenen Fehlertyp abzurufen. Eine Auflistung möglicher Fehler finden Sie unter der [oleuiconvert](/windows/win32/api/oledlg/nf-oledlg-oleuiconvertw) -Funktion in der Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeld-Steuerelemente durch Festlegen der Member der [m_cv](#m_cv) -Struktur initialisieren möchten, sollten Sie dies vor `DoModal`dem Aufrufen von tun, nachdem das Dialogfeld Objekt erstellt wurde.

Wenn `DoModal` IDOK zurückgibt, können Sie andere Element Funktionen aufrufen, um die Einstellungen oder Informationen abzurufen, die vom Benutzer in das Dialogfeld eingegeben wurden.

##  <a name="getclassid"></a>COleConvertDialog:: GetClassID

Mit dieser Funktion können Sie die CLSID abrufen, die dem Element zugeordnet ist, das der Benutzer im Dialogfeld "konvertieren" ausgewählt hat.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Rückgabewert

Die CLSID, die dem Element zugeordnet ist, das im Dialogfeld "konvertieren" ausgewählt wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nur aufgerufen werden, nachdem die [Domäne](#domodal) IDOK zurückgegeben hat.

Weitere Informationen finden Sie unter [CLSID-Schlüssel](/windows/win32/com/clsid-key-hklm) in der Windows SDK.

##  <a name="getdrawaspect"></a>COleConvertDialog:: getdrawaspect

Mit dieser Funktion können Sie feststellen, ob der Benutzer das ausgewählte Element als Symbol anzeigt.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Rückgabewert

Die Methode, die zum Rendering des-Objekts erforderlich ist.

- DVASPECT_CONTENT wird zurückgegeben, wenn das Kontrollkästchen als Symbol anzeigen nicht aktiviert wurde.

- DVASPECT_ICON wird zurückgegeben, wenn das Kontrollkästchen als Symbol anzeigen aktiviert wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nur aufgerufen werden, nachdem die [Domäne](#domodal) IDOK zurückgegeben hat.

Weitere Informationen zum Zeichnen-Aspekt finden Sie in der [formatusw](/windows/win32/api/objidl/ns-objidl-formatetc) .-Datenstruktur in der Windows SDK.

##  <a name="geticonicmetafile"></a>COleConvertDialog:: getikonicmetafile

Mit dieser Funktion können Sie ein Handle für die Metadatei abrufen, die den ikonischen Aspekt des ausgewählten Elements enthält.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Rückgabewert

Das Handle für die Metadatei, das den ikonischen Aspekt des ausgewählten Elements enthält, wenn das Kontrollkästchen als Symbol anzeigen beim Verwerfen des Dialog Felds aktiviert wurde, indem Sie auf OK klicken. andernfalls NULL.

##  <a name="getselectiontype"></a>COleConvertDialog:: GetSelectionType

Mit dieser Funktion können Sie den Typ der im Dialogfeld Konvertieren ausgewählten Konvertierung ermitteln.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Rückgabewert

Der Typ der Auswahl.

### <a name="remarks"></a>Hinweise

Die Rückgabetyp Werte werden durch `Selection` den Enumerationstyp angegeben `COleConvertDialog` , der in der-Klasse deklariert ist.

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

Im folgenden finden Sie eine kurze Beschreibung dieser Werte:

- `COleConvertDialog::noConversion`Wird zurückgegeben, wenn entweder das Dialogfeld abgebrochen wurde oder der Benutzer keine Konvertierung ausgewählt hat. Wenn `COleConvertDialog::DoModal` IDOK zurückgegeben wurde, ist es möglich, dass der Benutzer ein anderes Symbol als zuvor ausgewählt ausgewählt hat.

- `COleConvertDialog::convertItem`Wird zurückgegeben, wenn das Optionsfeld konvertieren in aktiviert wurde, hat der Benutzer ein anderes Element für die `DoModal` Konvertierung ausgewählt und IDOK zurückgegeben.

- `COleConvertDialog::activateAs`Wird zurückgegeben, wenn das Optionsfeld aktivieren als aktiviert wurde, hat der Benutzer ein anderes Element zum `DoModal` aktivieren ausgewählt und IDOK zurückgegeben.

##  <a name="m_cv"></a>COleConvertDialog:: m_cv

Struktur vom Typ "oleuiconvert", die zum Steuern des Verhaltens des Dialog Felds "konvertieren" verwendet wird.

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>Hinweise

Member dieser Struktur können entweder direkt oder über Element Funktionen geändert werden.

Weitere Informationen finden Sie in der [oleuiconvert](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) -Struktur im Windows SDK.

## <a name="see-also"></a>Siehe auch

[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
