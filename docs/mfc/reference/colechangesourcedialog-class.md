---
title: COleChangeSourceDialog-Klasse
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
ms.openlocfilehash: 1d118b132fc110402967e9c7f2b1d74a2164d7c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399719"
---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog-Klasse

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
|[COleChangeSourceDialog::DoModal](#domodal)|Zeigt das Dialogfeld für die Quelle für das OLE-ändern.|
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Ruft den Anzeigenamen für die vollständige Quelle ab.|
|[COleChangeSourceDialog::GetFileName](#getfilename)|Ruft den Dateinamen aus dem Quellnamen ab.|
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Ruft das Präfix der vorherigen Datenquelle ab.|
|[COleChangeSourceDialog::GetItemName](#getitemname)|Ruft den Namen des Elements nicht mit dem Quellnamen ab.|
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Ruft das Präfix des der neuen Quelle|
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Gibt an, ob die Datenquelle gültig ist.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleChangeSourceDialog::m_cs](#m_cs)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|

## <a name="remarks"></a>Hinweise

Erstellen Sie ein Objekt der Klasse `COleChangeSourceDialog` Wenn das Dialogfeld aufgerufen werden soll. Nach einer `COleChangeSourceDialog` -Objekts wird, können Sie mit der [M_cs](#m_cs) Struktur zum Initialisieren der Werte oder Zustände von Steuerelementen im Dialogfeld. Die `m_cs` Struktur ist vom Typ [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea). Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter den [DoModal](#domodal) Member-Funktion.

Weitere Informationen finden Sie unter den [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Struktur im Windows SDK.

Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeSourceDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs.h

##  <a name="colechangesourcedialog"></a>  COleChangeSourceDialog::COleChangeSourceDialog

Diese Funktion erstellt eine `COleChangeSourceDialog` Objekt.

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Zeiger auf die verknüpften [COleClientItem](../../mfc/reference/coleclientitem-class.md) , dessen Datenquelle ist, aktualisiert werden.

*pParentWnd*<br/>
Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs `CWnd`) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt werden.

### <a name="remarks"></a>Hinweise

Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.

Weitere Informationen finden Sie unter den [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Struktur und [OleUIChangeSource](/windows/desktop/api/oledlg/nf-oledlg-oleuichangesourcea) -Funktion in Windows SDK.

##  <a name="domodal"></a>  COleChangeSourceDialog::DoModal

Rufen Sie diese Funktion, um das Dialogfeld für die Quelle für das OLE-ändern anzuzeigen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- IDABORT, wenn ein Fehler aufgetreten. Wenn IDABORT zurückgegeben wird, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Liste der möglichen Fehler, finden Sie unter den [OleUIChangeSource](/windows/desktop/api/oledlg/nf-oledlg-oleuichangesourcea) -Funktion in Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_cs](#m_cs) Struktur, sollten Sie dies tun, vor dem Aufruf `DoModal`, allerdings nachdem das Dialogfeldobjekt erstellt wird.

Wenn `DoModal` gibt IDOK, Sie können Member-Funktionen zum Abrufen der freien Eingabe von Einstellungen oder Informationen über das Dialogfeld aufrufen. Die folgende Liste enthält die typische Abfragefunktionen:

- [GetFileName](#getfilename)

- [GetDisplayName](#getdisplayname)

- [GetItemName](#getitemname)

##  <a name="getdisplayname"></a>  COleChangeSourceDialog::GetDisplayName

Rufen Sie diese Funktion zum Abrufen der vollständige Anzeigename für den verknüpften Client-Element.

```
CString GetDisplayName();
```

### <a name="return-value"></a>Rückgabewert

Die vollständige Quelle Anzeigenamen (Moniker, Zielframeworkmoniker) für die [COleClientItem](../../mfc/reference/coleclientitem-class.md) im Konstruktor angegeben.

##  <a name="getfilename"></a>  COleChangeSourceDialog::GetFileName

Rufen Sie diese Funktion zum Abrufen des Datei-Moniker-Teils des Anzeigenamens für den verknüpften Client-Element.

```
CString GetFileName();
```

### <a name="return-value"></a>Rückgabewert

Die Datei-Moniker Teil der Anzeigename der Quelle für die [COleClientItem](../../mfc/reference/coleclientitem-class.md) im Konstruktor angegeben.

### <a name="remarks"></a>Hinweise

Die Datei-Moniker zusammen mit den Element-Moniker bietet der vollständige Anzeigename.

##  <a name="getfromprefix"></a>  COleChangeSourceDialog::GetFromPrefix

Rufen Sie diese Funktion rufen Sie die vorherigen Präfixzeichenfolge für die Quelle an.

```
CString GetFromPrefix();
```

### <a name="return-value"></a>Rückgabewert

Die vorherigen Präfixzeichenfolge der Quelle.

### <a name="remarks"></a>Hinweise

Diese Funktion nur nach dem Aufruf [DoModal](#domodal) IDOK zurückgibt.

Dieser Wert stammt direkt aus der `lpszFrom` Mitglied der [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Struktur.

Weitere Informationen finden Sie unter den [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Struktur im Windows SDK.

##  <a name="getitemname"></a>  COleChangeSourceDialog::GetItemName

Rufen Sie diese Funktion zum Abrufen des Element-Moniker-Teils des Anzeigenamens für den verknüpften Client-Element.

```
CString GetItemName();
```

### <a name="return-value"></a>Rückgabewert

Der Element-Moniker-Teil der Anzeigename der Quelle für die [COleClientItem](../../mfc/reference/coleclientitem-class.md) im Konstruktor angegeben.

### <a name="remarks"></a>Hinweise

Die Datei-Moniker zusammen mit den Element-Moniker bietet der vollständige Anzeigename.

##  <a name="gettoprefix"></a>  COleChangeSourceDialog::GetToPrefix

Rufen Sie diese Funktion, um die neue Präfixzeichenfolge für die Quelle zu erhalten.

```
CString GetToPrefix();
```

### <a name="return-value"></a>Rückgabewert

Die neue Präfixzeichenfolge der Quelle.

### <a name="remarks"></a>Hinweise

Diese Funktion nur nach dem Aufruf [DoModal](#domodal) IDOK zurückgibt.

Dieser Wert stammt direkt aus der `lpszTo` Mitglied der [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Struktur.

Weitere Informationen finden Sie unter den [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Struktur im Windows SDK.

##  <a name="m_cs"></a>  COleChangeSourceDialog::m_cs

Datenmember ist eine Struktur des Typs [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea).

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>Hinweise

`OLEUICHANGESOURCE` Dient zum Steuern des Verhaltens des Dialogfelds Quelle für das OLE-ändern. Mitglieder dieser Struktur können direkt geändert werden.

Weitere Informationen finden Sie unter den [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Struktur im Windows SDK.

##  <a name="isvalidsource"></a>  COleChangeSourceDialog::IsValidSource

Rufen Sie diese Funktion, um zu bestimmen, ob die neue Quelle gültig ist.

```
BOOL IsValidSource();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die neue Quelle gültig ist, andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion nur nach dem Aufruf [DoModal](#domodal) IDOK zurückgibt.

Weitere Informationen finden Sie unter den [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Struktur im Windows SDK.

## <a name="see-also"></a>Siehe auch

[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
