---
title: COleInsertDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
ms.openlocfilehash: 750243ddf6494ecc4a6a28c0cb47b05ca7089c33
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260685"
---
# <a name="coleinsertdialog-class"></a>COleInsertDialog-Klasse

Wird für das OLE-Dialogfeld "Objekt einfügen" verwendet.

## <a name="syntax"></a>Syntax

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Erstellt ein `COleInsertDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleInsertDialog::CreateItem](#createitem)|Erstellt das Element, das Sie im Dialogfeld ausgewählt.|
|[COleInsertDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Objekt einfügen.|
|[COleInsertDialog::GetClassID](#getclassid)|Ruft die CLSID, die dem ausgewählten Element zugeordnet.|
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Gibt an, ob das Element als ein Symbol zu zeichnen.|
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle der Metadatei zugeordnete Symbol Form dieses Elements ab.|
|[COleInsertDialog::GetPathName](#getpathname)|Ruft den vollständigen Pfad zu der Sie im Dialogfeld ausgewählte Datei ab.|
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Ruft den Typ des ausgewählten Objekts.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleInsertDialog::m_io](#m_io)|Eine Struktur vom Typ OLEUIINSERTOBJECT, die das Verhalten des Dialogfelds steuert.|

## <a name="remarks"></a>Hinweise

Erstellen Sie ein Objekt der Klasse `COleInsertDialog` Wenn das Dialogfeld aufgerufen werden soll. Nach einer `COleInsertDialog` -Objekts wird, können Sie mit der [M_io](#m_io) Struktur zum Initialisieren der Werte oder Zustände von Steuerelementen im Dialogfeld. Die `m_io` Struktur des Typs OLEUIINSERTOBJECT ist. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter den [DoModal](#domodal) Member-Funktion.

> [!NOTE]
>  Vom Assistenten generierten Container-Anwendungscode verwendet diese Klasse.

Weitere Informationen finden Sie unter den [OLEUIINSERTOBJECT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiinsertobjecta) Struktur im Windows SDK.

Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs.h

##  <a name="coleinsertdialog"></a>  COleInsertDialog::COleInsertDialog

Diese Funktion erstellt nur eine `COleInsertDialog` Objekt.

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Erstellung-Flag, die eine beliebige Anzahl von mit dem bitweisen OR-Operator kombiniert werden die folgenden Werte enthält:

- IOF_SHOWHELP gibt an, dass die Schaltfläche "Hilfe" angezeigt wird, wenn das Dialogfeld aufgerufen wird.

- IOF_SELECTCREATENEW gibt an, die das Erstellen neuer Optionsfeld ausgewählt anfänglich Wenn das Dialogfeld aufgerufen wird. Dies ist der Standardwert und kann nicht mit IOF_SELECTCREATEFROMFILE verwendet werden.

- IOF_SELECTCREATEFROMFILE angibt, das Optionsfeld aus der Datei zu erstellen ist ausgewählt, anfänglich Wenn das Dialogfeld aufgerufen wird. Kann nicht mit IOF_SELECTCREATENEW verwendet werden.

- IOF_CHECKLINK angibt, das Kontrollkästchen "Link" wird überprüft, anfänglich Wenn das Dialogfeld aufgerufen wird.

- IOF_DISABLELINK gibt an, dass das Kontrollkästchen aktivieren, um die Verknüpfung wird deaktiviert werden, wenn das Dialogfeld aufgerufen wird.

- IOF_CHECKDISPLAYASICON gibt an, das als Symbol Kontrollkästchen wird zunächst überprüft werden, die das aktuelle Symbol wird angezeigt und die Schaltfläche "Symbol ändern" wird aktiviert, wenn das Dialogfeld aufgerufen wird.

- IOF_VERIFYSERVERSEXIST gibt an, die im Dialogfeld Klassen überprüft werden sollen, die sie in das Listenfeld hinzufügt, indem Sie sicherstellen, dass die in der Registrierungsdatenbank angegebenen Server vorhanden sind, bevor Sie das Dialogfeld angezeigt wird. Wenn Sie dieses Flag kann die Leistung erheblich beeinträchtigen.

*pParentWnd*<br/>
Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs `CWnd`) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das übergeordnete Fenster des Dialog-Objekts auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.

##  <a name="createitem"></a>  COleInsertDialog::CreateItem

Mit dieser Funktion können Sie ein Objekt des Typs erstellen [COleClientItem](../../mfc/reference/coleclientitem-class.md) nur, wenn [DoModal](#domodal) IDOK zurückgibt.

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Verweist auf das Element, das erstellt werden.

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich NULL wurde Element erstellt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie müssen Zuordnen der `COleClientItem` Objekt, bevor Sie diese Funktion aufrufen können.

##  <a name="domodal"></a>  COleInsertDialog::DoModal

Rufen Sie diese Funktion, um das Dialogfeld "OLE Objekt einfügen" anzuzeigen.

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Einer der folgenden Werte:

`COleInsertDialog::DocObjectsOnly` Fügt nur DocObjects an.

`COleInsertDialog::ControlsOnly` Fügt nur ActiveX-Steuerelemente.

0 (null) fügt weder DocObject noch ein ActiveX-Steuerelement. Dieser Wert führt dieselbe Implementierung als ersten Prototyp die oben aufgeführten.

### <a name="return-value"></a>Rückgabewert

Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- IDABORT, wenn ein Fehler aufgetreten. Wenn IDABORT zurückgegeben wird, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Liste der möglichen Fehler, finden Sie unter den [OleUIInsertObject](/windows/desktop/api/oledlg/nf-oledlg-oleuiinsertobjecta) -Funktion in das Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_io](#m_io) Struktur, sollten Sie dies tun, vor dem Aufruf `DoModal`, allerdings nachdem das Dialogfeldobjekt erstellt wird.

Wenn `DoModal` gibt IDOK, Sie können andere Memberfunktionen aufrufen, dessen Einstellungen oder die Eingabe von Informationen in das Dialogfeld vom Benutzer abgerufen.

##  <a name="getclassid"></a>  COleInsertDialog::GetClassID

Rufen Sie diese Funktion rufen Sie die CLSID, die den ausgewählten Element nur, wenn zugeordnete [DoModal](#domodal) zurückgibt IDOK und den Auswahltyp `COleInsertDialog::createNewItem`.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die CLSID, die dem ausgewählten Element zugeordnet.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Schlüssel CLSID](/windows/desktop/com/clsid-key-hklm) im Windows SDK.

##  <a name="getdrawaspect"></a>  COleInsertDialog::GetDrawAspect

Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer hat das ausgewählte Element als Symbol anzuzeigen.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Rückgabewert

Die Methode, die zum Rendern des Objekts erforderlich sind.

- DVASPECT_CONTENT zurückgegeben, wenn das als Symbol Kontrollkästchen nicht aktiviert wurde.

- DVASPECT_ICON zurückgegeben, wenn das als Symbol Kontrollkästchen aktiviert wurde.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion nur, wenn [DoModal](#domodal) IDOK zurückgibt.

Weitere Informationen zum Zeichnen der Aspekt, finden Sie unter [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur der Daten in das Windows SDK.

##  <a name="geticonicmetafile"></a>  COleInsertDialog::GetIconicMetafile

Rufen Sie diese Funktion, um ein Handle der Metadatei zu erhalten, den Symbol Aspekt des ausgewählten Elements enthält.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Rückgabewert

Das Handle der Metadatei die iconic Aspekt des ausgewählten Elements, falls enthält, das als Symbol Kontrollkästchen aktiviert, wenn das Dialogfeld geschlossen wurde, dazu **OK**; andernfalls NULL.

##  <a name="getpathname"></a>  COleInsertDialog::GetPathName

Mit dieser Funktion können Sie den vollständigen Pfad der nur, wenn die ausgewählte Datei erhalten [DoModal](#domodal) gibt IDOK und den Typ der Auswahl ist nicht `COleInsertDialog::createNewItem`.

```
CString GetPathName() const;
```

### <a name="return-value"></a>Rückgabewert

Der vollständige Pfad der Datei, die im Dialogfeld ausgewählt. Wenn der Auswahltyp ist `createNewItem`, diese Funktion gibt eine bedeutungslos `CString` im Releasemodus oder verursacht eine Assertion im Debugmodus befindet.

##  <a name="getselectiontype"></a>  COleInsertDialog::GetSelectionType

Mit dieser Funktion wird zum Abrufen des Auswahltyps ausgewählt wird, wenn das Dialogfeld "Objekt einfügen" dazu verworfen wurde **OK**.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Rückgabewert

Typ der Auswahl getroffen wurde.

### <a name="remarks"></a>Hinweise

Der Rückgabetyp Werte angegeben sind die `Selection` Enumerationstyp deklariert wird, der `COleInsertDialog` Klasse.

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

Führen Sie die kurze Beschreibungen der folgenden Werte:

- `COleInsertDialog::createNewItem` Das Erstellen neuer Optionsfeld ausgewählt wurde.

- `COleInsertDialog::insertFromFile` Das Optionsfeld aus Datei erstellen wurde ausgewählt, und das Kontrollkästchen "Link" nicht aktiviert wurde.

- `COleInsertDialog::linkToFile` Das Optionsfeld aus Datei erstellen wurde ausgewählt, und das Kontrollkästchen "Link" aktiviert wurde.

##  <a name="m_io"></a>  COleInsertDialog::m_io

Struktur des Typs OLEUIINSERTOBJECT verwendet zur Steuerung des Verhaltens im Dialogfeld "Objekt einfügen".

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>Hinweise

Mitglieder dieser Struktur können entweder direkt oder über Memberfunktionen geändert werden.

Weitere Informationen finden Sie unter den [OLEUIINSERTOBJECT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiinsertobjecta) Struktur im Windows SDK.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
