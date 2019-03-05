---
title: COleLinksDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
ms.openlocfilehash: c5069bc63d61016e6f3c2f983de23901b9f35814
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301414"
---
# <a name="colelinksdialog-class"></a>COleLinksDialog-Klasse

Wird für das OLE-Dialogfeld "Verknüpfungen bearbeiten" verwendet.

## <a name="syntax"></a>Syntax

```
class COleLinksDialog : public COleDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|Erstellt ein `COleLinksDialog`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleLinksDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Verknüpfungen bearbeiten.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleLinksDialog::m_el](#m_el)|Eine Struktur vom Typ OLEUIEDITLINKS, die das Verhalten des Dialogfelds steuert.|

## <a name="remarks"></a>Hinweise

Erstellen Sie ein Objekt der Klasse `COleLinksDialog` Wenn das Dialogfeld aufgerufen werden soll. Nach einer `COleLinksDialog` -Objekts wird, können Sie mit der [M_el](#m_el) Struktur zum Initialisieren der Werte oder Zustände von Steuerelementen im Dialogfeld. Die `m_el` Struktur des Typs OLEUIEDITLINKS ist. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter den [DoModal](#domodal) Member-Funktion.

> [!NOTE]
>  Vom Assistenten generierten Container-Anwendungscode verwendet diese Klasse.

Weitere Informationen finden Sie unter den [OLEUIEDITLINKS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuieditlinksa) Struktur im Windows SDK.

Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleLinksDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs.h

##  <a name="domodal"></a>  COleLinksDialog::DoModal

Zeigt das Dialogfeld OLE Verknüpfungen bearbeiten.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- IDABORT, wenn ein Fehler aufgetreten. Wenn IDABORT zurückgegeben wird, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Liste der möglichen Fehler, finden Sie unter den [OleUIEditLinks](/windows/desktop/api/oledlg/nf-oledlg-oleuieditlinksa) -Funktion in das Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_el](#m_el) Struktur die, Sie tun es vor dem Aufruf `DoModal`, allerdings nachdem das Dialogfeldobjekt erstellt wird.

##  <a name="colelinksdialog"></a>  COleLinksDialog::COleLinksDialog

Erstellt ein `COleLinksDialog`-Objekt.

```
COleLinksDialog (
    COleDocument* pDoc,
    CView* pView,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*pDoc*<br/>
Verweist auf das OLE-Dokument, das den zu bearbeitenden enthält.

*pView*<br/>
Wiederherstellungspunkte für die aktuelle Ansicht *pDoc*.

*dwFlags*<br/>
Erstellung-Flag, die enthält entweder 0 oder ELF_SHOWHELP angeben, ob die Schaltfläche "Hilfe" angezeigt wird, wenn das Dialogfeld angezeigt wird.

*pParentWnd*<br/>
Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs `CWnd`) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Diese Funktion erstellt nur eine `COleLinksDialog` Objekt. Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.

##  <a name="m_el"></a>  COleLinksDialog::m_el

Struktur des Typs OLEUIEDITLINKS verwendet zur Steuerung des Verhaltens im Dialogfeld "Verknüpfungen bearbeiten".

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>Hinweise

Mitglieder dieser Struktur können entweder direkt oder über Memberfunktionen geändert werden.

Weitere Informationen finden Sie unter den [OLEUIEDITLINKS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuieditlinksa) Struktur im Windows SDK.

## <a name="see-also"></a>Siehe auch

[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
