---
title: Colechangesourcedialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
ms.openlocfilehash: 239d7eed89796f414a7665b203ca50fafec51277
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504386"
---
# <a name="colechangesourcedialog-class"></a>Colechangesourcedialog-Klasse

Wird für das OLE-Dialogfeld "Quelle ändern" verwendet.

## <a name="syntax"></a>Syntax

```
class COleChangeSourceDialog : public COleDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|Erstellt ein `COleChangeSourceDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleChangeSourceDialog::DoModal](#domodal)|Zeigt das OLE-Dialogfeld Quelle ändern an.|
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Ruft den Namen der kompletten Quell Anzeige ab.|
|[COleChangeSourceDialog::GetFileName](#getfilename)|Ruft den Dateinamen aus dem Quellnamen ab.|
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Ruft das Präfix der vorherigen Quelle ab.|
|[COleChangeSourceDialog::GetItemName](#getitemname)|Ruft den Elementnamen aus dem Quellnamen ab.|
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Ruft das Präfix der neuen Quelle ab.|
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Gibt an, ob die Quelle gültig ist.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleChangeSourceDialog::m_cs](#m_cs)|Eine-Struktur, die das Verhalten des Dialog Felds steuert.|

## <a name="remarks"></a>Hinweise

Erstellen Sie ein Objekt der `COleChangeSourceDialog` -Klasse, wenn Sie dieses Dialogfeld aufzurufen. Nachdem ein `COleChangeSourceDialog` -Objekt erstellt wurde, können Sie die [m_cs](#m_cs) -Struktur verwenden, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_cs` Struktur ist vom Typ " [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)". Weitere Informationen zum Verwenden dieser Dialogfeld Klasse finden Sie unter der [DoModal](#domodal) -Member-Funktion.

Weitere Informationen finden Sie in der [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) -Struktur unter Windows SDK.

Weitere Informationen zu OLE-spezifischen Dialogfeldern finden Sie in den Artikel [Dialogfeldern in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeSourceDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs. h

##  <a name="colechangesourcedialog"></a>Colechangesourcedialog:: colechangesourcedialog

Diese Funktion erstellt ein `COleChangeSourceDialog` -Objekt.

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Zeiger auf das verknüpfte [COleClientItem](../../mfc/reference/coleclientitem-class.md) , dessen Quelle aktualisiert werden soll.

*pParentWnd*<br/>
Zeigt auf das übergeordnete oder Besitzer Fenster Objekt (vom `CWnd`Typ), zu dem das Dialog Objekt gehört. Wenn er NULL ist, wird das übergeordnete Fenster des Dialog Felds auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Um das Dialogfeld anzuzeigen, müssen Sie die Funktion [DoModal](#domodal) aufrufen.

Weitere Informationen finden Sie in der [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) -Struktur und in der [oleuichangesource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) -Funktion in Windows SDK.

##  <a name="domodal"></a>Colechangesourcedialog::D omodal

Mit dieser Funktion wird das OLE-Dialogfeld "Quelle ändern" angezeigt.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Abschluss Status für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- Idabort, wenn ein Fehler aufgetreten ist. Wenn idabort zurückgegeben wird, können Sie die Member-Funktion [COleDialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) aufrufen, um weitere Informationen zum aufgetretenen Fehlertyp abzurufen. Eine Auflistung möglicher Fehler finden Sie unter der [oleuichangesource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) -Funktion in Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeld-Steuerelemente durch Festlegen der Member der [m_cs](#m_cs) -Struktur initialisieren möchten, sollten Sie dies vor `DoModal`dem Aufrufen von tun, nachdem das Dialogfeld Objekt erstellt wurde.

Wenn `DoModal` IDOK zurückgibt, können Sie Member-Funktionen aufrufen, um vom Benutzer eingegebene Einstellungen oder Informationen aus dem Dialogfeld abzurufen. In der folgenden Liste sind typische Abfragefunktionen aufgeführt:

- [GetFileName](#getfilename)

- [GetDisplayName](#getdisplayname)

- [GetItemName](#getitemname)

##  <a name="getdisplayname"></a>Colechangesourcedialog:: GetDisplayName

Rufen Sie diese Funktion auf, um den gesamten anzeigen Amen für das verknüpfte Client Element abzurufen.

```
CString GetDisplayName();
```

### <a name="return-value"></a>Rückgabewert

Der gesamte Quell Anzeige Name (Moniker) für das im Konstruktor angegebene [COleClientItem-Objekt](../../mfc/reference/coleclientitem-class.md) .

##  <a name="getfilename"></a>Colechangesourcedialog:: GetFilename

Rufen Sie diese Funktion auf, um den Datei-monikerteil des anzeigen Amens für das verknüpfte Client Element abzurufen.

```
CString GetFileName();
```

### <a name="return-value"></a>Rückgabewert

Der dateimonikerteil des Quell Anzeige namens für das im Konstruktor angegebene [COleClientItem](../../mfc/reference/coleclientitem-class.md) -Element.

### <a name="remarks"></a>Hinweise

Der dateimoniker mit dem elementmoniker gibt den gesamten anzeigen Amen an.

##  <a name="getfromprefix"></a>Colechangesourcedialog:: getfromprefix

Mit dieser Funktion können Sie die vorherige Präfix Zeichenfolge für die Quelle abrufen.

```
CString GetFromPrefix();
```

### <a name="return-value"></a>Rückgabewert

Die vorherige Präfix Zeichenfolge der Quelle.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nur aufgerufen werden, nachdem die [Domäne](#domodal) IDOK zurückgegeben hat.

Dieser Wert stammt direkt vom `lpszFrom` Member der [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) -Struktur.

Weitere Informationen finden Sie in der [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) -Struktur unter Windows SDK.

##  <a name="getitemname"></a>Colechangesourcedialog:: GetItemName

Mit dieser Funktion wird der elementmonikerteil des anzeigen Amens für das verknüpfte Client Element abgerufen.

```
CString GetItemName();
```

### <a name="return-value"></a>Rückgabewert

Der elementmonikerteil des Quell Anzeige namens für das im Konstruktor angegebene [COleClientItem](../../mfc/reference/coleclientitem-class.md) -Element.

### <a name="remarks"></a>Hinweise

Der dateimoniker mit dem elementmoniker gibt den gesamten anzeigen Amen an.

##  <a name="gettoprefix"></a>Colechangesourcedialog:: gettoprefix

Mit dieser Funktion können Sie die neue Präfix Zeichenfolge für die Quelle abrufen.

```
CString GetToPrefix();
```

### <a name="return-value"></a>Rückgabewert

Die neue Präfix Zeichenfolge der Quelle.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nur aufgerufen werden, nachdem die [Domäne](#domodal) IDOK zurückgegeben hat.

Dieser Wert stammt direkt vom `lpszTo` Member der [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) -Struktur.

Weitere Informationen finden Sie in der [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) -Struktur unter Windows SDK.

##  <a name="m_cs"></a>Colechangesourcedialog:: m_cs

Dieser Datenmember ist eine Struktur des Typs [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew).

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>Hinweise

`OLEUICHANGESOURCE`wird verwendet, um das Verhalten des OLE-Dialog Felds "Quelle ändern" zu steuern. Mitglieder dieser Struktur können direkt geändert werden.

Weitere Informationen finden Sie in der [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) -Struktur unter Windows SDK.

##  <a name="isvalidsource"></a>Colechangesourcedialog:: isvalidsource

Mit dieser Funktion können Sie ermitteln, ob die neue Quelle gültig ist.

```
BOOL IsValidSource();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn die neue Quelle gültig ist, andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nur aufgerufen werden, nachdem die [Domäne](#domodal) IDOK zurückgegeben hat.

Weitere Informationen finden Sie in der [oleuichangesource](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) -Struktur unter Windows SDK.

## <a name="see-also"></a>Siehe auch

[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
