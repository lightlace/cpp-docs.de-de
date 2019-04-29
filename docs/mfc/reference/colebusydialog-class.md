---
title: COleBusyDialog-Klasse
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
ms.openlocfilehash: 08e482e6900e96f1d02c34efddc7635bb8e0120e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400707"
---
# <a name="colebusydialog-class"></a>COleBusyDialog-Klasse

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
|[COleBusyDialog::DoModal](#domodal)|Zeigt das Dialogfeld "OLE Server ausgelastet" an.|
|[COleBusyDialog::GetSelectionType](#getselectiontype)|Bestimmt die Auswahl im Dialogfeld an.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleBusyDialog::m_bz](#m_bz)|Die Struktur des Typs OLEUIBUSY, die das Verhalten des Dialogfelds steuert.|

## <a name="remarks"></a>Hinweise

Erstellen Sie ein Objekt der Klasse `COleBusyDialog` beim Aufrufen dieser Dialogfelder aufgerufen werden soll. Nach einer `COleBusyDialog` -Objekts wird, können Sie mit der [M_bz](#m_bz) Struktur zum Initialisieren der Werte oder Zustände von Steuerelementen im Dialogfeld. Die `m_bz` Struktur des Typs OLEUIBUSY ist. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter den [DoModal](#domodal) Member-Funktion.

> [!NOTE]
>  Vom Assistenten generierten Container-Anwendungscode verwendet diese Klasse.

Weitere Informationen finden Sie unter den [OLEUIBUSY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuibusya) Struktur im Windows SDK.

Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleBusyDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs.h

##  <a name="colebusydialog"></a>  COleBusyDialog::COleBusyDialog

Diese Funktion erstellt, nur eine `COleBusyDialog` Objekt.

```
explicit COleBusyDialog(
    HTASK htaskBusy,
    BOOL bNotResponding = FALSE,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*htaskBusy*<br/>
Handle für die Serveraufgabe, die ausgelastet ist.

*bNotResponding*<br/>
Bei "true", rufen Sie das Dialogfeld nicht mehr reagiert, anstatt das Dialogfeld "Server ausgelastet". Das Dialogfeld nicht antwortet mit der Wortlaut ist etwas anders als mit dem Wortlaut in das Dialogfeld "Server ausgelastet" und "Abbrechen"-Schaltfläche deaktiviert ist.

*dwFlags*<br/>
Flag für die Erstellung. Kann 0 (null) oder mehrere der folgenden Werte mit dem bitweisen OR-Operator kombiniert enthalten:

- BZ_DISABLECANCELBUTTON Deaktivieren der Schaltfläche "Abbrechen" aus, wenn das Dialogfeld aufrufen.

- BZ_DISABLESWITCHTOBUTTON Deaktivieren der wechseln zu Schaltfläche beim Aufrufen des Dialogfelds.

- BZ_DISABLERETRYBUTTON deaktivieren Sie die Schaltfläche "Wiederholen", beim Aufrufen des Dialogfelds.

*pParentWnd*<br/>
Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs `CWnd`) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das übergeordnete Fenster des Dialog-Objekts auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Um das Dialogfeld anzuzeigen, rufen [DoModal](#domodal).

Weitere Informationen finden Sie unter den [OLEUIBUSY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuibusya) Struktur im Windows SDK.

##  <a name="domodal"></a>  COleBusyDialog::DoModal

Rufen Sie diese Funktion, um das Dialogfeld des OLE-Server ausgelastet "oder" Server antwortet nicht anzuzeigen.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- IDABORT, wenn ein Fehler aufgetreten. Wenn IDABORT zurückgegeben wird, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Liste der möglichen Fehler, finden Sie unter den [OleUIBusy](/windows/desktop/api/oledlg/nf-oledlg-oleuibusya) -Funktion in das Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_bz](#m_bz) Struktur, sollten Sie dies tun, vor dem Aufruf `DoModal`, allerdings nachdem das Dialogfeldobjekt erstellt wird.

Wenn `DoModal` gibt IDOK, Sie können andere Memberfunktionen aufrufen zum Abrufen der Einstellungen oder die Informationen, die in das Dialogfeld vom Benutzer eingegeben wurde.

##  <a name="getselectiontype"></a>  COleBusyDialog::GetSelectionType

Rufen Sie diese Funktion zum Abrufen des Auswahltyps, der vom Benutzer im Dialogfeld "Server ausgelastet" ausgewählt.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Rückgabewert

Typ der Auswahl getroffen wurde.

### <a name="remarks"></a>Hinweise

Der Rückgabetyp Werte angegeben sind die `Selection` Enumerationstyp deklariert wird, der `COleBusyDialog` Klasse.

```
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```

Führen Sie die kurze Beschreibungen der folgenden Werte:

- `COleBusyDialog::switchTo` Wechseln zu wurde gedrückt.

- `COleBusyDialog::retry` "Wiederholen"-Schaltfläche wurde gedrückt.

- `COleBusyDialog::callUnblocked` Aufruf zum Aktivieren des Servers ist jetzt aufgehoben wurde.

##  <a name="m_bz"></a>  COleBusyDialog::m_bz

Struktur des Typs OLEUIBUSY verwendet zur Steuerung des Verhaltens im Dialogfeld "Server ausgelastet".

```
OLEUIBUSY m_bz;
```

### <a name="remarks"></a>Hinweise

Mitglieder dieser Struktur können direkt oder über Memberfunktionen geändert werden.

Weitere Informationen finden Sie unter den [OLEUIBUSY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuibusya) Struktur im Windows SDK.

## <a name="see-also"></a>Siehe auch

[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
