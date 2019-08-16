---
title: Colebusydialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
ms.openlocfilehash: aa3f0d85bcbf34d325125187b22b38c4da01fb43
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504403"
---
# <a name="colebusydialog-class"></a>Colebusydialog-Klasse

Wird für die OLE-Dialogfelder "Server antwortet nicht" oder "Server ausgelastet" verwendet.

## <a name="syntax"></a>Syntax

```
class COleBusyDialog : public COleDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|Erstellt ein `COleBusyDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleBusyDialog::DoModal](#domodal)|Zeigt das Dialogfeld "OLE-Server ausgelastet" an.|
|[COleBusyDialog::GetSelectionType](#getselectiontype)|Bestimmt die Auswahl, die im Dialogfeld getroffen wird.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleBusyDialog::m_bz](#m_bz)|Struktur des Typs "oleuibusy", die das Verhalten des Dialog Felds steuert.|

## <a name="remarks"></a>Hinweise

Erstellen Sie ein Objekt der `COleBusyDialog` Klasse, wenn Sie diese Dialogfelder abrufen möchten. Nachdem ein `COleBusyDialog` -Objekt erstellt wurde, können Sie die [m_bz](#m_bz) -Struktur verwenden, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_bz` Struktur ist vom Typ "oleuibusy". Weitere Informationen zum Verwenden dieser Dialogfeld Klasse finden Sie unter der [DoModal](#domodal) -Member-Funktion.

> [!NOTE]
>  Vom Anwendungs-Assistenten generierter Container Code verwendet diese Klasse.

Weitere Informationen finden Sie in der [oleuibusy](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) -Struktur in der Windows SDK.

Weitere Informationen zu OLE-spezifischen Dialogfeldern finden Sie in den Artikel [Dialogfeldern in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleBusyDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs. h

##  <a name="colebusydialog"></a>Colebusydialog:: colebusydialog

Diese Funktion erstellt nur ein `COleBusyDialog` -Objekt.

```
explicit COleBusyDialog(
    HTASK htaskBusy,
    BOOL bNotResponding = FALSE,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*htaskBusy*<br/>
Handle für den Server Task, der ausgelastet ist.

*bNotResponding*<br/>
Wenn der Wert true ist, wird das Dialogfeld nicht Antworten anstelle des Dialog Felds Server ausgelastet aufgerufen. Der Wortlaut im Dialogfeld antwortet nicht antwortet unterscheidet sich geringfügig von dem Wortlaut im Dialogfeld Server ausgelastet, und die Schaltfläche Abbrechen ist deaktiviert.

*dwFlags*<br/>
Erstellungsflag. Kann NULL oder mehrere der folgenden Werte enthalten, kombiniert mit dem bitweisen OR-Operator:

- BZ_DISABLECANCELBUTTON deaktivieren Sie die Schaltfläche Abbrechen, wenn Sie das Dialogfeld aufrufen.

- BZ_DISABLESWITCHTOBUTTON deaktiviert die Schaltfläche "wechseln zu" beim Aufrufen des Dialog Felds.

- BZ_DISABLERETRYBUTTON deaktivieren Sie die Schaltfläche wiederholen, wenn Sie das Dialogfeld aufrufen.

*pParentWnd*<br/>
Zeigt auf das übergeordnete oder Besitzer Fenster Objekt (vom `CWnd`Typ), zu dem das Dialog Objekt gehört. Wenn er NULL ist, wird das übergeordnete Fenster des Dialog Objekts auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Um das Dialogfeld anzuzeigen, nennen Sie [DoModal](#domodal).

Weitere Informationen finden Sie in der [oleuibusy](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) -Struktur in der Windows SDK.

##  <a name="domodal"></a>Colebusydialog::D omodal

Mit dieser Funktion wird das Dialogfeld "OLE Server ausgelastet" oder "Server nicht reagiert" angezeigt.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Abschluss Status für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- Idabort, wenn ein Fehler aufgetreten ist. Wenn idabort zurückgegeben wird, können `COleDialog::GetLastError` Sie die Member-Funktion abrufen, um weitere Informationen zum aufgetretenen Fehlertyp abzurufen. Eine Auflistung möglicher Fehler finden Sie unter der Funktion [oleuibusy](/windows/win32/api/oledlg/nf-oledlg-oleuibusyw) im Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeld-Steuerelemente durch Festlegen der Member der [m_bz](#m_bz) -Struktur initialisieren möchten, sollten Sie dies vor `DoModal`dem Aufrufen von tun, nachdem das Dialogfeld Objekt erstellt wurde.

Wenn `DoModal` IDOK zurückgibt, können Sie andere Element Funktionen aufrufen, um die Einstellungen oder Informationen abzurufen, die vom Benutzer in das Dialogfeld eingegeben wurden.

##  <a name="getselectiontype"></a>Colebusydialog:: GetSelectionType

Mit dieser Funktion können Sie den Auswahl Typen abrufen, der vom Benutzer im Dialogfeld Server ausgelastet ausgewählt wurde.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Rückgabewert

Der Typ der Auswahl.

### <a name="remarks"></a>Hinweise

Die Rückgabetyp Werte werden durch `Selection` den Enumerationstyp angegeben `COleBusyDialog` , der in der-Klasse deklariert ist.

```
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```

Im folgenden finden Sie eine kurze Beschreibung dieser Werte:

- `COleBusyDialog::switchTo`Der Schalter auf die Schaltfläche wurde gedrückt.

- `COleBusyDialog::retry`Die Wiederholungs Schaltfläche wurde gedrückt.

- `COleBusyDialog::callUnblocked`Die Blockierung des Servers zum Aktivieren des Servers wird aufgehoben.

##  <a name="m_bz"></a>Colebusydialog:: m_bz

Struktur des Typs "oleuibusy", die zum Steuern des Verhaltens des Dialog Felds "Server ausgelastet" verwendet wird.

```
OLEUIBUSY m_bz;
```

### <a name="remarks"></a>Hinweise

Member dieser Struktur können direkt oder über Element Funktionen geändert werden.

Weitere Informationen finden Sie in der [oleuibusy](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) -Struktur in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
